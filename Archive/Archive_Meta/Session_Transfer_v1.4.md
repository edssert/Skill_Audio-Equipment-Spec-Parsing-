# Session Transfer — 음향 기기 데이터 파싱 스킬 프로젝트 (v1.4)

## 프로젝트 개요

L-Acoustics, d&b audiotechnik 등 여러 브랜드의 음향 기기 스펙 데이터를 오너 매뉴얼/스펙시트/A&E 시방서/웹 3계층에서 교차 검증해 단일 마스터 스키마 마크다운으로 통합하는 스킬 크리에이터 프로젝트. 상세 파싱 규칙 전문은 항상 루트의 최신 `SKILL_vX.X.md` 1개를 참조할 것 — 본 파일에는 규칙을 반복하지 않는다.

## 현재 상태: 4개 제품 dsp/latency 근거 보강 라운드 완료, 누적 제품 4개 (Phase 4 전환 기준 5개까지 1개 남음)

- Phase 1-2: LA12X(4채널) 6개 소스 교차 검증, 마스터 스키마 최초 구축 완료.
- Phase 3-1 (1차): LA7.16(16채널) 신규 파싱 + LA12X와 완벽한 양방향 스키마 동기화 완료.
- Phase 3-2: d&b audiotechnik D80(4채널) 신규 브랜드 최초 투입 완료. 신규 섹션 `d80_specific`(12개 Key) 신설.
- Phase 3-1 (2차): d&b audiotechnik D90(4채널, 투어링/모바일 특화 모델) 신규 파싱 완료. D80과 동일 브랜드이므로 Phase 3-1 성격(동일 브랜드 이기종 모델)으로 분류. D80과 공유되는 `d80_specific` 섹션의 12개 Key 중 8개에 실제 값을 채웠고, D90에만 있는 완전 신규 개념 9개는 신규 섹션 `d90_specific`으로 분리해 D80/LA12X/LA7.16 3개 파일에 null로 소급 반영.
- **DSP/Latency 근거 보강 라운드 (신규)**: 사용자가 D80의 dsp 섹션 `DSP_Sampling_Rate`(96 kHz)가 "96 kHz까지 지원"인지 "96 kHz 고정 동작"인지 원문 근거가 불명확하다고 지적, 또한 latency 값이 샘플레이트별로 달라지는지 재확인을 요청했다. 이에 따라 4개 제품 전체(D80/D90/LA12X/LA7.16)의 dsp/latency 섹션을 원본 PDF 본문(스펙 표가 아닌 서술 챕터)까지 재검토하여 각주를 대폭 보강했다:
  - **D80**: OM p.34 "System clocking"/"SRC" 절을 재검토한 결과, DSP_Sampling_Rate(96 kHz)는 내부 처리 고정값이며(48 kHz 입력은 자동 2배 업샘플링), Latency_Standard(0.3 ms)는 "SRC 비활성 + 입력 48/96 kHz" 조건에서만 성립하고 SRC 활성화 시 최대 +1 ms 증가할 수 있음을 확인. D80은 SRC를 기본 비활성화해두는 조건부 활성화 구조.
  - **D90**: 74p Reference Manual 전문을 SRC/clock 키워드로 전수 검색한 결과, D80과 같은 조건부 SRC 서술은 없고 "permanent, high-speed, high-quality SRCs"(상시 동작)로만 서술됨을 확인. D80보다 서술 상세도가 낮다는 한계를 각주에 명기.
  - **LA12X/LA7.16**: OM 본문(LA12X p.15, LA7.16 p.16)에서 모든 AES/EBU 입력에 SRC가 상시 하드웨어로 내장되어 "constant propagation delay regardless of the input sampling frequency"임을 확인. Latency 스펙 표에는 "independent from input Fs" 확정 문구가 직접 명시됨(LA12X p.86, LA7.16 p.94) — 4개 제품 중 근거 수준이 가장 높음.
  - **핵심 원칙**: d&b D80에는 샘플레이트 클로킹 동작 원리에 대한 상세 설명이 있는데 D90/L-Acoustics 제품에는 그 수준의 설명이 없는 경우(또는 반대의 경우), 이 "서술 상세도 차이" 자체를 각 파일에 명시적으로 교차 기록해야 한다는 것이 사용자의 두 번째 요청이었으며, 4개 파일 모두에 이 교차 참조가 반영되었다.
  - 4개 파일 모두 Value(96, 0.3, 3.84, 0.84, 1.18) 자체는 변경하지 않고 성립 조건/근거 문구만 각주로 병기했다.
- **SKILL.md 신규 규칙 — Surgical Versioning Protocol**: 사용자 요청으로 "작업 공간 관리 및 버전 체계화" 절에 새 규칙 신설. 새 버전 파일 생성 시 (1) 구버전을 먼저 복제해 새 파일명으로 만들고, (2) 구버전 원본을 Archive로 격리한 다음, (3) 새 파일에서만 국소 수정(Edit)을 수행하는 엄격한 순서(Strict Sequence)를 의무화. 이 규칙 자체가 처음 도입된 라운드에서 실제로는 Edit을 먼저 하고 나중에 Archive로 옮기는 순서 위반이 발생해 Archive의 v1.9가 일시적으로 v1.10 내용으로 오염되는 사고가 있었고, 이를 Archive의 v1.8 원본을 기준으로 복구한 뒤 규칙 문서에 위반 사례와 교훈을 함께 기록했다.
- **파일 무결성 이슈 (세션 전반에 걸쳐 반복 발생, 향후 세션 참고 필수)**: 이번 세션 내내 대용량 마크다운 파일(25-40 KB급)을 저장할 때 `mcp__workspace__bash` 도구가 실제 최신 내용을 반영하지 못하고 오래된 스냅샷(정확히 예전 바이트 수)을 계속 보고하는 현상이 반복적으로 관찰되었다. 반면 Read/Edit/Write/Grep 등 파일 도구는 즉시 최신 내용을 정확히 반영했다. 실제로 D90_v1.1.md, LA7.16_v1.6.md 등 일부 파일은 세션 중 진짜로 문장 중간에서 잘려 저장되는 사고도 발생했으며(Archive의 구버전 원문을 대조해 복구), bash가 이런 진짜 손상과 단순 캐시 지연을 구분 없이 똑같이 stale하게 보고하기 때문에 bash의 `wc`/`cat`/Python 읽기 결과만으로 파일 손상을 단정하지 말 것 — Read 도구로 offset 없이 전체를 읽거나 Grep으로 파일 끝부분 마커(예: "버전 변경 이력"의 마지막 항목)를 검색해 실제 완전성을 판단해야 한다. 사용자가 직접 파일을 열어 확인해준 사례(LA12X_v2.7)에서도 bash 보고와 실제 파일 상태가 달랐음이 확인되었다.
- 4개 파일(D80_v1.2, D90_v1.1, LA12X_v2.8, LA7.16_v1.6) Key 목록 100% 일치 재검증 완료 — 15개 섹션(amplification, power_supply, audio_performance, dsp, latency, input_analog, input_digital, input_avb, connectivity, control_monitoring, operating_conditions, physical, protection_summary, d80_specific, d90_specific), 121개 Key 전부 4개 파일에서 동일하게 확인(Grep을 통한 수동 대조, LA7.16의 connectivity 섹션 내 Terminal_Block_Pinout 보조 3열 표는 스키마 밖의 LA7.16 고유 보충 자료로 불일치 아님).

**현재 루트 최신 파일** (다음 세션은 이 5개 + 아래 폴더만 확인하면 됨):
- `SKILL_v1.10.md` — 파싱 규칙 전문(Surgical Versioning Protocol 신설)
- `LA7.16_v1.6.md`, `LA12X_v2.8.md`, `D80_v1.2.md`, `D90_v1.1.md` — 네 제품 마스터 스키마(Key 목록 100% 동일, 15개 섹션 121개 Key, dsp/latency 근거 보강 반영)
- `Original_PDFs/` — 네 제품 원본 매뉴얼/스펙시트/A&E 문서 보존
- `Raw_Web_Data/` — 네 제품 웹 텍스트 및 D80/D90의 A&E(txt) 원문 무수정 보존
- `Archive/` — 모든 구버전(과거 판단 근거 확인용, 평소엔 참조 불필요). Archive_Skill에는 SKILL_v1.0~v1.9, Archive_Data에는 각 제품의 모든 이전 버전 보존.

## 다음 세션에서 진행할 작업: Phase 4 전환 검토 (제품 5개 도달 시) 또는 Phase 3 계속

**옵션 A — 다섯 번째 제품 투입 후 Phase 4 전환**: 누적 제품 수가 5개가 되면(현재 4개), SKILL v1.10 Phase 4 절에 따라 이후부터는 매번 전량 재출력 대신 "변경된 Key와 영향받는 파일 목록"을 먼저 요약하고 사용자에게 일괄/개별 출력 여부를 묻는 방식으로 전환한다.

**옵션 B — Phase 3 계속(동일 브랜드 3번째 모델 또는 신규 브랜드)**: d&b 계열 다른 모델(예: D20, D40 등) 또는 완전히 다른 3번째 브랜드(Powersoft, Lab.gruppen, Crown 등)를 투입할 수 있다.

**필수 요건 공통** (SKILL_v1.10.md 참조):
1. 신규 제품에서 발견되는 신규 Key(신규 섹션 포함)는 기존 전 제품 파일에 `null`로 소급 반영(양방향 동기화 — 반대로 기존 제품 전용 Key도 신규 제품에 `null`로 반영).
2. 결과물은 관련된 전체 제품 파일을 동시 출력. N개 제품이면 N개 파일의 Key 목록이 100% 동일함을 검증할 것(대용량 파일은 bash의 Python/wc 결과가 stale할 수 있으므로, Read/Grep으로 실제 완전성을 재확인).
3. 원본 문서는 `Original_PDFs/`에, 웹 원문(및 txt로 제공되는 A&E 등 비-PDF 원문)은 `Raw_Web_Data/`에 동일 컨벤션으로 보존.
4. **Surgical Versioning Protocol(v1.10 신규, Strict Sequence)**: 새 버전 파일을 만들 때는 반드시 (1) 구버전을 새 파일명으로 먼저 복제 → (2) 구버전 원본을 즉시 Archive로 이동 → (3) 새 파일에서만 대상 부분을 국소 수정, 순서로 진행한다. Edit을 먼저 하고 나중에 Archive로 옮기면 Archive의 "구버전"이 이미 오염된 상태로 격리되는 사고가 발생하므로 순서를 반드시 지킨다.
5. d&b 계열처럼 동일 브랜드 신모델을 투입할 때, 기존 `[브랜드]_specific` 섹션(예: d80_specific)에 신모델의 실제 값을 채워 넣을 수 있으면 채우고, 신모델에만 있는 완전히 새로운 개념은 별도의 `[모델]_specific` 신규 섹션(예: d90_specific)으로 분리하는 패턴이 D90 라운드에서 확립되었다.
6. 값의 성립 조건(예: "몇 kHz까지 지원"인지 "고정값"인지, 특정 하드웨어 옵션이 켜져 있을 때만 성립하는지)이 스펙 표 수치만으로 불명확할 때는, 반드시 원본 PDF의 서술 챕터(스펙 표가 아닌 본문 설명)까지 대조하여 조건을 각주에 명기한다. 한 제품에는 이런 상세 서술이 있는데 비교 대상 제품에는 없다면, 그 "서술 유무 차이" 자체를 각 파일에 교차 기록한다(D80 dsp/latency 라운드에서 확립된 패턴).

## 참고: 과거 이력 요약 (상세 근거는 Archive 참조)

- SKILL.md는 v1.0부터 v1.10까지 10회 개정. 전문은 `Archive/Archive_Skill/`. v1.10에서 Surgical Versioning Protocol 신설.
- LA12X는 v1.0/v2.0~v2.8(시맨틱 버저닝, v2.0만 Major)로 누적. v2.8에서 dsp/latency 근거 보강. 재분류 근거는 `Archive/Archive_Data/`의 각 파일 상단 참조.
- LA7.16은 v1.0(최초 파싱) -> v1.1(양방향 동기화+오기재 정정) -> v1.2(파일명 참조 갱신) -> v1.3(터미널블록 핀맵) -> v1.4(d80_specific null 반영) -> v1.5(d90_specific null 반영) -> v1.6(dsp/latency 근거 보강) 순으로 발행. 전문은 `Archive/Archive_Data/`.
- D80은 v1.0(Phase 3-2 최초 파싱) -> v1.1(d90_specific null 반영) -> v1.2(dsp/latency 근거 보강) 순으로 발행. 전문은 `Archive/Archive_Data/`.
- D90은 v1.0(Phase 3-1 최초 파싱) -> v1.1(dsp/latency 근거 보강) 순으로 발행. 전문은 `Archive/Archive_Data/`.
- 이 파일(Session_Transfer.md) 자체도 v1.0(Phase 1-2 시점), v1.1(Phase 3-1 1차 완료 시점), v1.2(Phase 3-2 완료 시점), v1.3(D90 라운드 완료 시점)를 `Archive/Archive_Meta/`에 보존하고 있다.
