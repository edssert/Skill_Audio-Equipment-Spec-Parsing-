---
name: audio-spec-parsing
description: Parse and unify audio equipment specification data (owner's manuals, spec sheets, A&E specs, website tiers) from any manufacturer into a single master schema markdown file. Use whenever the user provides audio/sound equipment technical documents (PDF manuals, spec sheet PDFs, brochures, docx A&E specs, or copy-pasted website spec tables) and wants them parsed, cross-validated, or merged into a structured schema. Trigger this for requests to "parse spec sheets", "merge product data", "build a spec database", or "통합 스키마"/"스펙 파싱" regardless of manufacturer or product category.
---

# Audio Equipment Spec Parsing Skill

**Skill_Version: 1.4** (파일명 관례: SKILL_v1.4.md)

## 버전 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 초안 — 핵심 파싱 원칙(스키마 동적 발견, 데이터 정제, 측정 기준 분리, 무결성 유지), 마크다운+XML 하이브리드 문서 구조 채택 |
| v1.1 | 출력 포맷 규칙 4종 추가: 섹션 단위 출처 표기, 표 순수성 유지, 데이터 충돌 보존, L-Acoustics 브랜드 OM 우선 출처 규칙 |
| v1.2 | 이모지/특수 아이콘 사용 전면 금지 규칙 추가 |
| v1.3 | 데이터 정제 규칙에 저항값 유럽식 표기(2R7 등) 표준화 추가(Value와 Key 양쪽 모두 적용), 무결성 원칙에 "원본에 없는 수식어·마케팅 문구·괄호 설명 임의 첨가 절대 금지" 조항 강화 |
| v1.4 | Phase 3을 3-1(동종 브랜드 이기종 채널)/3-2(타 브랜드 교차)로 세분화하고, 신규 속성 발견 시 기존 제품 파일 전체에 `null` 소급 반영 및 갱신 파일 일괄 재출력을 필수 요건으로 명문화. Phase 4에 누적 제품 5개 이상일 때의 출력 방식 예외 규정 추가 |

이 스킬은 음향 기기(앰프, 스피커, 컨트롤러 등) 스펙 데이터를 여러 출처(오너 매뉴얼, 스펙시트 PDF, A&E 시방서, 웹사이트 계층별 텍스트)에서 추출하여 하나의 마스터 스키마 마크다운으로 통합한다. 대상 실행 환경은 Claude Sonnet(주력, 대량 반복 파싱)과 Claude Opus(보조, 복잡한 매뉴얼/충돌 해결)이며, 특히 Sonnet 기준으로 지침 경계를 명확히 설계한다.

문서 구조는 마크다운 골격 + XML 국소 삽입 하이브리드를 따른다: 워크플로/규칙 서술은 마크다운 헤더로, 예시 입출력 쌍·용어 매핑 사전·데이터 블록처럼 원문과 경계가 흐려지기 쉬운 부분은 XML 태그로 격리한다. 최종 산출물(파싱 결과)의 포맷은 항상 마크다운(.md)이다.

## 핵심 파싱 원칙

<core_principles>
1. **스키마 동적 발견**: 제조사마다 다른 용어(예: "Max Power", "최대 출력")를 공학 표준 스네이크 케이스 영문 키로 통합한다(예: `Rated_Power_Per_Ch_2.7_Ohms_W`).
2. **데이터 정제**: 값에서 단위를 분리하고 계산 가능한 숫자로 변환한다. 표 안에는 정제된 값만 남긴다 (자세한 규칙은 "표 순수성" 절 참조).
   - **저항값(Impedance) 표기 표준화 (Value와 Key 모두 적용)**: 유럽식 표기(예: `2R7`, `4R`, `8R`)는 소수점 표기(`2.7`, `4`, `8`)로 변환한다. 이 변환은 표의 Value 칸뿐 아니라 동적으로 생성하는 속성명(Key)에도 예외 없이 동일하게 적용한다.
     - Value: Unit 컬럼에 Ohm이 명시되어 있으면 Value는 순수 숫자만 남긴다. 예: 원문 `2R7` -> Value `2.7`, Unit `Ohm`.
     - Key: 저항 조건이 키 이름에 들어갈 때는 `<숫자>.<숫자>_Ohms` 또는 정수면 `<숫자>_Ohms` 형태의 스네이크 케이스로 치환한다. 예: `Rated_Power_Per_Ch_2R7` -> `Rated_Power_Per_Ch_2.7_Ohms`, `Rated_Power_Per_Ch_4R` -> `Rated_Power_Per_Ch_4_Ohms`, `Rated_Power_Per_Ch_8R` -> `Rated_Power_Per_Ch_8_Ohms`.
     - 키 이름에 유럽식 표기(`2R7` 등)를 관용적으로 남겨두는 것은 더 이상 허용하지 않는다 — Key와 Value 양쪽 모두 사람이 바로 읽을 수 있는 표준 표기여야 한다.
3. **측정 기준 별도 관리**: 오너 매뉴얼 등에 있는 측정 조건(-3dB, RMS, 핑크노이즈, 버스트 길이 등)은 표 안에 넣지 않고 주석/출처 섹션으로 분리한다.
4. **무결성 유지 (엄격)**: 없는 스펙은 억지로 만들지 않고 `null` 처리한다. 소스 간 값이 다르면 어느 한쪽도 버리지 않고 둘 다 보존한다(자세한 규칙은 "데이터 충돌 보존" 절 참조).
   - **임의 추론/수식어 첨가 절대 금지**: 원본 어느 문서에도 없는 수식어, 마케팅 문구, 괄호 설명, 해설성 표현을 표의 Value에 절대 덧붙이지 않는다. 여러 소스의 표현이 다를 경우(예: 한 소스는 "Class D", 다른 소스는 "High-efficiency Class D") 이를 동일한 사실로 조용히 병합해서는 안 되며, 반드시 "데이터 충돌 보존 원칙"에 따라 각주로 두 표현을 모두 노출하고 어느 소스에서 어느 표현이 나왔는지 명시한다. Value 컬럼에는 수식어가 없는 가장 보수적인 표현을 기본값으로 쓰고, 확장된 표현은 각주에서만 다룬다. 한 소스에만 등장한 문구를 다른 소스에도 있었던 것처럼 표기하는 것은 명백한 지침 위반이다.
</core_principles>

## 출력 포맷 규칙 (v1.1 이후 누적 적용)

### 1. 섹션 단위 출처 표기

개별 데이터 셀마다 각주를 달지 않는다. 대신 섹션(예: "음향 스펙", "물리적 스펙", "전원부") 단위로 묶어 하단 주석에 해당 섹션 전체가 어느 출처(문서+페이지/목차)에서 왔는지 한 번에 서술한다. 섹션 내 값 대부분이 동일 출처 조합에서 나왔다면 그 조합을 섹션 헤더 바로 아래 한 줄로 표기해도 좋다.

### 2. 표의 순수성 유지

<table_purity_rules>
- 표 컬럼은 `속성명(Key)` / `값(Value)` (필요 시 `단위`)만 둔다. 출처, 측정 조건, 채택 근거는 표 컬럼에 넣지 않는다.
- 표 하단에 `### 주석 및 출처 (Notes & Sources)` 소제목을 두고, 거기서 (a) 해당 섹션 전체의 출처 문서·페이지/목차, (b) 복잡한 측정 조건, (c) 데이터 채택 근거를 서술한다.
- 각주 기호 `[1]`, `[2]`는 특별 설명이 필요한 예외적 개별 값에만 붙인다 — 예: 소스 간 충돌이 있는 값, 측정 조건이 결과 해석에 필수적인 값. 모든 값에 기계적으로 붙이지 않는다.
</table_purity_rules>

<example_table_format>
```markdown
## audio_performance

| Key | Value | Unit |
|---|---|---|
| Frequency_Response | 20 - 20000 | Hz |
| THD_N_8ohm | < 0.05 | % |
| Noise_Level [1] | < -75 | dBV |

### 주석 및 출처 (Notes & Sources)

**출처**: 오너 매뉴얼(OM) p.83 "Specifications - General"; 스펙시트(SPS) 3p "Audio specifications"
**측정 조건**: Frequency Response는 8 옴 부하 60 W 출력 기준 ±0.1 dB. THD+N은 20 Hz-10 kHz 대역, 8옴 60W 기준.
**[1] Noise_Level 충돌**: OM/SPS는 -75 dBV, A&E 시방서(AE)는 -72 dBV로 상이. 두 값 모두 보존 — OM 개정이력(v10.0)에 노이즈 레벨 갱신이 명시되어 -75가 최신치로 판단되나, AE 수치도 삭제하지 않고 병기함.
```
</example_table_format>

### 3. 데이터 충돌 보존 원칙

<conflict_preservation_rules>
- 웹 데이터(리스트뷰/오버뷰)와 오너 매뉴얼(OM), 또는 임의의 두 소스 간 수치가 다를 경우 절대 한쪽을 버리지 않는다.
- 표 안의 `Value` 칸에는 채택(대표) 값 하나만 두고 각주를 붙인다. 각주 본문에서 "A 소스: X / B 소스: Y" 형태로 두 값을 모두 명시하고, 채택 근거(최신 개정, 다수결, 문서 위계 등)를 짧게 설명한다.
- 절대 상충 값을 조용히 삭제하거나 평균 내지 않는다.
</conflict_preservation_rules>

### 4. L-Acoustics 등 브랜드별 출처 우선순위

<brand_source_priority>
- 제품 브랜드가 **L-Acoustics**인 경우: 출처 위치(페이지 번호, 목차/섹션명)를 표기할 때 **오너 매뉴얼(OM)의 위치를 최우선으로 기록**한다. 예: "OM p.83 Specifications > General" 형식을 가장 먼저 적고, SPS/AE/웹은 보조로 뒤에 붙인다.
- 다른 브랜드는 Phase 3 이후 교차 테스트를 통해 우선순위 규칙을 확장한다. 기본값은 "가장 상세하고 개정 이력이 있는 문서 우선".
</brand_source_priority>

### 5. 이모지 및 특수 아이콘 금지

<no_emoji_rule>
스킬 지침 문서 자체와 파싱 결과물(마크다운 출력) 어디에도 이모지나 장식용 특수 기호(화살표 아이콘, 체크마크 이모지 등)를 사용하지 않는다. 표준 마크다운 문법(표, 목록, 굵게, 각주 번호)만 사용한다. 상태 표시가 필요하면 텍스트로 쓴다 (예: "충돌" 대신 이모지 금지, `[충돌]` 텍스트 태그는 허용).
</no_emoji_rule>

## 워크플로 (Phase 테스트 대응)

<phase_workflow>
- **Phase 1**: 단일 제품 기초 파싱 — 마스터 스키마 뼈대 구축.
- **Phase 2**: 복합 문서 통합 — 동일 제품의 매뉴얼/브로셔/웹 스펙을 교차 검증해 하나의 스키마로 병합. 이 단계부터 위 출력 포맷 규칙(섹션 단위 출처, 표 순수성, 충돌 보존)을 적용한다.
- **Phase 3**: 스키마 확장 및 하위 호환 동기화 — 새로운 제품 계열을 투입해 마스터 스키마를 확장하고, 그 결과를 기존에 파싱해 둔 모든 제품 파일에도 소급 반영한다. 두 하위 단계로 진행한다.
  - **Phase 3-1 (동종 브랜드 이기종 채널)**: 동일 브랜드의 다른 채널 수/아키텍처 제품(예: L-Acoustics 4채널 LA12X 대비 16채널 LA7.16(i))을 투입한다. 새 제품에만 존재하는 신규 속성(Key)이 발견되면, 그 Key를 기존에 이미 파싱해 둔 동일 브랜드(또는 전체) 제품 파일에도 `null` 값으로 추가한다. **동기화 필수 요건**: 결과 출력은 신규 제품 파일 1개로 끝내지 않고, 신규 Key가 반영되어 리팩토링된 기존 제품 파일까지 함께 출력한다(예: LA7.16 1개 + 갱신된 LA12X 1개 = 총 2개 파일).
  - **Phase 3-2 (타 브랜드 교차 테스트)**: 완전히 다른 브랜드(예: d&b audiotechnik)의 제품을 투입해 용어 매핑 사전을 확장하고, 그 브랜드 고유의 표기법·측정 기준을 스키마에 통합한다. **동기화 필수 요건**: 신규 브랜드 제품 파일과 함께, 이번에 확장된 스키마 규격이 소급 반영된 기존 모든 제품 파일(Phase 3-1까지 누적된 제품 전부)을 일괄 출력한다 — 예: d&b 제품 1개 + LA12X 갱신본 1개 + LA7.16 갱신본 1개 = 총 3개 파일. 모든 제품 파일의 스키마 형식(섹션 구성, Key 목록)이 서로 동일해졌음을 결과물로 증명해야 한다.
- **Phase 4**: 스키마 진화 및 하위 호환성 — Phase 3의 동기화 원칙을 표준 운영 절차로 고정한다. 이후 새로운 제품이나 카테고리가 투입되어 신규 속성이 발견될 때마다, 예외 없이 기존에 파싱해 둔 모든 제품 .md 파일에 해당 Key를 `null` 값으로 일괄 추가하고 리팩토링하며, 그 갱신된 파일들을 신규 제품 파일과 함께 전량 출력한다. 누적 제품 수가 많아지면(대략 5개 이상) 매번 전량 재출력하는 대신 "변경된 Key와 영향받는 파일 목록"을 먼저 요약하고, 사용자 확인 후 일괄 출력할지 개별 확인 후 출력할지 묻는다.
</phase_workflow>

## 용어 매핑 사전 (계속 확장)

<term_mapping_dictionary>
| 원문 표현 (예시) | 표준 키 |
|---|---|
| Max Power, Peak Power, 최대 출력 | Peak_Power_W |
| Output Power (all channels loaded), Rated Power | Rated_Power_Per_Ch_<load>_W |
| Frequency Response, Freq. Range | Frequency_Response_Hz |
| THD, Distortion | THD_N_pct |
</term_mapping_dictionary>

references/ 디렉토리에 브랜드별 용어 사전이 커지면 별도 파일로 분리한다 (300줄 이상 시).
