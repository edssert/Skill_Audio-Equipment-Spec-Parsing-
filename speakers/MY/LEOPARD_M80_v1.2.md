# LEOPARD-M80 (Meyer Sound) — Master Schema

**Category**: speakers | **Brand**: Meyer Sound (MY) | **Schema Phase**: Phase 4 (Meyer Sound 3번째 제품군 투입, PANTHER/TIGRA 대비)

**스켈레톤 근거**: `speakers/MY/LEOPARD_v1.0.md`(LEOPARD, 형제 파일)와 동일 원본 문서(SPS, "Architectural Specifications" 절 포함+OM)에서 독립 확인. **베리언트 간 차이는 Nominal_Directivity_Horizontal_deg(80° vs 110°)와 Linear_Peak_SPL(M-noise/Pink noise/B-noise 3종 수치+크레스트팩터)뿐** — Max_SPL_Peak(142dB)과 Phase_Response(92-18000Hz ±30°)는 LEOPARD와 완전 동일값(원문이 이렇게 명시, PANTHER/TIGRA와 다른 점 — 상세는 LEOPARD_v1.0.md 각주 [1] 참조). 나머지 전 섹션(트랜스듀서/커넥터/전원/보호회로/네트워크/앰프요구사항/리깅/치수/기계안전)도 LEOPARD와 완전 동일값이다.

**아키텍처 판단(원본 근거)**: LEOPARD_v1.0.md와 동일 — self-powered, 3채널 open-loop Class-D 앰프(드라이버 3발과 1:1 대응), Passive_Crossover_Network=No(2개 문서 전량 "crossover" 키워드 0건), Cardioid_Capability=No(2개 문서 전량 "cardioid" 키워드 0건).

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | LEOPARD-M80 | - |
| Model_Number | null | - |
| Product_Series | null | - |
| Product_Category | Line Array | - |
| Product_Type | Compact line array loudspeaker | - |
| Description | compact, self-powered, linear, low-distortion line array loudspeaker, 2-way, 80° horizontal coverage | - |
| Way_Count | 2 | - |
| Onboard_Amplification | Yes | - |
| Compliance_Standards | null | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처 및 상세 근거**: LEOPARD_v1.0.md의 general 섹션과 동일 문구 공유 — SPS 말미 "The narrow (80° coverage) compact linear line array loudspeaker shall be the Meyer Sound LEOPARD-M80." 원문에서 Description/Product_Type 근거 확보. SPS 자체 표제("Datasheet — LEOPARD / LEOPARD-M80")와 Features 절("Available in two models... LEOPARD-M80 for narrow controlled array coverage")도 M80을 명시적으로 별도 모델로 취급.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [5] | 55 - 18000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Frequency_Response_4dB_Hz | null | Hz |
| Max_SPL_Peak [1] | 142 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Linear_Peak_SPL [2] | 135 dB with 19 dB crest factor (M-noise), 132 dB (Pink noise), 136.5 dB (B-noise) | - |
| Nominal_Directivity_Horizontal_deg | 80 | deg |
| Nominal_Directivity_Vertical | Varies, depending on array length and configuration | - |
| Phase_Response | 92 - 18000 Hz ±30° | - |
| THD_IM_TIM | < 0.02% | - |
| Cardioid_Capability | No | - |
| DSP_Preset_Name | null | - |
| Cardioid_Pattern_Array_Min_Size | null | count |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS "Specifications" 표(ACOUSTICAL/COVERAGE/AMPLIFIERS, LEOPARD-M80 열) p.7-9; SPS "Architectural Specifications" 절 p.11-12. 상세 근거는 LEOPARD_v1.0.md와 동일(측정조건/Linear_Peak_SPL 병기 원칙/Usable_Bandwidth_Hz 조건부 서술 등) — [1][2][5] 각주 내용도 동일 문구 공유, LEOPARD-M80 자신의 수치(135dB/132dB/136.5dB, 80°)만 대입.
**[2] Linear_Peak_SPL(LEOPARD-M80 고유값)**: SPS "linear peak SPL for the LEOPARD-M80 shall be 135 dB with 19 dB crest factor" — LEOPARD(133.5dB/18dB)보다 높은 크레스트팩터·SPL, 좁은 지향각(80°)이 에너지를 더 집중시키는 결과로 추정되나 이는 추정일 뿐 원문이 이 인과관계를 직접 서술하지는 않음(추정 자체를 Value에 반영하지 않음).
**Frequency_Response_4dB_Hz(신규 Key)**: 750-LFC에서 신설된 범용 Key(-4dB 기준 대역폭) — 이 제품 자신의 원본에서 아직 재확인되지 않아 미확인 유지.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 2 x 9" long-excursion cone drivers | - |
| HF_Transducer | 1 x 3" diaphragm compression driver coupled to a constant-directivity horn through a patented REM manifold | - |
| LF_Acoustical_Load | null | - |
| HF_Acoustical_Load | constant-directivity horn (REM manifold) | - |
| Passive_Crossover_Network | No | - |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | null | W |
| Peak_Power_Handling_10ms_Overall | null | W |
| LF_Nominal_Impedance | 2 | Ohm |
| Nominal_Impedance_Overall | null | Ohm |
| HF_Nominal_Impedance | 4 | Ohm |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일** — 드라이버 구성은 두 베리언트 공통(수평 커버리지는 HF 혼 형상 차이로만 결정).
**Peak_Power_Handling_10ms_Overall(신규 Key)**: d&b CCL8에서 신설된 범용 Key — RMS_Power_Handling_Overall과 동일 사유(self-powered 구조상 드라이버 자신의 파워 핸들링이 아니라 Amplifier_Total_Output_Power로 보고)로 비적용.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Connector | XLR 5-pin female input with male loop output; XLR 3-pin female connectors available (balanced audio only, no RMS) | - |
| Analog_Loop_Output_Connector | XLR 5-pin male (integrated loop output) | - |
| Analog_Input_Impedance | 10000 | Ohm |
| Analog_Nominal_Input_Level | 6.0 dBV (2.0 V rms) continuous, typical onset of limiting | - |
| Analog_Input_Pinout_Pin1 | Chassis/earth through 1 kOhm, 1000 pF, 15V clamped network (virtual ground lift at audio frequencies) | - |
| Analog_Input_Pinout_Pin2 | Signal (+) | - |
| Analog_Input_Pinout_Pin3 | Signal (-) | - |
| Analog_Input_Pinout_Pin4 | RMS (polarity insensitive) | - |
| Analog_Input_Pinout_Pin5 | RMS (polarity insensitive) | - |
| Analog_Input_Pinout_Case [1] | null | - |
| Analog_Source_Drive_Requirement | +20 dBV (10 V rms) into 600 Ohm (for maximum peak SPL) | - |
| Digital_Input_Connector | null | - |
| Digital_Input_Format | null | - |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.1.md와 완전 동일** — 커넥터 사양은 두 베리언트 공통.
**[1] Analog_Input_Pinout_Case(신규 Key, v1.1)**: 2100-LFC 파싱 과정에서 신설된 신규 Key — LEOPARD와 동일 사유로 미확인(상세는 LEOPARD_v1.1.md 참조).

## power_supply

self-powered 아키텍처 전용 섹션(PANTHER/TIGRA/LEOPARD 전례 준용).

| Key | Value | Unit |
|---|---|---|
| AC_Connector | powerCON 20 (input with loop output) | - |
| AC_Nominal_Voltage_Range | 100, 110, or 230 | V AC |
| AC_Operating_Voltage_Range | 90 - 265 | V AC |
| AC_Frequency_Range | 50 - 60 | Hz |
| Max_Long_Term_Continuous_Power | null | W |
| Burst_Power | null | W |
| Idle_Power | null | W |
| Max_Cable_Round_Trip_Resistance | null | Ohm |
| AC_Inlet_Pinout | null | - |
| Power_Supply_Protection_Features | EMI filtering, soft current turn-on, surge suppression | - |
| Amplifier_Total_Output_Power | 3900 | W |
| Idle_Current | 0.46 A rms (115 V AC); 0.35 A rms (230 V AC); 0.49 A rms (100 V AC) | - |
| Max_Long_Term_Continuous_Current | 3.0 A rms (115 V AC); 1.5 A rms (230 V AC); 3.4 A rms (100 V AC) | - |
| Burst_Current | 4.4 A rms (115 V AC); 2.3 A rms (230 V AC); 5.5 A rms (100 V AC) | - |
| Max_Instantaneous_Peak_Current | 12.6 A peak (115 V AC); 6.3 A peak (230 V AC); 14.5 A peak (100 V AC) | - |
| Inrush_Current | < 20 | A peak |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일** — 전원부/앰프 출력/전류 스펙은 두 베리언트 공통(HF 혼 형상만 다르고 앰프/전원 모듈은 동일).

## protection_thermal

self-powered 아키텍처 전용 섹션(PANTHER/TIGRA/LEOPARD 전례 준용).

| Key | Value | Unit |
|---|---|---|
| Limiter_Type | null | - |
| Limiter_Indication | Active/Status LED: solid green=normal, flashing red=hardware fault or overheating (audio may continue with reduced limiter threshold); separate HF/LF Limit LEDs: unlit=normal, lit ≤2 sec(off ≥1 sec)=OK, lit >3 sec=hard limiting | - |
| Cooling_Type | Convection | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일** — IP_Rating=null(기본 구성에 TOP 커넥터 없음, Weather Protection 옵션 장착 시에만 IPX4) 포함 동일 근거.

## network_monitoring

네트워크/원격 모니터링 관련 섹션(PANTHER/TIGRA/LEOPARD 전례 준용).

| Key | Value | Unit |
|---|---|---|
| Network_Protocol | null | - |
| Telemetry_Software | Compass RMS (RMS™ remote monitoring system) | - |
| Telemetry_Transport | two-conductor, twisted-pair RMS network | - |
| Device_Identification_Function | null | - |
| Network_Connectivity_LED | null | - |
| AES67_Support | null | - |
| Service_Port_Type | null | - |
| Remote_Mute_Control | null | - |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일**.
**Remote_Mute_Control(신규 Key)**: 750-LFC/900-LFC에서 신설된 범용 Key(네트워크를 통한 원격 뮤트 활성화/비활성화 기능) — 이 제품 자신의 원본에서 아직 재확인되지 않아 미확인 유지.

## amplification_requirements

self-powered이므로 외부 앰프 매칭 개념이 원천적으로 비적용.

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | null | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (2-way, 3 discrete driver channels via internal 3-channel open-loop Class-D amplifier) | - |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일**.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | end frames with captive GuideALinks secured with quick-release pins (QRP); QuickFly rigging system | - |
| Inter_Enclosure_Angles_deg | 0.5 - 15 | deg |
| Handles | detachable side and rear handles | - |
| Weight_Net | 34.0 | kg |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일** — 리깅 시스템/중량은 두 베리언트 공통(캐비닛 외형 동일).

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 684 | mm |
| Height_mm | 282 | mm |
| Depth_mm | 550 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | premium multi-ply birch | - |
| Front_Material | powder-coated, hex-stamped steel with acoustical black mesh | - |
| Rigging_Components_Material | null | - |
| Finish_Color | slightly textured black | - |
| Finish_Type | null | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일** — 캐비닛 외형 치수는 두 베리언트 공통(HF 혼 내부 형상만 다름).

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일** — MAPP 소프트웨어 기반 시뮬레이션 방식, 소프트웨어 결과물 미제공으로 미확인.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일**.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown, LEOPARD/900-LFC 혼합 어레이 가능 | MG-LEOPARD/900 Multipurpose Grid | null | 23 |
| flown, LYON 어레이 하부 연결(다운필) | MTF-LYON/LEOPARD Transition Frame | null | 10 |
| 이동/보관(비행 구성 아님) | MCF-LEOPARD Caster Frame | null | 4 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 5:1 | - |
| Max_Wind_Load | null | - |

### 주석 및 출처 (Notes & Sources)

**LEOPARD_v1.0.md와 완전 동일** — 기계 안전 수치는 두 베리언트 공통(중량·캐비닛 동일, 리깅 액세서리가 모델명을 구분하지 않고 "LEOPARD"로 통칭).

## Null Report

**미확인(정보 부족)**: Model_Number, Product_Series, Compliance_Standards, WEEE_Marking, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, Frequency_Response_5dB_Hz, DSP_Preset_Name, Cardioid_Pattern_Array_Min_Size, LF_Acoustical_Load, RMS_Power_Handling_LF, RMS_Power_Handling_HF, Analog_Input_Pinout_Case, Digital_Input_Connector, Digital_Input_Format, Max_Long_Term_Continuous_Power, Burst_Power, Idle_Power, Max_Cable_Round_Trip_Resistance, AC_Inlet_Pinout, Limiter_Type, IP_Rating(protection_thermal), Network_Protocol, Device_Identification_Function, Network_Connectivity_LED, AES67_Support, Service_Port_Type, Rigging_Components_Material, Finish_Type, Max_Wind_Load, preset_guide_and_matching(전 항목), delay_defaults(전 항목), mechanical_safety(Safe_Limit 열 — 3개 Configuration 행의 null 셀, 3건), Frequency_Response_4dB_Hz, Remote_Mute_Control — 35건.
**비적용(LEOPARD-M80 아키텍처상 개념 자체 불성립)**: Compatible_Amplified_Controller, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Dimensions_Raw, IP_Rating(physical 섹션), Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module, AES75_Max_Linear_SPL, Peak_Power_Handling_10ms_Overall — 10건.

**총계**: null 45건 (미확인 35건 + 비적용 10건). 확정적 비존재(0/No)로 명시한 항목은 2건 — Passive_Crossover_Network, Cardioid_Capability. LEOPARD_v1.1.md와 완전 동일(총계까지 일치). **정정(2026-07-18)**: mechanical_safety Safe_Limit 결합형 불릿 오카운트(3개 행을 1건으로 카운트) 정정 — 미확인 30건→32건, 총계 39건→41건. **v1.1 신규 Key 반영**: `Analog_Input_Pinout_Case` 신설·null 동기화 — 미확인 32건→33건, 총계 41건→42건.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — LEOPARD와 동시 투입, LEOPARD_v1.0.md를 스켈레톤으로 사용(형제 파일). 베리언트 종속 2개 Key(Nominal_Directivity_Horizontal_deg=80°, Linear_Peak_SPL=135dB/19dB crest factor(M-noise), 132dB(Pink noise), 136.5dB(B-noise))만 LEOPARD-M80 자신의 원문값으로 대입, 나머지 전 섹션은 LEOPARD와 완전 동일(Max_SPL_Peak=142dB와 Phase_Response는 원문이 두 베리언트 공통값으로 명시 — PANTHER/TIGRA와 다른 점). Null Report 39건(미확인 30건+비적용 9건), LEOPARD와 총계까지 일치. **후속 정정(같은 v1.0, 2026-07-18)**: mechanical_safety Safe_Limit 결합형 불릿 오카운트 정정, Null Report 41건(미확인 32건+비적용 9건)으로 재계산(LEOPARD와 동일). |
| v1.0 to v1.1 | (양방향 동기화, Minor) Meyer Sound 신규 제품 2100-LFC 파싱 과정에서 신설된 Key `Analog_Input_Pinout_Case`를 null로 동기화(LEOPARD와 동일 사유). Null Report 미확인 32건→33건, 총계 41건→42건. |
| v1.1 to v1.2 | speakers 카테고리 전체 일괄 동기화 라운드(2026-07-18, d&b 대량 배치 완료 후) — 신규 Key `Frequency_Response_4dB_Hz`(미확인), `Peak_Power_Handling_10ms_Overall`(비적용), `Remote_Mute_Control`(750-LFC/900-LFC 유래, 미확인) 반영. Null Report 45건(미확인 35건+비적용 10건)으로 갱신. |
