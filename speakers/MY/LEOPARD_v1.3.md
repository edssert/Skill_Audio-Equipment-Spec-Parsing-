# LEOPARD (Meyer Sound) — Master Schema

**Category**: speakers | **Brand**: Meyer Sound (MY) | **Schema Phase**: Phase 4 (Meyer Sound 3번째 제품군 투입, PANTHER/TIGRA 대비)

**스켈레톤 근거**: `speakers/MY/TIGRA_L_v1.0.md`를 뼈대로 사용 — self-powered line array 아키텍처 공통. 다만 LEOPARD의 Datasheet(SPS) 문서 자체에 "Architectural Specifications" 섹션이 포함되어 있어(PANTHER/TIGRA처럼 별도 AE 파일이 제공되지 않음) 이 SPS 1개 문서가 SPS+AE 역할을 겸한다 — Original_PDFs에는 `LEOPARD_SPS_EN.pdf`(OM은 `LEOPARD_OM_EN.pdf`)로만 파일링했다.

**LEOPARD/LEOPARD-M80 개별 파일 분리(PANTHER/TIGRA 선례 적용, 재확인 없이 진행)**: 파트넘버 구분 없이 수평 지향각(110°/80°)만 다른 2개 모델명으로 병기하는 동일 패턴 — 사용자가 자리비움으로 추가 확인 없이 계속 진행하라 지시했으므로, `speakers/CLAUDE.md`에 이미 2회 확인된 Meyer Sound 브랜드 선례(PANTHER, TIGRA)를 따라 자동으로 개별 파일 분리 적용한다(TODO.md에 판단 근거 기록, 다음 세션에서 원하면 재검토 가능). **베리언트 간 차이는 Horizontal_Coverage와 Linear_Peak_SPL(M-noise/Pink noise/B-noise 3종 수치+크레스트팩터)뿐** — Maximum_SPL(142dB)과 Phase_Response(92Hz-18kHz ±30°)는 두 베리언트 공통(PANTHER/TIGRA와 달리 Max_SPL_Peak 자체는 변하지 않는 점이 다름, 아래 각주 참조).

**아키텍처 판단(원본 근거)**: LEOPARD는 SPS "Architectural Specifications" 절에 "The loudspeaker shall be a compact, self-powered, linear, low-distortion, line array loudspeaker"로 명시된다. 앰프는 "a 3-channel, open-loop, class D amplifier"로 확정 — 드라이버 3발(LF 2발+HF 1발)에 채널 3개로 1:1 대응(TIGRA의 2채널/3드라이버 불일치와 달리 명확한 구조). Passive_Crossover_Network는 SPS/OM 2개 문서 전체에서 "crossover" 키워드 전량 스캔 결과 0건으로 확정적 비존재(No) 판정.

**신규 Key 4종 도입(양방향 동기화 필요, TODO.md에 미완료로 기록)**: LEOPARD는 PANTHER/TIGRA가 쓰는 AES75-2022 표준을 전혀 사용하지 않고(2개 문서 전량 "AES75" 스캔 0건) 대신 Meyer 자체 "Linear Peak SPL" 지표(M-noise/Pink noise/B-noise 3개 노이즈 타입 + 크레스트팩터)를 쓴다 — 신규 Key `Linear_Peak_SPL`(단일 복합값, AES75_Max_Linear_SPL과 동일한 "번들 원자화 금지" 원칙). 그 외 `THD_IM_TIM`(왜율), `Amplifier_Total_Output_Power`(앰프 총 피크 출력), 전류 기반 소비전력 5종(`Idle_Current`/`Max_Long_Term_Continuous_Current`/`Burst_Current`/`Max_Instantaneous_Peak_Current`/`Inrush_Current`, 각각 115/230/100VAC 3조건 병기값)도 신규 도입 — PANTHER/TIGRA는 이 개념 자체가 없어(전력을 W 단위로만 제공, 전류는 별도 제공 안 함) 이번 라운드 완료 후 5개 기존 파일(PANTHER x3, TIGRA x2)에 null로 소급 반영 필요.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | LEOPARD | - |
| Model_Number | null | - |
| Product_Series | null | - |
| Product_Category | Line Array | - |
| Product_Type | Compact line array loudspeaker | - |
| Description | compact, self-powered, linear, low-distortion line array loudspeaker, 2-way, 110° horizontal coverage | - |
| Way_Count | 2 | - |
| Onboard_Amplification | Yes | - |
| Compliance_Standards | null | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS(Datasheet, "Architectural Specifications" 절 포함) p.1, p.11-12; OM(Operating Instructions) p.1-2.
**Product_Type="Compact line array loudspeaker"**: SPS 원문 "The loudspeaker shall be a compact, self-powered, linear, low-distortion, line array loudspeaker"에서 "compact"를 크기 등급으로 채택 — TIGRA의 "Medium-format", PANTHER의 등급 없음과 대비.
**Way_Count**: LF 2발(9인치)+HF 1발(3인치) 2-way 구조 — SPS TRANSDUCERS 표에서 확인(PANTHER/TIGRA와 동일하게 "2-way" 명시 문구는 없으나 Low Frequency/High Frequency 2대역 구조가 명확).
**Compliance_Standards/WEEE_Marking**: SPS/OM 2개 문서 전량 스캔 결과 인증 마크나 WEEE 문구 없음(PANTHER는 있었음, TIGRA도 없었음 — Meyer Sound 문서 내 일관성이 없어 보이며 확정 근거 없이 채택하지 않음) — 미확인.
**Model_Number/Product_Series**: 2개 문서 전량 스캔 결과 파트넘버나 시리즈 소속 표현 없음(다만 SPS가 LEOPARD를 "Meyer Sound's award-winning LEO® family of loudspeakers"의 일원으로 서술 — "family"는 "series"와 다른 개념으로 판단해 Product_Series에 채택하지 않음, 관련 서술은 스켈레톤 근거 각주에 기록) — 미확인.

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
| Linear_Peak_SPL [2] | 133.5 dB with 18 dB crest factor (M-noise), 130 dB (Pink noise), 134.5 dB (B-noise) | - |
| Nominal_Directivity_Horizontal_deg | 110 | deg |
| Nominal_Directivity_Vertical [3] | Varies, depending on array length and configuration | - |
| Phase_Response [4] | 92 - 18000 Hz ±30° | - |
| THD_IM_TIM | < 0.02% | - |
| Cardioid_Capability | No | - |
| DSP_Preset_Name | null | - |
| Cardioid_Pattern_Array_Min_Size | null | count |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS "Specifications" 표(ACOUSTICAL/COVERAGE/AMPLIFIERS, LEOPARD 열) p.7-9; SPS "Architectural Specifications" 절 p.11-12.
**[1] Max_SPL_Peak**: SPS 각주 4 "Maximum SPL is the peak measured in free-field at 4 m referred to 1 m using noise" — TIGRA와 동일 측정법. **LEOPARD/LEOPARD-M80 두 베리언트가 동일 값(142dB)을 공유** — PANTHER/TIGRA는 이 값이 베리언트마다 달랐으나 LEOPARD는 다르다(원문이 이렇게 명시).
**[2] Linear_Peak_SPL(신규 Key)**: AES75 표준 대신 Meyer 자체 지표 — SPS 각주 5 "Linear Peak SPL is measured 1 m on axis with typical boundary loading... M-noise is a full bandwidth (10Hz-22.5kHz) test signal... crest factor that increases with frequency... Pink noise is a full bandwidth test signal with Peak to RMS ratio of 12.5dB... B-noise is a Meyer Sound test signal used to ensure measurements reflect system behavior when reproducing the most common input spectrum". 3개 노이즈 타입 수치를 하나의 복합값으로 병기(AES75_Max_Linear_SPL과 동일한 "번들 원자화 금지" 원칙 적용, 다만 이 값은 AES75 표준이 아니므로 별도 Key로 분리).
**[3] Nominal_Directivity_Vertical**: PANTHER/TIGRA는 이 항목이 미확인이었으나, LEOPARD는 SPS COVERAGE 표에 "Varies, depending on array length and configuration"이라는 정성적 서술이 명시되어 있어 이를 그대로 채택(수치가 아닌 정성적 값이지만 원문에 실제로 존재하는 서술이므로 null 대신 채택).
**[4] Phase_Response(신규 Key)**: SPS "92 Hz – 18 kHz ±30 degrees" — PANTHER/TIGRA 문서에는 이 항목 자체가 없었음(LEOPARD 고유 신규 발견, 양방향 동기화 대상).
**THD_IM_TIM(신규 Key)**: SPS AMPLIFIERS 표 "THD, IM, TIM: < 0.02%".
**Cardioid_Capability=No**: SPS/OM 2개 문서 전량 "cardioid" 키워드 스캔 결과 0건 — 확정적 비존재.
**[5] Usable_Bandwidth_Hz — 측정 조건**: SPS 각주 3 "Recommended maximum operating frequency range. Response depends on loading conditions and room acoustics." — TIGRA(조건 서술 자체 없음)와 달리 LEOPARD는 "권장 최대 동작 대역"이며 부하/음향 환경에 따라 달라질 수 있다는 조건부 서술이 명시되어 있음. 값 자체(55-18000Hz)는 원문 그대로 채택하되 이 조건부 성격을 각주로 남긴다.
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

**출처**: SPS TRANSDUCERS 표 p.7-8("Two 9-inch long-excursion cone drivers; 2 Ω nominal impedance", "One 3-inch diaphragm compression driver coupled to a constant-directivity horn through a patented REM® manifold; 4 Ω nominal impedance").
**LF_Nominal_Impedance=2Ω**: PANTHER는 4Ω(LF)/8Ω(HF), TIGRA는 두 값 모두 미확인이었음 — LEOPARD는 SPS에 명시적으로 2Ω(LF)/4Ω(HF)로 확인, 임의로 통일하지 않고 원문 그대로 채택.
**Passive_Crossover_Network=No**: SPS/OM 2개 문서 전체에서 "crossover" 키워드 전량 스캔 결과 0건 — 확정적 비존재.
**Peak_Power_Handling_10ms_Overall(신규 Key)**: d&b CCL8에서 신설된 범용 Key — RMS_Power_Handling_Overall과 동일 사유(self-powered 구조상 드라이버 자신의 파워 핸들링이 아니라 Amplifier_Total_Output_Power로 보고)로 비적용.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Connector [1] | XLR 5-pin female input with male loop output; XLR 3-pin female connectors available (balanced audio only, no RMS) | - |
| Analog_Loop_Output_Connector | XLR 5-pin male (integrated loop output) | - |
| Analog_Input_Impedance | 10000 | Ohm |
| Analog_Nominal_Input_Level [2] | 6.0 dBV (2.0 V rms) continuous, typical onset of limiting | - |
| Analog_Input_Pinout_Pin1 | Chassis/earth through 1 kOhm, 1000 pF, 15V clamped network (virtual ground lift at audio frequencies) | - |
| Analog_Input_Pinout_Pin2 | Signal (+) | - |
| Analog_Input_Pinout_Pin3 | Signal (-) | - |
| Analog_Input_Pinout_Pin4 | RMS (polarity insensitive) | - |
| Analog_Input_Pinout_Pin5 | RMS (polarity insensitive) | - |
| Analog_Input_Pinout_Case [3] | null | - |
| Analog_Source_Drive_Requirement | +20 dBV (10 V rms) into 600 Ohm (for maximum peak SPL) | - |
| Digital_Input_Connector | null | - |
| Digital_Input_Format | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS AUDIO INPUT 표 p.8-9(Type/Maximum Common Mode Range/Connectors/Input Impedance/Wiring/Nominal Input Sensitivity/Input Levels), 각주 6("Pins 4 and 5 (RMS) only included with XLR 5-pin connector that accommodates both balanced audio and RMS signals").
**[1] Analog_Input_Connector**: PANTHER/TIGRA는 Neutrik XLR 3-pin TOP(옥외 방수) 단일 커넥터였으나, LEOPARD는 XLR 5-pin(오디오+RMS 겸용)이 기본이고 3-pin(오디오 전용, RMS 신호 미지원)은 대안 옵션 — 옥외방수(TOP) 등급이 아닌 표준 실내용 커넥터로 판단(protection_thermal 섹션 IP_Rating 참조).
**[2] Analog_Nominal_Input_Level**: TIGRA는 이 항목이 미확인이었으나 LEOPARD는 SPS에 "6.0 dBV (2.0 V rms) continuous is typically the onset of limiting for noise and music"로 명시 — PANTHER의 "0 dBV (1.0 V rms)"와 수치가 다름(임의로 통일하지 않고 LEOPARD 자신의 원문값 채택).
**Digital_Input_Connector/Format=null**: LEOPARD는 SPS/OM 전량 스캔 결과 Milan AVB나 다른 디지털 오디오 입력 형식에 대한 언급이 전혀 없음(PANTHER/TIGRA는 Milan AVB 지원, LEOPARD는 아날로그 전용 제품으로 판단되나 확정적 비존재로 단정할 근거는 부족해 미확인 유지) — 대신 별도의 "RMS Network"(2선 트위스트페어)로 원격 모니터링만 지원(network_monitoring 섹션 참조).
**[3] Analog_Input_Pinout_Case(신규 Key, v1.1)**: 2100-LFC 파싱 과정에서 신설된 신규 Key(PANTHER/TIGRA의 XLR 3-pin 커넥터 외피 접지 서술에서 유래) — LEOPARD는 XLR 5-pin 커넥터를 쓰며, 이번 라운드에서 참조한 SPS AUDIO INPUT 표에는 Case(커넥터 외피) 접지에 대한 별도 서술이 없다. LEOPARD_OM의 상세 배선 다이어그램 챕터까지는 이번 라운드에서 재조회하지 않아 미확인으로 유지 — 향후 LEOPARD OM을 상세 재조회할 기회에 확인 필요.

## power_supply

self-powered 아키텍처 전용 섹션(PANTHER/TIGRA 전례 준용).

| Key | Value | Unit |
|---|---|---|
| AC_Connector | powerCON 20 (input with loop output) | - |
| AC_Nominal_Voltage_Range [1] | 100, 110, or 230 | V AC |
| AC_Operating_Voltage_Range [1] | 90 - 265 | V AC |
| AC_Frequency_Range | 50 - 60 | Hz |
| Max_Long_Term_Continuous_Power | null | W |
| Burst_Power | null | W |
| Idle_Power | null | W |
| Max_Cable_Round_Trip_Resistance | null | Ohm |
| AC_Inlet_Pinout | null | - |
| Power_Supply_Protection_Features | EMI filtering, soft current turn-on, surge suppression | - |
| Amplifier_Total_Output_Power [2] | 3900 | W |
| Idle_Current [3] | 0.46 A rms (115 V AC); 0.35 A rms (230 V AC); 0.49 A rms (100 V AC) | - |
| Max_Long_Term_Continuous_Current [3] | 3.0 A rms (115 V AC); 1.5 A rms (230 V AC); 3.4 A rms (100 V AC) | - |
| Burst_Current [3] | 4.4 A rms (115 V AC); 2.3 A rms (230 V AC); 5.5 A rms (100 V AC) | - |
| Max_Instantaneous_Peak_Current [3] | 12.6 A peak (115 V AC); 6.3 A peak (230 V AC); 14.5 A peak (100 V AC) | - |
| Inrush_Current | < 20 | A peak |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS AC POWER/CURRENT DRAW 표 p.9-10; SPS Architectural Specifications 절 p.11-12.
**[1] AC_Nominal_Voltage_Range/AC_Operating_Voltage_Range**: SPS "Automatic Voltage Selection: 90-265 V AC", "Safety Rated Voltage Range: 100-240 V AC, 50-60 Hz", Architectural Specifications 절은 "nominal 100, 110, or 230 V AC line current... UL and CE operating voltage range shall be 100-240 V AC" — 두 서술 간 범위 표기가 미세하게 다름(90-265 vs 100-240), SPS 표 값(Automatic Voltage Selection, 실제 동작 범위)을 AC_Operating_Voltage_Range로, Architectural Specifications의 정격 전압 열거값을 AC_Nominal_Voltage_Range로 구분 채택(PANTHER/TIGRA와 다른 표기 방식이라 단순 병합하지 않음).
**[2] Amplifier_Total_Output_Power(신규 Key)**: SPS AMPLIFIERS 표 "Total Output Power: 3900 W peak", 각주 7 "Peak power based on the maximum unclipped peak voltage the amplifier will produce into the nominal load impedance." — PANTHER/TIGRA의 Max_Long_Term_Continuous_Power/Burst_Power(AC 입력 전력, W)와는 다른 개념(앰프 자체의 출력 정격)이라 별도 Key로 분리.
**[3] 전류(Amp) 기반 소비전력 5종(신규 Key군)**: PANTHER/TIGRA는 전력을 W(와트) 단위로만 제공했으나 LEOPARD는 전류를 A(암페어) 단위로 3개 전압 조건(115/230/100V AC)별로 병기 — 단위/개념이 달라 기존 Max_Long_Term_Continuous_Power/Burst_Power/Idle_Power Key에 억지로 대입하지 않고(전압×전류=전력 계산은 임의 추론 금지 원칙 위반) 신규 Key로 분리, 기존 W 단위 Key 3개는 LEOPARD에서 null 유지.
**Max_Cable_Round_Trip_Resistance/AC_Inlet_Pinout**: SPS/OM 2개 문서 전량 스캔 결과 서술 없음 — 미확인.

## protection_thermal

self-powered 아키텍처 전용 섹션(PANTHER/TIGRA 전례 준용).

| Key | Value | Unit |
|---|---|---|
| Limiter_Type | null | - |
| Limiter_Indication [1] | Active/Status LED: solid green=normal, flashing red=hardware fault or overheating (audio may continue with reduced limiter threshold); separate HF/LF Limit LEDs: unlit=normal, lit ≤2 sec(off ≥1 sec)=OK, lit >3 sec=hard limiting | - |
| Cooling_Type | Convection | - |
| IP_Rating [2] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.21("Active/Status LED"), p.19-20("HF and LF Limit LEDs"). SPS AMPLIFIERS 표 "Cooling: Convection".
**Limiter_Type**: PANTHER/TIGRA는 "TruPower limiting"으로 명시된 리미터 방식명이 있었으나, LEOPARD의 2개 문서 전량 스캔 결과 리미터 방식에 대한 고유 명칭(브랜드명)을 찾지 못함 — 동작 서술(HF/LF 개별 리미터, Limit LED)만 있고 명칭이 없어 미확인.
**[1] Limiter_Indication**: PANTHER/TIGRA는 단일 On/Status LED가 리미팅까지 표시했으나, LEOPARD는 Active/Status LED(하드웨어 상태 전용)와 별도의 HF/LF Limit LED(리미팅 전용, 대역별 개별 표시)가 물리적으로 분리되어 있음 — TIGRA보다 PANTHER의 "채널별 구분" 방식에 더 가까우나 LED 명칭 자체가 다름(TIGRA/PANTHER의 "On/Status"가 아닌 "Active/Status").
**[2] IP_Rating=null(구조적 차이)**: PANTHER/TIGRA는 기본 구성 자체가 Neutrik TOP(옥외 방수) 커넥터를 사용해 IP55/65 등급을 기본 보유했으나, LEOPARD는 표준 XLR 커넥터(TOP 아님)를 사용하는 실내용 기본 구성이며, "Weather Protection"이라는 별도 옵션 액세서리를 장착해야만 IPX4 등급을 확보한다(OM p.1715 부근 "Meyer Sound designs toward an IP rating of IPX4... for Standard Weather" 서술) — 기본 구성에는 IP 등급이 없는 것이 PANTHER/TIGRA와의 구조적 차이이므로, 옵션 장착 시에만 성립하는 IPX4를 기본 스펙 Key에 채택하지 않고 null 유지(각주로 옵션 존재는 기록).

## network_monitoring

네트워크/원격 모니터링 관련 섹션(PANTHER/TIGRA 전례 준용, 다만 LEOPARD는 Milan AVB가 아닌 Meyer 자체 RMS Network 사용).

| Key | Value | Unit |
|---|---|---|
| Network_Protocol | null | - |
| Telemetry_Software | Compass RMS (RMS™ remote monitoring system) | - |
| Telemetry_Transport [1] | two-conductor, twisted-pair RMS network | - |
| Device_Identification_Function | null | - |
| Network_Connectivity_LED | null | - |
| AES67_Support | null | - |
| Service_Port_Type | null | - |
| Remote_Mute_Control | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS RMS NETWORK 표 p.10("Equipped with two-conductor, twisted-pair network; reports all amplifier operating parameters to host computers"); SPS 본문("LEOPARD and 900-LFC loudspeakers work with Meyer Sound's RMS™ remote monitoring system, which provides comprehensive monitoring of system parameters from a Mac® or Windows®-based computer").
**[1] Telemetry_Transport**: PANTHER/TIGRA는 표준 Ethernet(네트워크 연결) 기반이었으나, LEOPARD는 "two-conductor, twisted-pair" 전용 RMS 네트워크 배선(이더넷과 다른 물리 계층) — Network_Protocol을 "Milan AVB"로 채택하지 않고 null 유지(LEOPARD 자신의 문서에 Milan/AVB 언급이 전혀 없음, RMS Network는 Meyer 고유의 별도 프로토콜로 판단되나 정식 명칭이 문서에 없어 Network_Protocol에는 채택하지 않음).
**Device_Identification_Function/Network_Connectivity_LED**: PANTHER/TIGRA의 Wink 기능이나 네트워크 LED 표시에 대응하는 서술을 LEOPARD 2개 문서에서 찾지 못함 — 미확인.
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

**비적용 사유**: LEOPARD는 자체 앰프를 내장한 self-powered 제품이라 외부 앰프와 매칭할 필요가 없다(PANTHER/TIGRA와 동일 원칙).
**Crossover_Type**: SPS AMPLIFIERS 표 "Type: 3-channel, open-loop, class D" — 드라이버 3발(LF 2발+HF 1발)에 앰프 채널도 3개로 1:1 대응(TIGRA는 드라이버 3발에 채널 2개로 불일치가 있었으나 LEOPARD는 명확).

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | end frames with captive GuideALinks secured with quick-release pins (QRP); QuickFly rigging system | - |
| Inter_Enclosure_Angles_deg | 0.5 - 15 | deg |
| Handles | detachable side and rear handles | - |
| Weight_Net | 34.0 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS PHYSICAL 표 p.10("Rigging: End frames with captive GuideALinks secured with 0.3125 in x 0.63 in quick-release pins that allow 0.5° to 15° splay angles; detachable side and rear handles").
**Inter_Enclosure_Angles_deg**: PANTHER(0.5-9°)/TIGRA(0.5-10°)보다 넓은 범위(0.5-15°) — 임의로 통일하지 않고 LEOPARD 자신의 원문값 채택.
**Handles="detachable side and rear handles"**: PANTHER/TIGRA는 "side handles"만 언급했으나 LEOPARD는 "rear handles"도 추가로 명시.

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

**출처**: SPS PHYSICAL 표 "Dimensions: W: 26.93 in (684 mm) x H: 11.11 in (282 mm) x D: 21.66 in (550 mm)"; SPS Architectural Specifications 절 "Dimensions shall be W: 26.93 in (684 mm) x H: 11.11 in (282 mm) x D: 21.66 in (550 mm)" — 두 서술 완전 일치(같은 문서 내 교차검증), W/H/D 축 명시적 라벨링으로 축 불확실성 없이 확정(TODO.md 치수 감사 기준 (1) 충족).
**Dimensions_Raw**: 축이 명확히 확인되어 상위 호환 Key로 대체 — null.
**Front_Material**: PANTHER/TIGRA의 "powder-coated stamped steel"과 달리 LEOPARD는 "hex-stamped steel with acoustical black mesh"로 원문이 더 상세 — 임의로 요약하지 않고 원문 그대로 채택.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: PANTHER/TIGRA와 동일 — Meyer Sound MAPP System Design Tool로 시뮬레이션하는 방식, 소프트웨어 결과물 미제공.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: preset_guide_and_matching과 동일.

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

**출처**: OM Table 4 "LEOPARD Rigging Options" p.23-24(MG-LEOPARD/900, GROUNDSTACK DOWNTILT KIT, MVP motor Vee plate, MTF-LYON/LEOPARD, PBF-LEOPARD, MCF-LEOPARD); SPS Accessories 절 p.3-4.
**MG-LEOPARD/900 Multipurpose Grid**: "With some restrictions, flies up to 23 LEOPARDs at a 5:1 safety factor and BGV C1 with some angle restrictions... supports mixed arrays of LEOPARD and 900-LFC cabinets flown or ground-stacked without any transition hardware."
**MTF-LYON/LEOPARD Transition Frame**: "flies up to ten LEOPARDs at a 5:1 safety factor... for downfill below LYON arrays" — TIGRA의 MTF-T1(PANTHER 어레이 하부용)과 유사한 역할이나 LEOPARD는 LYON 어레이 하부용.
**MCF-LEOPARD Caster Frame**: "Safely transports up to four fully rigged LEOPARD cabinets" — 비행 구성이 아닌 이동/보관용.
**Safe_Limit 열 null 사유**: PANTHER/TIGRA와 동일 — MAPP 소프트웨어가 개별 배치 검증을 대신하는 방식.
**Max_Wind_Load(미확인)**: 2개 문서 전량 스캔 결과 구체적 수치 없음.

## Null Report

**미확인(정보 부족)**: Model_Number, Product_Series, Compliance_Standards, WEEE_Marking, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, Frequency_Response_5dB_Hz, DSP_Preset_Name, Cardioid_Pattern_Array_Min_Size, LF_Acoustical_Load, RMS_Power_Handling_LF, RMS_Power_Handling_HF, Analog_Input_Pinout_Case, Digital_Input_Connector, Digital_Input_Format, Max_Long_Term_Continuous_Power, Burst_Power, Idle_Power, Max_Cable_Round_Trip_Resistance, AC_Inlet_Pinout, Limiter_Type, IP_Rating(protection_thermal), Network_Protocol, Device_Identification_Function, Network_Connectivity_LED, AES67_Support, Service_Port_Type, Rigging_Components_Material, Finish_Type, Max_Wind_Load, preset_guide_and_matching(전 항목), delay_defaults(전 항목), mechanical_safety(Safe_Limit 열 — 3개 Configuration 행의 null 셀, 3건), Frequency_Response_4dB_Hz, Remote_Mute_Control — 35건.
**비적용(LEOPARD 아키텍처상 개념 자체 불성립)**: Compatible_Amplified_Controller, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Dimensions_Raw, IP_Rating(physical 섹션), Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module, AES75_Max_Linear_SPL(LEOPARD는 이 표준 자체를 사용하지 않고 Linear_Peak_SPL로 대체), Peak_Power_Handling_10ms_Overall — 10건.

**총계**: null 45건 (미확인 35건 + 비적용 10건). 확정적 비존재(0/No)로 명시한 항목은 2건 — Passive_Crossover_Network, Cardioid_Capability(둘 다 2개 문서 전량 스캔 근거). **정정(2026-07-18, 각주 버전 참조 최신성 감사에서 발견)**: mechanical_safety의 Safe_Limit 미확인이 결합형 불릿으로 서술되며 실제 3개 Configuration 행 각각의 null 셀인데도 1건으로만 카운트되어 있던 것을 발견·정정(speakers/LA K1_v1.11.md 등과 동일 유형) — 미확인 30건→32건, 총계 39건→41건. 데이터(Key/Value/Unit) 자체는 전혀 변경하지 않았다. **v1.1 신규 Key 반영(2100-LFC 파싱 라운드)**: `Analog_Input_Pinout_Case` 신설·null 동기화(LEOPARD_OM 상세 배선 챕터 미재조회로 미확인) — 미확인 32건→33건, 총계 41건→42건.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — Meyer Sound 3번째 제품군(LEOPARD) 최초 투입, TIGRA_L_v1.0.md를 스켈레톤으로 사용. `upload/` 폴더 제공 Datasheet(SPS, Architectural Specifications 절 포함)+Operating Instructions(OM) 2개 문서 통합(AE 별도 파일 없음). LEOPARD/LEOPARD-M80이 PANTHER/TIGRA와 동일한 "파트넘버 없는 지향각 베리언트" 패턴임을 확인 — 사용자 취침으로 재확인 없이 기존 선례(2회 확인됨) 따라 개별 파일 분리 자동 적용(TODO.md 기록). PANTHER/TIGRA 대비 신규 개념 다수 발견: AES75 미사용(Linear_Peak_SPL 신규 Key로 대체), THD_IM_TIM/Phase_Response/Amplifier_Total_Output_Power/전류 기반 소비전력 5종 신규 Key 도입(양방향 동기화는 3개 제품 전부 완료 후 일괄 진행 예정, TODO.md에 미완료로 기록). IP_Rating은 PANTHER/TIGRA와 달리 기본 구성에 없음(옵션 Weather Protection 장착 시에만 IPX4). Null Report 39건(미확인 30건+비적용 9건). **후속 정정(같은 v1.0, 2026-07-18)**: mechanical_safety Safe_Limit 결합형 불릿 오카운트 정정, Null Report 41건(미확인 32건+비적용 9건)으로 재계산. |
| v1.0 to v1.1 | (양방향 동기화, Minor) Meyer Sound 신규 제품 2100-LFC 파싱 과정에서 신설된 Key `Analog_Input_Pinout_Case`를 null로 동기화 — 이번 라운드에서 참조한 LEOPARD SPS AUDIO INPUT 표에는 Case 접지 서술이 없어 미확인 처리(OM 상세 배선 챕터는 이번 라운드에서 재조회하지 않음, 향후 확인 필요). Null Report 미확인 32건→33건, 총계 41건→42건. |
| v1.1 to v1.2 | (표기 정정, Minor) 사용자 지적(2026-07-18) — 스켈레톤 근거 각주의 "사용자가 심야 취침으로"라는 표현이 실제 작업 시각과 무관하게 부정확한 시간대 서술이라 "사용자가 자리비움으로"로 정정. 데이터(Key/Value/Unit) 자체는 전혀 변경하지 않았다. |
| v1.2 to v1.3 | speakers 카테고리 전체 일괄 동기화 라운드(2026-07-18, d&b 대량 배치 완료 후) — 신규 Key `Frequency_Response_4dB_Hz`(미확인), `Peak_Power_Handling_10ms_Overall`(비적용), `Remote_Mute_Control`(750-LFC/900-LFC 유래, 미확인) 반영. Null Report 45건(미확인 35건+비적용 10건)으로 갱신. |
