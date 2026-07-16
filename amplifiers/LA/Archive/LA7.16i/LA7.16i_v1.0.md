# LA7.16i - Master Spec Schema

Schema_Version: 1.0 (Phase 3-1 신규 제품 파싱 - Upload 폴더 4개 제품 중 마지막)
최종 작업 일시: 2026-07-15 21:43 (수요일)
Manufacturer: L-Acoustics
Product_Category: Amplified_Controller (16-channel install-specific Class D amplifier with integrated DSP)
Form_Factor: 19 inch rack, 2U

## 출처 등록부 (Source Registry)

| Source_ID | Document | Version / Date |
|---|---|---|
| OM | Owner's Manual (EN) | version 5.0, distribution Dec. 1, 2025 |
| AE | Architects and Engineers Spec (docx) | undated |

**소스 범위에 대한 참고**: 기존 제품과 동일하게 `Upload` 폴더에 OM PDF와 AE docx 2개 소스만 제공되어 이 2개만으로 파싱했다. L-Acoustics 브랜드 규칙에 따라 출처 표기는 OM의 페이지/목차 위치를 최우선으로 기록한다.

본 파일은 LA1.16i_v1.0.md의 Key 목록 및 마크다운 구조를 뼈대로 복제하여 작성되었다(SKILL v1.10 작업공간 관리 규칙에 따른 신규 제품 스켈레톤 재사용 방식) — LA7.16i는 L-Acoustics OM 자체가 "LA1.16i, LA2Xi, LA4X, LA7.16(i)"를 Q-SYS 플러그인 지원 목록으로 함께 묶고 있으며(OM p.17), L-SMART가 최초로 LA7.16i에서 도입된 사실(OM p.9 "First introduced with... LA7.16i")과 별개로, 커넥터 아키텍처(터미널 블록 스피커 출력, 12핀 AES/ANA+GPIO+24VDC 통합 단자대, LED-only 프론트패널)가 LA1.16i와 동일 계열이므로 이를 기반 파일로 채택했다. 다만 LA7.16i는 LA1.16i와 달리 **브릿지 모드를 지원하지 않으며**(OM p.16, p.34 명시적 확정), **단일 PSU**(LA1.16i는 2개), **32A powerCON 커넥터**(LA1.16i는 V-Lock IEC)를 사용하는 등 실질적 아키텍처 차이가 다수 존재한다(아래 각 섹션 각주 참조). 신규 발견 Key는 없다 — LA1.16i/LA2Xi 파싱 단계에서 이미 스키마에 편입된 Key(BTL 출력 5종, AES67_Support, Service_Port_Type, Speaker_Terminal_Block_SE_BTL_Wiring 등)를 그대로 사용하되, 브릿지 미지원 제품 특성에 맞게 "확정된 비존재"(0/No) 값으로 채웠다.

---

## amplification (증폭부)

| Key | Value | Unit |
|---|---|---|
| Channel_Count_In | 16 | ch |
| Channel_Count_Out | 16 | ch |
| Amplification_Class | High-efficiency Class D | - |
| Rated_Power_Per_Ch_2.7_Ohms | null | W |
| Rated_Power_Per_Ch_4_Ohms | 1000 | W |
| Rated_Power_Per_Ch_8_Ohms | 920 | W |
| Rated_Power_Per_Ch_16_Ohms | 580 | W |
| Peak_Power_Per_Ch_4_Ohms | 1100 | W |
| Peak_Power_Per_Ch_8_Ohms | 1300 | W |
| Peak_Power_Per_Ch_16_Ohms | 700 | W |
| Total_Power_Capability | null | W |
| Max_Output_Voltage_Peak | 152 | V |
| Amplification_Gain | 32 | dB |
| Output_Delay_Range | 0 - 1000 | ms |
| Bridging_Support [1] | No - LA7.16i does not support any bridge mode (confirmed absent) | - |
| Rated_Power_Per_Ch_BTL_8_Ohms [1] | null | W |
| Rated_Power_Per_Ch_BTL_16_Ohms [1] | null | W |
| Peak_Power_Per_Ch_BTL_8_Ohms [1] | null | W |
| Peak_Power_Per_Ch_BTL_16_Ohms [1] | null | W |
| Rated_Power_Per_Ch_PBTL_4_Ohms [1] | null | W |
| Rated_Power_Per_Ch_PBTL_8_Ohms [1] | null | W |
| Rated_Power_Per_Ch_PBTL_16_Ohms [1] | null | W |
| Peak_Power_Per_Ch_PBTL_4_Ohms [1] | null | W |
| Peak_Power_Per_Ch_PBTL_8_Ohms [1] | null | W |
| Peak_Power_Per_Ch_PBTL_16_Ohms [1] | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.62 "Specifications > General > Output power" (최우선) / AE "Technical requirements > Amplification"

**측정 조건**: `Peak_Power_Per_Ch_*`는 12 dB Crest Factor, 2 ms, 1 kHz, all channels driven, sine burst 조건(OM/AE 일치, 수치 완전 동일). `Rated_Power_Per_Ch_*`는 CEA-2006/490A, 20 ms, ≤1% THD, 1 kHz, all channels driven, sine burst 조건(OM p.62 스펙 표에서만 확인, AE는 CEA 기준 수치를 별도 제공하지 않고 12dB Crest Factor 값만 반복 — LA1.16i와 동일 패턴). Max_Output_Voltage_Peak(152V, loaded 8Ω, single sine wave 1kHz)와 Amplification_Gain(32dB)은 OM 스펙 표(p.62)에만 존재하며 AE는 두 항목 모두 언급하지 않음(충돌 아닌 단순 누락). Rated_Power_Per_Ch_2.7_Ohms, Total_Power_Capability는 기존 제품과 동일한 사유로 null 유지.

**[1] Bridging_Support 확정 비존재**: OM은 두 위치에서 명시적으로 브릿지 모드 미지원을 경고한다 — p.16 "Speaker outputs" 절: "Risk of speaker and amplified controller damage: LA7.16i does not support any bridge mode." / p.34 "Speaker" 절에 동일 경고 반복. AE의 "Architecture: 16 x 16"에도 브릿지 모드(BTL/PBTL) 언급이 전혀 없다(LA1.16i/LA2Xi AE가 "Bridge Mode" 아키텍처를 별도 명시한 것과 대조적). 전체 문서(OM 전량, AE 전량) 검색으로 브릿지 관련 서술이 전무함을 확인하여 Bridging_Support="No"로 확정했다. BTL/PBTL 출력 Key 10종(각 4/8/16Ω 또는 4/8/16Ω Rated/Peak)은 LA4X_v1.0.md 선례(Bridging 미지원 제품의 BTL/PBTL 전력 Key는 "0 W"가 아니라 "해당 동작 모드 자체가 존재하지 않아 측정값이 정의되지 않음"을 의미하는 null로 표기)를 따라 동일하게 null로 통일했다 — Bridging_Support 자체는 기능의 존재 여부를 묻는 Key이므로 "No"(확정 비존재)가 맞으나, BTL/PBTL Rated/Peak_Power_Per_Ch_* Key는 "특정 부하 임피던스에서 측정된 출력 전력값"을 담는 Key로서 그 동작 모드가 아예 없는 제품에서는 0W(측정된 실제 출력이 0이라는 의미)가 아니라 "정의되지 않음(null)"이 더 정확한 표현이다(SKILL v1.9 원칙과 LA4X 선례에 따른 정정). Speaker_Terminal_Block_SE_BTL_Wiring 및 PBTL_Activation_Method도 connectivity 섹션에서 동일 원칙(null/N/A)으로 처리했다.

---

## power_supply (전원부)

| Key | Value | Unit |
|---|---|---|
| PSU_Type [2] | 1 universal Switched Mode Power Supply (SMPS) with Power Factor Correction (PFC) | - |
| Mains_Voltage_Range | 100 - 240 (+/-10%) | V AC |
| Mains_Frequency_Range | 50 - 60 | Hz |
| Nominal_Current_100_120V [3] | 30 | A |
| Nominal_Current_200_240V | 16 | A |
| Power_Factor | greater than 0.95 (at full load) | - |
| Power_Consumption_Idle | 138 | W |
| Power_Consumption_Standby | 18 | W |
| Mains_Connector [4] | 32 A powerCON | - |
| PSU_Mains_Rated_Power | 2800 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.63 "Specifications > Power supply", p.23-24 "Installation > Electrical specifications, Power consumption" (최우선) / AE "Technical requirements > Mains rating, Nominal current requirements"

**측정 조건**: Power_Consumption Idle/Standby는 230V 기준 값(OM p.24: Idle 1.0A/138W, Standby 0.8A/18W; 120V/100V는 전류만 배율 환산, W값은 동일하게 138W/18W로 명시 — LA1.16i와 달리 전압별 W값이 모두 동일하게 표기됨). AE는 Idle/Standby 소비전력을 별도 언급하지 않는다.

**[2] PSU_Type — LA1.16i와의 아키텍처 차이**: LA1.16i는 채널 1-8/9-16을 각각 담당하는 2개의 독립 SMPS를 사용하나(OM p.12), LA7.16i는 OM 전반에서 일관되게 단수형("The PSU", "a universal Switched Mode Power Supply")으로 서술한다(p.9, p.16, p.63 스펙 표). 이는 16채널 전체를 L-SMART가 동적으로 관리하는 단일 PSU 아키텍처이며, OM p.9는 "The PSU can provide extremely high short-term peak power and 7000 W for longer hold times, and this energy is delivered dynamically and intelligently to the advanced Class-D output stages"라고 명시한다. 이 7000W 장시간 홀드 파워 수치는 기존 스키마에 대응 Key가 없어 별도 Key화하지 않고 본 각주에만 기록한다.

**[3] Nominal_Current_100_120V 표기 방식**: LA1.16i의 OM/AE는 100V(20A)와 120V(15A)를 별개 수치로 구분했으나, LA7.16i의 OM은 안전 섹션(p.6)과 스펙 표(p.63) 모두에서 "100-120V: 30A"로 통합 단일 수치를 제공하며 100V/120V를 구분하지 않는다. AE도 200-240V 전류값(16A)만 명시하고 100-120V 수치는 제공하지 않는다(OM 단독 출처, 충돌 아닌 누락). 따라서 LA1.16i처럼 두 조건을 병기할 필요 없이 OM의 통합값(30A)을 그대로 채택했다.

**[4] Mains_Connector — LA1.16i와의 아키텍처 차이**: LA1.16i는 "V-Lock compatible IEC" 커넥터를 사용하나, LA7.16i는 최대 전류 요구량(100-120V 기준 30A)이 더 높아 "32 A powerCON" 커넥터를 사용한다(OM p.63 Power supply 표 Connector 행, p.24 "Plugging the amplified controller" 절 powerCON 다이어그램). 이는 실제 제품 사양 차이이며 소스 간 충돌이 아니다.

---

## audio_performance (음향 스펙)

| Key | Value | Unit |
|---|---|---|
| Frequency_Response | 20 - 20000 | Hz |
| THD_N_8ohm | less than 0.1 | % |
| THD_N_4ohm | null | % |
| Output_Dynamic_Range | greater than 119 | dB |
| Noise_Level [5] | less than -79 | dBV |
| Channel_Separation | greater than 65 | dB |
| Damping_Factor | 500 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.62 "Specifications > General" (최우선) / AE "Technical requirements > Amplification"

**측정 조건**: Frequency_Response는 ±0.05dB 허용오차, 20Hz-20kHz 기준(OM/AE 일치). THD_N_8ohm은 20Hz-20kHz, 8Ω, 60W 출력 기준(OM/AE 일치, 충돌 없음). Output_Dynamic_Range/Noise_Level은 20Hz-20kHz, 8Ω, A-weighted, digital input 기준. Channel_Separation은 1kHz, 8Ω, 60W 기준(OM/AE 일치). Damping_Factor는 20Hz-1kHz, 8Ω load 기준 — OM에만 존재(AE는 damping factor를 언급하지 않음, 충돌 아닌 누락). THD_N_4ohm은 두 소스 모두 4Ω 조건 수치를 제공하지 않아 null 처리. LA7.16i는 브릿지 모드를 지원하지 않으므로 LA1.16i/LA2Xi 파일과 달리 SE/BTL 값 분리가 불필요하다.

**[5] Noise_Level 충돌**: OM(p.62)은 "< -79 dBV"로 명시. AE는 동일 항목을 "Noise level < -78 dBV"로 표기 — 수치가 1dB 다르다(단위는 이번엔 양쪽 모두 dBV로 일치하여 LA1.16i의 dBu/dBV 단위 불일치 사례와는 다른 패턴). 두 값 모두 보존 — OM 최우선 원칙에 따라 -79dBV를 Value로 채택하고, AE의 -78dBV는 본 각주에 병기한다.

---

## dsp (신호 처리)

| Key | Value | Unit |
|---|---|---|
| DSP_Processor [6] | Gen. 5 dual SHARCs, 32-bit floating point, 96 kHz sampling rate | - |
| DSP_Sampling_Rate | 96 (internal, fixed, independent from input Fs) | kHz |
| Routing_Matrix | 16x16 routing and summation matrix | - |
| EQ_Filters_Per_Output | null | - |
| Per_Channel_DSP_Tools | Multiband EQ, Array morphing, Air absorption compensation filter | - |
| Amplifier_Power_Management | L-SMART adaptive power management | - |
| Speaker_Protection | L-DRIVE (excursion, temperature, over-voltage) | - |
| Preset_Memory_User | null | slots |
| Preset_Memory_Factory | null | slots |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.13 "Technical description > Main features > Internal components", p.16 "DSP architecture", p.62 "Specifications > General" (최우선) / AE "Technical requirements > DSP"

**측정 조건**: 없음(사양값). Per_Channel_DSP_Tools는 OM p.16 "audio path parameters" 다이어그램의 채널별 처리 블록을 그대로 채택. DSP_Sampling_Rate는 OM p.14 "There is no AES/EBU external synchronization mode. The amplified controller's clock always runs at 96 kHz..." 및 AES67 모드 관련 "the amplified controller's clock always runs at 96 kHz, referenced to the PTPv2 network clock. The AES67 streams at 48 kHz are automatically upsampled to 96 kHz"(p.14)에 근거 — LA1.16i/LA7.16/LA12X와 동일 원칙.

**[6] DSP_Processor — LA1.16i와 다른 패턴(SHARC 명칭 OM에도 존재)**: LA1.16i의 OM은 "SHARC"라는 칩 브랜드명을 전혀 사용하지 않아 AE의 "SHARC" 언급을 각주로만 처리했으나, LA7.16i의 OM은 스펙 표(p.62)에서 "Digital Signal Processor (DSP): Gen. 5 dual SHARCs 32-bit, floating point, 96 kHz sampling rate"로 **SHARC 명칭을 직접 사용**한다. AE("Gen. 5 Dual SHARC 32-bit, floating-point, 96 kHz Sampling frequency")와도 완전히 일치하여 충돌이 없다. 따라서 LA1.16i와 달리 SHARC 명칭을 Value에 그대로 채택했다. EQ_Filters_Per_Output/Preset_Memory_User/Preset_Memory_Factory는 LA1.16i와 동일하게 OM/AE 어디에도 정확한 개수가 명시되지 않아 null 유지(임의 추론 금지 원칙).

---

## latency (지연 시간)

| Key | Value | Unit |
|---|---|---|
| Latency_Standard | 3.84 (independent from input Fs) | ms |
| Latency_Low_Mode | 1.18 (independent from input Fs) | ms |
| AVB_Max_Network_Latency | 2 | ms |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.64 "Specifications > Latency", p.64 "Specifications > Milan-AVB" (최우선) / AE "Technical requirements > DSP > Latency for analog and digital inputs"

**측정 조건**: Analog/AES-EBU 입력 기준, 입력 샘플링 주파수와 무관(OM/AE 일치, 수치 완전 동일 — LA1.16i·LA7.16(구형)과도 동일한 3.84ms/1.18ms 조합으로, 동일 세대 DSP 플랫폼 공유를 시사하나 이는 추론이며 문서상 명시적 확정은 없음).

---

## input_analog (아날로그 입력)

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Channels | 1 | ch |
| Input_Impedance | 22 | kOhm |
| Max_Input_Level | 22 | dBu |
| ADC_Architecture [7] | 1 x 32-bit A/D converter at 96 kHz sampling rate | - |
| Analog_Link_Type | active link with failsafe relay, shared 12-point terminal block (AES/ANA IN + AES/ANA LINK) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Technical description > Signal processing and amplification > Analog", p.14 "Signal inputs" (최우선) / AE "Technical requirements > Analog input"

**측정 조건**: Input_Impedance/Max_Input_Level은 balanced 기준, THD 1%(AE 명시; OM은 22dBu 헤드룸만 서술하고 임피던스 수치는 미제공 — 충돌 아닌 누락이므로 AE 값을 그대로 채택). Analog_Input_Channels(1)는 16개 증폭 채널 전체가 공유하는 보조(AUX) 입력 구조로 LA1.16i와 동일.

**[7] ADC 다이나믹레인지 충돌**: OM(p.15)은 "encoding dynamic range of 117 dB (A-weighted, 20 kHz bandwidth)"로 명시. AE는 동일 항목을 "121 dB dynamic range, 20 Hz - 20 kHz, A-weighted"로 표기 — 두 값이 다르다(117 vs 121 dB). 두 값 모두 보존 — ADC_Architecture Value에는 다이나믹레인지 수치를 넣지 않고 컨버터 구성만 기재했으며, 상충 수치는 본 각주에 병기한다. AE의 "121 dB"는 LA1.16i AE·LA7.16(구형) AE의 동일 항목 수치와도 정확히 일치하는데, 이는 AE 문서 작성 시 동일 템플릿 수치가 여러 제품에 걸쳐 반복 사용되었을 가능성을 시사한다(추정일 뿐, 임의로 배제하지 않음 — LA1.16i 파일 각주[11]과 동일 패턴).

---

## input_digital (디지털 입력)

| Key | Value | Unit |
|---|---|---|
| Digital_Input_Channels | 2 | ch |
| Digital_Standard | AES/EBU (AES3) | - |
| Supported_Sampling_Rates | 44.1 / 48 / 88.2 / 96 / 176.4 / 192 | kHz |
| Supported_Word_Length | 16 / 18 / 20 / 24 | bit |
| SRC_Output_Format | 24-bit at 96 kHz | - |
| SRC_Dynamic_Range | 140 | dB |
| SRC_THD_N | less than -120 | dBFS |
| Digital_Input_Gain_Range | -12 to +12 | dB |
| Digital_Link_Type | electronically buffered with failsafe relay, shared 12-point terminal block (AES/ANA LINK) | - |
| Max_AES_Cable_Length | 300 | m |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Technical description > Signal processing and amplification > AES/EBU", p.64 "Specifications > Input signal distribution" (최우선) / AE "Technical requirements > Digital input, Sample Rate Converter"

**측정 조건**: Max_AES_Cable_Length는 단일 케이블, 48kHz 샘플링, Belden 1696A 또는 Klotz OT234H 케이블 기준(OM p.15) — LA1.16i/LA7.16(구형)/LA12X와 동일 조건, 동일 값(300m). Digital_Input_Gain_Range는 0.1dB 스텝(OM p.15). 모든 항목 OM/AE 일치, 충돌 없음.

---

## input_avb (AVB / Milan-AVB 입력)

| Key | Value | Unit |
|---|---|---|
| AVB_Certification | MILAN and Avnu certified (Bridge and Listener) | - |
| AVB_Channels [8] | 16 | ch |
| AVB_Stream_Count | 16 (in normal or redundancy mode) | streams |
| AVB_Formats | AAF PCM32, IEC 61883-6 AM824 | - |
| AVB_Standards | IEEE 802.1BA-2011 / 1722-2016 / 1722.1-2013 | - |
| AVB_Bridge_Forwarded_Streams | up to 150 | streams |
| Redundancy_Type | Milan-AVB or AES67 seamless, automatic switchover and recovery (redundant mode requires star topology, port 1 = primary, port 2 = secondary) | - |
| Fallback_Modes | AVB or AES67 to AES/EBU or analog (shared input), user-defined mapping | - |
| AES67_Support | Yes - AES67-2023, 16 streams up to 8 ch each, L16/L24 at 48 kHz, PTPv2 clock, user-selectable alternative to Milan-AVB | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Signal inputs, Milan-AVB, AES67", p.64-65 "Specifications > Milan-AVB, AES67" (최우선) / AE "Technical requirements > AVB input"

**측정 조건**: AVB_Bridge_Forwarded_Streams는 OM 스펙 표(p.65)에만 존재(AE는 미언급, 충돌 아닌 누락). Switchover 조건은 AVB 또는 AES67 loss of lock(OM p.65).

**[8] AVB_Channels — 정의 기준**: LA1.16i 파일과 동일한 정의를 사용한다. OM(p.14)은 "capable of receiving up to 128 channels from 16 AVB streams at 48 kHz or 96 kHz"로 서술하나, 이는 16개 스트림 × 최대 8채널의 총 수신 용량이며 실제 증폭 채널 수(16)와는 다른 층위의 숫자다. Value는 증폭 채널 아키텍처와 일치하는 16을 채택하고, 총 수신 용량 128채널은 본 각주에만 기록한다(LA1.16i와 동일 원칙 적용, 두 파일 간 정의 일관성 유지).

---

## connectivity (커넥터)

| Key | Value | Unit |
|---|---|---|
| Input_Connectors | 1 x 12-point terminal block (AES/ANA IN + LINK, GPIO, 24 V DC backup), 2 x etherCON RJ45 (Milan-AVB/AES67 I/O) | - |
| Terminal_Block_Pinout [9] | 12핀: AES/ANA IN(+/-/Shield), GPIO 1, GPIO 3, +24V IN / AES/ANA LINK(+/-/Shield), GPIO 2, GND GPIO — 상세 핀맵은 하단 표 참조 | - |
| XLR_Pin_Polarity | null | - |
| Speaker_Connectors | 8 x female 4-point terminal block (pitch 5.08 mm) | - |
| SpeakON_Left_Pinout | null | - |
| SpeakON_Right_Pinout | null | - |
| CACOM_Pinout | null | - |
| SC32_Channel_Mapping | null | - |
| Speaker_Output_Accessories | null | - |
| Network_Connectors | 2x etherCON RJ45, 1 Gb/s | - |
| Service_Port_Type [10] | 1 x USB Micro-B (serial number < 168000 6000) or USB-C (serial number ≥ 168000 6000), 2.0 compliant (IP configuration via USB Terminal tool of LA Network Manager) | - |
| Speaker_Terminal_Block_SE_BTL_Wiring [1] | N/A - LA7.16i does not support bridge mode (confirmed absent); all 8 terminal block pairs wired as SE only (4 individual output channels per block pair) | - |
| PBTL_Activation_Method [1] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.13 "Front and rear panels", p.22 "Installation > General Purpose I/O (GPIO)", p.27 "Audio and network cabling > Connection panels, Speaker connectors", p.35 "Connector references" (최우선) / AE "Technical requirements > Connectors"

**측정 조건**: 없음(커넥터 규격 및 결선표). XLR/SpeakON/CACOM/SC32 관련 Key는 LA7.16i에 해당 커넥터가 전혀 존재하지 않아 null 처리(비적용). 극성 정보는 PDF 텍스트 레이어에 문자로 명시되어 있어 별도 이미지 분석 없이 텍스트 추출만으로 확인했다.

**[9] Terminal_Block_Pinout — LA1.16i와의 명칭 차이**: 구조는 LA1.16i와 동일한 12핀 단자대(24V DC 백업 전원, GPIO x3 + 공통 리턴, AES/ANA IN 3핀, AES/ANA LINK 3핀)이나, LA7.16i OM(p.22)은 GPIO 공통 리턴 핀을 "GND GPIO"로 표기하는 반면 LA1.16i OM은 "GPIO RTN"으로 표기한다(LA7.16(구형)의 "GPIO GND"와 유사). 기능은 동일한 것으로 판단되나 원문 표기가 다르므로 임의로 통일하지 않고 각 제품 파일에 원문 그대로 보존한다(SKILL v1.9 원칙). 상세 핀 배치:

| Pin 그룹 | Pin 이름 | 기능 |
|---|---|---|
| DSP 백업 전원 | +24V IN | DSP 백업 전원 입력(+), 24 V DC(±10%), 15 W minimum |
| DSP 백업 전원 | GND (⏚) | 24V DC 백업 회로 그라운드 |
| GPIO | GPIO 1 | General Purpose I/O 1 |
| GPIO | GPIO 2 | General Purpose I/O 2 |
| GPIO | GPIO 3 | General Purpose I/O 3 |
| GPIO | GND GPIO | GPIO 공통 리턴 |
| AES/ANA IN | + | 입력 신호 +(hot) |
| AES/ANA IN | - | 입력 신호 -(cold) |
| AES/ANA IN | ⏚ (shield) | 입력 실드/그라운드 |
| AES/ANA LINK | + | 데이지체인 출력 신호 + |
| AES/ANA LINK | - | 데이지체인 출력 신호 - |
| AES/ANA LINK | ⏚ (shield) | 출력 실드/그라운드 |

출처: OM p.13(핀 목록), p.22(GPIO 다이어그램 및 표), p.25(24V DC 다이어그램), p.29(analog/digital connectors 다이어그램).

**[10] Service_Port_Type — 시리얼 번호 기준 하드웨어 개정**: LA1.16i 파일은 단일 "USB-C" 값을 채택했으나, LA7.16i의 OM(p.13, 개정이력 p.11 v5.0 항목: "Updated Front and rear panels to reflect new USB-C port introduced in latest LA7.16i revision")은 두 세대의 USB 포트를 명시적으로 구분한다: 시리얼번호 168000 6000 미만 유닛은 USB Micro-B, 이상 유닛은 USB-C(OM p.13 "5. 1 USB port... either: USB Micro-B (units with serial number lower than 168000 6000), USB-C (units with serial number 168000 6000 or higher)"). 스펙 표(p.63)도 "1 USB Micro-B or USB-C, 2.0 compliant"로 동일하게 이원화되어 있다. AE는 서비스 포트 자체를 언급하지 않는다(누락). 이는 실제 하드웨어 개정 이력이며 소스 충돌이 아니다.

---

## control_monitoring (제어 및 모니터링)

| Key | Value | Unit |
|---|---|---|
| Remote_Software | LA Network Manager | - |
| Network_Topologies | daisy-chain, star, hybrid | - |
| Third_Party_Control | Q-SYS, Crestron | - |
| Front_Panel [11] | LED indicators only (power, L-NET, status, 16 signal LEDs) - no display or encoder wheel | - |
| Settings_Protection [12] | Yes - configurable via LA Network Manager; does not prevent actions performed via the USB Terminal utility | - |
| GPIO_Count | 3 | ea |
| GPIO_Type | isolated optocoupler inputs, isolated relay contacts | - |
| DSP_Backup_Power_Input [13] | 24 | V DC |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.17 "Technical description > Monitoring and control", p.22 "Installation > General Purpose I/O (GPIO)", p.38 "Operation > Other operations", p.65 "Specifications > Remote control and monitoring" (최우선) / AE "Technical requirements > Third-party management solutions, Connectors"

**측정 조건**: L-NET 네트워크는 최대 253대 제어 가능, CAT5e U/FTP 이상 케이블 사용(OM p.17). Third_Party_Control은 OM(p.17)이 "For other control platforms, an HTTP API is available on request after signing a memorandum of understanding"로 조건부 서술하나(LA1.16i 각주[17]와 동일 패턴), Value에는 Q-SYS/Crestron만 채택하고 HTTP API의 MOU 조건부 제공 사실은 본 각주에 기록한다.

**[11] Front_Panel — AE의 입력채널 LED 서술 불일치**: AE(Display 절)는 "Information LED: power, network, status / Input channels LED: signal, limit, clip / Output channels LED: signal, limit, clip"로 입력채널용 LED와 출력채널용 LED를 별도 항목으로 명시하나, OM의 전면 패널 실물 사진(p.13, p.36-37) 및 Meters 절(p.37)은 "power LED, L-NET LED, status LED, 16개 signal LED(출력 채널 대응)"만 서술하며 입력 채널 전용 LED는 어디에도 존재하지 않는다(전면 패널 사진상 LED 그룹은 3개 상태 LED + 16개뿐). 이는 AE 문서 작성 시 다른 제품(예: 입출력 채널이 분리 표시되는 구형 제품)의 템플릿 문구가 갱신되지 않고 남은 것으로 추정되나 확정할 근거는 없다. OM 최우선 원칙 및 전면 패널 실물 서술을 근거로 Value에는 OM 서술만 채택했다.

**[12] Settings_Protection — LA1.16i와 달리 정보 확보**: LA1.16i 파일은 해당 정보를 찾지 못해 null 처리했으나, LA7.16i의 OM(p.38 "Other operations" 표)은 LA Network Manager 열에 "Enable settings protection: yes"를 명시하고, 각주 3번으로 "Settings Protection does not prevent actions done from the USB Terminal utility. Take measures to restrict access to the USB port of the amplified controller"를 부연한다. AE는 이 기능을 언급하지 않는다(OM 단독 출처).

**[13] DSP_Backup_Power_Input 정격 차이**: OM(p.25)은 "The external power supply should be rated 24 V DC (± 10%) 15 W minimum (-5°C/23°F to 50°C/122°F ambient)"로 명시 — LA1.16i의 17W minimum과 다른 수치다(제품 간 실제 소비전력 차이로 판단, 소스 충돌 아님). AE는 "24 V DC 2-point terminal block"으로 전압값만 명시하고 W 정격은 언급하지 않는다(누락). OM은 추가로 "LS10 24 V DC output is not powerful enough to supply LA7.16i DSP"라는 운용 주의사항을 명시한다(참고용, Key화하지 않음).

---

## operating_conditions (동작 환경)

| Key | Value | Unit |
|---|---|---|
| Operating_Temp_Range | -5 to 50 | degrees C |
| Cooling | DSP-controlled fans, front to rear airflow | - |
| Fan_Count [14] | 5 | ea |
| Fan_Noise_Min | 33 | dBA |
| Fan_Noise_Max | 62 | dBA |
| EMC_Class | non-residential (Class A) | - |
| Max_Operating_Altitude | 2000 | m |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.6 "Important safety instructions", p.63 "Specifications > Operating conditions", p.21 "Installation > Ventilation" (최우선) / AE "Technical requirements > Operating conditions"

**측정 조건**: Operating_Temp_Range는 안전 섹션(p.6)과 스펙 섹션(p.63) 일치, 충돌 없음(OM/AE 동일: -5°C/23°F ~ 50°C/122°F). Fan_Noise는 free field, 1m 거리 기준(Min=Idle모드, Max=최고속, OM p.63). Max_Operating_Altitude는 LA1.16i의 3000m과 다른 값(OM p.63 "Maximum altitude 2000 m")이나, 서로 다른 제품의 실제 스펙 차이이며 소스 충돌이 아니다.

**[14] Fan_Count — LA1.16i와 달리 정보 확보**: LA1.16i 파일은 팬 개수 정보를 찾지 못해 null 처리했으나, LA7.16i의 AE(Operating conditions 절)는 "Cooling system: 2 integrated, temperature-controled fans"가 아니라 **"5 integrated, DSP-controlled fans"**로 명시한다(LA7.16(구형) AE의 5개 팬 수치와 동일). OM은 정확한 개수를 텍스트로 명시하지 않으나 "DSP-controlled fans"라는 동일 표현을 사용하여 충돌은 없다(OM은 개수 미언급, AE가 유일한 수치 출처).

---

## physical (물리적 스펙)

| Key | Value | Unit |
|---|---|---|
| Width | 483 | mm |
| Height [15] | 88 | mm |
| Depth [15] | 465 | mm |
| Weight [15] | 14.5 | kg |
| Protection_Rating | IP2x | - |
| Finish | black | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.20 "Installation > Mounting > LA7.16i dimensions", p.66 "Specifications > Physical data" (최우선) / AE "Physical data"

**측정 조건**: OM은 2U(88mm) 랙 마운트 제품임을 본문에서 명시적으로 확인한다("The LA7.16i is two rack units high (2U)", p.20). 리어브래킷 장착 시 최대 깊이 534.3mm/21.02in(OM p.20, 대표값 아님, 참고용).

**[15] LA1.16i와 달리 OM/AE 전항목 값 일치**: LA1.16i 파일에서는 Height(44.45 vs 88mm), Depth(대응불가), Weight(5.9 vs 5.6kg) 모두 OM/AE 간 충돌이 있었으나, LA7.16i는 Height(88mm), Depth(465mm), Weight(14.5kg) 세 항목 모두 OM과 AE가 정확히 일치한다(OM p.66 "483mm/439mm/465mm(W/-/D 관련 치수), 88mm, 14.5kg" vs AE "483mm, 88mm, 465mm / 14.5 kg"). 충돌 없이 두 소스 모두에서 동일 수치를 확인했다.

---

## protection_summary (보호 회로)

| Key | Value |
|---|---|
| Protection_Mains_PSU | over and under voltage, over temperature, L-SMART, overcurrent (fuse protection, inrush current protection), power budget limiter |
| Protection_Outputs | overcurrent, DC, short circuit, over temperature |
| Protection_Transducer | L-DRIVE: excursion, temperature, over-voltage |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.63 "Specifications > Protection" (최우선) / AE에는 대응 소단락 없음(OM 단독 출처)

**측정 조건**: 없음(보호 기능 목록). 세 항목 모두 OM 원문 표기를 그대로 채택했으며 LA1.16i와 문구가 거의 동일하다(임의 통일이 아니라 OM 원문 자체가 유사한 표준 문구를 사용).

---

## d80_specific (d&b D80 고유 속성)

| Key | Value | Unit |
|---|---|---|
| CMRR_Analog_Input | null | dB |
| Digital_Input_Impedance | null | Ohm |
| SN_Ratio_Analog_Input | null | dBr |
| SN_Ratio_Digital_Input | null | dBr |
| System_Start_Up_Time | null | sec |
| Storage_Temp_Range | null | degrees C |
| Storage_Humidity | null | % rel. |
| LoadMatch_Max_Cable_Length | null | m |
| Signal_Path_Management | null | - |
| Load_Monitoring_System_Check | null | - |
| Output_Mode_Selectable | null | - |
| Mains_Current_Limiter_Range | null | % of rated current |

### 주석 및 출처 (Notes & Sources)

**출처**: 해당 없음(D80_v1.0.md 신규 섹션의 양방향 동기화 반영, LA1.16i_v1.0.md 구조 복제).

**섹션 전체**: LA7.16i의 OM/AE 어디에도 이들 항목에 대응하는 스펙이 확인되지 않아 전량 null 유지.

---

## d90_specific (d&b D90 고유 속성)

| Key | Value | Unit |
|---|---|---|
| Milan_Device_Type | null | - |
| Milan_Input_Channel_Streams | null | - |
| Milan_Redundancy | null | - |
| Milan_Routable_Inputs | null | ch |
| Network_IP_Default | null | - |
| Time_To_Tone | null | sec |
| Energy_Saving_Detail | null | - |
| AmpPresets_Detail | null | - |
| Output_Noise_Dynamic_Range_Detail | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: 해당 없음(D90_v1.0.md 신규 섹션의 양방향 동기화 반영, LA1.16i_v1.0.md 구조 복제).

**섹션 전체**: LA7.16i의 OM/AE 어디에도 이들 항목에 대응하는 스펙이 확인되지 않아 전량 null 유지.

## Null Report

이번 소스 집합에서 정의되지 않아 null 처리된 항목: Rated_Power_Per_Ch_2.7_Ohms, Total_Power_Capability, THD_N_4ohm, EQ_Filters_Per_Output, Preset_Memory_User, Preset_Memory_Factory, XLR_Pin_Polarity, SpeakON_Left_Pinout, SpeakON_Right_Pinout, CACOM_Pinout, SC32_Channel_Mapping, Speaker_Output_Accessories (LA7.16i 자체 소스 근거 부족, 총 12건), Rated/Peak_Power_Per_Ch_BTL_8/16_Ohms(4건) + Rated/Peak_Power_Per_Ch_PBTL_4/8/16_Ohms(6건) + PBTL_Activation_Method(1건) — 브릿지 모드 미지원(확정)에 따라 해당 동작 모드의 측정값 자체가 정의되지 않아 null 처리, 총 11건(각주[1], LA4X 선례 준용), d80_specific 12건, d90_specific 9건. 전체 44건.

(참고: Bridging_Support와 Speaker_Terminal_Block_SE_BTL_Wiring은 브릿지 모드 지원 여부를 묻는 Key로서 OM에 의해 명시적으로 부인되므로 "확정된 비존재"(No/N/A 텍스트)로 처리했으며 Null Report에는 포함하지 않는다 — 반면 BTL/PBTL 전력값 Key들은 "그 동작 모드가 없어 측정값이 정의되지 않음"을 의미하므로 null로 처리하고 Null Report에 포함한다 — SKILL v1.9 원칙에 따른 구분, LA4X_v1.0.md 선례 준용.)

## 버전 변경 이력

v1.0: Phase 3-1 신규 제품(Upload 폴더 4개 제품 중 마지막) 최초 투입. OM(69p, 텍스트 레이어 전량 추출) + AE(docx, zip 압축 해제 후 텍스트 추출) 2개 소스를 교차 검증하여 마스터 스키마 최초 구축(LA1.16i_v1.0.md의 Key 목록/구조를 뼈대로 복제 후 서지컬 교체 — LA1.16i와 동일 커넥터 아키텍처 계열이나 브릿지 모드 미지원, 단일 PSU, 32A powerCON 등 실질적 차이 다수). 신규 Key 추가는 없음(기존 4개 제품 파싱을 거치며 이미 스키마에 편입된 Key를 재사용, 브릿지 관련 15개 Key 중 Bridging_Support/Speaker_Terminal_Block_SE_BTL_Wiring 2개는 "확정된 비존재"(No/N/A)로, 나머지 BTL/PBTL 전력값 및 PBTL_Activation_Method 11개는 "동작 모드 부재로 측정값 미정의"(null)로 값 채움 — LA4X 선례 준용). 소스 간 데이터 충돌 2건(Noise_Level, ADC dynamic range) 발견, 각주로 보존. Height/Depth/Weight는 LA1.16i와 달리 OM/AE 전항목 일치. Settings_Protection과 Fan_Count는 LA1.16i에서 null이었던 것과 달리 이번 소스에서 확보됨. 기존 5개 제품 파일(LA12X, LA7.16, D80, D90, LA1.16i)과 이번에 함께 파싱된 LA2Xi/LA4X로의 양방향 동기화는 Upload 폴더 4개 제품 파싱 완료 후 Phase 4 규칙(누적 제품 5개 이상)에 따라 사용자 확인을 받아 일괄 진행 예정.
