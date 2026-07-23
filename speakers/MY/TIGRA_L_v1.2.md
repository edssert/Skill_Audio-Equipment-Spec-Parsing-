# TIGRA-L (Meyer Sound) — Master Schema

**Category**: speakers | **Brand**: Meyer Sound (MY) | **Schema Phase**: Phase 4 (Meyer Sound 2번째 제품군 투입, PANTHER 대비)

**스켈레톤 근거**: `speakers/MY/PANTHER_L_v1.0.md`를 뼈대로 사용 — TIGRA도 PANTHER와 동일하게 self-powered line array 아키텍처(내장 앰프, Neutrik TOP 커넥터, Milan AVB, Nebra 소프트웨어 제어)를 공유한다. 다만 앰프 채널 수(TIGRA 2채널 vs PANTHER 4채널), 드라이버 구성(TIGRA 2xLF+1xHF vs PANTHER 2xLF+2xHF), 냉각 방식(TIGRA 컨벡션 vs PANTHER 강제공랭 팬 2개), 카디오이드 최소 어레이 대수(TIGRA 6대 vs PANTHER 4대)가 서로 달라 해당 Key들은 TIGRA 자신의 원본에서 독립 확인했다.

**TIGRA-L/TIGRA-W 개별 파일 분리(사용자 확인 2026-07-18)**: PANTHER-L/M/W와 동일한 패턴 — 공식 문서(Datasheet/AE)가 파트넘버 구분 없이 수평 지향각(85°/110°)만 다른 2개 모델명(TIGRA-L/TIGRA-W)으로 병기한다. `speakers/CLAUDE.md`의 "제품 구성 판단" 절이 PANTHER 분리를 향후 유사 사례에 자동 일반화하지 말고 재확인하라고 명시하고 있어, 사용자에게 재확인한 결과 PANTHER와 동일하게 개별 파일 분리를 확정했다. **베리언트 간 차이는 Max_SPL_Peak/AES75_Max_Linear_SPL/Nominal_Directivity_Horizontal_deg 3개 Key뿐**이며 나머지 전 섹션(트랜스듀서/커넥터/전원/보호회로/네트워크/앰프요구사항/리깅/치수/기계안전)은 TIGRA-W와 완전 동일값이다(원본 자체가 이 3개 값 외에는 베리언트를 구분하지 않음).

**아키텍처 판단(원본 근거)**: TIGRA는 OM/AE 원문에 "The self-powered TIGRA™ linear array loudspeaker..."(OM p.1), "The loudspeaker shall be a self-powered, linear, low-distortion, line array loudspeaker"(AE)로 명시된다. 앰프는 AE "The loudspeaker shall incorporate internal processing and a 2-channel class-D amplifier"로 확정 — PANTHER(4채널, LF/HF 각 2발씩 개별 채널)와 달리 TIGRA는 드라이버 3발(LF 2발 + HF 1발)에 앰프 채널 2개뿐이라, LF 2발이 하나의 채널을 병렬 공유하고 HF 1발이 나머지 채널을 구동하는 구조로 추정된다(원문이 이 병렬 배선 자체를 명시하지는 않으나, 채널 수와 드라이버 수의 산술적 정합성에서 도출). Passive_Crossover_Network는 OM/SPS/AE 3개 문서 전체에서 "crossover" 키워드 전량 스캔 결과 0건으로 확정적 비존재(No) 판정.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | TIGRA-L | - |
| Model_Number | null | - |
| Product_Series | null | - |
| Product_Category | Line Array | - |
| Product_Type | Medium-format line array loudspeaker | - |
| Description | self-powered, linear, low-distortion line array loudspeaker, 2-way, 85° horizontal coverage | - |
| Way_Count | 2 | - |
| Onboard_Amplification | Yes | - |
| Compliance_Standards | null | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: AE(Architectural Specification) p.1-2; OM(Operating Instructions) p.1-2; SPS(Datasheet) p.1-4.
**Model_Number**: PANTHER와 동일하게 3개 문서 어디에도 공식 파트넘버 표기가 없어 미확인(문서 하단 "PN: 04.336.04.02 B 2606" 등은 문서 자체의 발간 관리번호이지 제품 파트넘버가 아님 — 혼동하지 않도록 채택하지 않음).
**Product_Type="Medium-format line array loudspeaker"**: AE 말미 "The 85° coverage medium-format line array loudspeaker shall be the Meyer Sound TIGRA-L." 원문에서 직접 채택 — PANTHER의 AE에는 이런 크기 등급(format) 서술이 없어 PANTHER_L 파일과 다른 근거로 확보했다.
**Way_Count**: SPS 각주 3 "The TIGRA 2-way loudspeaker has a unique placement of low-mid transducers and a computationally optimized high horn..." — 명시적으로 2-way.
**Compliance_Standards**: PANTHER는 SPS 이미지 내 인증 마크(c(UL)us, CE)로 확보했으나, TIGRA의 3개 문서(SPS/OM/AE) 전량을 텍스트+이미지 모두 스캔한 결과 이런 인증 마크나 문구를 찾지 못함 — 미확인. UL 60320-1(AC 인렛 관련, 커넥터 자체의 규격이지 제품 전체 인증이 아님)과 혼동하지 않도록 별도 처리.
**WEEE_Marking**: 3개 문서 전량 스캔 결과 EU WEEE 마킹 문구 없음 — 미확인(PANTHER와 동일 사유, 미국 제조사 문서 특성).
**Product_Series**: 3개 문서 전량을 "series" 키워드로 스캔했으나 TIGRA를 특정 시리즈에 소속시키는 표현 없음 — 미확인.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [5] | 55 - 16000 (dB 기준 미표기) | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Frequency_Response_4dB_Hz | null | Hz |
| Max_SPL_Peak [1] | 146 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL [2] | 122 dBZ / 140.5 dBZpk (input +4 dBV) | - |
| Linear_Peak_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 85 | deg |
| Nominal_Directivity_Vertical | null | - |
| Phase_Response | null | - |
| THD_IM_TIM | null | - |
| Cardioid_Capability [3] | Array-based, automatic (6대 이상 표준 배치에서 자동 발현, 반전 유닛·프리셋 불필요) | - |
| DSP_Preset_Name | null | - |
| Cardioid_Pattern_Array_Min_Size | 6 | count |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.1-2 "TIGRA specifications" 표(ACOUSTICAL, TIGRA-L 열); AE p.1 "Performance specifications for a typical production unit... measured at 1/3-octave resolution"; OM p.1.
**[1] Max_SPL_Peak 측정 조건**: SPS 각주 2 "The maximum sound level is the Lpeak measured using burst noise", AE는 "measured in free-field at 4 m referred to 1 m using noise"로 더 상세 — 두 문서 값 완전 일치(교차검증 성공).
**[2] AES75_Max_Linear_SPL(단일 통합 Key)**: AES75-2022 기준 dBZ/dBZpk/기준입력레벨(dBV) 3개 수치를 하나의 복합값 Key로 병기(PANTHER와 동일 원칙, "번들 원자화 금지"). TIGRA는 PANTHER와 달리 dBA 값이 원문에 없어(SPS/AE 모두 dBZ/dBZpk만 제공) 2개 수치만 병기.
**[3] Cardioid_Capability — PANTHER와 동일 4번째 유형이나 최소 대수 다름**: SPS 각주 3 "Arrays of six units and longer functionally create a cardioid polar pattern, which remains consistent at all SPL levels, including when pushed into limiting, and does not require any user settings." — PANTHER(4대 이상)와 원리는 동일(전용 카디오이드 드라이버군/반전 유닛/프리셋 불필요, 표준 배치 기하학적 설계만으로 자동 발현)하나 최소 성립 대수가 6대로 다르다 — 임의로 PANTHER 값(4)을 가져오지 않고 TIGRA 자신의 원문값(6)을 채택.
**DSP_Preset_Name**: PANTHER와 동일 사유 — Nebra 소프트웨어로 시스템 레벨 제어("Tru-Shaping filters"), 명명된 프리셋 개념 자체가 없어 미확인.
**Nominal_Directivity_Vertical**: 3개 문서 전량 스캔했으나 수직 지향각 수치나 서술 발견 못함 — 미확인.
**[5] Usable_Bandwidth_Hz — 측정 조건 부재(사용자 지적 2026-07-18)**: SPS "Operating frequency range: 55 Hz – 16 kHz"와 AE "For all models, the operating frequency range shall be 55 Hz – 16 kHz"는 값만 제시할 뿐 dB 기준점(예: -6dB, -10dB)이나 측정 조건(부하/음향 환경 등)을 전혀 명시하지 않는다 — LEOPARD의 SPS 각주 3("Recommended maximum operating frequency range. Response depends on loading conditions and room acoustics.")처럼 조건부 서술조차 없다. 값 자체(55-16000Hz)는 원문 그대로 채택하되, 근거 조건이 원문에 없다는 사실 자체를 명시적으로 남긴다(임의로 조건을 추정하거나 타 제품 관례를 대입하지 않음).
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

**출처**: SPS p.2-3 "TRANSDUCERS" 표(TIGRA-L/W 공통); AE p.1(드라이버 상세 서술).
**트랜스듀서 스펙 L/W 공통**: 드라이버 구성은 두 베리언트 모두 동일 — 수평 커버리지 각도는 HF 혼의 형상 차이로만 결정(원문이 드라이버 자체 스펙을 베리언트별로 구분하지 않음).
**Passive_Crossover_Network=No 판단 근거**: OM/AE/SPS 3개 문서 전체에서 "crossover" 키워드 전량 스캔 결과 0건 검출 — 확정적 비존재.
**LF/HF_Nominal_Impedance**: PANTHER는 SPS에 이 값이 있었으나(LF 4Ω/HF 8Ω), TIGRA의 3개 문서 전량 스캔 결과 드라이버별 임피던스 수치 자체가 없음 — 미확인(self-powered 제품 특성상 임피던스가 앰프-드라이버 내부 매칭값이라 공개하지 않는 것으로 추정되나 확정 근거 아님).
**LF_Acoustical_Load**: OM/AE/SPS 어디에도 LF 인클로저 로딩 방식(bass-reflex 등) 명시적 표기 없음 — 미확인.
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

**출처**: OM p.23-24(3-pin XLR wiring scheme, Pin 1/2/3), p.24-25(Calculating Loop Load Impedance); SPS p.3(ANALOG/DIGITAL AUDIO INPUT); AE p.1. 커넥터 사양은 TIGRA-L/W 공통.
**Analog_Input_Pinout**: OM 텍스트 레이어에 핀 번호별 배선이 명시되어 있어 텍스트 우선 스캔만으로 확보(PANTHER와 동일 배선 체계).
**Digital_Input_Connector="x2"**: SPS "Two Neutrik RJ45 etherCON TOP... airtight network inputs" — PANTHER의 단수 표기와 달리 TIGRA는 원문이 명시적으로 개수(2개)를 표기해 그대로 반영.
**Analog_Nominal_Input_Level**: PANTHER는 AE에 "nominal 0 dBV (1.0 V rms)" 수치가 있었으나(AE p.1), TIGRA의 AE는 이 항목 자체를 언급하지 않음(입력 임피던스 10kΩ만 명시) — 미확인.
**Input_Connector/Link_Connector/PA_COM_Pinout_*/NLT4_Pinout_* 미생성**: TIGRA 자신의 3개 원본 문서를 "PA-COM"/"NLT4"/"speakON" 키워드로 전량 스캔한 결과 0건 검출 — PANTHER와 동일하게 애초에 생성하지 않음.
**[1] Analog_Input_Pinout_Case(신규 Key, v1.1)**: OM p.24 "Case — earth (AC) ground and chassis" — 2100-LFC 파싱 과정에서 신설된 신규 Key를 TIGRA 자신의 원본에서 재확인해 실값 반영(2100-LFC_v1.0.md 참조).

## power_supply

self-powered 아키텍처 전용 섹션(PANTHER 전례 준용).

| Key | Value | Unit |
|---|---|---|
| AC_Connector | Neutrik powerCON TRUE1 Chassis Connector (NAC3PX-TRUE1) | - |
| AC_Nominal_Voltage_Range | 100 - 240 | V AC |
| AC_Operating_Voltage_Range [1] | 90 - 275 | V AC |
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

**출처**: SPS p.2 "AC POWER"/"POWER CONSUMPTION"; AE p.2; OM p.6-8(Electrical Service Requirements, Input Voltage Protection and Operating Behavior, Power Supply). 전원부는 TIGRA-L/W 공통.
**교차검증**: Max_Long_Term_Continuous_Power(550W)/Burst_Power(1270W)/AC_Nominal_Voltage_Range(100-240VAC)는 SPS·AE·OM 3개 문서 모두 일치.
**[1] AC_Operating_Voltage_Range**: OM "If the AC input voltage drops below approximately 90 V, the loudspeaker may continue operating briefly... AC input above approximately 275 V exceeds power-supply limits and may damage the loudspeaker." — PANTHER는 정격전압(200-240V) 대비 동작범위(160-264V)가 문서에 명시적 범위로 나와 있었으나, TIGRA는 "approximately 90V"/"approximately 275V"라는 근사치 서술만 있어 그대로 채택(근사치임을 각주로 명시).
**Max_Cable_Round_Trip_Resistance**: PANTHER는 OM에 이 수치(5Ω)가 있었으나, TIGRA의 OM 전량 스캔 결과 케이블 왕복 저항 관련 수치 서술을 찾지 못함 — 미확인.

## protection_thermal

self-powered 아키텍처 전용 섹션(PANTHER 전례 준용).

| Key | Value | Unit |
|---|---|---|
| Limiter_Type | TruPower limiting | - |
| Limiter_Indication [1] | On/Status LED: green=normal, red flash=clipping, yellow (≥1 sec)=RMS limiting active, red blinking=error | - |
| Cooling_Type [2] | convection (no fans) | - |
| IP_Rating [3] | 65 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: AE p.2("TruPower limiting"); OM p.19-20(On/Status LED, Limiting); OM p.25(Amplifier Cooling); OM p.6, p.14(IP65, UL50E — AC 인렛/오디오·네트워크 커넥터 공통).
**[1] Limiter_Indication**: PANTHER는 "solid yellow 1 sec = HF channel limiting; pulsing yellow = LF channel limiting"로 채널별 구분이 있었으나, TIGRA의 On/Status LED 서술(OM p.19-20)은 채널별 구분 없이 단일 LED로 Off/Green blinking(startup)/Green(ready)/Red flash(clipping)/Yellow(RMS limiting)/Red blinking(error) 6개 상태만 정의 — TIGRA는 2채널(LF 병렬+HF)이라 PANTHER의 4채널별 구분 표시 체계 자체가 없는 것으로 판단된다.
**[2] Cooling_Type="convection (no fans)"**: OM "The TIGRA amplifier module uses convection cooling."로 명시 — PANTHER의 "forced-air, 2 variable-speed fans"와 명확히 다른 아키텍처. 방열판(rear heat sink) 주변 공기 순환 여유 공간(후면 30cm, 상부 1m, 소핏 마운트 시 측면 30cm)이 필요하다는 서술도 확인.
**[3] IP_Rating 소스 간 충돌**: SPS(Datasheet) p.2와 AE p.2는 모두 "IP55, when connected to cables terminated with Neutrik powerCON® TRUE1 cable connectors"로 명시. 반면 OM은 AC 인렛(p.6)과 오디오/네트워크 커넥터(p.14) 양쪽에서 각각 "IP65"(후자는 "IP65, UL50E"까지 명시)로 일관되게 서술 — PANTHER와 완전히 동일한 유형의 소스 충돌 패턴이며, PANTHER 선례와 동일하게 인증 규격까지 명시하고 반복 확인되는 OM의 IP65를 채택, SPS/AE의 IP55는 각주로 보존.

## network_monitoring

self-powered/네트워크 연동 아키텍처 전용 섹션(PANTHER 전례 준용).

| Key | Value | Unit |
|---|---|---|
| Network_Protocol | Milan AVB | - |
| Telemetry_Software | Nebra | - |
| Telemetry_Transport | via network (Ethernet) connection | - |
| Device_Identification_Function | Wink | - |
| Network_Connectivity_LED [1] | (L) amber=link speed, (A) green=activity — 5단계 표(no link / 100Base-Tx no activity / 100Base-Tx activity / 1000Base-Tx+ no activity / 1000Base-Tx+ activity) | - |
| AES67_Support | null | - |
| Service_Port_Type | null | - |
| Remote_Mute_Control | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.2(Nebra 소프트웨어 개요, RPM 텔레메트리), p.19-20(Network connector LEDs 표), p.15-19(WINK 기능). 3개 문서 전량 "AES67" 키워드 스캔 결과 0건.
**[1] Network_Connectivity_LED**: PANTHER는 "illuminated when 100 bT link established"라는 단순 서술이었으나, TIGRA의 OM은 (L)amber/(A)green 2색 LED 조합으로 5단계 상태(무연결/100Base 무활동/100Base 활동/1000Base+ 무활동/1000Base+ 활동)를 상세 표로 제공 — PANTHER보다 훨씬 상세한 근거이므로 그대로 채택.
**AES67_Support/Service_Port_Type**: TIGRA 3개 문서 전량 스캔했으나 AES67이나 별도 서비스 포트(USB-C 등) 언급 없음 — 미확인.
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

**비적용 사유**: TIGRA는 자체 앰프를 내장한 self-powered 제품이라 K1/GSL처럼 외부 앰프와 매칭할 필요가 없다(PANTHER와 동일 원칙).
**Crossover_Type**: AE 원문 "The loudspeaker shall incorporate internal processing and a 2-channel class-D amplifier" — 드라이버 3발(LF 2발+HF 1발)에 앰프 채널은 2개뿐이라, PANTHER(드라이버 4발=채널 4개, 1:1 대응)와 달리 TIGRA는 LF 2발이 하나의 채널을 공유하는 구조로 추정된다(원문이 이 배선 자체를 명시하지는 않음, 산술적 정합성에 근거한 추정임을 명시). Passive_Crossover_Network=No(transducers 섹션 확정) 근거와 정합.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | end frames with captive GuideALinks secured with quick-release pins (QRP); QuickFly rigging system | - |
| Inter_Enclosure_Angles_deg [1] | 0.5 - 10 | deg |
| Handles | detachable side handles | - |
| Weight_Net | 54 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.2 "PHYSICAL"(Rigging 행); AE p.2; OM p.28-35(TIGRA Rigging Accessories 표: MTG-T1 Top Grid Kit, MBG-T1 Grid Box, MSB-T1 Shackle Bar, MPBF-T1 Pull Back Frame, MCF-T1 Caster Frame, MTF-T1 Transition Frame, MVP Motor V Plate). 리깅 시스템/중량은 TIGRA-L/W 공통.
**[1] Inter_Enclosure_Angles_deg**: SPS 원문 "0.375 x 0.75 inches quick-release pins that allow 0.5°– 10° splay angles" — PANTHER(0.5°-9°)와 미세하게 다른 범위, 임의로 통일하지 않고 TIGRA 자신의 원문값(0.5-10) 그대로 채택.
**Handles**: SPS는 개수를 명시하지 않고 "detachable side handles"로만 서술 — 정확한 개수는 미확인.

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

**출처**: SPS p.2 "PHYSICAL"(Dimensions 행 "W: 33.92 in (862 mm) x H: 12.76 in (324 mm) x D: 22.25 in (565 mm)"); AE p.2 "Dimensions shall be 33.92 in (862 mm) wide, 12.76 in (324 mm) high, and 22.25 in (565 mm) deep" — 두 문서 모두 W/H/D 축을 원문에 명시적으로 라벨링해 축 불확실성 없이 확정(TODO.md 치수 감사 기준 (1) 충족). 캐비닛 외형 치수는 TIGRA-L/W 공통.
**Dimensions_Raw**: 축이 명확히 확인되어 상위 호환 Key(Width/Height/Depth_mm)로 대체 — null 처리(PANTHER와 동일 원칙).
**IP_Rating**: protection_thermal 섹션의 IP_Rating(충돌 있음, 55 vs 65)으로 이전 — physical 섹션에서는 중복 방지를 위해 null.
**Rigging_Components_Material/Finish_Type**: 3개 문서 전량 스캔했으나 별도 서술 없음 — 미확인.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: TIGRA는 K1처럼 명명된 프리셋 조합 가이드를 OM/AE/SPS에 포함하지 않는다 — PANTHER와 동일하게 Meyer Sound MAPP System Design and Prediction 소프트웨어로 시뮬레이션하는 방식(OM 여러 곳에서 MAPP 3D 언급). 소프트웨어 기반 시뮬레이션 결과물은 이 세션에 제공되지 않아 미확인.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: preset_guide_and_matching과 동일 — MAPP 소프트웨어가 딜레이 정렬을 자동 계산하는 방식으로 추정되며, OM에 K1과 같은 고정 딜레이 기본값 표가 없음.

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

**출처**: OM p.32-35(TIGRA Rigging Accessories 표, Model/Weight/Features/Required quick-release pins 열). 기계 안전 수치는 TIGRA-L/W 공통(중량·캐비닛 동일).
**MTG-T1 Top Grid Kit**: "Supports up to 16 TIGRA without splay angle limitations with a 5:1 safety factor" 및 "For up to 24 TIGRA, limited to 23-degrees of maximum uptilt, no Downtilt restriction, 5:1 safety factor: TIGRA 2-11(2° 이하 스플레이), TIGRA 12-18(8° 이하 스플레이), TIGRA 19-22(스플레이 각 제한 없음)" — 두 조건을 별도 행으로 보존(PANTHER의 MVP+MG-PANTHER 25대 단일 조건보다 복합적).
**MPBF-T1 Pull Back Frame**: "For up to 12 TIGRA, 5:1 safety factor... For any number of cabinets, can support up to 1464 lb (664 kg) of array weight not supported by the grid box" — 대수 상한(12대)과 중량 상한(664kg) 두 조건이 병존, 대수 상한만 표에 반영하고 중량 상한은 각주 보존.
**MTF-T1 Transition Frame**: "up to six (6) TIGRA at any available splay angle, 5:1 safety factor. For rigging limitations, consider the added TIGRA as PANTHER cabinets and do not exceed the limits of a PANTHER array." — PANTHER 어레이 하부에 TIGRA를 연결하는 다운필 구성 전용(PANTHER_L 파일의 "flown, LEOPARD downfill" 행과 유사한 이종제품 결합 구성).
**MCF-T1 Caster Frame**: "Safely transports up to four TIGRA cabinets" — 이는 비행(flown) 구성이 아니라 지상 이동/보관용 카트이므로 다른 행들과 성격이 다름을 명시.
**Safe_Limit 열 null 사유**: PANTHER와 동일 — OM 원문이 "Maximum" 상한만 제공하고 별도 "안전 한도(safe limit)" 수치를 구분해 제공하지 않음(MAPP 소프트웨어가 개별 배치 검증을 대신하는 방식으로 추정).
**Max_Wind_Load(미확인)**: OM에 정성적 서술만 있고 구체적 수치가 명시되어 있지 않음 — 3개 문서 전량 스캔 결과 확정.

## Null Report

**미확인(정보 부족)**: Model_Number, Product_Series, Compliance_Standards, WEEE_Marking, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, Frequency_Response_5dB_Hz, Nominal_Directivity_Vertical, DSP_Preset_Name, LF_Acoustical_Load, RMS_Power_Handling_LF, RMS_Power_Handling_HF, LF_Nominal_Impedance, HF_Nominal_Impedance, Analog_Nominal_Input_Level, Max_Cable_Round_Trip_Resistance, AES67_Support, Service_Port_Type, Handles(정확한 개수), Rigging_Components_Material, Finish_Type, Max_Wind_Load, preset_guide_and_matching(전 항목), delay_defaults(전 항목), mechanical_safety(Safe_Limit 열 — MTG-T1 2개 구성/MPBF-T1/MTF-T1/MCF-T1 각 1개 구성, 총 5개 Configuration 행의 null 셀, 5건), Linear_Peak_SPL, Phase_Response, THD_IM_TIM, Amplifier_Total_Output_Power, Idle_Current, Max_Long_Term_Continuous_Current, Burst_Current, Max_Instantaneous_Peak_Current, Inrush_Current, Frequency_Response_4dB_Hz, Remote_Mute_Control — 39건.
**비적용(TIGRA 아키텍처상 개념 자체 불성립)**: Compatible_Amplified_Controller, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Dimensions_Raw, IP_Rating(physical 섹션, protection_thermal로 이전), Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module, Peak_Power_Handling_10ms_Overall — 9건.

**총계**: null 48건 (미확인 39건 + 비적용 9건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Passive_Crossover_Network(No, 3개 문서 전량 스캔 근거). **정정(2026-07-18, 각주 버전 참조 최신성 감사에서 발견)**: mechanical_safety의 Safe_Limit 미확인이 "Safe_Limit 열"이라는 결합형 불릿으로 서술되며 실제 5개 Configuration 행 각각의 null 셀인데도 1건으로만 카운트되어 있던 것을 발견·정정(speakers/LA K1_v1.11.md 등과 동일 유형) — 미확인 33건→37건, 총계 41건→45건. 데이터(Key/Value/Unit) 자체는 전혀 변경하지 않았다.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — Meyer Sound 2번째 제품군(TIGRA) 최초 투입, PANTHER_L_v1.0.md를 스켈레톤으로 사용. `upload/` 폴더에 제공된 Datasheet(SPS)+Operating Instructions(OM)+Architectural Specification(AE) 3개 문서 통합. TIGRA-L/TIGRA-W가 PANTHER-L/M/W와 동일한 "파트넘버 없는 지향각 베리언트" 패턴임을 확인, 사용자 재확인(2026-07-18) 후 PANTHER와 동일하게 개별 파일 분리 적용. PANTHER 대비 아키텍처 차이 다수 확인: 앰프 2채널(PANTHER 4채널), 드라이버 LF 2발+HF 1발(PANTHER 2발+2발), 컨벡션 냉각(PANTHER 강제공랭 팬), 카디오이드 최소 6대(PANTHER 4대), Network_Connectivity_LED 5단계 표(PANTHER는 단순 서술). IP_Rating은 PANTHER와 동일한 SPS/AE(55) vs OM(65) 충돌 패턴 확인, OM값 채택도 동일 원칙 적용. Compliance_Standards는 PANTHER와 달리 원문에서 확인되지 않아 미확인. Usable_Bandwidth_Hz는 측정 조건 서술 자체가 원문에 없다는 점을 각주로 명시(사용자 지적 2026-07-18). LEOPARD/LINA 파싱 이후 발견된 신규 Key 9종(Linear_Peak_SPL/Phase_Response/THD_IM_TIM/전류 기반 소비전력 5종)도 이 v1.0 파일에 아직 미커밋 상태였으므로 별도 버전 상향 없이 같은 v1.0에 통합 반영(전부 미확인). Null Report 41건(미확인 33건+비적용 8건). **후속 정정(같은 v1.0, 2026-07-18)**: mechanical_safety Safe_Limit 결합형 불릿 오카운트(5개 Configuration 행을 1건으로 카운트) 발견·정정, Null Report 45건(미확인 37건+비적용 8건)으로 재계산. |
| v1.0 to v1.1 | (양방향 동기화, Minor) Meyer Sound 신규 제품 2100-LFC 파싱 과정에서 신설된 Key `Analog_Input_Pinout_Case`를 실값("Earth (AC) ground and chassis")으로 반영 — TIGRA 자신의 OM p.24 원본 재확인 결과 확인. Null Report 총계는 영향 없음. |
| v1.1 to v1.2 | speakers 카테고리 전체 일괄 동기화 라운드(2026-07-18, d&b 대량 배치 완료 후) — 신규 Key `Frequency_Response_4dB_Hz`(미확인), `Peak_Power_Handling_10ms_Overall`(비적용), `Remote_Mute_Control`(750-LFC/900-LFC 유래, 미확인) 반영. Null Report 48건(미확인 39건+비적용 9건)으로 갱신. |
