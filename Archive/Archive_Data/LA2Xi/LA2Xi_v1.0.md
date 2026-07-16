# LA2Xi - Master Spec Schema

Schema_Version: 1.0 (Phase 3-1 신규 제품 파싱 - L-Acoustics "i" 설치전용 라인, 4채널 소형기)
최종 작업 일시: 2026-07-15 21:43 (수요일)
Manufacturer: L-Acoustics
Product_Category: Amplified_Controller (4-channel install-specific Class D amplifier with integrated DSP)
Form_Factor: 19 inch rack, 1U

## 출처 등록부 (Source Registry)

| Source_ID | Document | Version / Date |
|---|---|---|
| OM | Owner's Manual (EN) | version 4.0, distribution Mar. 10, 2025 |
| AE | Architects and Engineers Spec (docx) | undated |

**소스 범위에 대한 참고**: LA1.16i와 동일하게 OM PDF와 AE docx 2개 소스만으로 파싱했다(SPS/웹 데이터 미제공).

본 파일은 LA1.16i_v1.0.md의 Key 목록/구조를 뼈대로 복제하여 작성되었다. LA2Xi는 LA1.16i와 같은 "i" 설치전용 라인이지만 4채널 소형기로, L-SMART 미탑재(단일 PSU), 아날로그 4채널 전용 입력(공유 AUX 아님), SE/BTL/PBTL 3단 브릿징(LA1.16i는 SE/BTL 2단), mini USB(LA1.16i는 USB-C), 서드파티 제어 범위 확장(Extron/SNMP 추가) 등 다수의 아키텍처 차이가 있어 다시 한번 대부분의 Value가 다르며 신규 Key도 추가되었다(아래 각주 참조).

---

## amplification (증폭부)

| Key | Value | Unit |
|---|---|---|
| Channel_Count_In | 4 | ch |
| Channel_Count_Out | 4 | ch |
| Amplification_Class | High-efficiency Class D | - |
| Rated_Power_Per_Ch_2.7_Ohms | null | W |
| Rated_Power_Per_Ch_4_Ohms [1] | 640 | W |
| Rated_Power_Per_Ch_8_Ohms [1] | 360 | W |
| Rated_Power_Per_Ch_16_Ohms [1] | 190 | W |
| Peak_Power_Per_Ch_4_Ohms | 710 | W |
| Peak_Power_Per_Ch_8_Ohms | 370 | W |
| Peak_Power_Per_Ch_16_Ohms | 190 | W |
| Total_Power_Capability | null | W |
| Max_Output_Voltage_Peak | null | V |
| Amplification_Gain | 32 | dB |
| Output_Delay_Range | 0 - 1000 | ms |
| Bridging_Support [2] | Yes - SE, BTL, or PBTL selectable per channel pair/group (GPIO PAR pin, or push-button on optional I/O-CON accessory) | - |
| Rated_Power_Per_Ch_BTL_8_Ohms [1] | 1260 | W |
| Rated_Power_Per_Ch_BTL_16_Ohms [1] | 710 | W |
| Peak_Power_Per_Ch_BTL_8_Ohms | null | W |
| Peak_Power_Per_Ch_BTL_16_Ohms | null | W |
| Rated_Power_Per_Ch_PBTL_4_Ohms [신규][3] | 2550 | W |
| Rated_Power_Per_Ch_PBTL_8_Ohms [신규][3] | 1400 | W |
| Rated_Power_Per_Ch_PBTL_16_Ohms [신규][3] | 780 | W |
| Peak_Power_Per_Ch_PBTL_4_Ohms [신규][3] | null | W |
| Peak_Power_Per_Ch_PBTL_8_Ohms [신규][3] | null | W |
| Peak_Power_Per_Ch_PBTL_16_Ohms [신규][3] | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.53 "Specifications > General > Output power", p.25 "Power consumption" (최우선) / AE "Technical requirements > Amplification"

**[1] 측정 조건 표기 차이 (LA1.16i/LA7.16/LA12X와 다름)**: LA1.16i 등 다른 제품의 `Rated_Power_Per_Ch_*`는 CEA-2006/490A 20ms 표준 조건을 명시하나, LA2Xi의 OM(p.17, p.53)과 AE는 이 표준명을 전혀 언급하지 않고 대신 "no limiter, 200 ms sine burst, < 1% THD, 1 kHz, all channels driven"라는 독자적 측정 조건을 사용한다. 두 조건(CEA-2006/490A 20ms vs no-limiter 200ms)은 서로 다른 표준이며 수치를 직접 비교할 근거가 없다 — 따라서 `Rated_Power_Per_Ch_*` Key는 형식상 LA1.16i 등과 이름이 같지만, LA2Xi 값을 다른 제품과 동일 기준으로 비교하지 않도록 주의해야 한다(SKILL v1.9 "표기 기준이 다른 동일 물리량의 임의 변환 금지" 원칙과 같은 맥락). BTL 조건도 동일하게 "no limiter 200ms" 기준이며, 4Ω 조건 BTL 수치는 OM/AE 어디에도 제공되지 않아 null 처리.

**[신규][2] Bridging_Support 3단 확장**: LA1.16i는 SE/BTL 2단 브릿징만 지원했으나, LA2Xi는 SE/BTL/PBTL(parallel bridge-tied load) 3단을 지원한다(OM p.17 "Speaker outputs", p.32 "Speaker"). PBTL은 4채널 전체를 하나의 초고출력 채널로 묶는 모드다.

**[신규][3] PBTL 관련 6개 Key**: LA1.16i에는 없던 PBTL 모드 전용 Key. OM p.53 스펙 표의 "In PBTL mode" 행에서 채택(no-limiter 200ms 조건만 제공, Peak 조건은 SE 모드에만 별도로 주어져 PBTL/BTL의 Peak 값은 소스에 없어 null). 이 6개 Key는 amplification 섹션 각주[2](BTL 관련)와 마찬가지로 기존 4개 제품(LA12X, LA7.16, D80, D90) 및 LA1.16i에 양방향 동기화가 필요하며, Upload 폴더 4개 제품 파싱 완료 후 일괄 반영 예정이다.

---

## power_supply (전원부)

| Key | Value | Unit |
|---|---|---|
| PSU_Type [4] | 1 universal Switched Mode Power Supply (SMPS) with Power Factor Correction (PFC) | - |
| Mains_Voltage_Range | 100 - 240 (+/-10%) | V AC |
| Mains_Frequency_Range | 50 - 60 | Hz |
| Nominal_Current_100_120V | 20 A (100 V) / 15 A (120 V) | A |
| Nominal_Current_200_240V | 10 | A |
| Power_Factor | greater than 0.9 (at full load) | - |
| Power_Consumption_Idle | 27 | W |
| Power_Consumption_Standby | 16 | W |
| Mains_Connector | V-Lock compatible IEC | - |
| PSU_Mains_Rated_Power | 550 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.54 "Specifications > Power supply", p.23 "Installation > Electrical specifications" (최우선) / AE "Technical requirements > Mains rating"

**측정 조건**: Power_Consumption Idle/Standby는 230V 기준(OM p.25). PSU_Mains_Rated_Power(550W)는 LA1.16i(430W, 듀얼 PSU 합산)보다 크지만 LA2Xi는 단일 PSU 구성이다.

**[4] PSU_Type — L-SMART 미탑재**: LA1.16i/LA7.16은 L-SMART 기술을 탑재한 듀얼 PSU 구조였으나, LA2Xi는 단일 SMPS(PFC만 탑재, L-SMART 없음) 구조다. OM/AE 어디에도 LA2Xi 관련 "L-SMART" 언급이 없다(OM p.17 "Power supply and amplifier section" 절 확인). dsp 섹션의 Amplifier_Power_Management Key도 이에 따라 null 처리했다(아래 참조).

---

## audio_performance (음향 스펙)

| Key | Value | Unit |
|---|---|---|
| Frequency_Response | 20 - 20000 | Hz |
| THD_N_8ohm [5] | less than 0.1 | % |
| THD_N_4ohm | null | % |
| Output_Dynamic_Range [6] | greater than 113 (digital input) | dB |
| Noise_Level [7] | less than -77 (digital input) | dBV |
| Channel_Separation | greater than 80 | dB |
| Damping_Factor | greater than 80 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.53 "Specifications > General" (최우선) / AE "Technical requirements > Amplification"

**측정 조건**: Frequency_Response는 ±0.25dB(OM 스펙 표 기준; AE는 동일 항목에 "8Ω, 60W 출력" 조건을 추가 명시, 각주[5] 참조). Damping_Factor는 20Hz-200Hz, 4Ω 부하 기준. THD_N_4ohm은 두 소스 모두 4Ω 조건 수치 없어 null.

**[5] THD_N_8ohm 측정 조건 표기 차이**: OM(p.53)은 조건을 명시하지 않고 "< 0.1%"만 기재. AE는 동일 수치에 "(20 Hz - 10 kHz, 8 ohms, 60 W output power)" 조건을 병기한다. 값 자체는 일치(0.1%), 충돌 아님 — AE의 조건 설명을 각주로 보강 기록.

**[6] Output_Dynamic_Range — 아날로그/디지털 입력 구분**: OM은 디지털 입력(>113dB)과 아날로그 입력(>102dB) 두 조건을 구분 명시한다(LA1.16i/LA7.16에는 없던 구분). Value에는 디지털 입력 조건을 채택하고 아날로그 입력 조건(102dB)은 각주에 병기한다.

**[7] Noise_Level 충돌 및 아날로그/디지털 구분**: OM(p.53)은 디지털 입력 기준 "< -77 dBV", 아날로그 입력 기준 "< -67 dBV"로 구분 명시. AE는 디지털 입력 조건에 대응하는 수치를 "< -78 dBV"로 표기 — OM(-77)과 AE(-78) 사이에 1dB 차이가 있다. 두 값 모두 보존 — OM 최우선 원칙에 따라 -77 dBV 채택, AE의 -78 dBV 및 OM의 아날로그 입력 조건(-67dBV)은 본 각주에 병기한다.

---

## dsp (신호 처리)

| Key | Value | Unit |
|---|---|---|
| DSP_Processor [8] | Gen. 4 dual DSP engine, 32-bit floating point, 96 kHz sampling rate | - |
| DSP_Sampling_Rate [9] | 96 (internal, fixed, independent from input Fs) | kHz |
| Routing_Matrix | 4x4 routing and summation matrix | - |
| EQ_Filters_Per_Output | null | - |
| Per_Channel_DSP_Tools | Multiband EQ, Array morphing, Air absorption compensation filter | - |
| Amplifier_Power_Management [10] | null | - |
| Speaker_Protection | L-DRIVE (excursion, temperature, over-voltage) | - |
| Preset_Memory_User [11] | 10 | slots |
| Preset_Memory_Factory | null | slots |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Technical description > Main features > Internal components", p.16 "DSP architecture" (최우선) / AE "Technical requirements > DSP"

**측정 조건**: 없음(사양값). Per_Channel_DSP_Tools는 OM p.16 "audio path parameters" 다이어그램의 채널별 처리 블록("ARRAY MORPHING + MULTI-BAND EQ + AIR ABSORPTION COMPENSATION FILTER")을 채택.

**[8] DSP_Processor 명칭 근거**: LA1.16i와 동일 사유로 OM에는 "SHARC" 명칭이 없고(OM은 "Gen. 4 dual DSP engine"만 서술), AE만 "Gen. 4 Dual SHARC"로 명시한다. OM 우선 원칙에 따라 OM 서술을 채택하고 AE의 "SHARC" 명칭은 각주에 기록.

**[9] DSP_Sampling_Rate 근거**: OM p.15 "There is no AES/EBU external synchronization mode. The amplified controller's clock always runs at 96 kHz, referenced to its internal clock when on XLR input mode, or on the connected AVB audio stream when on AVB input mode... while preventing phase shift"로 확정. AES67 모드에서도 동일하게 96kHz 고정 및 PTPv2 참조가 확인된다(OM p.15).

**[10] Amplifier_Power_Management — L-SMART 미탑재**: power_supply 섹션 각주[4]에서 설명한 대로, LA2Xi는 단일 PSU 구조로 L-SMART 기술이 없다. OM/AE 어디에도 관련 서술이 없어 null 처리 — LA1.16i/LA7.16의 "L-SMART" 값을 임의로 이식하지 않았다.

**[11] Preset_Memory_User**: AE가 "Built-in library with factory presets for all manufacturer's loudspeakers and 10 user memories"로 명시(LA1.16i AE에는 이 문구가 없었으나 LA2Xi AE에는 명시되어 있어 값을 채택할 수 있었다). OM에는 구체적 슬롯 수 서술이 없다(단일 소스, 충돌 아님).

---

## latency (지연 시간)

| Key | Value | Unit |
|---|---|---|
| Latency_Standard | 3.84 (independent from input Fs) | ms |
| Latency_Low_Mode [12] | 0.76 (independent from input Fs) | ms |
| AVB_Max_Network_Latency | 2 | ms |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.56 "Specifications > Latency", p.56 "Specifications > Milan-AVB" (최우선) / AE "Technical requirements > DSP > Latency"

**측정 조건**: Analog/AES-EBU 입력 기준, 입력 샘플링 주파수와 무관(OM/AE 일치).

**[12] Latency_Low_Mode — LA1.16i/LA7.16과 다른 값**: LA1.16i와 LA7.16은 모두 1.18ms였으나 LA2Xi는 0.76ms로 다르다. 이는 소스 충돌이 아니라 제품별 실제 값 차이다 — OM의 개정 이력(p.11)에 "v2.3(Jan. 2022): Corrected the latency value in low latency operating mode"라는 항목이 있어, 이 수치가 과거 한 차례 정정된 이력이 있는 값임을 참고로 기록한다.

---

## input_analog (아날로그 입력)

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Channels [13] | 4 | ch |
| Input_Impedance | 22 | kOhm |
| Max_Input_Level | 22 | dBu |
| ADC_Architecture [14] | 1 x 32-bit A/D converter at 96 kHz sampling rate, 121 dB dynamic range (A-weighted, 20 Hz - 20 kHz) | - |
| Analog_Link_Type [15] | active link, 4 dedicated input channels (A/B/C/D) with 2 daisy-chain link terminal blocks (A LINK, C LINK) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Technical description > Signal processing and amplification > Analog", p.55 "Specifications > Input signal distribution" (최우선) / AE "Technical requirements > Analog input"

**측정 조건**: Input_Impedance/Max_Input_Level은 balanced 기준(OM/AE 일치, THD 1%).

**[13] Analog_Input_Channels — LA1.16i/LA7.16과 다른 아키텍처**: LA1.16i/LA7.16은 16개 증폭 채널이 공유하는 단일 AUX 입력(1채널) 구조였으나, LA2Xi는 4개 증폭 채널 각각에 대응하는 4개의 전용 아날로그 입력(ANA IN A/B/C/D)을 갖는다(OM p.15). LA12X와 유사한 채널 전용 입력 구조에 가깝다.

**[14] ADC_Architecture 다이나믹레인지 — 충돌 없음**: OM(p.15) "121 dB dynamic range"와 AE "121 dB dynamic range"가 정확히 일치한다 — LA1.16i에서 발견된 99dB(OM)/121dB(AE) 충돌과 달리 LA2Xi는 두 소스가 일치하므로 단일 값으로 Value에 직접 병기했다.

**[15] Analog_Link_Type — 데이지체인 구조 차이**: LA1.16i/LA7.16은 단일 공유 IN/LINK 회로였으나, LA2Xi는 ANA A LINK가 다음 유닛의 ANALOG IN B로, ANA C LINK가 다음 유닛의 ANALOG IN D로 연결되는 방식이다(OM p.16, p.29) — 즉 한 유닛의 입력 A/C가 다음 유닛에서는 입력 B/D로 나타난다. 시리얼 넘버 1730003000 이후 유닛부터는 LINK 포트가 AES/EBU와 ANALOG 모드를 모두 지원(그 이전 유닛은 AES/EBU 전용).

---

## input_digital (디지털 입력)

| Key | Value | Unit |
|---|---|---|
| Digital_Input_Channels | 4 | ch |
| Digital_Standard [16] | AES/EBU (AES3) | - |
| Supported_Sampling_Rates | 44.1 / 48 / 88.2 / 96 / 176.4 / 192 | kHz |
| Supported_Word_Length | 16 / 18 / 20 / 24 | bit |
| SRC_Output_Format | 24-bit at 96 kHz | - |
| SRC_Dynamic_Range | 140 | dB |
| SRC_THD_N | less than -120 | dBFS |
| Digital_Input_Gain_Range | -12 to +12 | dB |
| Digital_Link_Type | electronically buffered with failsafe relay, 2 daisy-chain link terminal blocks (AES LINK A&B, AES LINK C&D) | - |
| Max_AES_Cable_Length | 300 | m |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Technical description > Signal processing and amplification > AES/EBU", p.55 "Specifications > Input signal distribution" (최우선) / AE "Technical requirements > Digital input"

**측정 조건**: Max_AES_Cable_Length는 단일 케이블, 48kHz 샘플링, Belden 1696A/Klotz OT234H 기준(OM p.15) — 다른 제품과 동일 조건, 동일 값(300m).

**[16] Digital_Standard — S/PDIF 병기 여부**: AE는 "Standards: AES/EBU (AES3) or S/PDIF"로 S/PDIF도 지원한다고 명시하나, OM의 공식 스펙 표(p.55 "Supported digital input format")는 "AES/EBU (AES3)"만 명시하고 S/PDIF를 언급하지 않는다. Value는 OM 최우선 원칙에 따라 AES/EBU만 채택하고, AE의 S/PDIF 병기 서술은 여기 각주로 남긴다 — 임의로 Value에 추가하지 않는다(LA12X 스키마에 유사한 S/PDIF 병기 사례가 있었던 것으로 추정되나 본 세션에서 직접 대조하지 못했다).

---

## input_avb (AVB / Milan-AVB 입력)

| Key | Value | Unit |
|---|---|---|
| AVB_Certification | MILAN and Avnu certified (Bridge and Listener) | - |
| AVB_Channels [17] | 4 | ch |
| AVB_Stream_Count [17] | 1 (in normal or redundancy mode) | streams |
| AVB_Formats | AAF PCM32, IEC 61883-6 AM824 | - |
| AVB_Standards | IEEE 802.1BA-2011 / 1722-2016 / 1722.1-2013 | - |
| AVB_Bridge_Forwarded_Streams | up to 150 | streams |
| Redundancy_Type | Milan-AVB seamless, automatic switchover and recovery | - |
| Fallback_Modes | AVB to AES/EBU or analog; AES/EBU to analog, user-defined mapping | - |
| AES67_Support [18] | Yes - AES67-2023, 1 stream up to 8 ch, L16/L24 at 48 kHz, PTPv2 clock, user-selectable alternative to Milan-AVB (available from firmware 2.15.0) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Signal inputs, Milan-AVB", p.56 "Specifications > Milan-AVB" (최우선) / AE "Technical requirements > AVB input"

**측정 조건**: Switchover 조건은 AVB loss of lock(AVB→AES/analog), AES/EBU→analog는 no clock/loss of lock/CRC error/bipolar encoding error/data slip 중 하나(OM p.57).

**[17] AVB_Channels/AVB_Stream_Count — LA1.16i/LA7.16i보다 단순한 구조**: LA1.16i/LA7.16i는 16개 스트림(각 최대 8채널)을 수신할 수 있었으나, LA2Xi는 단 1개의 AVB 스트림(최대 8채널)에서 4채널만 추출하는 훨씬 단순한 구조다(OM p.14 "One AVB stream of up to eight channels may be connected to LA2Xi. LA2Xi retrieves up to four channels from this stream"). 이는 채널 밀도가 낮은 소형 앰프의 아키텍처 차이로 판단되며 소스 충돌이 아니다.

**[18] AES67_Support**: LA2Xi는 OM 개정이력(p.11) v4.0(Mar. 2025)에서 "Added AES67 specifications"로 신규 추가되었으며, "AES67 support is available from firmware version 2.15.0, and audio network mode selection is available in LA Network Manager from version 2025.1"로 버전 조건이 명시되어 있다(OM p.15) — LA1.16i에는 없던 이 firmware 버전 조건 정보를 각주가 아닌 Value 자체에 포함시켰다(LA1.16i의 동일 Key와 표현 통일성보다 소스에 명시된 구체적 조건을 우선했다).

---

## connectivity (커넥터)

| Key | Value | Unit |
|---|---|---|
| Input_Connectors [19] | 4 x male 3-point terminal blocks (2 analog, 2 AES/EBU or analog) + 2 x male 3-point link terminal blocks, 2 x etherCON RJ45 (Milan-AVB/AES67 I/O) | - |
| Terminal_Block_Pinout [19] | GPIO는 별도 10핀 블록, 24V DC는 별도 2핀 블록, 오디오 입력/링크는 6개의 개별 3핀 블록으로 분리 구성 — 상세 핀맵은 하단 표 참조 | - |
| XLR_Pin_Polarity [20] | null (base unit); optional I/O-CON accessory adds 4 female XLR in + 2 male XLR link, pin 1 shield / pin 2 + / pin 3 - | - |
| Speaker_Connectors | 2 x female 4-point terminal block | - |
| SpeakON_Left_Pinout [20] | null (base unit); optional I/O-CON accessory adds 2 x female 4-point speakON | - |
| SpeakON_Right_Pinout | null | - |
| CACOM_Pinout | null | - |
| SC32_Channel_Mapping | null | - |
| Speaker_Output_Accessories [21] | DOE cables (AVB network), SP-Y1 (SE breakout to 2 passive enclosures), SP5 BTL (BTL direct connect); optional LA2Xi I/O-CON accessory panel (XLR + speakON) | - |
| Network_Connectors | 2x etherCON RJ45, 1 Gb/s | - |
| Service_Port_Type [22] | 1 x mini USB (IP configuration via USB Terminal tool of LA Network Manager) | - |
| Speaker_Terminal_Block_SE_BTL_Wiring [23] | 2 x female 4-point terminal blocks; SE: 4 independent outputs; BTL: 2 bridged pairs; PBTL: all 4 channels combined into 1 output via GPIO PAR pin grounded to chassis ground | - |
| PBTL_Activation_Method [신규][24] | GPIO PAR pin connected to a chassis ground pin (base unit); recessed push-button (optional I/O-CON accessory) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Front and rear panels", p.22 "Installation > General Purpose I/O (GPIO)", p.27 "Audio and network cabling > Connection panels" (최우선) / AE "Technical requirements > Connectors"

**측정 조건**: 없음(커넥터 규격 및 결선표).

**[19] Terminal_Block_Pinout — LA1.16i와 다른 분리형 구조**: LA1.16i는 GPIO/24V DC/오디오 입출력을 단일 12핀 블록에 통합했으나, LA2Xi는 각 기능을 별도 블록으로 분리한다: GPIO 전용 10핀 블록(OM p.22), 24V DC 전용 2핀 블록(OM p.26), 그리고 오디오 입력/링크용 6개의 개별 3핀 블록(AES IN A&B/ANA IN A, AES LINK A&B/ANA A LINK, ANALOG IN B, AES IN C&D/ANA IN C, AES LINK C&D/ANA C LINK, ANALOG IN D)(OM p.28). 상세 GPIO 핀맵:

| Pin | 기능 |
|---|---|
| GND | GPIO 그라운드 |
| 1-4 | General Purpose I/O 1-4 (input or output) |
| PAR | PBTL 브릿징용 — 섀시 그라운드 핀에 연결 시 PBTL 모드 활성화 |
| chassis ground x2 | 섀시 그라운드 |
| OUT +12V | 컨택트 릴레이 구동용 (최대 45 mA) |
| chassis ground | 섀시 그라운드 |

출처: OM p.22 "General Purpose I/O (GPIO)" 다이어그램 및 표.

**[20] XLR/SpeakON — 옵션 액세서리로만 존재**: 기본 유닛(LA2Xi 본체)에는 XLR/speakON 커넥터가 없어 null 유지(비적용). 다만 LA1.16i와 달리 LA2Xi는 "LA2Xi I/O-CON"이라는 별매 액세서리 패널(XLR 4입력 + XLR 2링크 + speakON 2출력, 1U, 0.6kg)을 장착하면 표준 XLR/speakON 커넥터로 전환할 수 있다(OM Appendix A, p.59-65). 이는 LA2Xi 고유의 옵션 구조로, 향후 필요 시 별도 액세서리 하위 스키마(예: `la2xi_io_con_specific`)로 분리할 수 있으나 이번 v1.0에서는 커넥터 Key의 각주로만 기록했다.

**[신규][21] Speaker_Output_Accessories 및 [신규][24] PBTL_Activation_Method**: LA1.16i에는 없던 신규 개념. LA2Xi는 SP-Y1(SE 분기), SP5 BTL(BTL 직결), I/O-CON(XLR/speakON 변환) 등 전용 케이블/액세서리 생태계를 갖추고 있으며(OM p.12-13, Appendix A), PBTL 모드 활성화 방식도 GPIO PAR 핀(본체) 또는 푸시버튼(I/O-CON)으로 별도 명시되어 있다(OM p.32, p.64). 두 Key 모두 향후 양방향 동기화 대상.

**[신규][22] Service_Port_Type — 커넥터 타입 차이**: LA1.16i는 USB-C였으나 LA2Xi는 mini USB다(OM p.14 "7. mini USB for configuring IP settings"). 원문 그대로 보존 — 임의로 통일하지 않음.

**[23] Speaker_Terminal_Block_SE_BTL_Wiring — PBTL 배선 추가**: LA1.16i의 동일 Key는 SE/BTL만 서술했으나 LA2Xi는 PBTL 배선까지 포함한다(OM p.27 표, p.32 배선도). 좌측 터미널 블록은 CH1-2, 우측은 CH3-4를 담당하며, PBTL 모드에서는 두 블록의 특정 핀들이 서로 연결되어 4채널이 하나의 출력으로 합쳐진다(OM p.32 PBTL 배선도).

---

## control_monitoring (제어 및 모니터링)

| Key | Value | Unit |
|---|---|---|
| Remote_Software [25] | LA Network Manager (Windows/Mac) | - |
| Network_Topologies | daisy-chain, star, hybrid | - |
| Third_Party_Control [26] | Q-SYS, Crestron, Extron, SNMP | - |
| Front_Panel | LED indicators only (power, L-NET, status, 4 signal LEDs) - no display or encoder wheel | - |
| Settings_Protection [27] | null | - |
| GPIO_Count [28] | 4 | ea |
| GPIO_Type | isolated optocoupler inputs, isolated relay contacts | - |
| DSP_Backup_Power_Input | 24 | V DC |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.17 "Technical description > Monitoring and control", p.22 "Installation > General Purpose I/O (GPIO)", p.57 "Specifications > Remote control and monitoring" (최우선) / AE "Technical requirements > Third-party management solutions"

**측정 조건**: L-NET 네트워크는 최대 253대 제어 가능, CAT5e U/FTP 이상 케이블 사용(OM p.17, 다른 제품과 동일).

**[25] Remote_Software OS 정보 — LA1.16i와 달리 확인됨**: LA1.16i AE에는 OS 지원 서술이 없어 생략했으나, LA2Xi AE는 "network management software can be run on both Windows and Mac OS X"로 명시하고 있어 이번에는 Value에 포함시켰다(단일 소스, 충돌 아님).

**[26] Third_Party_Control — 범위 확장**: LA1.16i는 Q-SYS/Crestron(+ 조건부 HTTP)만 지원했으나, LA2Xi는 AE/OM(p.18) 모두에서 Extron® 파트너 프로그램 인증과 SNMP 지원을 추가로 확인했다: "L-Acoustics is a certified member of the Crestron® and Extron® partner programs" 및 "L-Acoustics provides SNMP support to facilitate the integration via third-party control and monitoring systems." HTTP API 조건부 제공 서술은 LA2Xi 소스에서 발견되지 않았다(LA1.16i에만 있던 서술).

**[27] Settings_Protection**: OM p.36 "Other operations" 표에 "Enable settings protection: yes (LA Network Manager)"라는 기능 존재 자체는 확인되나, 구체적 동작 방식(PIN 코드 등)에 대한 서술이 없어 기존 Key 값 형식(구체적 스펙 서술)에 맞는 정보가 부족하다고 판단해 null을 유지했다 — 기능 존재 사실 자체는 본 각주에 참고로 남긴다.

**[28] GPIO_Count — LA1.16i와 다른 개수**: LA1.16i는 GPIO 3개였으나 LA2Xi는 4개다(OM p.22, AE "4 GPIO" 일치). 제품 간 실제 차이이며 충돌 아님.

---

## operating_conditions (동작 환경)

| Key | Value | Unit |
|---|---|---|
| Operating_Temp_Range | -5 to 50 | degrees C |
| Cooling | fans with temperature-controlled speed, front to rear airflow | - |
| Fan_Count | 2 | ea |
| Fan_Noise_Min | 31 | dBA |
| Fan_Noise_Max | 56 | dBA |
| EMC_Class [29] | residential (Class B) | - |
| Max_Operating_Altitude | 2000 | m |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.7 "Important safety instructions", p.54-55 "Specifications > Operating conditions/Protection" (최우선) / AE "Technical requirements > Operating conditions"

**측정 조건**: Operating_Temp_Range는 안전 섹션과 스펙 섹션 일치, 충돌 없음. Fan_Noise는 free field, 1m 거리 기준. Fan_Count(2)는 AE "2 integrated, temperature-controlled fans"에서 확인(OM은 팬 개수를 명시하지 않으나 냉각 방식 서술은 일치, 충돌 아님).

**[29] EMC_Class — LA1.16i와 다른 기본값**: LA1.16i는 기본값이 non-residential(Class A)이고 페라이트 부착 시 Class B로 승급 가능한 구조였으나, LA2Xi의 안전 섹션(OM p.7)은 "The product can be used in the following environment: residential (class B)"로 **처음부터 Class B만** 명시하며 Class A나 페라이트 관련 서술이 전혀 없다. 이는 소형 저전력 제품의 실제 EMC 인증 차이로 판단되며 소스 충돌이 아니다.

---

## physical (물리적 스펙)

| Key | Value | Unit |
|---|---|---|
| Width | 483 | mm |
| Height | 44.45 | mm |
| Depth | 265 | mm |
| Weight | 4.4 | kg |
| Protection_Rating | IP2x | - |
| Finish | black | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.21 "Installation > Mounting > LA2Xi dimensions", p.58 "Specifications > Physical data" (최우선) / AE "Physical data"

**측정 조건**: 없음. **LA1.16i와 달리 이번에는 OM/AE 두 소스가 Height(44.45mm), Depth(265mm), Weight(4.4kg) 모두 정확히 일치하며 충돌이 전혀 없다** — LA1.16i의 Height(44.45 vs 88mm) 충돌이 AE 템플릿 오기였을 가능성을 간접적으로 뒷받침하는 정황이나(다른 제품 AE는 정확), 이미 작성된 LA1.16i 파일의 각주는 수정하지 않고 그대로 둔다(원본 소스 값 보존 원칙).

---

## protection_summary (보호 회로)

| Key | Value |
|---|---|
| Protection_Mains_PSU [30] | over and under voltage, over temperature, overcurrent (fuse protection, inrush current protection) |
| Protection_Outputs | overcurrent, DC, short circuit, over temperature |
| Protection_Transducer | L-DRIVE: excursion, temperature, over-voltage |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.55 "Specifications > Protection" (최우선) / AE에는 대응 소단락 없음(OM 단독 출처)

**[30] Protection_Mains_PSU — L-SMART/전력예산 리미터 제외**: LA1.16i/LA7.16의 동일 Key에는 "L-SMART"와 "power budget limiter"가 포함되었으나, LA2Xi의 OM(p.55) 보호 목록에는 이 두 항목이 없다 — dsp/power_supply 섹션의 L-SMART 미탑재와 일관된다. OM 원문 목록을 그대로 반영했다.

---

## d80_specific (d&b D80 고유 속성, Phase 3-2 신규 섹션)

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

**[신규] 섹션 전체**: LA2Xi의 OM/AE 어디에도 이들 항목에 대응하는 스펙이 확인되지 않아 전량 null 유지.

---

## d90_specific (d&b D90 고유 속성, Phase 3-1 신규 섹션)

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

**[신규] 섹션 전체**: LA2Xi의 OM/AE 어디에도 이들 항목에 대응하는 스펙이 확인되지 않아 전량 null 유지.

## Null Report

이번 소스 집합에서 정의되지 않아 null 처리된 항목: Rated_Power_Per_Ch_2.7_Ohms, Total_Power_Capability, Max_Output_Voltage_Peak, Peak_Power_Per_Ch_BTL_8/16_Ohms, Peak_Power_Per_Ch_PBTL_4/8/16_Ohms, THD_N_4ohm, EQ_Filters_Per_Output, Amplifier_Power_Management(L-SMART 미탑재로 비적용), Preset_Memory_Factory, XLR_Pin_Polarity(본체 비적용, I/O-CON 액세서리에서만 존재), SpeakON_Left/Right_Pinout(본체 비적용), CACOM_Pinout, SC32_Channel_Mapping, Settings_Protection(구체적 서술 부족), (LA2Xi 자체 소스 근거 부족, 총 17건), d80_specific 12건, d90_specific 9건. 전체 38건.

## 버전 변경 이력

v1.0: Phase 3-1 신규 제품 파싱. OM(69p) + AE(docx) 2개 소스를 교차 검증하여 마스터 스키마 최초 구축(LA1.16i_v1.0.md의 Key 목록/구조를 뼈대로 복제 후 서지컬 교체). LA1.16i와 같은 "i" 라인이지만 4채널 소형기로서 다수의 아키텍처 차이 발견: L-SMART 미탑재(단일 PSU), 4채널 전용 아날로그 입력, SE/BTL/PBTL 3단 브릿징, mini USB, Extron/SNMP 지원 확장, EMC Class B 기본값. 신규 Key 8개(PBTL 관련 6개, Speaker_Output_Accessories, PBTL_Activation_Method) 발견 — 기존 5개 제품 파일로의 양방향 동기화는 Upload 폴더 4개 제품 파싱 완료 후 Phase 4 규칙에 따라 사용자 확인을 받아 일괄 진행 예정. 소스 간 데이터 충돌 1건(Noise_Level -77 vs -78 dBV) 발견 및 각주로 보존 — LA1.16i 대비 충돌 건수가 크게 줄었으며(Height/Depth/Weight 모두 일치), 이는 LA1.16i AE 문서의 일부 수치(88mm 등)가 템플릿 오기였을 가능성을 시사하나 확정하지 않는다.
