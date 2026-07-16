# PANTHER (Meyer Sound) — Master Schema

**Category**: speakers | **Brand**: Meyer Sound (MY) | **Schema Phase**: Phase 3-2 (타 브랜드 교차 테스트, K1/GSL8/GSL12 대비)

**스켈레톤 근거**: 완전히 새로운 브랜드 최초 투입이며, 기존 파일 중 아키텍처가 가장 유사한 것은 없다(K1/GSL8/GSL12는 모두 외부 앰프 구동 패시브/하이브리드 토폴로지, PANTHER는 self-powered) — 따라서 K1_v1.2.md의 섹션 구조를 뼈대로 재사용하되, self-powered 아키텍처 전용 신규 섹션(power_supply, connectivity의 오디오 입출력 상세, protection_thermal, network_monitoring)을 대거 신설했다. 사용자 지침(2026-07-16)에 따라 신규 브랜드 최초 제품이므로 K1/GSL 수준의 깊이(원본 문서 전체 스캔, 다중 소스 교차검증)를 동일하게 적용했다.

**PANTHER 제품 구성**: PANTHER는 PANTHER-L(80°)/PANTHER-M(95°)/PANTHER-W(110°) 3개 수평 지향각 베리언트로 구성된 하나의 제품이다(공식 Datasheet가 3개 베리언트를 한 표에 나란히 제공하는 방식 — GSL8/GSL12처럼 별도 모델/파트넘버가 부여된 별개 제품이 아니라 동일 "PANTHER" 제품명의 지향각 베리언트이므로 1개 파일로 통합했다). 값이 베리언트별로 다른 Key는 Value 칸에 "L: x / M: y / W: z" 형식으로 병기한다.

**아키텍처 판단(원본 근거)**: PANTHER는 AE/OM 원문에 명시적으로 "self-powered"로 표기되며("The loudspeaker shall be a self-powered... line array loudspeaker", AE p.1; "The self-powered PANTHERTM linear line array loudspeaker...", OM p.1), 내장 4채널 Class-D 앰프와 온보드 DSP를 탑재한다("The loudspeaker shall incorporate internal processing and a 4-channel class-D amplifier", AE).크로스오버는 Active로 판단 — 3개 원본 문서(OM/AE/Datasheet) 전체에 "crossover" 키워드가 0건 검출되어(전량 스캔 근거) 내부 패시브 크로스오버가 없으며, 4채널 앰프가 LF 2발+HF 2발 각 드라이버를 개별 채널로 구동하는 구조로 판단된다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | PANTHER | - |
| Model_Number | null | - |
| Product_Category | Line Array | - |
| Description | self-powered, linear, low-distortion line array loudspeaker, 2-way | - |
| Way_Count | 2 | - |
| Onboard_Amplification | Yes | - |
| Variant_Names | PANTHER-L, PANTHER-M, PANTHER-W | - |
| Compliance_Standards | c(UL)us Listed (3K59 or 3JKB Commercial Audio System); CE marked | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: AE(Architectural Specification, Meyer Sound, docs.meyersound.com) p.1; OM(Operating Instructions) p.1-2; SPS(Datasheet) p.1.
**Model_Number**: d&b GSL8/GSL12의 Z0750/Z0751 같은 공식 파트넘버 표기가 3개 문서 어디에도 없어 미확인.
**Way_Count**: SPS 각주 "The PANTHER 2-way loudspeaker has a unique placement of low-mid transducers..." — 명시적으로 2-way.
**Compliance_Standards**: SPS(Datasheet) p.3-4 하단 인증 마크 이미지에서 확인("3K59 OR 3JKB COMMERCIAL AUDIO SYSTEM", "c(UL)us LISTED", CE 마크) — 텍스트 레이어가 아닌 이미지 내 텍스트라 SKILL v1.13 PDF 이미지 처리 예외 규정(원문 인증 로고는 텍스트화되지 않는 경우가 많아 육안 확인)에 따라 확보. K1(2006/42/EC Machinery Directive)·GSL(WEEE-Reg-Nr)과 인증 체계가 상이 — 표기 방식이 다른 인증이므로 임의로 통일하지 않고 각 제품 원문 그대로 보존.
**WEEE_Marking**: 3개 문서 전량 스캔했으나 EU WEEE 폐기물 마킹이나 문구를 찾지 못함 — 미확인(K1/GSL은 명시적 WEEE 조항 있음, PANTHER는 미국 제조사 문서 특성상 다를 수 있으나 확정할 근거 없어 null 유지).

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [3] | 55 - 16000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak [1] | L: 150.5 / M: 150.5 / W: 149.5 | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL [2] | L: 127.5 dBZ / 144.5 dBZpk / 125.5 dBA (input +8.3 dBV); M: 126.5 dBZ / 144 dBZpk / 125 dBA (input +6.8 dBV); W: 126.5 dBZ / 142.5 dBZpk / 123 dBA (input +6.4 dBV) | - |
| Nominal_Directivity_Horizontal_deg | L: 80 / M: 95 / W: 110 | deg |
| Nominal_Directivity_Vertical | null | - |
| DSP_Preset_Name | null | - |
| Cardioid_Pattern_Array_Min_Size | 4 | count |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.1-2 "Specifications" 표(ACOUSTICAL); AE p.1 "Performance specifications for a typical production unit... measured at 1/3-octave resolution"; OM p.1-2.
**[1] Max_SPL_Peak 측정 조건**: SPS 각주 "Maximum Sound Level is the Lpeak measured using burst noise", AE는 "measured in free-field at 4 m referred to 1 m using noise"로 더 상세 — 두 문서 값은 완전 일치(교차검증 성공), 측정 방법론 서술은 AE가 더 상세하여 채택.
**[2] AES75_Max_Linear_SPL(v1.2, 사용자 피드백 반영, 단일 Key로 통합)**: AES75-2022는 AES(Audio Engineering Society)가 공식 발간한 브랜드 무관 업계 표준(Max Linear Sound Level 측정법)이므로, 이 표준을 사용하는지 여부는 계속 동기화 대상이다. 다만 이전 버전에서는 dBZ/dBZpk/dBA/기준입력레벨을 4개 별도 Key로 쪼갰는데, 이는 AES75 측정을 채택한 제조사가 "한 번에 보고하는 하나의 묶음 데이터"를 인위적으로 원자화(atomize)한 것이었다 — 이 표준을 쓰지 않는 제조사(K1/K2/GSL) 입장에서는 4개의 개별 null이 아니라 "AES75 측정 자체를 제공하지 않는다"는 하나의 사실이므로, 표 순수성 원칙(Key/Value/Unit)의 취지를 유지하면서도 실질적으로는 하나의 복합값(compound value)을 갖는 단일 Key로 합쳤다. 베리언트별 dBZ/dBZpk/dBA와 그 측정에 사용된 기준 입력 레벨(dBV)을 Value 칸에 함께 병기.
**DSP_Preset_Name**: K1처럼 명명된 프리셋을 앰프에 로드하는 방식이 아니라(PANTHER는 자체 DSP 내장), OM/AE/SPS 어디에도 프리셋 이름 개념이 없음 — 대신 Meyer Sound Compass/Galileo GALAXY 소프트웨어로 시스템 레벨 제어(OM p.14 "Groups and Controls in Compass"). 프리셋 명명 체계 자체가 없어 미확인.
**Nominal_Directivity_Vertical**: 3개 문서 전량 스캔했으나 수직 지향각 수치나 서술 발견 못함 — 미확인.
**Cardioid_Pattern_Array_Min_Size**: SPS 각주 3 — "Arrays of four units and longer functionally create a cardioid polar pattern... does not require any user settings."
**[3] Operating_Frequency_Range_Hz -> Usable_Bandwidth_Hz 개명(v1.4, 전수 검사로 발견)**: 12개 스피커 파일 전체 Key 목록 교차 검사 결과, PANTHER만 이 개념을 "Operating_Frequency_Range_Hz"라는 별도 이름으로 갖고 있었음을 발견 — K1~L2/GSL8/GSL12는 모두 "Usable_Bandwidth_Hz"로 동일 개념(기본 동작 대역폭)을 표현한다. SPS 원문 "Operating Frequency Range"라는 표현 자체는 그대로였으나(각주 없이 dB 임계값 미표기, L2와 유사한 사례), 브랜드마다 다른 원문 라벨을 그대로 Key 이름에 반영하면 안 된다는 원칙(SKILL v1.14 "동기화 대상 Key의 범위 제한")에 따라 범용 Key 이름으로 통일했다 — 값 자체는 변경 없음(55-16000Hz).

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 2 x 12" long-excursion cone drivers | - |
| LC_Transducer | null | - |
| HF_Transducer | 2 x 3" diaphragm compression drivers coupled to a constant-directivity horn through a patented ribbon emulation manifold | - |
| LF_Acoustical_Load | null | - |
| LC_Acoustical_Load | null | - |
| HF_Acoustical_Load | constant-directivity horn (ribbon emulation manifold) | - |
| Passive_Crossover_Network | No | - |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | null | W |
| LF_Nominal_Impedance | 4 | Ohm |
| LC_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall | null | Ohm |
| HF_Nominal_Impedance | 8 | Ohm |
| MF_Transducer | null | - |
| MF_Acoustical_Load | null | - |
| MF_Nominal_Impedance | null | Ohm |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.3 "TRANSDUCERS" 표; AE p.1 (드라이버 상세 서술, "ribbon emulation manifold" 등 SPS에 없는 표현 추가 확인).
**Passive_Crossover_Network=No 판단 근거**: OM/AE/SPS 3개 문서 전체에서 "crossover" 키워드 전량 스캔 결과 0건 검출 — 4채널 Class-D 앰프가 LF 2채널+HF 2채널을 개별 구동하는 구조로 판단(확정적 비존재, SKILL v1.13 원칙).
**MF_* 계열 null 사유(비적용)**: PANTHER는 2-way(LF+HF)이며 MF 대역이 없음. MF는 웨이/대역 구조라는 브랜드 무관 범용 개념(3-way K1에는 실값, 2-way PANTHER는 비적용)이므로 계속 동기화 대상으로 유지.
**Front_LF/Side_LF/Power_Handling_Front_LF/Power_Handling_Side_LF_MF_HF 계열 Key 삭제(v1.1, 사용자 정책 변경)**: 이전 버전에서는 GSL8/GSL12에서 유래한 이 6개 Key를 PANTHER에 비적용/미확인 null로 동기화했으나, 사용자 피드백(2026-07-16)에 따라 완전히 삭제했다 — GSL의 전방/측면 LF 물리 배선 구조를 그대로 반영한 브랜드 고유 명칭이며, PANTHER나 다른 브랜드에는 대응 개념 자체가 없다. 판단 기준은 K1_v1.4.md 참조.
**LF_Acoustical_Load**: OM/AE/SPS 어디에도 LF 인클로저 로딩 방식(bass-reflex 등) 명시적 표기 없음 — 미확인.

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
| Analog_Source_Drive_Requirement | +24 dBu into 50 Ohm (for maximum peak SPL) | - |
| Digital_Input_Connector | Neutrik etherCON TOP | - |
| Digital_Input_Format | AVB, Milan Certified | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14-17(Amplification and Audio, Audio Connectors, Analog Audio Input/Loop Output, Calculating Analog Input Load Impedance); SPS p.3(ANALOG/DIGITAL AUDIO INPUT); AE p.1.
**Analog_Input_Pinout**: OM 텍스트 레이어에 핀 번호별 배선이 명시되어 있어(Pin 1/2/3 문자 표기) 별도 이미지 분석 없이 텍스트 우선 스캔만으로 확보 — Case(커넥터 외피)는 Earth(AC) ground/chassis.
**Analog_Loop_Output**: Input과 동일 배선(패럴렐), 다중 PANTHER를 하나의 소스에서 데이지체인 가능. OM 특기사항: "The Loop output connector is wired in parallel to the Input connector and transmits the unbuffered source signal even when the loudspeaker is powered off."
**Analog_Source_Drive_Requirement**: OM/SPS 교차검증 일치(+24 dBu/dBU into 50 Ohm — 대소문자 표기 차이만 있음, 동일 물리량).
**Input_Connector/Link_Connector/PA_COM_Pinout_*/NLT4_Pinout_* Key 삭제(v1.2, 사용자 피드백 반영)**: PANTHER 자신의 3개 원본 문서(OM/AE/SPS)를 "PA-COM"/"NLT4"/"speakON" 키워드로 전량 스캔한 결과 0건 검출 — PANTHER의 오디오 입력 커넥터는 이 문서들에 명시된 대로 아날로그 XLR 3-pin(Analog_Input_Connector/Analog_Loop_Output_Connector)과 디지털 Neutrik etherCON(Digital_Input_Connector, Milan AVB) 두 종류뿐이며, 둘 다 이미 PANTHER 자신의 Key로 온전히 표현되어 있다. K1/GSL에서 유래한 PA-COM/NLT4 핀아웃 Key는 이 두 실제 커넥터 중 어느 것과도 대응되지 않아 null로 남기지 않고 삭제했다.

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

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.2 "AC POWER"/"POWER CONSUMPTION"; AE p.1-2; OM p.9-12(Assembly of Power Cables, PANTHER Voltage Requirements, Power Supply).
**교차검증**: Max_Long_Term_Continuous_Power(1100W)/Burst_Power(2200W)/AC_Nominal_Voltage_Range(200-240VAC)는 SPS·AE·OM 3개 문서 모두 일치.
**[1] AC_Operating_Voltage_Range/Max_Cable_Round_Trip_Resistance**: OM에만 있는 상세 정보(SPS/AE는 명목 전압 범위만 제공) — PANTHER는 TPL(True Power Limiting) 작동 시 정전력 부하로 동작해 전압이 낮아지면 전류가 증가하므로, 230V 소스 기준 케이블 왕복 저항이 5Ω을 넘으면 피크 출력 시 AC 인렛 전압이 160V 미만으로 떨어질 수 있다(OM 원문 근거).
**Idle_Power**: SPS에만 명시(AE/OM에는 별도 대기전력 수치 없음).

## protection_thermal

self-powered 아키텍처 전용 신규 섹션 — K1/GSL8/GSL12에는 비적용.

| Key | Value | Unit |
|---|---|---|
| Limiter_Type | TruPower limiting | - |
| Limiter_Indication | On/Status LED: solid yellow 1 sec = HF channel limiting; pulsing yellow = LF channel limiting | - |
| Cooling_Type | forced-air, 2 variable-speed fans | - |
| IP_Rating [1] | 65 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: AE p.1("TruPower limiting"); OM p.19-20(On/Status and Limiting Indication), p.20-21(Amplifier Cooling System); OM p.8, p.9, p.15(IP65, UL50E — AC 인렛/오디오·네트워크 커넥터 공통).
**[1] IP_Rating 소스 간 충돌**: SPS(Datasheet) p.2와 AE p.2는 모두 "IP55, when connected to cables terminated with Neutrik TOP connectors"로 명시. 반면 OM은 별도로 3곳에서(p.1-2 서문, p.8 AC 인렛 커넥터, p.15 아날로그/네트워크 커넥터) 일관되게 "IP65, UL50E"로 명시하며 인증 규격(UL50E)까지 병기한다. 두 값 모두 보존 — 채택 근거는 브랜드 기본 우선순위 원칙("가장 상세하고 개정 이력이 있는 문서 우선")에 따라, 인증 규격까지 명시하며 3곳에서 반복 확인되는 OM의 IP65를 채택했다. 다만 SPS/AE 양쪽 모두 IP55로 일치하는 점을 고려하면 OM의 오기재 가능성도 배제할 수 없어, 두 값을 모두 표(위)와 이 각주에 병기해 향후 재검증 여지를 남긴다.

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

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.2("Nebra software is used to monitor PANTHER telemetry data... transmitted via the network connection. The Wink function identifies loudspeakers..."), p.19("Ethernet/Network Connectivity LED... illuminated when a 100 bT link is established").
**AES67_Support/Service_Port_Type**: 앰프 카테고리 용어 매핑 사전에서 유래한 Key(d&b 제품군에서 확립) — PANTHER 3개 문서 전량 스캔했으나 AES67이나 별도 서비스 포트(USB-C 등) 언급 없음 — 미확인.

## amplification_requirements

self-powered이므로 외부 앰프 매칭 개념이 원천적으로 비적용.

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | null | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (2-way, 4 discrete driver channels via internal 4-channel Class-D amplifier) | - |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: PANTHER는 자체 앰프를 내장한 self-powered 제품이라 K1/GSL처럼 외부 앰프와 매칭할 필요가 없다 — Compatible_Amplified_Controller 등은 개념 자체가 없어 비적용.
**Crossover_Type**: AE 원문 "The loudspeaker shall incorporate internal processing and a 4-channel class-D amplifier" — LF 2발+HF 2발 각 드라이버가 개별 채널로 구동되는 것으로 판단(4채널=4드라이버 1:1 매칭 추정). Passive_Crossover_Network=No(transducers 섹션 확정) 근거와 정합.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | end frames with captive GuideALinks secured with quick-release pins (QRP); QuickFly rigging system | - |
| Inter_Enclosure_Angles_deg | 0.5, 1, 2, 3, 4, 5, 6, 7, 8, 9 | deg |
| Handles | detachable side handles | - |
| Weight_Net | 68 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.2 "PHYSICAL"(Rigging 행); OM p.22-26(PANTHER Rigging Accessories, MVP Motor V Plate).
**Inter_Enclosure_Angles_deg**: SPS 원문 "quick-release pins that allow 0.5°– 9° splay angles" — K1/GSL처럼 이산적인 개별 각도값 목록이 아니라 연속 범위(0.5°-9°)로 표기되어, 이 프로젝트의 다른 제품과 표기 형식이 다름을 인지하고 원문 그대로 범위로 기재(임의로 이산값을 만들어내지 않음).
**Handles**: SPS는 개수를 명시하지 않고 "detachable side handles"로만 서술 — 정확한 개수는 미확인.

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

**출처**: AE p.2 "Dimensions shall be 38.15 in (969 mm) wide, 14.85 in (377 mm) high, and 22.25 in (565 mm) deep" — W/H/D 축이 원문에 명시적으로 라벨링되어 있어, K1/GSL과 달리 축 불확실성 없이 확정. Width_mm/Height_mm/Depth_mm는 이번에 PANTHER 투입으로 신설된 Key(향후 K1/GSL의 Dimensions_Raw도 도면을 육안 확인하면 이 형태로 전환 가능).
**Dimensions_Raw**: PANTHER는 축이 명확히 확인되어 이 Key(K1/GSL의 축-미확정 원시값 보존용)가 필요 없음 — 비적용이 아니라 상위 호환 Key(Width/Height/Depth_mm)로 대체되었다는 의미에서 null 처리.
**IP_Rating**: protection_thermal 섹션의 IP_Rating(충돌 있음, 55 vs 65)으로 이전 — physical 섹션에서는 중복 방지를 위해 null.
**Rigging_Components_Material/Finish_Type**: 3개 문서 전량 스캔했으나 리깅 부품 재질/피니시 타입 명명 체계에 대한 별도 서술 없음 — 미확인.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: PANTHER는 K1처럼 명명된 프리셋 조합 가이드를 OM/AE/SPS에 포함하지 않는다 — 대신 Meyer Sound MAPP System Design and Prediction 소프트웨어로 어레이/서브우퍼(LFC 제품군) 조합을 시뮬레이션하는 방식(OM 명시: "PANTHER is designed to be deployed alongside Meyer Sound LFC products"). 소프트웨어 기반 시뮬레이션 결과물은 이 세션에 제공되지 않아 미확인.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: preset_guide_and_matching과 동일 — MAPP 소프트웨어가 딜레이 정렬을 자동 계산하는 방식으로 추정되며, OM에 K1과 같은 고정 딜레이 기본값 표가 없음.

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

**출처**: OM p.24-26(Table 3. MVP Motor V Plate load ratings — "Maximum Number of PANTHER Loudspeakers + MG-PANTHER Grid Kit: 25"), p.23-24(MTF-LYON/LEOPARD Transition Frame Kit 서술).
**안전계수**: 모든 리깅 액세서리 공통 5:1 안전계수(OM 반복 명시) — K1의 "safe limit/maximum limit" 이원 체계와 달리 PANTHER는 MAPP 소프트웨어 시뮬레이션으로 개별 배치의 안전성을 검증하는 방식이 기본이며("Always model each array configuration in Meyer Sound's MAPP System Design and Prediction software... Do not suspend an array when the Safety Limits Analysis in MAPP displays 'Configuration has exceeded the rated load capacity.'"), OM에 고정 수치로 명시된 것은 MVP Motor V Plate 구성(25대)과 LEOPARD 다운필 전환프레임(최대 10대) 두 건뿐이다.
**Safe_Limit 열 null 사유**: OM은 K1(Soundvision 기반이지만 safe/maximum 이원 수치를 직접 제공)과 달리, MAPP 소프트웨어가 "exceeded/not exceeded" 이진 판정만 제공하는 것으로 서술되어 별도의 "safe limit"(항상 만족) 수치를 찾지 못함 — 미확인.
**기본 PANTHER 단일 인클로저(MG-PANTHER Grid Kit 단독, MVP 미사용) 최대 대수**: OM 본문에 MVP 없이 Grid Kit만 사용하는 기본 구성의 별도 상한 수치가 명시되어 있지 않아(MVP 구성표에서만 25라는 수치 확인) 미확인 처리.
**Safety_Factor**: OM 전체에서 반복 확인되는 값(MVP Motor V Plate, PBF-LYON, MTF-LYON/LEOPARD Transition Frame 모두 5:1) — K1의 4:1(2006/42/EC 기준)과 다른 수치, 임의로 통일하지 않고 원문 그대로 보존.
**Max_Wind_Load(미확인)**: OM에 "prevent movement due to light wind", "land arrays when there are high winds"처럼 정성적 서술만 있고 K1처럼 구체적 수치(예: Beaufort 등급)가 명시되어 있지 않음 — 3개 문서 전량 스캔 결과 확정.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Nominal_Directivity_Vertical, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, Frequency_Response_5dB_Hz, DSP_Preset_Name, LF_Acoustical_Load, RMS_Power_Handling_LF, RMS_Power_Handling_MF, RMS_Power_Handling_HF, AES67_Support, Service_Port_Type, Handles(정확한 개수), Rigging_Components_Material, Finish_Type, Max_Wind_Load, preset_guide_and_matching(전 항목), delay_defaults(전 항목), mechanical_safety(Safe_Limit 열, 기본 Grid Kit 단독 구성 상한) — 20건. (AES75_Max_Linear_SPL은 PANTHER 자신이 실값을 보유한 Key이므로 null 목록에서 제외.)
**비적용(PANTHER 아키텍처상 개념 자체 불성립, K1/GSL에서 유래)**: MF_Transducer, MF_Acoustical_Load, MF_Nominal_Impedance, Compatible_Amplified_Controller, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Dimensions_Raw, IP_Rating(physical 섹션, protection_thermal로 이전) — 8건. Input_Connector/Link_Connector/PA_COM_Pinout_*/NLT4_Pinout_*는 PANTHER 자신의 OM/AE/SPS 전량 스캔 결과 PA-COM/NLT4/speakON류 커넥터 언급이 전혀 없어(실제 커넥터는 Analog_Input_Connector/Digital_Input_Connector로 이미 표현됨) 애초에 생성하지 않음(v1.2, 사용자 피드백).

**총계**: null 28건 (미확인 20건 + 비적용 8건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Passive_Crossover_Network(No, 3개 문서 전량 스캔 근거) — 이 수치는 Kiva II/L2 투입 이전 기준. Kiva II/L2 투입으로 신설된 6개 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)가 이 파일에 모두 비적용 null로 추가 반영되어 실제 총계는 위 수치+6건이다(이 제품은 LC 대역·단일 채널 패시브 아키텍처·멀티모듈 구조가 모두 없음). v1.1에서 GSL 고유 배선 구조 명칭 8개 Key 삭제, v1.2에서 스피커 레벨 다채널 커넥터 Key(Input_Connector/Link_Connector/PA_COM_Pinout_*/NLT4_Pinout_*, 7개) 추가 삭제, AES75_Max_Linear_SPL 단일 Key로 통합(실값 보유), Frequency_Response_3dB/6dB_Hz + RMS_Power_Handling_LF/MF/HF null 추가.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리 Phase 3-2(Meyer Sound 신규 브랜드 교차 테스트). K1_v1.2.md를 뼈대로 재사용하되 self-powered 전용 신규 섹션(power_supply, protection_thermal, network_monitoring) 4개 신설. 3개 소스(OM/AE/SPS) 전체 교차검증 — IP_Rating 소스 간 충돌(SPS/AE=IP55 vs OM=IP65) 발견 및 보존. PANTHER-L/M/W 3개 지향각 베리언트를 별도 파일이 아닌 Value 병기 방식으로 1개 파일에 통합(GSL8/GSL12와 다른 처리 — 공식 문서가 하나의 제품명으로 취급). Width_mm/Height_mm/Depth_mm 신규 Key 도입(AE에 축이 명시적으로 라벨링되어 있어 가능). |
| v1.1 | 사용자 정책 변경(2026-07-16) 반영 — GSL 고유 배선 구조 명칭(Front_LF/Side_LF/Power_Handling_Front_LF/Power_Handling_Side_LF_MF_HF) 8개 Key를 transducers 섹션에서 삭제. 판단 기준은 K1_v1.4.md 참조. |
| v1.2 | 사용자 피드백(2026-07-16) 반영 — (1) Input_Connector/Link_Connector/PA_COM_Pinout_*/NLT4_Pinout_* 완전 삭제: PANTHER 자신의 OM/AE/SPS 3개 문서를 "PA-COM"/"NLT4"/"speakON" 키워드로 전량 스캔한 결과 0건 검출, 실제 커넥터는 Analog_Input_Connector/Analog_Loop_Output_Connector/Digital_Input_Connector로 이미 온전히 표현되어 있어 K1/GSL 유래 커넥터 모델별 핀아웃 Key를 null로 남기지 않고 삭제. (2) AES75_Max_Linear_SPL_dBZ/dBZpk/dBA/Reference_Input_Level 4개 Key를 AES75_Max_Linear_SPL 단일 Key로 통합 — AES75는 브랜드 무관 업계 표준이나, 하나의 측정 번들을 인위적으로 원자화하지 않기 위함. (3) K1/K2 유래 Frequency_Response_3dB/6dB_Hz, RMS_Power_Handling_LF/MF/HF를 null로 동기화. |
| v1.3 | Kiva II/L2(신규 제품) 투입으로 신설된 6개 범용 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)를 이 제품에 비적용 null로 동기화 반영(SKILL v1.15 원칙 — 브랜드 무관 범용 개념이므로 동기화 대상). |

| v1.4 | Operating_Frequency_Range_Hz -> Usable_Bandwidth_Hz 개명 — 12개 파일 전수 Key 목록 대조 감사에서 발견된 PANTHER만의 이름 불일치 수정(같은 개념을 다른 제품은 모두 Usable_Bandwidth_Hz로 표현). |
