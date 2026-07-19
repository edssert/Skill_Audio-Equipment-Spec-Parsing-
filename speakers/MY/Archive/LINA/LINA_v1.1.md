# LINA (Meyer Sound) — Master Schema

**Category**: speakers | **Brand**: Meyer Sound (MY) | **Schema Phase**: Phase 4 (Meyer Sound 4번째 제품군 투입, PANTHER/TIGRA/LEOPARD 대비)

**스켈레톤 근거**: `speakers/MY/LEOPARD_v1.0.md`를 뼈대로 사용 — self-powered line array 아키텍처, Meyer 자체 Linear Peak SPL 지표(AES75 미사용), 전류 기반 소비전력 스펙, XLR 커넥터(TOP 아님)+옵션 Weather Protection(IPX4)까지 LEOPARD와 거의 동일한 패턴을 공유한다. LEOPARD와 마찬가지로 Datasheet(SPS) 문서 자체에 "Architectural Specifications" 섹션이 포함되어 있어 별도 AE 파일이 없다.

**LINA는 지향각 베리언트 없는 단일 모델(분리 불필요)**: PANTHER/TIGRA/LEOPARD와 달리 LINA는 SPS/OM 어디에도 복수 모델명이 없다 — SPS Architectural Specifications 절 말미 "The loudspeaker shall be the Meyer Sound LINA."로 단일 제품임이 명시적으로 확인된다. 따라서 파일 분리 판단 자체가 불필요.

**아키텍처 판단(원본 근거)**: SPS "The loudspeaker shall be a compact, self-powered, linear, low-distortion, line array loudspeaker"로 명시. 앰프는 "a 3-channel, class D amplifier"(LEOPARD의 "open-loop" 수식어는 LINA 원문에 없음, 임의로 추가하지 않음) — 드라이버 3발(LF 2발+HF 1발)에 채널 3개로 1:1 대응. Passive_Crossover_Network는 SPS/OM 2개 문서 전체에서 "crossover" 키워드 전량 스캔 결과 0건으로 확정적 비존재(No) 판정. Cardioid_Capability도 동일 스캔 방식으로 0건 확인, No.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | LINA | - |
| Model_Number | null | - |
| Product_Series | null | - |
| Product_Category | Line Array | - |
| Product_Type | Compact line array loudspeaker | - |
| Description | compact, self-powered, linear, low-distortion line array loudspeaker, 2-way, 100° horizontal coverage | - |
| Way_Count | 2 | - |
| Onboard_Amplification | Yes | - |
| Compliance_Standards | null | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS(Datasheet, "Architectural Specifications" 절 포함) p.1, p.11-12; OM(Operating Instructions) p.1-2.
**Product_Type="Compact line array loudspeaker"**: SPS 원문 "The loudspeaker shall be a compact, self-powered, linear, low-distortion, line array loudspeaker"에서 LEOPARD와 동일하게 "compact" 채택.
**Way_Count**: LF 2발(6.5인치)+HF 1발(3인치) 2-way 구조 — SPS TRANSDUCERS 표에서 확인.
**Compliance_Standards/WEEE_Marking**: SPS/OM 2개 문서 전량 스캔 결과 인증 마크나 WEEE 문구 없음(LEOPARD/TIGRA와 동일 사유) — 미확인.
**Model_Number/Product_Series**: 2개 문서 전량 스캔 결과 파트넘버나 시리즈 소속 표현 없음. SPS 본문 "LINA evolved from the highly successful MINA™ loudspeaker"라는 계보 서술은 있으나 이는 "series" 소속이 아닌 이전 세대 제품과의 관계 서술로 판단해 Product_Series에 채택하지 않음.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [1] | 65 - 18000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak [2] | 138 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Linear_Peak_SPL [3] | 132 dB with 19 dB crest factor (M-noise), 128 dB (Pink noise), 130 dB (B-noise) | - |
| Nominal_Directivity_Horizontal_deg | 100 | deg |
| Nominal_Directivity_Vertical | Varies, depending on array length and configuration | - |
| Phase_Response | 100 - 18000 Hz ±45° | - |
| THD_IM_TIM | < 0.02% | - |
| Cardioid_Capability | No | - |
| DSP_Preset_Name | null | - |
| Cardioid_Pattern_Array_Min_Size | null | count |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS "Specifications" 표(ACOUSTICAL/COVERAGE/AMPLIFIER) p.7-9; SPS "Architectural Specifications" 절 p.11-12.
**[1] Usable_Bandwidth_Hz — 측정 조건**: SPS 각주 2 "Recommended maximum operating frequency range. Response depends on loading conditions and room acoustics." — LEOPARD와 동일한 조건부 서술.
**[2] Max_SPL_Peak**: SPS 각주 3 "Maximum SPL is the peak measured in free-field at 4 m referred to 1 m using noise" — TIGRA/LEOPARD와 동일 측정법.
**[3] Linear_Peak_SPL**: SPS 각주 4 "Linear Peak SPL is measured in free-field at 4 m referred to 1 m. Loudspeaker SPL compression measured with M-noise at the onset of limiting, 2-hour duration, and 50°C ambient temperature is <2 dB." — LEOPARD와 측정 조건 서술이 미세하게 다름(LEOPARD는 "measured 1 m on axis with typical boundary loading", LINA는 "measured in free-field at 4 m referred to 1 m") — 임의로 통일하지 않고 LINA 자신의 원문 그대로 채택. M-noise/Pink noise/B-noise 정의는 LEOPARD와 완전 동일 문구(Meyer 브랜드 공통 정의로 판단).
**Phase_Response**: SPS "100 Hz – 18 kHz ±45 degrees" — LEOPARD(92-18000Hz ±30°)와 범위·허용오차 모두 다름, 원문 그대로 채택.
**Cardioid_Capability=No**: SPS/OM 2개 문서 전량 "cardioid" 키워드 스캔 결과 0건 — 확정적 비존재.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 2 x 6.5" long-excursion cone drivers | - |
| HF_Transducer | 1 x 3" diaphragm compression driver coupled to a constant-directivity horn through a patented REM manifold | - |
| LF_Acoustical_Load | null | - |
| HF_Acoustical_Load | constant-directivity horn (REM manifold) | - |
| Passive_Crossover_Network | No | - |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | null | W |
| LF_Nominal_Impedance | 4 | Ohm |
| Nominal_Impedance_Overall | null | Ohm |
| HF_Nominal_Impedance | 8 | Ohm |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS TRANSDUCERS 표 p.7-8("Two 6.5-inch long-excursion cone drivers; 4 Ω nominal impedance", "One 3-inch diaphragm compression driver coupled to a constant-directivity horn through a patented REM® manifold; 8 Ω nominal impedance").
**LF/HF_Nominal_Impedance**: LEOPARD(2Ω/4Ω)보다 높은 임피던스(4Ω/8Ω) — 더 작은 드라이버(6.5인치 vs 9인치)와 정합, 원문 그대로 채택.
**Passive_Crossover_Network=No**: SPS/OM 2개 문서 전체에서 "crossover" 키워드 전량 스캔 결과 0건 — 확정적 비존재.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Connector [1] | XLR 3-pin female input with male loop output; optional XLR 5-pin connector (balanced audio + RMS) | - |
| Analog_Loop_Output_Connector | XLR 3-pin male (integrated loop output) | - |
| Analog_Input_Impedance | 10000 | Ohm |
| Analog_Nominal_Input_Level | 0 dBV (1.0 V rms) continuous, typical onset of limiting | - |
| Analog_Input_Pinout_Pin1 | Chassis/earth through 1 kOhm, 1000 pF, 15V clamp network (virtual ground lift at audio frequencies) | - |
| Analog_Input_Pinout_Pin2 | Signal (+) | - |
| Analog_Input_Pinout_Pin3 | Signal (-) | - |
| Analog_Input_Pinout_Pin4 | RMS | - |
| Analog_Input_Pinout_Pin5 | RMS | - |
| Analog_Input_Pinout_Case [2] | null | - |
| Analog_Source_Drive_Requirement | +20 dBV (10 V rms) into 600 Ohm (for maximum peak SPL) | - |
| Digital_Input_Connector | null | - |
| Digital_Input_Format | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS AUDIO INPUT 표 p.8-9; 각주 5("Pins 4 and 5 (RMS) only included with XLR 5-pin connector that accommodates both balanced audio and RMS signals").
**[1] Analog_Input_Connector — LEOPARD와 기본/옵션 관계가 반대**: LEOPARD는 XLR 5-pin이 기본이고 3-pin이 대안이었으나, LINA는 **XLR 3-pin이 기본**이고 5-pin이 옵션("Optional XLR 5-pin connector to accommodate both balanced audio and RMS signals") — 임의로 LEOPARD와 동일하다고 가정하지 않고 LINA 자신의 원문 순서 그대로 채택.
**Analog_Nominal_Input_Level="0 dBV"**: LEOPARD(6.0 dBV)와 다름, PANTHER(0 dBV)와 동일값이나 우연의 일치로 판단(각 제품 자신의 원문에서 독립 확인).
**Digital_Input_Connector/Format=null**: LEOPARD와 동일 사유 — Milan AVB나 디지털 오디오 입력 언급 없음.
**[2] Analog_Input_Pinout_Case(신규 Key, v1.1)**: 2100-LFC 파싱 과정에서 신설된 신규 Key — LINA SPS AUDIO INPUT 표에도 Case 접지 서술이 없어 미확인(LEOPARD와 동일 사유, 상세는 LEOPARD_v1.1.md 참조).

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
| Amplifier_Total_Output_Power | 1950 | W |
| Idle_Current | 0.25 A rms (115 V AC); 0.25 A rms (230 V AC); 0.29 A rms (100 V AC) | - |
| Max_Long_Term_Continuous_Current | 2.3 A rms (115 V AC); 1.16 A rms (230 V AC); 2.8 A rms (100 V AC) | - |
| Burst_Current | 3.9 A rms (115 V AC); 1.7 A rms (230 V AC); 4.5 A rms (100 V AC) | - |
| Max_Instantaneous_Peak_Current | 8.8 A peak (115 V AC); 4.0 A peak (230 V AC); 9.2 A peak (100 V AC) | - |
| Inrush_Current | < 20.0 | A peak |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS AC POWER/CURRENT DRAW 표 p.9-10; SPS Architectural Specifications 절 p.11-12.
**Amplifier_Total_Output_Power=1950W**: LEOPARD(3900W)의 정확히 절반 — 더 작은 드라이버/캐비닛 규모와 정합, SPS 각주 6("Peak power based on the maximum unclipped peak voltage the amplifier will produce into the nominal load impedance")도 LEOPARD와 동일 문구.
**전류(Amp) 기반 소비전력 5종**: LEOPARD와 동일 개념·단위 체계(115/230/100V AC 3조건 병기), 수치는 LINA 자신의 원문값.

## protection_thermal

self-powered 아키텍처 전용 섹션(PANTHER/TIGRA/LEOPARD 전례 준용).

| Key | Value | Unit |
|---|---|---|
| Limiter_Type | null | - |
| Limiter_Indication [1] | Active/Status LED: solid green=normal, flashing red=hardware fault or overheating (audio may continue with reduced limiter threshold); separate HF/LF Limit LEDs: unlit=normal, lit ≤2 sec(off ≥1 sec)=OK, lit >3 sec=hard limiting | - |
| Cooling_Type | Convection | - |
| IP_Rating [2] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.947-951("Active/Status LED"), p.876-914("HF and LF Limit LEDs"). SPS AMPLIFIER 표 "Cooling: Convection".
**[1] Limiter_Indication**: LEOPARD와 완전 동일 구조(Active/Status LED + 별도 HF/LF Limit LED), 리미터 방식 고유 명칭은 LINA도 2개 문서 전량 스캔 결과 찾지 못함(Limiter_Type 미확인).
**[2] IP_Rating=null**: LEOPARD와 동일한 구조적 이유 — 기본 구성이 표준 XLR 커넥터(TOP 아님)이며, OM에 별도 "Weather Protection" 옵션(IPX4 목표치, "Meyer Sound designs toward an IP rating of IPX4... for Standard Weather")을 장착해야만 IP 등급이 성립 — 기본 구성 자체는 IP 등급이 없어 null 유지.

## network_monitoring

네트워크/원격 모니터링 관련 섹션(PANTHER/TIGRA/LEOPARD 전례 준용).

| Key | Value | Unit |
|---|---|---|
| Network_Protocol | null | - |
| Telemetry_Software | null | - |
| Telemetry_Transport [1] | two-conductor, twisted-pair network (optional RMS module) | - |
| Device_Identification_Function | null | - |
| Network_Connectivity_LED | null | - |
| AES67_Support | null | - |
| Service_Port_Type | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS "RMS NETWORK (OPTIONAL)" 표 p.10("Equipped with two-conductor twisted-pair network, reporting all operating parameters of amplifiers to system operator's host computer").
**[1] Telemetry_Transport — LEOPARD와 달리 옵션 취급**: LEOPARD는 SPS 섹션 제목이 "RMS NETWORK"(옵션 여부 불명시)였으나, LINA는 명시적으로 "RMS NETWORK (OPTIONAL)"로 표기 — 기본 구성에는 RMS 네트워크 모듈이 없고 옵션 장착 시에만 성립함을 원문이 직접 밝힘(AE 절도 "The loudspeaker shall accommodate an optional RMS remote monitoring system module"). Telemetry_Software는 LEOPARD의 "Compass RMS" 같은 소프트웨어명이 LINA 문서에 없어 미확인(LEOPARD와 임의로 통일하지 않음).

## amplification_requirements

self-powered이므로 외부 앰프 매칭 개념이 원천적으로 비적용.

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | null | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (2-way, 3 discrete driver channels via internal 3-channel Class-D amplifier) | - |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: LINA는 자체 앰프를 내장한 self-powered 제품이라 외부 앰프와 매칭할 필요가 없다.
**Crossover_Type**: SPS AMPLIFIER 표 "Type: 3-channel, Class-D"(LEOPARD의 "open-loop" 수식어가 LINA 원문에는 없음 — 임의로 추가하지 않고 원문 그대로 채택) — 드라이버 3발에 앰프 채널 3개로 1:1 대응.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | end frames with captive GuideALinks secured with quick-release pins (QRP); QuickFly rigging system | - |
| Inter_Enclosure_Angles_deg [1] | 1 - 11 | deg |
| Handles | null | - |
| Weight_Net | 19.5 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS PHYSICAL 표 p.10("Rigging: End frames with captive GuideALinks secured with 0.25 in x 0.53 in quick release pins that allow 0° to 11° splay angles. M6 attachment points for optional MYA-MINA/LINA mounting yoke and MUB-MINA/LINA U-bracket").
**[1] Inter_Enclosure_Angles_deg**: SPS 본문("splay angles from 1 to 11 degrees")과 PHYSICAL 표("0° to 11° splay angles") 간 하한이 다름(1° vs 0°) — 소스 간 충돌로 판단, 더 상세한 스펙 표(PHYSICAL) 값을 채택하고 본문 서술 차이는 각주로 보존.
**Handles**: PANTHER/TIGRA/LEOPARD는 모두 "detachable side handles" 서술이 있었으나, LINA는 2개 문서 전량 스캔 결과 핸들 관련 서술을 찾지 못함(M6 마운팅 포인트만 명시) — 미확인.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 515 | mm |
| Height_mm | 213 | mm |
| Depth_mm | 389 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | premium multi-ply birch | - |
| Front_Material | powder-coated, hex-stamped steel with acoustical black mesh | - |
| Rigging_Components_Material | null | - |
| Finish_Color | slightly textured black | - |
| Finish_Type | null | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS PHYSICAL 표 "Dimensions: W: 20.27 in (515 mm) x H: 8.38 in (213 mm) x D: 15.32 in (389 mm)"; SPS Architectural Specifications 절 "Dimensions shall be W: 20.27 in (515 mm) x H: 8.38 in (213 mm) x D: 15.32 in (389 mm)" — 두 서술 완전 일치(같은 문서 내 교차검증), W/H/D 축 명시적 라벨링으로 축 불확실성 없이 확정(TODO.md 치수 감사 기준 (1) 충족).
**Dimensions_Raw**: 축이 명확히 확인되어 상위 호환 Key로 대체 — null.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: PANTHER/TIGRA/LEOPARD와 동일 — Meyer Sound MAPP System Design Tool로 시뮬레이션하는 방식, 소프트웨어 결과물 미제공.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: preset_guide_and_matching과 동일.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown, LINA/750-LFC 혼합 어레이 가능 | MG-MINA/LINA/750-LFC Multipurpose Grid Kit | null | 16 |
| 전면/발코니 하부 마운트(20° 틸트) | MUB-MINA/LINA U-Bracket | null | 4 |
| 단일 포인트 서스펜션 | MYA-MINA/LINA Yoke | null | 4 |
| 이동/보관(비행 구성 아님) | MCF-MINA/LINA Caster Frame | null | 5 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 5:1 | - |
| Max_Wind_Load | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Table 4 "LINA Rigging Options" p.22-23(MG-MINA/LINA/750-LFC); SPS Accessories 절 p.3-6(MUB-MINA/LINA U-Bracket, PBF-LINA Pull Back Frame, MYA-MINA/LINA Yoke, MCF-MINA/LINA Caster Frame, MVP motor Vee plate).
**MG-MINA/LINA/750-LFC Multipurpose Grid Kit**: "With some restrictions, flies up to 16 LINA cabinets at a 5:1 safety factor and BGV C1 with some angle restrictions" — LEOPARD의 MG-LEOPARD/900(23대)보다 적은 최대 대수(LINA가 더 작은 제품이라는 점과 정합).
**MUB-MINA/LINA U-Bracket**: "Mounts up to four LINA cabinets for front-fill or under-balcony coverage with up to 20 degrees of tilt. Pole-mounts up to two cabinets" — PANTHER/TIGRA/LEOPARD에는 없던 신규 액세서리 유형(전면채움/발코니용 U자형 브래킷).
**MYA-MINA/LINA Yoke**: "Suspends arrays of up to four LINA cabinets from a single point" — 이 역시 PANTHER/TIGRA/LEOPARD에 없던 단일 포인트 서스펜션 방식.
**MCF-MINA/LINA Caster Frame**: "Safely transports up to five fully rigged LINA cabinets" — LEOPARD(4대)보다 1대 많음(LINA가 더 가볍고 작아 카트 1대당 더 많이 실을 수 있는 것으로 추정되나 이는 추정, 원문 수치만 채택).
**PBF-LINA Pull Back Frame**: SPS에 구체적 최대 대수가 명시되지 않아("Attaches to the bottom cabinet of LINA and 750-LFC arrays and provides pull-back for extreme array downtilt") 표에 포함하지 않음 — 각주로만 존재 기록.
**Safe_Limit 열 null 사유**: PANTHER/TIGRA/LEOPARD와 동일 — MAPP 소프트웨어가 개별 배치 검증을 대신하는 방식.
**Max_Wind_Load(미확인)**: 2개 문서 전량 스캔 결과 구체적 수치 없음.

## Null Report

**미확인(정보 부족)**: Model_Number, Product_Series, Compliance_Standards, WEEE_Marking, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, Frequency_Response_5dB_Hz, DSP_Preset_Name, Cardioid_Pattern_Array_Min_Size, LF_Acoustical_Load, RMS_Power_Handling_LF, RMS_Power_Handling_HF, Analog_Input_Pinout_Case, Digital_Input_Connector, Digital_Input_Format, Max_Long_Term_Continuous_Power, Burst_Power, Idle_Power, Max_Cable_Round_Trip_Resistance, AC_Inlet_Pinout, Limiter_Type, IP_Rating(protection_thermal), Network_Protocol, Telemetry_Software, Device_Identification_Function, Network_Connectivity_LED, AES67_Support, Service_Port_Type, Handles, Rigging_Components_Material, Finish_Type, Max_Wind_Load, preset_guide_and_matching(전 항목), delay_defaults(전 항목), mechanical_safety(Safe_Limit 열 — 4개 Configuration 행의 null 셀, 4건) — 35건.
**비적용(LINA 아키텍처상 개념 자체 불성립)**: Compatible_Amplified_Controller, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Dimensions_Raw, IP_Rating(physical 섹션), Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module, AES75_Max_Linear_SPL — 9건.

**총계**: null 44건 (미확인 35건 + 비적용 9건). 확정적 비존재(0/No)로 명시한 항목은 2건 — Passive_Crossover_Network, Cardioid_Capability(둘 다 2개 문서 전량 스캔 근거). **정정(2026-07-18, 각주 버전 참조 최신성 감사에서 발견)**: mechanical_safety의 Safe_Limit 미확인이 결합형 불릿으로 서술되며 실제 4개 Configuration 행 각각의 null 셀인데도 1건으로만 카운트되어 있던 것을 발견·정정(speakers/LA K1_v1.11.md 등과 동일 유형) — 미확인 31건→34건, 총계 40건→43건. 데이터(Key/Value/Unit) 자체는 전혀 변경하지 않았다. **v1.1 신규 Key 반영**: `Analog_Input_Pinout_Case` 신설·null 동기화 — 미확인 34건→35건, 총계 43건→44건.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — Meyer Sound 4번째 제품군(LINA) 최초 투입, LEOPARD_v1.0.md를 스켈레톤으로 사용. `upload/` 폴더 제공 Datasheet(SPS, Architectural Specifications 절 포함)+Operating Instructions(OM) 2개 문서 통합(AE 별도 파일 없음). PANTHER/TIGRA/LEOPARD와 달리 지향각 베리언트가 없는 단일 모델임을 원문("The loudspeaker shall be the Meyer Sound LINA")으로 확인해 파일 분리 판단 자체가 불필요. LEOPARD 대비 세부 차이 다수 확인: Analog_Input_Connector 기본/옵션 관계 반대(LINA는 3-pin 기본, LEOPARD는 5-pin 기본), RMS Network가 명시적으로 "OPTIONAL", Inter_Enclosure_Angles_deg 소스 간 충돌(본문 1-11° vs 표 0-11°), MUB-MINA/LINA U-Bracket/MYA-MINA/LINA Yoke 등 LEOPARD에 없던 신규 액세서리 유형. Null Report 40건(미확인 31건+비적용 9건). **후속 정정(같은 v1.0, 2026-07-18)**: mechanical_safety Safe_Limit 결합형 불릿 오카운트 정정, Null Report 43건(미확인 34건+비적용 9건)으로 재계산. |
| v1.0 to v1.1 | (양방향 동기화, Minor) Meyer Sound 신규 제품 2100-LFC 파싱 과정에서 신설된 Key `Analog_Input_Pinout_Case`를 null로 동기화(LEOPARD와 동일 사유 — SPS 표에 Case 접지 서술 없음). Null Report 미확인 34건→35건, 총계 43건→44건. |
