# PANTHER-W (Meyer Sound) — Master Schema

**Category**: speakers | **Brand**: Meyer Sound (MY) | **Schema Phase**: Phase 3-2 (타 브랜드 교차 테스트, K1/GSL8/GSL12 대비)

**스켈레톤 근거**: 완전히 새로운 브랜드 최초 투입이며, 기존 파일 중 아키텍처가 가장 유사한 것은 없다(K1/GSL8/GSL12는 모두 외부 앰프 구동 패시브/하이브리드 토폴로지, PANTHER는 self-powered) — 따라서 K1_v1.2.md의 섹션 구조를 뼈대로 재사용하되, self-powered 아키텍처 전용 신규 섹션(power_supply, connectivity의 오디오 입출력 상세, protection_thermal, network_monitoring)을 대거 신설했다. 사용자 지침(2026-07-16)에 따라 신규 브랜드 최초 제품이므로 K1/GSL 수준의 깊이(원본 문서 전체 스캔, 다중 소스 교차검증)를 동일하게 적용했다.

**PANTHER-L/M/W 개별 파일 분리(사용자 지시 2026-07-18)**: 최초 투입 시(v1.0~v1.9) PANTHER-L(80°)/PANTHER-M(95°)/PANTHER-W(110°) 3개 수평 지향각 베리언트를 1개 파일에 "L: x / M: y / W: z" 형식으로 통합했었으나, 사용자가 이를 뒤집고 3개 개별 파일로 분리하라고 지시 — Surgical Versioning Protocol에 따라 통합본(`speakers/MY/Archive/PANTHER/PANTHER_v1.9.md`, v1.0~v1.9 전체 이력 포함)을 아카이브하고 이 파일을 v1.0으로 새로 시작한다. **베리언트 간 차이는 수평 지향각(80°/95°/110°)에 종속되는 3개 음향 Key(Max_SPL_Peak, AES75_Max_Linear_SPL, Nominal_Directivity_Horizontal_deg)뿐이며, 나머지 전 섹션은 PANTHER-L/PANTHER-M과 완전히 동일값이다** — 상세 근거·각주는 PANTHER_L_v1.0.md와 동일 문구를 공유(원본 자체가 이 3개 값 외에는 베리언트를 구분하지 않으므로).

**아키텍처 판단(원본 근거)**: PANTHER는 AE/OM 원문에 명시적으로 "self-powered"로 표기되며("The loudspeaker shall be a self-powered... line array loudspeaker", AE p.1; "The self-powered PANTHERTM linear line array loudspeaker...", OM p.1), 내장 4채널 Class-D 앰프와 온보드 DSP를 탑재한다. 크로스오버는 Active로 판단 — 3개 원본 문서 전체에 "crossover" 키워드가 0건 검출되어(전량 스캔 근거) 내부 패시브 크로스오버가 없으며, 4채널 앰프가 LF 2발+HF 2발 각 드라이버를 개별 채널로 구동하는 구조로 판단된다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | PANTHER-W | - |
| Model_Number | null | - |
| Product_Series | null | - |
| Product_Category | Line Array | - |
| Product_Type | Self-powered line array loudspeaker | - |
| Description | self-powered, linear, low-distortion line array loudspeaker, 2-way, 110° horizontal coverage | - |
| Way_Count | 2 | - |
| Onboard_Amplification | Yes | - |
| Compliance_Standards | c(UL)us Listed (3K59 or 3JKB Commercial Audio System); CE marked | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: AE(Architectural Specification, Meyer Sound, docs.meyersound.com) p.1; OM(Operating Instructions) p.1-2; SPS(Datasheet) p.1.
**Model_Number**: d&b GSL8/GSL12의 Z0750/Z0751 같은 공식 파트넘버 표기가 3개 문서 어디에도 없어 미확인.
**Way_Count**: SPS 각주 "The PANTHER 2-way loudspeaker has a unique placement of low-mid transducers..." — 명시적으로 2-way.
**Compliance_Standards**: SPS(Datasheet) p.3-4 하단 인증 마크 이미지에서 확인 — 텍스트 레이어가 아닌 이미지 내 텍스트라 SKILL v1.13 예외 규정에 따라 확보.
**WEEE_Marking**: 3개 문서 전량 스캔했으나 EU WEEE 폐기물 마킹이나 문구를 찾지 못함 — 미확인.
**Product_Series/Product_Type**: Product_Type은 OM/AE의 "The self-powered PANTHER™ linear line array loudspeaker..." 서술에서 채택. Product_Series는 OM/AE/SPS 3개 문서 전량을 "series" 키워드로 스캔했으나 0건 검출 — null.
**Product_Name="PANTHER-W"**: 원문(SPS/OM) 자체가 "PANTHER-L"/"PANTHER-M"/"PANTHER-W" 표기를 사용 — GSL8/GSL12 전례와 동일하게 원문 모델 표기를 Product_Name으로 채택.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [3] | 55 - 16000 (dB 기준 미표기) | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Frequency_Response_4dB_Hz | null | Hz |
| Max_SPL_Peak [1] | 149.5 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL [2] | 126.5 dBZ / 142.5 dBZpk / 123 dBA (input +6.4 dBV) | - |
| Linear_Peak_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 110 | deg |
| Nominal_Directivity_Vertical | null | - |
| Phase_Response | null | - |
| THD_IM_TIM | null | - |
| Cardioid_Capability [4] | Array-based, automatic (4대 이상 표준 배치에서 자동 발현, 반전 유닛·프리셋 불필요) | - |
| DSP_Preset_Name | null | - |
| Cardioid_Pattern_Array_Min_Size | 4 | count |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.1-2 "Specifications" 표(ACOUSTICAL, PANTHER-W 열); AE p.1; OM p.1-2.
**[1] Max_SPL_Peak 측정 조건**: SPS 각주 "Maximum Sound Level is the Lpeak measured using burst noise", AE는 "measured in free-field at 4 m referred to 1 m using noise"로 더 상세 — 두 문서 값 일치. W 베리언트는 L/M(150.5dB)보다 낮은 149.5dB — 넓은 커버리지(110°)로 인한 축상 SPL 감소로 추정(원문에 명시적 설명은 없음).
**[2] AES75_Max_Linear_SPL(단일 통합 Key)**: AES75-2022는 브랜드 무관 업계 표준 — dBZ/dBZpk/dBA/기준입력레벨(dBV) 4개 수치를 하나의 복합값 Key로 병기.
**DSP_Preset_Name**: PANTHER는 자체 DSP 내장, Compass/Galileo GALAXY 소프트웨어로 시스템 레벨 제어 — 프리셋 명명 체계 자체가 없어 미확인.
**Nominal_Directivity_Vertical**: 3개 문서 전량 스캔했으나 수직 지향각 수치나 서술 발견 못함 — 미확인.
**[4] Cardioid_Capability — 4번째 유형**: 원문(SPS) "Arrays of four units and longer functionally create a cardioid polar pattern... does not require any user settings." — 전용 카디오이드 드라이버군 없이 표준 LF/MF 드라이버 배치의 기하학적 설계만으로 4대 이상 정상 배치 시 자동으로 카디오이드 패턴이 발현. 상세 근거는 PANTHER_L_v1.0.md 참조.
**[3] Usable_Bandwidth_Hz**: 원문 "Operating Frequency Range"를 브랜드 무관 범용 Key 이름으로 통일 — PANTHER-L/M/W 3개 베리언트 공통값.
**Frequency_Response_4dB_Hz(신규 Key)**: 750-LFC에서 신설된 범용 Key(-4dB 기준 대역폭) — 이 제품 자신의 원본에서 아직 재확인되지 않아 미확인 유지.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 2 x 12" long-excursion cone drivers | - |
| HF_Transducer | 2 x 3" diaphragm compression drivers coupled to a constant-directivity horn through a patented ribbon emulation manifold | - |
| LF_Acoustical_Load | null | - |
| HF_Acoustical_Load | constant-directivity horn (ribbon emulation manifold) | - |
| Passive_Crossover_Network | No | - |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | null | W |
| Peak_Power_Handling_10ms_Overall | null | W |
| LF_Nominal_Impedance | 4 | Ohm |
| Nominal_Impedance_Overall | null | Ohm |
| HF_Nominal_Impedance | 8 | Ohm |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.3 "TRANSDUCERS" 표(3개 베리언트 공통); AE p.1.
**트랜스듀서 스펙 L/M/W 공통**: 드라이버 구성·재질·임피던스는 3개 베리언트 모두 동일 — 수평 커버리지 각도는 HF 혼/도파관의 형상 차이로만 결정.
**Passive_Crossover_Network=No 판단 근거**: OM/AE/SPS 3개 문서 전체 "crossover" 키워드 전량 스캔 0건 검출.
**LF_Acoustical_Load**: 명시적 표기 없음 — 미확인.
**Peak_Power_Handling_10ms_Overall(신규 Key)**: d&b CCL8에서 신설된 범용 Key — RMS_Power_Handling_Overall과 동일 사유(self-powered 구조상 드라이버 자신의 파워 핸들링이 아니라 Amplifier_Total_Output_Power로 보고)로 비적용.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Connector | Neutrik XLR 3-pin TOP, female | - |
| Analog_Loop_Output_Connector | Neutrik XLR 3-pin TOP, male | - |
| Analog_Input_Impedance | 10000 | Ohm |
| Analog_Nominal_Input_Level | 0 dBV (1.0 V rms) | - |
| Analog_Input_Pinout_Pin1 | 1 kOhm to chassis and earth ground (ESD clamped) | - |
| Analog_Input_Pinout_Pin2 | Signal (+) | - |
| Analog_Input_Pinout_Pin3 | Signal (-) | - |
| Analog_Input_Pinout_Case [1] | Earth (AC) ground and chassis | - |
| Analog_Source_Drive_Requirement | +24 dBu into 50 Ohm (for maximum peak SPL) | - |
| Digital_Input_Connector | Neutrik etherCON TOP | - |
| Digital_Input_Format | AVB, Milan Certified | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14-17; SPS p.3(ANALOG/DIGITAL AUDIO INPUT); AE p.1. 커넥터 사양은 3개 베리언트 공통.
**Input_Connector/Link_Connector/PA_COM_Pinout_*/NLT4_Pinout_* 미생성**: PANTHER 자신의 3개 원본 문서를 "PA-COM"/"NLT4"/"speakON" 키워드로 전량 스캔한 결과 0건 검출.
**[1] Analog_Input_Pinout_Case(신규 Key, v1.2)**: OM "Case — earth (AC) ground and chassis" — 2100-LFC 파싱 과정에서 신설된 신규 Key를 PANTHER 자신의 원본에서 재확인해 실값 반영(2100-LFC_v1.0.md 참조).

## power_supply

self-powered 아키텍처 전용 신규 섹션 — K1/GSL8/GSL12(외부 앰프 구동)에는 비적용.

| Key | Value | Unit |
|---|---|---|
| AC_Connector | Neutrik powerCON TRUE1 TOP | - |
| AC_Nominal_Voltage_Range | 200 - 240 | V AC |
| AC_Operating_Voltage_Range [1] | 160 - 264 | V AC |
| AC_Frequency_Range | 50 - 60 | Hz |
| Max_Long_Term_Continuous_Power | 1100 | W |
| Burst_Power | 2200 | W |
| Idle_Power | 150 | W |
| Max_Cable_Round_Trip_Resistance [1] | 5 | Ohm |
| AC_Inlet_Pinout | L (Line), N (Neutral), Protective Earth/Ground | - |
| Power_Supply_Protection_Features | EMI filtering (common mode and differential mode), soft-start current turn-on, surge suppression (up to several kilovolts) | - |
| Amplifier_Total_Output_Power | null | W |
| Idle_Current | null | - |
| Max_Long_Term_Continuous_Current | null | - |
| Burst_Current | null | - |
| Max_Instantaneous_Peak_Current | null | - |
| Inrush_Current | null | A peak |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.2 "AC POWER"/"POWER CONSUMPTION"; AE p.1-2; OM p.9-12. 전원부는 3개 베리언트 공통.
**[1] AC_Operating_Voltage_Range/Max_Cable_Round_Trip_Resistance**: OM에만 있는 상세 정보 — TPL(True Power Limiting) 정전력 부하 특성상 케이블 왕복 저항 5Ω 초과 시 피크 출력 시 AC 인렛 전압이 160V 미만으로 떨어질 수 있음.
**Idle_Power**: SPS에만 명시.

## protection_thermal

self-powered 아키텍처 전용 신규 섹션 — K1/GSL8/GSL12에는 비적용.

| Key | Value | Unit |
|---|---|---|
| Limiter_Type | TruPower limiting | - |
| Limiter_Indication | On/Status LED: solid yellow 1 sec = HF channel limiting; pulsing yellow = LF channel limiting | - |
| Cooling_Type | forced-air, 2 variable-speed fans | - |
| IP_Rating [1] | 65 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: AE p.1; OM p.19-20, p.20-21; OM p.8, p.9, p.15. 3개 베리언트 공통.
**[1] IP_Rating 소스 간 충돌**: SPS/AE는 "IP55", OM은 3곳에서 일관되게 "IP65, UL50E" — OM 값 채택, SPS/AE 값 각주 보존.

## network_monitoring

self-powered/네트워크 연동 아키텍처 전용 신규 섹션 — K1/GSL8/GSL12에는 비적용.

| Key | Value | Unit |
|---|---|---|
| Network_Protocol | Milan AVB | - |
| Telemetry_Software | Nebra | - |
| Telemetry_Transport | via network (Ethernet) connection | - |
| Device_Identification_Function | Wink | - |
| Network_Connectivity_LED | illuminated when 100 bT link established | - |
| AES67_Support | null | - |
| Service_Port_Type | null | - |
| Remote_Mute_Control | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.2, p.19. 3개 베리언트 공통.
**AES67_Support/Service_Port_Type**: 3개 문서 전량 스캔했으나 언급 없음 — 미확인.
**Remote_Mute_Control(신규 Key)**: 750-LFC/900-LFC에서 신설된 범용 Key(네트워크를 통한 원격 뮤트 활성화/비활성화 기능) — 이 제품 자신의 원본에서 아직 재확인되지 않아 미확인 유지.

## amplification_requirements

self-powered이므로 외부 앰프 매칭 개념이 원천적으로 비적용.

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | null | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (2-way, 4 discrete driver channels via internal 4-channel Class-D amplifier) | - |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: PANTHER는 자체 앰프를 내장한 self-powered 제품이라 외부 앰프와 매칭할 필요가 없다.
**Crossover_Type**: AE 원문 "The loudspeaker shall incorporate internal processing and a 4-channel class-D amplifier" — LF 2발+HF 2발 각 드라이버가 개별 채널로 구동.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | end frames with captive GuideALinks secured with quick-release pins (QRP); QuickFly rigging system | - |
| Inter_Enclosure_Angles_deg | 0.5, 1, 2, 3, 4, 5, 6, 7, 8, 9 | deg |
| Handles | detachable side handles | - |
| Weight_Net | 68 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.2 "PHYSICAL"; OM p.22-26. 리깅 시스템/중량은 3개 베리언트 공통.
**Inter_Enclosure_Angles_deg**: 연속 범위(0.5°-9°)로 원문 그대로 기재.
**Handles**: 정확한 개수는 미확인.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 969 | mm |
| Height_mm | 377 | mm |
| Depth_mm | 565 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | premium multi-ply birch | - |
| Front_Material | powder-coated stamped steel (protective grille) | - |
| Rigging_Components_Material | null | - |
| Finish_Color | slightly textured black | - |
| Finish_Type | null | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: AE p.2 "Dimensions shall be 38.15 in (969 mm) wide, 14.85 in (377 mm) high, and 22.25 in (565 mm) deep" — 캐비닛 외형 치수는 3개 베리언트 공통.
**Dimensions_Raw**: 축이 명확히 확인되어 상위 호환 Key로 대체 — null.
**IP_Rating**: protection_thermal 섹션으로 이전 — physical에서는 중복 방지로 null.
**Rigging_Components_Material/Finish_Type**: 별도 서술 없음 — 미확인.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: PANTHER는 명명된 프리셋 조합 가이드가 없음 — MAPP System Design and Prediction 소프트웨어로 시뮬레이션. 소프트웨어 기반 결과물은 이 세션에 제공되지 않아 미확인.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: preset_guide_and_matching과 동일 — OM에 고정 딜레이 기본값 표가 없음.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown (with horizontal aim adjustment) | MVP Motor V Plate + MG-PANTHER Grid Kit | null | 25 |
| flown, LEOPARD downfill | MTF-LYON/LEOPARD Transition Frame Kit | null | up to 10 LEOPARD |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 5:1 | - |
| Max_Wind_Load | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.24-26, p.23-24. 기계 안전 수치는 3개 베리언트 공통.
**안전계수**: 모든 리깅 액세서리 공통 5:1 — MAPP 소프트웨어 시뮬레이션이 기본 검증 방식.
**Safe_Limit 열 null 사유**: MAPP은 이진 판정만 제공 — 미확인.
**기본 구성 최대 대수**: 별도 상한 미명시 — 미확인.
**Max_Wind_Load(미확인)**: 정성적 서술만 있고 구체적 수치 없음.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Nominal_Directivity_Vertical, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, Frequency_Response_5dB_Hz, DSP_Preset_Name, LF_Acoustical_Load, RMS_Power_Handling_LF, RMS_Power_Handling_HF, AES67_Support, Service_Port_Type, Handles(정확한 개수), Rigging_Components_Material, Finish_Type, Max_Wind_Load, preset_guide_and_matching(전 항목), delay_defaults(전 항목), mechanical_safety(Safe_Limit 열 — MVP+MG-PANTHER/LEOPARD downfill 2개 Configuration 행의 null 셀, 2건), Linear_Peak_SPL, Phase_Response, THD_IM_TIM, Amplifier_Total_Output_Power, Idle_Current, Max_Long_Term_Continuous_Current, Burst_Current, Max_Instantaneous_Peak_Current, Inrush_Current, Frequency_Response_4dB_Hz, Remote_Mute_Control — 31건.
**비적용(PANTHER 아키텍처상 개념 자체 불성립, K1/GSL에서 유래)**: Compatible_Amplified_Controller, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Dimensions_Raw, IP_Rating(physical 섹션, protection_thermal로 이전), Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module, Peak_Power_Handling_10ms_Overall — 9건.

**총계**: null 40건 (미확인 31건 + 비적용 9건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Passive_Crossover_Network(No, 3개 문서 전량 스캔 근거). **추가 정정(2026-07-18, 같은 감사 라운드)**: mechanical_safety Safe_Limit 결합형 불릿 오카운트(2개 행을 1건으로 카운트) 정정 — 미확인 28건→29건, 총계 36건→37건. 데이터(Key/Value/Unit) 자체는 전혀 변경하지 않았다.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | PANTHER-L/M/W 개별 파일 분리(사용자 지시 2026-07-18) — 통합 파일 `PANTHER_v1.9.md`(v1.0~v1.9 전체 이력, `speakers/MY/Archive/PANTHER/`에 보존)에서 PANTHER-W 베리언트만 분리해 이 파일로 시작. 베리언트별 값(Max_SPL_Peak=149.5dB, AES75_Max_Linear_SPL, Nominal_Directivity_Horizontal_deg=110°)만 단일화하고 나머지는 통합 파일의 최종 상태(v1.9) 그대로 승계. |
| v1.0 to v1.1 | (양방향 동기화, Minor) Meyer Sound 신규 제품 TIGRA/LEOPARD/LINA 파싱 과정에서 발견된 9개 신규 Key(Linear_Peak_SPL/Phase_Response/THD_IM_TIM/Amplifier_Total_Output_Power/Idle_Current/Max_Long_Term_Continuous_Current/Burst_Current/Max_Instantaneous_Peak_Current/Inrush_Current)를 null로 소급 반영(상세 근거는 PANTHER_L_v1.1.md 동일 라운드 참조). PANTHER 자신의 3개 문서 재스캔 결과 전부 미확인. Null Report 27건에서 36건으로 증가. **후속 정정(같은 v1.1, 2026-07-18)**: mechanical_safety Safe_Limit 결합형 불릿 오카운트 정정, Null Report 37건(미확인 29건+비적용 8건)으로 재계산. |
| v1.1 to v1.2 | (양방향 동기화, Minor) Meyer Sound 신규 제품 2100-LFC 파싱 과정에서 신설된 Key `Analog_Input_Pinout_Case`를 실값("Earth (AC) ground and chassis")으로 반영 — PANTHER 자신의 OM 원본 재확인 결과 확인(상세 근거는 PANTHER_L_v1.2.md 동일 라운드 참조). Null Report 총계는 영향 없음. |
| v1.2 to v1.3 | speakers 카테고리 전체 일괄 동기화 라운드(2026-07-18, d&b 대량 배치 완료 후) — 신규 Key `Frequency_Response_4dB_Hz`(미확인), `Peak_Power_Handling_10ms_Overall`(비적용), `Remote_Mute_Control`(750-LFC/900-LFC 유래, 미확인) 반영. Null Report 40건(미확인 31건+비적용 9건)으로 갱신. |