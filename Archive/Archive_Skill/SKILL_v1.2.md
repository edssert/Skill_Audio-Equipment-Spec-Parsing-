---
name: audio-spec-parsing
description: Parse and unify audio equipment specification data (owner's manuals, spec sheets, A&E specs, website tiers) from any manufacturer into a single master schema markdown file.
---

# Audio Equipment Spec Parsing Skill

Skill_Version: 1.2 (재구성본 — 이모지 및 특수 아이콘 금지 규칙 추가)

이 스킬은 음향 기기(앰프, 스피커, 컨트롤러 등) 스펙 데이터를 여러 출처(오너 매뉴얼, 스펙시트 PDF, A&E 시방서, 웹사이트 계층별 텍스트)에서 추출하여 하나의 마스터 스키마 마크다운으로 통합한다. 대상 실행 환경은 Claude Sonnet(주력, 대량 반복 파싱)과 Claude Opus(보조, 복잡한 매뉴얼/충돌 해결)이다.

문서 구조는 마크다운 골격 + XML 국소 삽입 하이브리드를 따른다.

## 핵심 파싱 원칙

<core_principles>
1. 스키마 동적 발견: 제조사마다 다른 용어를 공학 표준 스네이크 케이스 영문 키로 통합한다.
2. 데이터 정제: 값에서 단위를 분리하고 계산 가능한 숫자로 변환한다. 표 안에는 정제된 값만 남긴다.
3. 측정 기준 별도 관리: 측정 조건(-3dB, RMS, 핑크노이즈 등)은 표 안에 넣지 않고 주석/출처 섹션으로 분리한다.
4. 무결성 유지: 없는 스펙은 억지로 만들지 않고 null 처리한다. 소스 간 값이 다르면 어느 한쪽도 버리지 않고 둘 다 보존한다.
</core_principles>

## 출력 포맷 규칙 (신규)

### 1. 섹션 단위 출처 표기
개별 데이터 셀마다 각주를 달지 않는다. 대신 섹션 단위로 묶어 하단 주석에 출처(문서+페이지/목차)를 한 번에 서술한다.

### 2. 표의 순수성 유지
<table_purity_rules>
표 컬럼은 Key/Value(필요 시 Unit)만 둔다. 출처, 측정 조건, 채택 근거는 표 하단 "주석 및 출처" 섹션으로 분리한다. 각주는 소스 간 충돌 등 예외적 개별 값에만 붙인다.
</table_purity_rules>

### 3. 데이터 충돌 보존 원칙
<conflict_preservation_rules>
소스 간 수치가 다를 경우 절대 한쪽을 버리지 않는다. Value 칸에는 채택값 하나, 각주에 두 값을 모두 명시하고 채택 근거를 서술한다.
</conflict_preservation_rules>

### 4. L-Acoustics 등 브랜드별 출처 우선순위
<brand_source_priority>
L-Acoustics 브랜드는 오너 매뉴얼(OM)의 페이지/목차 위치를 출처 표기 최우선으로 기록한다.
</brand_source_priority>

### 5. 이모지 및 특수 아이콘 금지 (신규)
<no_emoji_rule>
스킬 지침 문서 자체와 파싱 결과물 어디에도 이모지나 장식용 특수 기호를 사용하지 않는다. 표준 마크다운 문법(표, 목록, 굵게, 각주 번호)만 사용한다.
</no_emoji_rule>

## 워크플로 (Phase 테스트)

<phase_workflow>
Phase 1: 단일 제품 기초 파싱.
Phase 2: 복합 데이터 통합 - 이 단계부터 위 출력 포맷 규칙을 적용한다.
Phase 3: 타 브랜드 교차 테스트.
Phase 4: 스키마 진화 및 하위 호환성.
</phase_workflow>

## 참고

이 버전에는 아직 저항 표기 표준화, 임의 추론 금지 강화 조항이 포함되어 있지 않다.
