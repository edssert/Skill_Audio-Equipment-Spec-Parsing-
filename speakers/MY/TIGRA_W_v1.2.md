# TIGRA-W (Meyer Sound) — Master Schema

**Category**: speakers | **Brand**: Meyer Sound (MY) | **Schema Phase**: Phase 4 (Meyer Sound 2번째 제품군 투입, PANTHER 대비)

**스켈레톤 근거**: `speakers/MY/TIGRA_L_v1.0.md`(TIGRA-L, 형제 파일)와 동일 원본 문서(SPS/OM/AE)에서 독립 확인. **베리언트 간 차이는 Max_SPL_Peak/AES75_Max_Linear_SPL/Nominal_Directivity_Horizontal_deg 3개 Key뿐**이며 나머지 전 섹션(트랜스듀서/커넥터/전원/보호회로/네트워크/앰프요구사항/리깅/치수/기계안전)은 TIGRA-L과 완전 동일값이다 — 상세 근거·각주는 TIGRA_L_v1.0.md와 동일 문구를 공유(원본 자체가 이 3개 값 외에는 베리언트를 구분하지 않으므로, PANTHER-L/M/W 전례와 동일 원칙).

**아키텍처 판단(원본 근거)**: TIGRA_L_v1.0.md와 동일 — self-powered, 2채널 Class-D 앰프(LF 2발 병렬 공유+HF 1발 추정), Passive_Crossover_Network=No(3개 문서 전량 "crossover" 키워드 0건).

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | TIGRA-W | - |
| Model_Number | null | - |
| Product_Series | null | - |
| Product_Category | Line Array | - |
| Product_Type | Medium-format line array loudspeaker | - |
| Description | self-powered, linear, low-distortion line array loudspeaker, 2-way, 110° horizontal coverage | - |
| Way_Count | 2 | - |
| Onboard_Amplification | Yes | - |
| Compliance_Standards | null | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처 및 상세 근거**: TIGRA_L_v1.0.md의 general 섹션과 동일 문구 공유 — AE 말미 "The 110° coverage medium-format line array loudspeaker shall be the Meyer Sound TIGRA-W." 원문에서 Product_Type 직접 채택.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [5] | 55 - 16000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Frequency_Response_4dB_Hz | null | Hz |
| Max_SPL_Peak [1] | 145 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL [2] | 121 dBZ / 139.5 dBZpk (input +3 dBV) | - |
| Linear_Peak_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 110 | deg |
| Nominal_Directivity_Vertical | null | - |
| Phase_Response | null | - |
| THD_IM_TIM | null | - |
| Cardioid_Capability [3] | Array-based, automatic (6대 이상 표준 배치에서 자동 발현, 반전 유닛·프리셋 불필요) | - |
| DSP_Preset_Name | null | - |
| Cardioid_Pattern_Array_Min_Size | 6 | count |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.1-2 "TIGRA specifications" 표(ACOUSTICAL, TIGRA-W 열); AE p.1(TIGRA-W 문단); OM p.1. 상세 근거는 TIGRA_L_v1.0.md와 동일(측정조건/AES75 병기 원칙/Cardioid 4번째 유형 판단/Usable_Bandwidth_Hz 측정조건 부재 등) — [1][2][3][5] 각주 내용도 동일 문구 공유, TIGRA-W 자신의 수치(145dB, 121dBZ/139.5dBZpk @+3dBV, 110°)만 대입. **[5] Usable_Bandwidth_Hz**: TIGRA-L과 완전 동일값(55-16000Hz)이며 측정 조건이 원문에 없다는 사실도 동일 — TIGRA_L_v1.0.md 각주 [5] 참조.
**Frequency_Response_4dB_Hz(신규 Key)**: 750-LFC에서 신설된 범용 Key(-4dB 기준 대역폭) — 이 제품 자신의 원본에서 아직 재확인되지 않아 미확인 유지.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 2 x 10" long-excursion cone drivers | - |
| HF_Transducer | 1 x 4" diaphragm compression driver coupled to a constant-directivity horn through a manifold | - |
| LF_Acoustical_Load | null | - |
| HF_Acoustical_Load | constant-directivity horn (manifold) | - |
| Passive_Crossover_Network | No | - |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | null | W |
| Peak_Power_Handling_10ms_Overall | null | W |
| LF_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall | null | Ohm |
| HF_Nominal_Impedance | null | Ohm |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일** — 드라이버 구성은 두 베리언트 공통(수평 커버리지는 HF 혼 형상 차이로만 결정).
**Peak_Power_Handling_10ms_Overall(신규 Key)**: d&b CCL8에서 신설된 범용 Key — RMS_Power_Handling_Overall과 동일 사유(self-powered 구조상 드라이버 자신의 파워 핸들링이 아니라 Amplifier_Total_Output_Power로 보고)로 비적용.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Connector | Neutrik XLR 3-pin TOP, female | - |
| Analog_Loop_Output_Connector | Neutrik XLR 3-pin TOP, male | - |
| Analog_Input_Impedance | 10000 | Ohm |
| Analog_Nominal_Input_Level | null | - |
| Analog_Input_Pinout_Pin1 | 1 kOhm to chassis and earth/ground (ESD clamped) | - |
| Analog_Input_Pinout_Pin2 | Signal (+) | - |
| Analog_Input_Pinout_Pin3 | Signal (-) | - |
| Analog_Input_Pinout_Case [1] | Earth (AC) ground and chassis | - |
| Analog_Source_Drive_Requirement | +24 dBU into 50 Ohm (for maximum peak SPL) | - |
| Digital_Input_Connector | Neutrik RJ45 etherCON TOP (x2) | - |
| Digital_Input_Format | Milan AVB | - |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.1.md와 완전 동일** — 커넥터 사양은 두 베리언트 공통.
**[1] Analog_Input_Pinout_Case(신규 Key, v1.1)**: OM p.24 "Case — earth (AC) ground and chassis" — 2100-LFC 파싱 과정에서 신설된 신규 Key를 TIGRA 자신의 원본에서 재확인해 실값 반영(2100-LFC_v1.0.md 참조).

## power_supply

self-powered 아키텍처 전용 섹션(PANTHER 전례 준용).

| Key | Value | Unit |
|---|---|---|
| AC_Connector | Neutrik powerCON TRUE1 Chassis Connector (NAC3PX-TRUE1) | - |
| AC_Nominal_Voltage_Range | 100 - 240 | V AC |
| AC_Operating_Voltage_Range | 90 - 275 | V AC |
| AC_Frequency_Range | 50 - 60 | Hz |
| Max_Long_Term_Continuous_Power | 550 | W |
| Burst_Power | 1270 | W |
| Idle_Power | 50 | W |
| Max_Cable_Round_Trip_Resistance | null | Ohm |
| AC_Inlet_Pinout | L (Line), N (Neutral), Protective Earth/Ground | - |
| Power_Supply_Protection_Features | EMI filtering (common mode and differential mode), soft-start current turn-on, surge suppression (up to several kilovolts) | - |
| Amplifier_Total_Output_Power | null | W |
| Idle_Current | null | - |
| Max_Long_Term_Continuous_Current | null | - |
| Burst_Current | null | - |
| Max_Instantaneous_Peak_Current | null | - |
| Inrush_Current | null | A peak |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일** — 전원부는 두 베리언트 공통.

## protection_thermal

self-powered 아키텍처 전용 섹션(PANTHER 전례 준용).

| Key | Value | Unit |
|---|---|---|
| Limiter_Type | TruPower limiting | - |
| Limiter_Indication | On/Status LED: green=normal, red flash=clipping, yellow (≥1 sec)=RMS limiting active, red blinking=error | - |
| Cooling_Type | convection (no fans) | - |
| IP_Rating [1] | 65 | - |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일** — [1] IP_Rating 소스 간 충돌(SPS/AE=IP55 vs OM=IP65, OM 채택) 포함 동일 근거.

## network_monitoring

self-powered/네트워크 연동 아키텍처 전용 섹션(PANTHER 전례 준용).

| Key | Value | Unit |
|---|---|---|
| Network_Protocol | Milan AVB | - |
| Telemetry_Software | Nebra | - |
| Telemetry_Transport | via network (Ethernet) connection | - |
| Device_Identification_Function | Wink | - |
| Network_Connectivity_LED | (L) amber=link speed, (A) green=activity — 5단계 표(no link / 100Base-Tx no activity / 100Base-Tx activity / 1000Base-Tx+ no activity / 1000Base-Tx+ activity) | - |
| AES67_Support | null | - |
| Service_Port_Type | null | - |
| Remote_Mute_Control | null | - |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일**.
**Remote_Mute_Control(신규 Key)**: 750-LFC/900-LFC에서 신설된 범용 Key(네트워크를 통한 원격 뮤트 활성화/비활성화 기능) — 이 제품 자신의 원본에서 아직 재확인되지 않아 미확인 유지.

## amplification_requirements

self-powered이므로 외부 앰프 매칭 개념이 원천적으로 비적용.

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | null | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (2-way, 2 discrete amplifier channels via internal 2-channel Class-D amplifier) | - |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일**.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | end frames with captive GuideALinks secured with quick-release pins (QRP); QuickFly rigging system | - |
| Inter_Enclosure_Angles_deg | 0.5 - 10 | deg |
| Handles | detachable side handles | - |
| Weight_Net | 54 | kg |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일** — 리깅 시스템/중량은 두 베리언트 공통(캐비닛 외형 동일).

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 862 | mm |
| Height_mm | 324 | mm |
| Depth_mm | 565 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | premium multi-ply birch | - |
| Front_Material | powder-coated stamped steel (protective grille) | - |
| Rigging_Components_Material | null | - |
| Finish_Color | slightly textured black | - |
| Finish_Type | null | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일** — 캐비닛 외형 치수는 두 베리언트 공통(HF 혼 내부 형상만 다름).

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일** — MAPP 소프트웨어 기반 시뮬레이션 방식, 소프트웨어 결과물 미제공으로 미확인.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일**.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown, no splay limit | MTG-T1 Top Grid Kit | null | 16 |
| flown, splay-limited(2-11대: ≤2°, 12-18대: ≤8°, 19-22대: 제한 없음) | MTG-T1 Top Grid Kit | null | 24 |
| flown, 하부 추가 다운틸트 | MPBF-T1 Pull Back Frame | null | 12 |
| PANTHER 어레이 하부 연결(다운필) | MTF-T1 Transition Frame | null | 6 |
| 이동/보관(비행 구성 아님) | MCF-T1 Caster Frame | null | 4 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 5:1 | - |
| Max_Wind_Load | null | - |

### 주석 및 출처 (Notes & Sources)

**TIGRA_L_v1.0.md와 완전 동일** — 기계 안전 수치는 두 베리언트 공통(중량·캐비닛 동일).

## Null Report

**미확인(정보 부족)**: Model_Number, Product_Series, Compliance_Standards, WEEE_Marking, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, Frequency_Response_5dB_Hz, Nominal_Directivity_Vertical, DSP_Preset_Name, LF_Acoustical_Load, RMS_Power_Handling_LF, RMS_Power_Handling_HF, LF_Nominal_Impedance, HF_Nominal_Impedance, Analog_Nominal_Input_Level, Max_Cable_Round_Trip_Resistance, AES67_Support, Service_Port_Type, Handles(정확한 개수), Rigging_Components_Material, Finish_Type, Max_Wind_Load, preset_guide_and_matching(전 항목), delay_defaults(전 항목), mechanical_safety(Safe_Limit 열 — 5개 Configuration 행의 null 셀, 5건), Linear_Peak_SPL, Phase_Response, THD_IM_TIM, Amplifier_Total_Output_Power, Idle_Current, Max_Long_Term_Continuous_Current, Burst_Current, Max_Instantaneous_Peak_Current, Inrush_Current, Frequency_Response_4dB_Hz, Remote_Mute_Control — 39건.
**비적용(TIGRA 아키텍처상 개념 자체 불성립)**: Compatible_Amplified_Controller, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Dimensions_Raw, IP_Rating(physical 섹션, protection_thermal로 이전), Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module, Peak_Power_Handling_10ms_Overall — 9건.

**총계**: null 48건 (미확인 39건 + 비적용 9건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Passive_Crossover_Network(No, 3개 문서 전량 스캔 근거). TIGRA_L_v1.0.md와 완전 동일(총계까지 일치). **정정(2026-07-18)**: mechanical_safety Safe_Limit 결합형 불릿 오카운트(5개 행을 1건으로 카운트) 정정 — 미확인 33건→37건, 총계 41건→45건.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — TIGRA-L과 동시 투입, TIGRA_L_v1.0.md를 스켈레톤으로 사용(형제 파일). 베리언트 종속 3개 Key(Max_SPL_Peak=145dB, AES75_Max_Linear_SPL=121dBZ/139.5dBZpk@+3dBV, Nominal_Directivity_Horizontal_deg=110°)만 TIGRA-W 자신의 원문값으로 대입, 나머지 전 섹션은 TIGRA-L과 완전 동일(원본 자체가 이 3개 값 외에는 베리언트를 구분하지 않음). LEOPARD/LINA 파싱 이후 발견된 신규 Key 9종도 미커밋 상태였던 이 v1.0에 통합 반영(전부 미확인). Null Report 41건(미확인 33건+비적용 8건), TIGRA-L과 총계까지 일치. **후속 정정(같은 v1.0, 2026-07-18)**: mechanical_safety Safe_Limit 결합형 불릿 오카운트 정정, Null Report 45건(미확인 37건+비적용 8건)으로 재계산(TIGRA-L과 동일). |
| v1.0 to v1.1 | (양방향 동기화, Minor) Meyer Sound 신규 제품 2100-LFC 파싱 과정에서 신설된 Key `Analog_Input_Pinout_Case`를 실값("Earth (AC) ground and chassis")으로 반영 — TIGRA 자신의 OM p.24 원본 재확인 결과 확인(TIGRA-L과 동일). Null Report 총계는 영향 없음. |
| v1.1 to v1.2 | speakers 카테고리 전체 일괄 동기화 라운드(2026-07-18, d&b 대량 배치 완료 후) — 신규 Key `Frequency_Response_4dB_Hz`(미확인), `Peak_Power_Handling_10ms_Overall`(비적용), `Remote_Mute_Control`(750-LFC/900-LFC 유래, 미확인) 반영. Null Report 48건(미확인 39건+비적용 9건)으로 갱신. |
