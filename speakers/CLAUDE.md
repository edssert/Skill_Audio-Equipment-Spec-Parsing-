# speakers 카테고리 폴더 지침

이 폴더는 스피커(라인어레이 엘리먼트, 서브우퍼 등) 제품군을 브랜드별 하위 폴더로 관리한다. 브랜드 폴더명: L-Acoustics -> `LA`, d&b audiotechnik -> `db`, Meyer Sound -> `MY`.

각 브랜드 폴더(`LA/`, `db/`, `MY/`)는 `amplifiers/` 카테고리와 동일한 내부 구조를 따른다:

- `{제품명}_v{버전}.md` — 해당 제품의 최신 마스터 스키마 파일 (브랜드 폴더 루트에 위치)
- `Original_PDFs/{제품명}/` — 원본 문서(OM/SPS/AE, PDF 또는 docx) 보존. 파일명 규칙은 `amplifiers/CLAUDE.md`와 동일. 원본은 절대 수정하지 않는다.
- `Raw_Web_Data/{제품명}_Raw_Web_Data.md` — 웹사이트 계층별 텍스트 병합 보존. **주의**: 사용자가 붙여넣은 텍스트가 실제로는 웹사이트 원문이 아니라 다른 세션의 파싱 결과물 등 "출처 미검증" 자료일 수 있다(K1 사례) — 이 경우 파일 상단에 그 사실을 명시하고, 마스터 스키마에는 자체 보유 원본으로 재검증에 성공한 항목만 반영한다.
- `Archive/{제품명}/` — 해당 제품의 과거 버전 마스터 스키마 보관.
- `References/` (LA에만 존재) — 특정 제품 하나에 속하지 않고 여러 제품에 걸쳐 사용되는 브랜드 공용 기술 문서(예: L-Acoustics의 Amplification Reference Technical Bulletin, Preset Guide). `Original_PDFs/{제품명}/`처럼 제품별로 분류할 수 없는 문서를 여기 보존한다.

## 브랜드별 아키텍처 참고사항 (2026-07-16/17 라운드에서 확립)

- **L-Acoustics(LA)**: 대부분 패시브(외부 앰프 구동) 토폴로지지만 예외가 있다 — Kiva II는 이 카테고리 최초의 **패시브 크로스오버** 제품(단일 채널 입력, 인클로저 내부에서 LF/HF 분리), L2는 **16채널** 능동 구동(37-point 커넥터)에 LC(Low frequency Cardioid) 대역까지 갖는 가장 복잡한 아키텍처다. 커넥터도 제품별로 다르다(K1/K2=PA-COM, K3/Kara II/Kiva II/KS28=speakON, K3i/Kara IIi=terminal block, L2=37-point 전용). **아키텍처를 절대 이름이나 형제 제품에서 추정하지 말고 반드시 그 제품 자신의 원본에서 판정할 것** — amplifiers 카테고리에서 확립된 "이름과 아키텍처는 무관하다" 교훈이 speakers에도 그대로 적용된다.
- **d&b audiotechnik(db)**: GSL8/GSL12는 하이브리드 크로스오버(전방 LF 채널은 active, 측면 LF/MF/HF 채널은 내부 passive crossover)이며 NLT4 커넥터 사용. CUT/HFC/Coupling이라는 파라미터형 음향 보정 기능(named preset이 아닌 컨트롤러 설정값)을 갖는 것이 L-Acoustics의 프리셋 기반 방식과 다른 핵심 차이.
- **Meyer Sound(MY)**: 이 카테고리 최초의 self-powered(자체 앰프 내장) 브랜드. self-powered 제품은 amplification_requirements 섹션 전체가 비적용이며, 대신 power_supply/protection_thermal/network_monitoring 신규 섹션을 갖는다. **self-powered 제품이라고 해서 "라인 레벨 입력만 받는다"는 식으로 일반화하지 말 것** — PANTHER는 아날로그(XLR)뿐 아니라 디지털(Milan AVB, etherCON) 입력도 있다. 커넥터나 아키텍처에 대한 판단은 항상 그 제품 자신의 원본 문서 확인 결과로만 서술한다(SKILL v1.15 "각주 서술 전반에 대한 원본성 요건").
  - **PANTHER 이후 투입된 TIGRA/LEOPARD(LEOPARD-M80)/LINA(2026-07-18)에서 확인된 브랜드 내부 다양성 — Meyer Sound라고 전부 PANTHER와 같은 방식이라고 짐작하지 말 것**: (1) AES75 표준 채택 여부가 제품마다 다름 — PANTHER/TIGRA는 AES75_Max_Linear_SPL을 쓰지만, LEOPARD/LINA는 AES75를 전혀 쓰지 않고 Meyer 자체 "Linear Peak SPL"(M-noise/Pink noise/B-noise 3종 노이즈 기반) 지표를 쓴다 — 신규 Key `Linear_Peak_SPL`로 별도 관리(AES75_Max_Linear_SPL과 상호 배타적으로 둘 중 하나만 실값을 가짐). (2) 커넥터 등급이 다름 — PANTHER/TIGRA는 기본 구성 자체가 Neutrik TOP(옥외 방수) 커넥터라 IP55/65를 기본 보유하지만, LEOPARD/LINA는 표준 XLR 커넥터(TOP 아님)가 기본이라 IP 등급이 없고, "Weather Protection"이라는 별도 옵션 액세서리를 장착해야만 IPX4를 확보한다. (3) 전력 스펙 단위가 다름 — PANTHER/TIGRA는 소비전력을 W(와트) 단위로만 제공하지만, LEOPARD/LINA는 A(암페어) 단위로 115/230/100V AC 3개 조건별 전류를 병기한다(신규 Key군: Idle_Current/Max_Long_Term_Continuous_Current/Burst_Current/Max_Instantaneous_Peak_Current/Inrush_Current) — 두 단위 체계를 임의로 환산(W=V×A)하지 말 것(임의 추론 금지 원칙 위반). (4) LED 명칭/구조가 다름 — PANTHER/TIGRA는 "On/Status LED", LEOPARD/LINA는 "Active/Status LED"+별도 HF/LF Limit LED. (5) 지향각 베리언트를 파트넘버 없이 병기하는 패턴(PANTHER-L/M/W, TIGRA-L/W, LEOPARD/LEOPARD-M80)이 이 브랜드에서 3회 반복 확인되어 사실상 Meyer Sound의 일관된 관례로 보이나, LINA처럼 베리언트가 아예 없는 단일 모델 제품도 있다(자동으로 "이 브랜드는 항상 변형이 있다"고 가정하지 말 것).

## 스키마 설계에서 반복적으로 나온 판단 기준 (SKILL v1.14/v1.15 참조)

새 브랜드/제품 투입 시 아래 두 축을 혼동하지 않는다:

1. **브랜드 무관 범용 측정/개념 Key** — 부하 임피던스, 4대 어레이 SPL(`Max_SPL_4x_Array_Far_Field_Scaled_1m`), 다중 dB 임계값 대역폭(`Frequency_Response_3dB_Hz` 등), AES75 같은 업계 표준 채택 여부, LC 대역 유무, 단일 채널 패시브 아키텍처(`Nominal_Impedance_Overall`/`RMS_Power_Handling_Overall`) — 이런 개념은 어느 브랜드든 가질 수 있으므로 다른 제품 파일에도 **null로 동기화**한다.
2. **브랜드/제품 고유 물리 설계·부품·커넥터 모델명이 Key 이름에 박힌 경우, 또는 근본적으로 다른 아키텍처 카테고리에만 성립하는 기능 개념인 경우** — GSL의 `Front_LF_Transducer`, 커넥터 모델명을 그대로 딴 `PA_COM_Pinout_*`/`NLT4_Pinout_*`/`SpeakON_Pinout_*`/`Terminal_Block_Pinout_*`/`Connector_16Channel_Pinout`, d&b의 `CUT_Mode_*`/`HFC_Function_Settings`/`Coupling_Function_Range` — 이런 Key는 다른 제품 파일에 null로 끌어오지 않고 **아예 생성하지 않는다**(각 제품은 자기 자신의 실제 커넥터/기능을 자기 자신의 Key로 온전히 표현). 여러 개의 커넥터 모델별 핀아웃 Key 그룹이 한 파일에 공존해서는 안 된다 — 그 제품이 실제로 쓰는 커넥터의 Key 그룹만 남긴다.
   - **이름에 브랜드/모델명이 박혀 있지 않아도 이 규칙이 적용되는 경우(2026-07-19 확립)**: Meyer Sound(self-powered)에만 있는 `network_monitoring` 섹션 전체(`Remote_Mute_Control`, `AES67_Support`, `Service_Port_Type`, `Network_Protocol`, `Telemetry_Software`, `Device_Identification_Function`, `Network_Connectivity_LED` 등)는 이름 자체는 범용처럼 보이지만, "온보드 앰프+네트워크 인터페이스를 가진 self-powered 제품에서만 성립하는 개념"이라 패시브(외부 앰프 구동) 아키텍처인 LA/db에는 애초에 null로도 동기화하지 않는다 — 이 섹션 자체가 처음부터 LA/db 어느 파일에도 존재한 적이 없다. 신규 Key를 동기화 대상에 넣을지 판단할 때는 "이름에 고유명사가 있는가"뿐 아니라 "이 Key가 속한 상위 섹션/개념 자체가 특정 아키텍처 카테고리(self-powered vs 패시브 등)에서만 성립하는가"도 함께 확인할 것.

측정 표준/프로토콜 번들(AES75 등)은 하위 수치(dBZ/dBZpk/dBA 등)를 개별 Key로 원자화하지 않고 하나의 복합값 Key로 유지한다.

## 제품 구성 판단 (변형/베리언트 처리)

같은 제품명 아래 여러 지향각/폭 변형이 있을 때, 별도 파일로 분리할지 한 파일에 Value 병기(`"L: x / M: y / W: z"`)할지는 공식 문서가 그 변형들을 별개 모델(별도 파트넘버 등)로 취급하는지, 하나의 제품명의 베리언트로 취급하는지에 따라 정한다 — GSL8/GSL12(별도 파트넘버 Z0750/Z0751)는 별도 파일.

**PANTHER-L/M/W는 예외적으로 정책이 뒤집힌 사례(사용자 지시 2026-07-18)**: 파트넘버 구분이 없어(공식 Datasheet가 하나의 표에 병기) 최초에는 위 원칙에 따라 통합 파일(`PANTHER_v1.0.md`~`v1.9.md`)로 파싱했으나, 사용자가 파트넘버 유무와 무관하게 **개별 지향각 베리언트는 항상 별도 파일로 분리**하라고 명시적으로 지시해 `PANTHER_L_v1.0.md`/`PANTHER_M_v1.0.md`/`PANTHER_W_v1.0.md` 3개로 재분리했다(통합본 이력은 `speakers/MY/Archive/PANTHER/`에 전체 보존). 이는 "파트넘버 유무" 판단 기준 자체를 폐기한 것이 아니라, **사용자가 이 특정 케이스에 대해 분리를 명시적으로 원했다는 개별 지시**로 처리한다 — 향후 유사한 파트넘버-미구분 베리언트 제품이 나오면, 위 원칙(통합)을 기본값으로 삼되 이 PANTHER 선례를 사용자에게 환기하고 재확인할 것(자동으로 분리 정책을 일반화하지 않는다).

**TIGRA-L/W도 동일 패턴으로 개별 파일 분리 확인(2026-07-18, 2번째 사례)**: PANTHER와 마찬가지로 파트넘버 구분 없이 지향각(85°/110°)만 다른 TIGRA-L/TIGRA-W 투입 시, 위 PANTHER 선례를 사용자에게 환기하고 재확인한 결과 동일하게 분리 결정(`TIGRA_L_v1.0.md`/`TIGRA_W_v1.0.md`). Meyer Sound 브랜드에서 2번째로 이 패턴이 확인되어 "Meyer Sound는 지향각 베리언트를 파트넘버 없이 병기하는 관례"일 가능성이 있으나, 아직 브랜드 전체에 대한 확정 원칙으로 격상하지 않는다 — Meyer Sound의 향후 신규 제품(LEOPARD/LINA 등)에서도 유사 패턴이 나오면 이번에도 자동 일반화하지 말고 재확인할 것.

향후 신규 카테고리(예: `amp_racks/`) 투입 시에도 이 폴더와 동일한 브랜드 하위 폴더 패턴(카테고리/브랜드/...)을 루트에 병렬로 적용한다.
