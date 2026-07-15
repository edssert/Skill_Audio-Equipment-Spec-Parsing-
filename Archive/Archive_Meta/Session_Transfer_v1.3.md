# Session Transfer — 음향 기기 데이터 파싱 스킬 프로젝트 (v1.3)

## 프로젝트 개요

L-Acoustics, d&b audiotechnik 등 여러 브랜드의 음향 기기 스펙 데이터를 오너 매뉴얼/스펙시트/A&E 시방서/웹 3계층에서 교차 검증해 단일 마스터 스키마 마크다운으로 통합하는 스킬 크리에이터 프로젝트. 상세 파싱 규칙 전문은 항상 루트의 최신 `SKILL_vX.X.md` 1개를 참조할 것 — 본 파일에는 규칙을 반복하지 않는다.

## 현재 상태: Phase 3-1(D90) 완료, 누적 제품 4개 (Phase 4 전환 기준 5개까지 1개 남음)

- Phase 1-2: LA12X(4채널) 6개 소스 교차 검증, 마스터 스키마 최초 구축 완료.
- Phase 3-1 (1차): LA7.16(16채널) 신규 파싱 + LA12X와 완벽한 양방향 스키마 동기화 완료.
- Phase 3-2: d&b audiotechnik D80(4채널) 신규 브랜드 최초 투입 완료. 신규 섹션 `d80_specific`(12개 Key) 신설, 3개 파일 Key 목록 100% 일치(14개 섹션, 112개 Key) 검증 완료.
- Phase 3-1 (2차): d&b audiotechnik D90(4채널, 투어링/모바일 특화 모델) 신규 파싱 완료. D80과 동일 브랜드이므로 Phase 3-1 성격(동일 브랜드 이기종 모델)으로 분류. OM(Reference Manual 1.3, 74p), SPS(Datasheet 1.4, 4p — 상세 스펙표+A&E 겸비), AE(txt 1.2), 웹 3계층 총 6개 소스 교차 검증. D80과 공유되는 `d80_specific` 섹션의 12개 Key 중 8개(CMRR 3주파수 확장, System_Start_Up_Time, Storage_Temp/Humidity, LoadMatch_Max_Cable_Length, Signal_Path_Management, Load_Monitoring_System_Check, Output_Mode_Selectable, Mains_Current_Limiter_Range)에 실제 값을 채웠고, D90에만 있는 완전 신규 개념(Milan 오디오 네트워크 상세, Time to tone, EcoMode 등 에너지 절약, AmpPresets 3종 슬롯, Output noise 절대치 상세) 9개는 신규 섹션 `d90_specific`으로 분리해 D80/LA12X/LA7.16 3개 파일에 null로 소급 반영. 4개 파일(D80_v1.1, D90_v1.0, LA12X_v2.7, LA7.16_v1.5) Key 목록 100% 일치 검증 완료(15개 섹션, 121개 Key).
- 특기 사항: AE(txt)의 Depth 값(465 mm)이 OM/SPS/WEB-F(512 mm)와 충돌하는 것을 D90에서 처음 발견, 각주로 양쪽 보존(3개 독립 소스 일치 근거로 512 mm 채택). D90은 GPIO_Count=0(D80과 동일 패턴, 전문 검색 0건 근거)으로 확정. SKILL.md 규칙 변경 없음(v1.9 유지) — 이번 라운드는 순수 데이터 확장이었음.

**현재 루트 최신 파일** (다음 세션은 이 5개 + 아래 폴더만 확인하면 됨):
- `SKILL_v1.9.md` — 파싱 규칙 전문(변경 없음, D80 라운드에서 확정된 버전)
- `LA7.16_v1.5.md`, `LA12X_v2.7.md`, `D80_v1.1.md`, `D90_v1.0.md` — 네 제품 마스터 스키마(Key 목록 100% 동일, 15개 섹션 121개 Key)
- `Original_PDFs/` — 네 제품 원본 매뉴얼/스펙시트/A&E 문서 보존
- `Raw_Web_Data/` — 네 제품 웹 텍스트 및 D80/D90의 A&E(txt) 원문 무수정 보존
- `Archive/` — 모든 구버전(과거 판단 근거 확인용, 평소엔 참조 불필요)

## 다음 세션에서 진행할 작업: Phase 4 전환 검토 (제품 5개 도달 시) 또는 Phase 3 계속

**옵션 A — 다섯 번째 제품 투입 후 Phase 4 전환**: 누적 제품 수가 5개가 되면(현재 4개), SKILL v1.9 Phase 4 절에 따라 이후부터는 매번 전량 재출력 대신 "변경된 Key와 영향받는 파일 목록"을 먼저 요약하고 사용자에게 일괄/개별 출력 여부를 묻는 방식으로 전환한다.

**옵션 B — Phase 3 계속(동일 브랜드 3번째 모델 또는 신규 브랜드)**: d&b 계열 다른 모델(예: D20, D40 등) 또는 완전히 다른 3번째 브랜드(Powersoft, Lab.gruppen, Crown 등)를 투입할 수 있다.

**필수 요건 공통** (SKILL_v1.9.md 참조):
1. 신규 제품에서 발견되는 신규 Key(신규 섹션 포함)는 기존 전 제품 파일에 `null`로 소급 반영(양방향 동기화 — 반대로 기존 제품 전용 Key도 신규 제품에 `null`로 반영).
2. 결과물은 관련된 전체 제품 파일을 동시 출력. N개 제품이면 N개 파일의 Key 목록이 100% 동일함을 스크립트로 검증할 것.
3. 원본 문서는 `Original_PDFs/`에, 웹 원문(및 txt로 제공되는 A&E 등 비-PDF 원문)은 `Raw_Web_Data/`에 동일 컨벤션으로 보존.
4. 새 파일 생성만 허용, 기존 파일 직접 수정 금지 — 버전을 올려 새로 만들고 구버전은 `Archive/Archive_Data`(제품 스키마) 또는 `Archive/Archive_Skill`(SKILL.md)로 이동.
5. d&b 계열처럼 동일 브랜드 신모델을 투입할 때, 기존 `[브랜드]_specific` 섹션(예: d80_specific)에 신모델의 실제 값을 채워 넣을 수 있으면 채우고, 신모델에만 있는 완전히 새로운 개념은 별도의 `[모델]_specific` 신규 섹션(예: d90_specific)으로 분리하는 패턴이 D90 라운드에서 확립되었다 — 다음 d&b 모델 투입 시 이 패턴을 우선 따를 것.

## 참고: 과거 이력 요약 (상세 근거는 Archive 참조)

- SKILL.md는 v1.0부터 v1.9까지 9회 개정. 전문은 `Archive/Archive_Skill/`. D90 라운드에서는 규칙 변경 없음.
- LA12X는 v1.0/v2.0~v2.7(시맨틱 버저닝, v2.0만 Major)로 누적. 재분류 근거는 `Archive/Archive_Data/`의 각 파일 상단 참조.
- LA7.16은 v1.0(최초 파싱) -> v1.1(양방향 동기화+오기재 정정) -> v1.2(파일명 참조 갱신) -> v1.3(터미널블록 핀맵) -> v1.4(d80_specific null 반영) -> v1.5(d90_specific null 반영) 순으로 발행. 전문은 `Archive/Archive_Data/`.
- D80은 v1.0(Phase 3-2 최초 파싱) -> v1.1(d90_specific null 반영) 순으로 발행. 전문은 `Archive/Archive_Data/`.
- D90은 v1.0(Phase 3-1 최초 파싱, 기존 3개 파일과 동시 동기화 반영) 단일 버전으로 시작. 이전 버전 없음.
- 이 파일(Session_Transfer.md) 자체도 v1.0(Phase 1-2 시점), v1.1(Phase 3-1 1차 완료 시점), v1.2(Phase 3-2 완료 시점)를 `Archive/Archive_Meta/`에 보존하고 있다.
