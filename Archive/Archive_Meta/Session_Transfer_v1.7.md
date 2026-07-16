# Session Transfer — 음향 기기 데이터 파싱 스킬 프로젝트 (v1.7)

## 프로젝트 개요

L-Acoustics, d&b audiotechnik, Meyer Sound 등 여러 브랜드의 음향 기기 스펙 데이터를 오너 매뉴얼/스펙시트/A&E 시방서/웹 3계층에서 교차 검증해 단일 마스터 스키마 마크다운으로 통합하는 스킬 크리에이터 프로젝트. 상세 파싱 규칙 전문은 항상 루트의 최신 `SKILL_vX.X.md` 1개를 참조할 것 — 본 파일에는 규칙을 반복하지 않는다.

**이 파일은 v1.4 이후 크게 뒤처져 있었다** — v1.4는 4개 제품(LA12X/LA7.16/D80/D90) 시점에서 작성되었으나, 그 이후 세션들에서 L-Acoustics "i" 라인 4개(LA1.16i/LA2Xi/LA4X/LA7.16i)와 d&b audiotechnik 신규 라인 8개(D25/D40/5D/5DM/10D/30D/25D/40D)가 순차 투입되어 실제 제품 수는 16개로 늘어났다. v1.5는 이 전체 이력을 반영해 처음부터 다시 작성되었다.

**v1.6에서는 폴더 구조가 카테고리/브랜드 계층형으로 재편되었다** — 앰프 외에 스피커, 3채널 앰프렉 등으로 제품군을 확장할 예정이라, 루트에 흩어져 있던 앰프 제품 데이터 전체를 `amplifiers/{brand}/` 하위로 이동했다.

**v1.7에서는 신규 카테고리 `speakers/`가 실제로 투입되어 12개 제품이 추가되었다** — amplifiers(16개)와 함께 프로젝트 전체 누적 제품 수는 28개. 아래 "이번 라운드에 있었던 일"의 최신 항목 참조.

## 현재 상태: amplifiers 16개 + speakers 12개(총 28개), SKILL v1.15, speakers 카테고리 최초 투입 완료

**현재 파일 위치**(카테고리 `amplifiers`, 브랜드별 하위 폴더):
- `amplifiers/LA/`(L-Acoustics, 6개): `LA12X_v3.2.md`, `LA7.16_v2.2.md`, `LA1.16i_v2.2.md`, `LA2Xi_v2.2.md`, `LA4X_v2.2.md`, `LA7.16i_v2.2.md`
- `amplifiers/db/`(d&b audiotechnik — Milan/터치스크린 계열, 4개): `D80_v2.2.md`, `D90_v2.2.md`, `D25_v1.3.md`, `D40_v1.2.md`
- `amplifiers/db/`(d&b audiotechnik — 차세대 설치용 계열, 6개): `5D_v1.1.md`, `5DM_v1.1.md`, `10D_v1.0.md`, `30D_v1.0.md`, `25D_v1.0.md`, `40D_v1.0.md`
- 각 브랜드 폴더 내부에 `Original_PDFs/{제품명}/`, `Raw_Web_Data/`, `Archive/{제품명}/`가 동일하게 존재. 상세 규칙은 `amplifiers/CLAUDE.md` 참조.
- `speakers/LA/`(L-Acoustics, 9개): `K1_v1.7.md`, `K2_v1.1.md`, `K3_v1.2.md`, `K3i_v1.2.md`, `Kara_II_v1.2.md`, `Kara_IIi_v1.2.md`, `Kiva_II_v1.1.md`, `KS28_v1.1.md`, `L2_v1.1.md`
- `speakers/db/`(d&b audiotechnik, 2개): `GSL8_v1.3.md`, `GSL12_v1.3.md`
- `speakers/MY/`(Meyer Sound, 1개): `PANTHER_v1.5.md`
- `speakers/` 내부 구조는 `amplifiers/`와 동일(`Original_PDFs/{제품명}/`, `Raw_Web_Data/`, `Archive/{제품명}/`)하되, `speakers/LA/`에만 `References/`(제품 단일에 속하지 않는 L-Acoustics 브랜드 공용 기술문서 — Amplification Reference Technical Bulletin, Preset Guide)가 추가로 존재. 상세 규칙은 `speakers/CLAUDE.md` 참조.
- 루트에는 이제 `SKILL_v1.15.md`, `Session_Transfer_v1.7.md`, `CLAUDE.md`, 카테고리 폴더(`amplifiers/`, `speakers/`), 전역 `Archive/`(`Archive_Skill`, `Archive_Meta`)만 남는다.

**중요 — 제품명 혼동 주의**: `25D`≠`D25`, `40D`≠`D40`, `10D`/`30D`/`5D`/`5DM`은 이름이 비슷해 보이지만 서로 완전히 다른 제품 계열이다. 특히 `25D`와 `40D`는 실제로는 Milan-AVB 네트워크(D25/D40/D90 계열)와 Phoenix Euroblock 커넥터+실동 GPIO(10D/30D 계열)를 결합한 **하이브리드 아키텍처**로 확인되어, 이름만으로 스켈레톤을 추정하면 안 된다는 것이 이번 라운드의 핵심 교훈이다(아래 "핵심 교훈" 참조).

**amplifiers 스키마 구조**: 17개 데이터 섹션(amplification, power_supply, audio_performance, dsp, latency, input_analog, input_digital, input_avb, input_dante, network, connectivity, control_monitoring, operating_conditions, physical, protection_summary) + Null Report + 버전 변경 이력. 137개 Key, 16개 파일 전체 100% 동일 목록으로 grep-diff 검증 완료(10D_v1.0.md를 기준선으로 사용). **`d80_specific`/`d90_specific` 같은 모델명 그랩백 섹션은 전부 폐지되었다** — 과거 이 섹션들에 있던 Key는 전부 주제 기반 기존/신규 섹션(예: `network`, `input_dante`)으로 재배치되었다.

**speakers 스키마 구조**: amplifiers와는 별개의 독립 스키마(제품 카테고리가 다르므로 섹션 구성 자체가 다름) — acoustical_performance, amplification_requirements(패시브 제품용) 또는 power_supply/protection_thermal/network_monitoring(self-powered 제품용), physical, connectivity 등으로 구성. K1(L-Acoustics, 최초 투입 제품)이 스키마 origin 파일 역할을 했으며 v1.0→v1.7까지 7개 버전을 거치며 구조가 다듬어졌다. LA 9개/db 2개/MY 1개 총 12개 파일 Key 목록 100% 일치 확인(2026-07-16/17 라운드 감사에서 GSL8/GSL12 diff exit 0, PANTHER 2건 수정 후 확인). 브랜드별 아키텍처 차이(패시브/능동/하이브리드 크로스오버, 커넥터 모델별 핀아웃, self-powered 전용 섹션)에 대한 상세는 `speakers/CLAUDE.md` 참조.

## 이번 라운드(2026-07-16/17)에 있었던 일 — speakers 카테고리 최초 투입

1. **신규 카테고리 `speakers/` 신설**: 사용자가 `upload/`에 3사(L-Acoustics/d&b/Meyer Sound) 스피커 제품 매뉴얼+스펙시트를 올리고 Phase 1부터 재시작 지시. K1(L-Acoustics)을 최초 제품으로 선정, 이후 GSL8/GSL12(d&b, 별도 파트넘버라 2개 파일), PANTHER(Meyer Sound, self-powered) 순으로 Phase 1-2 완료.
2. **L-Acoustics 8개 제품 연속 투입**: 사용자가 추가로 K2/K3/K3i/Kara_II/Kara_IIi/Kiva_II/KS28/L2 원본을 올리고 "순서 상관없이 토큰 소진까지 계속 파싱" 지시. 제품별로 아키텍처를 자기 원본에서 독립 판정(K1/K2=PA-COM 3-way active, K3/Kara II=speakON 2-way active, K3i/Kara IIi=terminal block install 변형, Kiva II=이 카테고리 최초 패시브 크로스오버, KS28=서브우퍼 전용, L2=16채널 능동 구동+LC 대역의 가장 복잡한 아키텍처).
3. **양방향 동기화 범위 규칙 정교화 (SKILL v1.13→v1.14)**: 반복적으로 발생한 문제 — 새 제품에서 발견된 Key를 무조건 전 제품에 null로 동기화하다 보니 브랜드/커넥터 고유 Key(`PA_COM_Pinout_*`, `SpeakON_Pinout_*`, `Terminal_Block_Pinout_*`, `NLT4_Pinout_*`)가 여러 커넥터 모델 조합으로 모든 파일에 누적되는 스키마 오염이 발생. 사용자 지적으로 "브랜드 무관 범용 개념(null 동기화 대상)"과 "브랜드/제품 고유 물리 설계·커넥터 모델명이 Key 이름에 박힌 경우(동기화 대상에서 제외, 해당 없는 파일엔 아예 생성 안 함)"의 판별 기준을 SKILL v1.14에 명문화. 이후 7개 파일(K3/K3i/Kara_II/Kara_IIi/Kiva_II/KS28/L2)에서 잘못 동기화되어 있던 타 커넥터 모델 null Key 그룹을 전량 삭제하는 정리 작업 수행.
4. **각주 서술 원본성 요건 확장 (SKILL v1.15)**: PANTHER(self-powered)의 커넥터 Key를 null 처리하며 "self-powered 스피커는 항상 라인 레벨 입력만 받는다"는 근거 없는 일반화 문장을 각주에 썼다가 사용자에게 강하게 지적받음(PANTHER는 실제로 Milan AVB/etherCON 디지털 입력도 있음). 이를 계기로 SKILL v1.15에서 "0 vs null 판정"뿐 아니라 **모든 각주/설명 서술 전반**이 반드시 해당 제품 자신의 원본 문서 근거에 기반해야 한다는 원칙으로 확장. 아울러 AES75 같은 측정 표준 프로토콜 번들을 개별 Key로 원자화하지 않고 하나의 복합값 Key로 유지하는 원칙도 이 버전에서 신설.
5. **PDF 그래픽 전용 콘텐츠(극성 아이콘) 열람 방법 확립**: Read 도구의 `pages` 파라미터가 의존하는 `pdftoppm`(poppler-utils)이 이 환경에서 설치 후에도 격리된 백엔드 문제로 작동하지 않는 것을 확인(winget 설치, PATH 복사 모두 실패). 대안으로 **PowerShell + Windows 네이티브 `Windows.Data.Pdf` WinRT API**를 사용해 PDF 특정 페이지를 PNG로 직접 래스터라이즈한 뒤 그 PNG를 Read로 여는 방법을 발견 — K1의 delay_defaults 극성 데이터(색상 코드 아이콘으로만 표기)를 이 방법으로 확정. 향후 그래픽 전용 PDF 콘텐츠(치수 도면 등) 검증에도 재사용 가능한 기법으로 기록.
6. **12개 파일 전수 Key-parity 감사 및 카테고리 컨벤션 문서화**: 사용자의 "검토를 계속 반복하라" 지시에 따라 12개 speakers 파일 전체의 Key 목록을 grep/diff로 전수 대조. PANTHER에서 2건 발견 및 수정(`Operating_Frequency_Range_Hz`→`Usable_Bandwidth_Hz` 리네임, 누락되었던 `Max_SPL_4x_Array_Far_Field_Scaled_1m` 복원). `speakers/CLAUDE.md` 신설(브랜드별 아키텍처 참고사항, 두 축 판별 기준, 변형/베리언트 파일 분리 기준 문서화).

## 이번 라운드(2026-07-16, amplifiers 폴더 재편)에 있었던 일

1. **Upload 폴더 일괄 투입**: 사용자가 `upload/`에 8개 제품 PDF(5D/5DM/10D/30D/25D/40D/D25/D40)를 한 번에 올리고 "제품 하나 단위로 파싱, 동기화 완료마다 커밋"을 지시. 제품별로 순서대로 파싱하며 매번 양방향 스키마 동기화를 수행했다.
2. **d80_specific/d90_specific 섹션 폐지 및 재배치**: 사용자 요청으로 두 그랩백 섹션의 21개 Key(d80_specific 12개 + d90_specific 9개)를 주제 기준 기존 섹션(input_analog, input_digital, audio_performance, dsp, operating_conditions, control_monitoring, connectivity, power_supply)과 신설 섹션(`network`)으로 재배치. Milan 관련 3개 Key(Milan_Input_Channel_Streams 등)는 input_avb의 기존 AVB_* Key로 흡수.
3. **BTL/PBTL Key 통폐합**: 부하 임피던스별로 세분화되어 있던 10개 Key(Rated/Peak_Power_Per_Ch_BTL_8/16_Ohms, PBTL_4/8/16_Ohms)를 4개(Rated/Peak_Power_Per_Ch_BTL, Rated/Peak_Power_Per_Ch_PBTL)로 통합 — null 나열로 인한 가독성 저하를 해소하고, 실값 있는 제품(LA1.16i/LA2Xi)은 Value 셀에 임피던스 조건을 슬래시로 병기해 데이터 손실 없이 보존.
4. **신규 아키텍처 개념 3건 확인**: `input_dante` 섹션(5D 파싱 중 신설, Dante 오디오오버IP 전용), `network` 섹션(Network_IP_Default 등 IP 설정), `Web_Remote_Interface` Key(10D 파싱 중 신설, 브라우저 기반 내장 웹 UI — R1/ArrayCalc 없이 접속 가능한 개념으로 Remote_Software와 별도 Key). 세 확장 모두 기존 전 제품 파일에 null로 소급 반영 완료, grep 검증 완료.
5. **8개 신규 제품 파싱 완료**: D25 → D40 → 5D → 5DM → 10D → 30D → 25D/40D(병렬 서브에이전트) 순으로 진행. 각 제품의 아키텍처는 절대 이름이나 형제 제품에서 추정하지 않고 자기 자신의 SPS/OM 원본에서 독립적으로 판정했다(SKILL v1.11 "판단 근거의 원본성 요건").
6. **폴더 구조 카테고리/브랜드 계층형 재편**: 스피커, 3채널 앰프렉 등 신규 제품 카테고리 투입을 앞두고, 루트에 흩어져 있던 앰프 16개 제품의 마스터 스키마 파일·`Original_PDFs`·`Raw_Web_Data`·`Archive/Archive_Data`를 `amplifiers/{LA,db}/` 하위로 전량 이관(`git mv`로 이력 보존). 전역 문서(`Archive_Skill`, `Archive_Meta`)만 루트 `Archive/`에 남겼다. 신규 컨벤션 문서 `amplifiers/CLAUDE.md` 신설, 루트 `CLAUDE.md`와 SKILL v1.12에도 반영. `upload/` 폴더는 이미 `Original_PDFs`에 백업 완료된 파일 14개를 비우고 빈 상태로 유지 — 다음 신규 제품 원본을 여기에 올릴 예정.

## 핵심 교훈 — 이름과 아키텍처는 무관하다

이번 라운드에서 가장 중요하게 확인된 패턴: d&b의 "X" vs "XD" 이름 규칙은 아키텍처를 전혀 예측하지 못한다.
- `D25`/`D40`/`D90` = Milan-AVB 네트워크 + XLR/NL4/NL8 커넥터 + 터치스크린, GPIO 없음(GPIO_Count=0 확정적 비존재).
- `5D`/`5DM` = Dante(또는 5DM은 Milan) 오디오오버IP + IEC C14 마운트 + 하프랙, GPI 4핀(비-옵토커플러, 입력 전용).
- `10D`/`30D` = AES3(Dante/Milan 모두 미사용) + Ethernet(OCA)/CAN-Bus 제어 + Phoenix Euroblock 커넥터 + LED-only 패널(터치스크린 없음) + 실동 GPIO 5핀(옵토커플러, 입출력 겸용) + Web Remote Interface.
- `25D`/`40D` = **하이브리드**: Milan-AVB 네트워크(D25/D40/D90과 동일) + Phoenix Euroblock 커넥터 + 실동 GPIO(10D/30D와 유사하되 8xGPI+4xGPO 완전 분리형) + 터치스크린 + Web Remote Interface. 앰프/DSP 코어 실측값은 각각 D25/D40과 소수점까지 일치(동일 파워앰프 세대 공유 추정), 반면 I/O 전면부는 차세대 설치용 라인 패턴을 그대로 사용.

**따라서 신규 제품 파싱 시 스켈레톤을 고를 때는 반드시 그 제품 자신의 SPS/OM에서 (1) 오디오 네트워크 프로토콜, (2) 커넥터 시스템, (3) GPIO 유무/구조, (4) UI(터치스크린 vs LED-only), (5) 랙 크기를 확인한 뒤 가장 유사한 기존 파일을 골라야 한다** — 이름의 유사성이나 "이 브랜드는 항상 이렇다"는 가정에 의존하면 안 된다.

## 기타 확인된 패턴

- **소스 간 수치 상충이 반복적으로 발견됨**: SPS(데이터시트)의 대표값과 OM(레퍼런스 매뉴얼) 상세 부록 표의 조건별 실측값이 일치하지 않는 사례가 10D/30D의 Power_Consumption_Idle에서 발견됨(예: 10D는 SPS 1.3kW vs OM 상세표 1.07kW). 25D의 Network_IP_Default에서도 SPS(.25)와 OM(.40, 공교롭게도 D40의 실제 IP와 일치)이 상충. 모두 두 값을 보존하고 각주로 상충 사실과 채택 근거를 명기하는 방식으로 처리 — 절대 임의로 하나를 버리지 않는다.
- **Bridging_Support/Third_Party_Control 등 다수 Key가 25D/40D에서 처음 실값 확보**: 이전까지 d&b 계열 전체가 null이었던 Key들(GPIO_Type, Fault_Contact_Type, Routing_Matrix 등)이 축약판 OM만 제공된 제품에서도 아키텍처 판정 과정에서 다수 실값 확보됨.
- **Git 사고 — upload/ 폴더 오커밋**: 세션 도중 백그라운드 서브에이전트 하나가 스코프를 벗어나 `git add -A` 유사 동작으로 `upload/` 폴더 전체(~70MB, 아직 파싱 전이던 25D/40D 원본 포함)와 여러 제품 파일을 한 커밋에 묶어 origin/main에 푸시하는 사고가 있었다. 이미 푸시된 상태라 히스토리 재작성(force-push)은 하지 않았고, 대신 `.gitignore`에 `upload/`를 추가해 추적만 중단했다(로컬 파일은 보존). **향후 세션에서 서브에이전트를 쓸 때는 "git commit/push는 절대 하지 말 것"을 프롬프트에 명시할 것** — 이번 세션 후반부부터는 이 지시를 모든 서브에이전트 프롬프트에 포함시켰다.
- **사용자 지시(2026-07-16 세션 후반)**: 이 시점부터는 제품별 완료마다 즉시 푸시하지 말고, 남은 제품 파싱이 전부 완료된 뒤 한 번에 푸시할 것. 커밋 자체는 계속 제품 단위로 로컬에 생성.

## 다음 세션에서 확인할 것

1. **Push 대기 중**: amplifiers 라운드부터 이어진 미푸시 커밋에 더해, 이번 speakers 라운드의 로컬 커밋들도 아직 origin에 푸시되지 않았을 수 있다 — `git log --oneline origin/main..HEAD`로 확인 후 사용자 확인을 받아 푸시할 것.
2. **사용자의 "검토/수정 반복" 표준 지시 (2026-07-17 세션 종료 시점 유효)**: "업로드된 제품을 모두 조사했다면 작업을 끝내지 말고 세션 토큰 소진까지 계속 검토·수정을 반복하라"는 지시가 있었다. speakers 12개 파일에 대한 1차 감사(Key parity)는 완료되었으나, Null Report 총계와 실제 테이블 null 셀 수 일치 여부, 각주의 버전 번호 상호참조가 최신인지, 그 밖의 자잘한 표기 불일치는 아직 2차 감사가 필요하다 — 다음 세션에서도 사용자가 별도 지시 없이 세션을 이어가면 이 감사를 계속하는 것이 맞다.
3. **차기 제품 투입 시(양쪽 카테고리 공통)**: amplifiers는 "핵심 교훈" 절의 5가지 아키텍처 축 확인 원칙을, speakers는 `speakers/CLAUDE.md`의 브랜드별 아키텍처 참고사항(이름으로 크로스오버/커넥터 추정 금지)을 계속 적용할 것. 두 카테고리 모두 "동기화 대상 Key의 범위 제한"(SKILL v1.14, 범용 개념 vs 브랜드 고유 커넥터/부품명 Key 판별) 원칙을 신규 Key 발견 시마다 재적용해야 한다.
4. **신규 카테고리(앰프렉 등) 투입 시**: 루트에 새 카테고리 폴더(예: `amp_racks/`)를 만들고, `amplifiers/`/`speakers/`와 동일한 브랜드 하위 폴더 패턴을 그대로 재사용할 것 — 상세 규칙은 SKILL v1.15 "작업 공간 관리 및 버전 체계화" 절, 폴더별 컨벤션은 각 카테고리 폴더의 `CLAUDE.md` 참조.

## 참고: 과거 이력 요약 (상세 근거는 Archive 참조)

- SKILL.md는 v1.0부터 v1.15까지 개정. 전문은 `Archive/Archive_Skill/`. v1.10에서 Surgical Versioning Protocol 신설, v1.11에서 스켈레톤 재사용 규칙 및 출처 원본성 요건 명문화, v1.12에서 카테고리/브랜드 폴더 구조 재편 반영, v1.13은 changelog를 `SKILL_Changelog.md`로 분리, v1.14에서 양방향 동기화 대상 Key 범위 제한(범용 개념 vs 브랜드 고유 커넥터/부품명) 명문화, v1.15에서 각주 서술 전반의 원본성 요건 확장 및 측정 표준 번들 비원자화 원칙 신설.
- 이 파일(Session_Transfer.md) 자체는 v1.0(Phase 1-2 시점) ~ v1.6(16개 제품, speakers 투입 이전)까지를 `Archive/Archive_Meta/`에 보존하고 있다. v1.4 이후 실제 제품 수가 4개 → 16개로 늘어났음에도 장기간 갱신되지 않았던 것이 v1.5 재작성의 계기였다 — CLAUDE.md가 경고하는 "Session_Transfer가 실제 리포지토리 상태에 뒤처질 수 있다"는 사례가 실제로 발생한 것이므로, 향후에는 8개 정도의 신규 제품이 쌓이기 전에, 또는 폴더 구조/카테고리가 바뀔 때마다 더 자주 갱신할 것을 권장한다(v1.6→v1.7은 신규 카테고리 투입을 계기로 즉시 갱신한 사례).
- 각 제품 파일의 버전 이력은 파일 자체 하단 "버전 변경 이력" 절 참조(본 파일에서 반복하지 않음).
