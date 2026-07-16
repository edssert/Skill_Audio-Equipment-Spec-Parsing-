# LA4X - Master Spec Schema

Schema_Version: 2.0 (구조 개편 - d80_specific/d90_specific 섹션 폐지, BTL/PBTL Key 통폐합)
최종 작업 일시: 2026-07-16
Manufacturer: L-Acoustics
Product_Category: Amplified_Controller (4-channel Class D amplifier with integrated DSP, full front-panel LCD/encoder UI)
Form_Factor: 19 inch rack, 2U

## 출처 등록부 (Source Registry)

| Source_ID | Document | Version / Date |
|---|---|---|
| OM | Owner's Manual (EN) | version 16.3, distribution Jan. 22, 2026 |
| AE | Architects and Engineers Spec (docx) | undated |

**소스 범위에 대한 참고**: LA1.16i/LA2Xi와 동일하게 OM PDF와 AE docx 2개 소스만으로 파싱했다.

**아키텍처 계열에 대한 중요 참고**: LA4X는 지금까지 파싱한 Upload 폴더의 다른 신제품(LA1.16i, LA2Xi)과 달리 L-Acoustics의 신형 "i" 설치전용 라인이 아니다 — 2U 섀시, 전면 LCD 화면+인코더 휠+메뉴 버튼의 완전한 로컬 UI, XLR 커넥터(터미널 블록 아님), speakON 스피커 출력, AES67 미지원(Milan-AVB만, 그마저도 하드웨어 버전에 따라 옵션)이라는 점에서 오히려 기존에 파싱되어 있는 LA12X/구형 LA7.16과 아키텍처가 훨씬 가깝다. 이 때문에 본 파일은 LA1.16i_v1.0.md가 아니라 **LA7.16_v1.6.md의 Key 목록/구조를 뼈대로 복제**하여 작성했다(XLR/speakON 계열 커넥터 Key를 그대로 재사용 가능하기 때문). LA1.16i/LA2Xi 파싱 시 새로 추가된 Key(BTL/PBTL 관련, AES67_Support, Service_Port_Type, Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method 등)는 LA4X에 해당 사항이 없어 전량 null로 유지했다.

---

## amplification (증폭부)

| Key | Value | Unit |
|---|---|---|
| Channel_Count_In | 4 | ch |
| Channel_Count_Out | 4 | ch |
| Amplification_Class | High-efficiency Class D | - |
| Rated_Power_Per_Ch_2.7_Ohms | null | W |
| Rated_Power_Per_Ch_4_Ohms [1] | 1000 | W |
| Rated_Power_Per_Ch_8_Ohms [1] | 1000 | W |
| Rated_Power_Per_Ch_16_Ohms | null | W |
| Peak_Power_Per_Ch_4_Ohms [1] | null | W |
| Peak_Power_Per_Ch_8_Ohms [1] | null | W |
| Peak_Power_Per_Ch_16_Ohms | null | W |
| Total_Power_Capability | null | W |
| Max_Output_Voltage_Peak | 150 | V |
| Max_Output_Current_Peak [신규] | null | A |
| Amplification_Gain | 32 | dB |
| Output_Delay_Range | 0 - 1000 | ms |
| Bridging_Support [2] | No (not supported — no BTL/PBTL mode, no bridging procedure in OM) | - |
| Rated_Power_Per_Ch_BTL [2a] | null | W |
| Peak_Power_Per_Ch_BTL [2a] | null | W |
| Rated_Power_Per_Ch_PBTL [2a] | null | W |
| Peak_Power_Per_Ch_PBTL [2a] | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.78 "Specifications > General > Output power", p.17 "Power supply and amplifier section" (최우선) / AE "Technical requirements > Amplification"

**[1] 측정 조건 표기 — 세 번째 독자적 표준**: LA4X의 OM/AE는 "Output power EIA (1% THD, 1 kHz, all channels driven)" 또는 AE 표현으로 "no limiter 200 ms sine bursts, 1 kHz, < 1% THD"라는 조건을 사용하며, 이는 LA1.16i의 CEA-2006/490A 20ms 표준과도, LA2Xi의 "no limiter 200ms"(LA2Xi와는 문구가 유사하나 LA4X 자체의 별도 측정치)와도 다른 독립적인 측정 세트다. 특히 LA4X는 8Ω과 4Ω에서 **동일하게 1000W**로 명시되어 있다(OM p.78 "4 × 1000 W RMS (at 8 or 4 Ω)", DSP 섹션 p.17 "LA4X delivers 4 x 1000 W RMS into 8 or 4 Ω with record hold times" — 부하 임피던스와 무관하게 동일 출력을 유지하는 것이 이 제품의 설계 특징으로 서술되어 있다). OM/AE 어디에도 "12 dB Crest Factor" 조건의 별도 피크 수치가 제공되지 않아 Peak_Power_Per_Ch_* 키는 전부 null 처리했다 — LA1.16i/LA2Xi처럼 Peak/Rated 두 조건이 별도로 주어지는 구조가 아니다. 16Ω 조건 자체도 LA4X 소스에는 없다(비적용/미제공).

**[2] Bridging_Support 확정적 비존재**: LA1.16i/LA2Xi와 달리 LA4X의 OM(89페이지 전량 텍스트 스캔) 어디에도 BTL, PBTL, bridging 등의 용어나 절차가 등장하지 않는다 — speakON 출력 배선표(p.25)도 SE 방식(Out1~4을 각각 독립 배선)만 서술한다. AE도 브릿징 관련 언급이 없다. 이는 SKILL v1.9의 "확정된 비존재(0)와 미확인(null)의 구분" 원칙에 따라 단순 미확인이 아니라 "제품 자체에 해당 기능이 없음"으로 판단해 Value에 "No"로 명시했다(다만 관련 BTL/PBTL 세부 Key들은 애초에 수치 자체가 있을 수 없는 항목이므로 null 유지).

**[2a][구조 개편 v2.0] BTL/PBTL 전력 Key 통폐합 (가독성 개선)**: v1.0까지는 부하 임피던스(8/16 Ohm, PBTL은 4/8/16 Ohm)별로 Rated/Peak를 전부 분리한 10개 Key(Rated_Power_Per_Ch_BTL_8_Ohms, Rated_Power_Per_Ch_BTL_16_Ohms, Peak_Power_Per_Ch_BTL_8_Ohms, Peak_Power_Per_Ch_BTL_16_Ohms, Rated_Power_Per_Ch_PBTL_4_Ohms, Rated_Power_Per_Ch_PBTL_8_Ohms, Rated_Power_Per_Ch_PBTL_16_Ohms, Peak_Power_Per_Ch_PBTL_4_Ohms, Peak_Power_Per_Ch_PBTL_8_Ohms, Peak_Power_Per_Ch_PBTL_16_Ohms)였다. 브릿지 모드를 지원하지 않거나 미확인인 제품(D80/D90/LA12X/LA7.16/LA4X/LA7.16i)에서 이 10개 Key가 전부 null로 나열되어 가독성이 크게 떨어진다는 사용자 피드백에 따라(D80_v2.0.md/D90_v2.0.md와 동일 처리), 4개 Key(Rated_Power_Per_Ch_BTL, Peak_Power_Per_Ch_BTL, Rated_Power_Per_Ch_PBTL, Peak_Power_Per_Ch_PBTL)로 통합했다. 이 각주는 위 [2]의 Bridging_Support 확정적 비존재 판단과 별개다 — Bridging_Support Value("No", 확정적 비존재) 자체는 이번 구조 개편으로 전혀 변경되지 않았으며, 이번 변경은 순수하게 그 하위 세부 전력 Key들의 개수만 10개에서 4개로 줄인 것이다. LA4X는 브릿지 관련 서술 자체가 없어(각주 [2] 참조) 4개 Key 모두 null 유지.

---

## power_supply (전원부)

| Key | Value | Unit |
|---|---|---|
| PSU_Type | 1 universal Switched Mode Power Supply (SMPS) with Power Factor Correction (PFC) | - |
| Mains_Voltage_Range | 100 - 240 (+/-10%) | V AC |
| Mains_Frequency_Range | 50 - 60 | Hz |
| Nominal_Current_100_120V | 20 | A |
| Nominal_Current_200_240V | 10 | A |
| Power_Factor | greater than 0.9 (4 Ohm full power) | - |
| Power_Consumption_Idle | 60 | W |
| Power_Consumption_Standby | 11 | W |
| Mains_Connector [3] | powerCON 20 A | - |
| PSU_Mains_Rated_Power [4] | 1500 | W |
| Mains_Current_Limiter_Range [4a] | null | % of rated current |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.79 "Specifications > Power supply", p.21 "Installation > Electrical specifications", p.22 "Power cord" (최우선) / AE "Technical requirements > Connectors, Power supply"

**측정 조건**: Nominal_Current는 LA1.16i처럼 100V/120V를 분리하지 않고 "100-120V: 20A"로 통합 표기하는 것이 OM/AE 공통 관례다(LA2Xi/LA1.16i와 달리 여기서는 갈등 없이 기존 Key 형식에 그대로 들어맞는다).

**[3] Mains_Connector**: LA4X는 IEC가 아니라 20A 정격 powerCON 커넥터를 사용한다(OM p.22 "The removable power cord is fitted at one end with a 20 A powerCON connector"). LA7.16(구형)의 "powerCON 32A"와는 정격이 다르다 — 제품 간 실제 차이.

**[4] PSU_Mains_Rated_Power**: OM/AE 본문에는 명시적 수치가 없으나, 설치 다이어그램의 후면 패널 라벨 그래픽(OM p.20, p.22)에 "MAINS: 90-265VAC / 50-60Hz / 1500W" 및 "MAINS: 100-240V~/50-60Hz/1500W"로 표기되어 있어 이를 채택했다.

**[4a][구조 개편 v2.0] Mains_Current_Limiter_Range**: v1.x까지 "d80_specific" 섹션에 있던 Key를 power_supply로 재배치(Key/Value/Unit 및 근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

---

## audio_performance (음향 스펙)

| Key | Value | Unit |
|---|---|---|
| Frequency_Response | 20 - 20000 | Hz |
| THD_N_8ohm [5] | less than 0.05 | % |
| THD_N_4ohm | null | % |
| Output_Dynamic_Range | greater than 110 | dB |
| Noise_Level [6] | less than -70 | dBV |
| Channel_Separation | greater than 80 | dB |
| Damping_Factor | greater than 500 | - |
| SN_Ratio_Analog_Input [6a] | null | dBr |
| SN_Ratio_Digital_Input [6a] | null | dBr |
| Output_Noise_Dynamic_Range_Detail [6b] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.78 "Specifications > General" (최우선) / AE "Technical requirements > Amplification"

**측정 조건**: Frequency_Response는 8Ω 기준 ±0.25dB(OM/AE 일치). Output_Dynamic_Range는 20Hz-20kHz, 8Ω, A-weighted(OM/AE 일치, LA2Xi처럼 아날로그/디지털 입력 구분이 없다 — 단일 조건). Damping_Factor는 100Hz 이하, 8Ω 기준.

**[5] THD_N_8ohm — 측정 조건 표기 차이(값은 일치)**: OM 스펙 표(p.78)는 "< 0.05%, at 8Ω, 11 dB below rated power"로 조건을 명시. AE는 동일 수치(< 0.05%)에 "(20 Hz - 10 kHz, 8 ohms, 11 dB below rated power)"로 대역폭 조건을 추가 병기한다. 값 자체는 정확히 일치(0.05%) — 충돌 아님, AE가 조건을 더 상세히 서술한 경우.

**[6] Noise_Level**: OM(p.78) "-70 dBV"와 AE "< -71 dBV" — 1dB 차이가 있어 값 충돌로 분류. OM 최우선 원칙에 따라 -70 dBV 채택, AE의 -71 dBV는 근소한 차이이나 원문 값이므로 각주에 병기한다.

**[6a][구조 개편 v2.0] SN_Ratio_Analog_Input/SN_Ratio_Digital_Input**: v1.x까지 "d80_specific" 섹션에 있던 Key를 audio_performance로 재배치(Key/Value/Unit 및 근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

**[6b][구조 개편 v2.0] Output_Noise_Dynamic_Range_Detail**: v1.x까지 "d90_specific" 섹션에 있던 Key를 audio_performance로 재배치(Output_Dynamic_Range/Noise_Level과 인접 배치, Key/Value/근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

---

## dsp (신호 처리)

| Key | Value | Unit |
|---|---|---|
| DSP_Processor [7] | SHARC 32-bit, floating point, 96 kHz sampling rate | - |
| DSP_Sampling_Rate [8] | 96 (internal, fixed, independent from input Fs) | kHz |
| Routing_Matrix | 4x4 routing and summation matrix | - |
| EQ_Filters_Per_Output | null | - |
| Per_Channel_DSP_Tools | Array morphing, Multi-band EQ, Air absorption compensation filter | - |
| Amplifier_Power_Management | null | - |
| Speaker_Protection | L-DRIVE (excursion, temperature, over-voltage) | - |
| Preset_Memory_User | 10 | slots |
| Preset_Memory_Factory [9] | 189 | slots |
| System_Start_Up_Time [9a] | null | sec |
| LoadMatch_Max_Cable_Length [9a] | null | m |
| Load_Monitoring_System_Check [9a] | null | - |
| Time_To_Tone [9b] | null | sec |
| Energy_Saving_Detail [9b] | null | - |
| AmpPresets_Detail [9b] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Technical description > Main features", p.16 "DSP architecture" (최우선) / AE "Technical requirements > DSP"

**측정 조건**: 없음(사양값). Per_Channel_DSP_Tools는 OM p.16 "audio path parameters" 다이어그램("ARRAY MORPHING + MULTI-BAND EQ + AIR ABSORPTION COMPENSATION FILTER")에서 채택.

**[7] DSP_Processor — LA1.16i/LA2Xi와 달리 OM이 SHARC 명칭을 직접 사용**: LA1.16i/LA2Xi의 OM은 "SHARC" 명칭을 쓰지 않았으나, LA4X의 스펙 표(p.78)는 "Digital Signal Processor (DSP): SHARC 32 bit, floating point, 96 kHz sampling rate"로 OM 자체가 SHARC를 명시한다(AE도 동일). 따라서 이번에는 OM/AE 모두에서 확인된 값으로 그대로 채택 — 임의 이식이 아니다.

**[8] DSP_Sampling_Rate 근거**: OM p.15 "There is no external synchronization mode. The amplified controller's clock runs using its high-precision internal quartz at 96 kHz (or on the clock of the connected AVB input stream on compatible LA4X)"로 확정.

**[9] Preset_Memory_Factory — 신규로 구체적 수치 확보**: LA1.16i/LA2Xi/LA7.16 모두 null이었던 항목인데, LA4X의 LOAD PRESET 메뉴 설명(OM p.38 표: "LOAD PRESET FACTORY, memory range 11 to 199 (read only), Factory preset library...")에서 팩토리 프리셋이 메모리 011~199에 위치함을 명시하여, 199-11+1=189개로 산출했다. 사용자 프리셋(1~10, 10개)과 합쳐 전체 메모리 범위는 001~199(199슬롯)이다. 이 값은 계산에 의한 도출값임을 밝힌다(원문에 "189"라는 숫자가 직접 등장하지는 않으며, 011~199 범위 서술로부터 산출).

**[9a][구조 개편 v2.0] System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check**: v1.x까지 "d80_specific" 섹션에 있던 Key를 dsp로 재배치(Key/Value/Unit 및 근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

**[9b][구조 개편 v2.0] Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail**: v1.x까지 "d90_specific" 섹션에 있던 Key를 dsp로 재배치(Preset_Memory_User/Factory·System_Start_Up_Time과 같은 전원/프리셋 관련 성격이므로 인접 배치, Key/Value 및 근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

---

## latency (지연 시간)

| Key | Value | Unit |
|---|---|---|
| Latency_Standard | 3.84 (independent from input Fs) | ms |
| Latency_Low_Mode [10] | 0.84 (independent from input Fs) | ms |
| AVB_Max_Network_Latency | 2 | ms |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.81 "Specifications > Latency", p.81 "Specifications > Milan-AVB" (최우선) / AE "Technical requirements > DSP > Latency"

**측정 조건**: Analog/AES-EBU 입력 기준, 입력 샘플링 주파수와 무관(OM 스펙 표에 "independent from input Fs" 명시, OM/AE 일치).

**[10] Latency_Low_Mode 충돌**: OM 스펙 표(p.81, Specifications 섹션)는 "0.84 ms"로 명시하나, AE는 "0.76 ms"로 다르게 표기한다 — LA2Xi의 실제 값(0.76ms)과 우연히 일치하는 수치다. 두 값 모두 보존 — OM 최우선 원칙에 따라 0.84ms를 채택하고 AE의 0.76ms를 각주에 병기한다. 참고로 OM 개정이력(p.11)에 "v2.3(Jan. 2022): Corrected the latency value in low latency operating mode" 항목이 있어, AE가 그 수정 이전의 구버전 수치(혹은 LA2Xi 스펙을 잘못 복사)를 담고 있을 가능성이 있으나 확정하지 않는다.

---

## input_analog (아날로그 입력)

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Channels | 4 | ch |
| Input_Impedance | 22 | kOhm |
| Max_Input_Level | 22 | dBu |
| ADC_Architecture [11] | 4 cascaded 24-bit A/D converters, 96 kHz sampling rate, 128 dB dynamic range (A-weighted, 20 Hz - 20 kHz) | - |
| Analog_Link_Type | passively wired XLR link connectors (LINK A to LINK D), ESD protected | - |
| CMRR_Analog_Input [11a] | null | dB |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.16 "Technical description > Signal processing and amplification > Analog", p.80 "Specifications > Analog input" (최우선) / AE "Technical requirements > Analog input"

**측정 조건**: Input_Impedance/Max_Input_Level은 balanced 기준(OM/AE 일치, THD 1%).

**[11] ADC_Architecture — 충돌 없음, LA2Xi 계열 구조**: OM(p.16, p.80) "4 cascaded 24-bit A/D converters... 128 dB dynamic range"와 AE "4 cascaded 24-bit A/D converter (128 dB dynamic range...)"가 정확히 일치한다. LA2Xi(32-bit 컨버터, 121dB)와는 다른 세대/사양의 컨버터이며, 두 소스가 서로 일치하므로 단일 값으로 채택했다.

**[11a][구조 개편 v2.0] CMRR_Analog_Input**: v1.x까지 "d80_specific" 섹션에 있던 Key를 input_analog로 재배치(Key/Value/Unit 및 근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

---

## input_digital (디지털 입력)

| Key | Value | Unit |
|---|---|---|
| Digital_Input_Channels | 4 | ch |
| Digital_Standard [12] | AES/EBU (AES3) or electrical S/PDIF (IEC 60958 Type II) | - |
| Supported_Sampling_Rates [13] | 44.1 / 48 / 64 / 88.2 / 96 / 128 / 176.4 / 192 | kHz |
| Supported_Word_Length | 16 / 18 / 20 / 24 | bit |
| SRC_Output_Format | 24-bit at 96 kHz | - |
| SRC_Dynamic_Range | 140 | dB |
| SRC_THD_N | less than -120 | dBFS |
| Digital_Input_Gain_Range | -12 to +12 | dB |
| Digital_Link_Type | electronically buffered XLR link connectors with failsafe relay, ESD protected, transformer balanced | - |
| Max_AES_Cable_Length | 300 | m |
| Digital_Input_Impedance [13a] | null | Ohm |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Technical description > Signal processing and amplification > AES/EBU", p.80 "Specifications > Digital input" (최우선) / AE "Technical requirements > Digital input"

**측정 조건**: Max_AES_Cable_Length는 단일 케이블, 48kHz 샘플링, Belden 1696A/Klotz OT234H 기준(OM p.15) — 다른 제품과 동일 조건, 동일 값(300m).

**[13a][구조 개편 v2.0] Digital_Input_Impedance**: v1.x까지 "d80_specific" 섹션에 있던 Key를 input_digital로 재배치(Key/Value/Unit 및 근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

**[12] Digital_Standard — S/PDIF가 OM 본문에도 명시됨**: LA2Xi에서는 AE만 S/PDIF를 언급하고 OM 공식 스펙 표에는 없어 각주 처리했으나, LA4X는 OM 본문(p.15 "compliant with the AES/EBU (AES3) or electrical S/PDIF (IEC 60958 Type II) digital audio standards")과 스펙 표(p.80 "Standard AES/EBU (AES3) or electrical S/PDIF (IEC 60958 Type II)") 모두에서 S/PDIF를 명시적으로 포함한다. 따라서 이번에는 OM 근거로 Value에 직접 포함시켰다 — LA2Xi 파일의 처리 방식과 다른 이유를 명확히 남긴다.

**[13] Supported_Sampling_Rates — 더 넓은 범위**: LA4X는 다른 제품들(44.1/48/88.2/96/176.4/192)보다 넓은 범위를 지원한다 — 64kHz와 128kHz가 추가로 포함된다(OM p.80 스펙 표, AE 동일: "44.1, 48, 64, 88.2, 96, 128, 176.4 or 192 kHz"). 제품 간 실제 사양 차이이며 소스 충돌이 아니다.

---

## input_avb (AVB / Milan-AVB 입력)

| Key | Value | Unit |
|---|---|---|
| AVB_Certification [14] | MILAN and Avnu certified (Bridge and Listener) — hardware-dependent, see note | - |
| AVB_Channels | 4 | ch |
| AVB_Stream_Count | 1 | streams |
| AVB_Formats | AAF PCM32, IEC 61883-6 AM824 | - |
| AVB_Standards | IEEE 802.1BA-2011 / 1722-2016 / 1722.1-2013 | - |
| AVB_Bridge_Forwarded_Streams | up to 150 | streams |
| Redundancy_Type [14] | Not supported (no redundancy on any LA4X hardware version) | - |
| Fallback_Modes | AVB to XLR (on compatible units); XLR AB to XLR CD (digital to analog or digital to digital) | - |
| AES67_Support [15] | No (not supported on any LA4X hardware version) | - |
| AVB_Device_Type [15a] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Signal inputs, Milan-AVB", p.81 "Specifications > Milan-AVB" (최우선) / AE "Technical requirements > AVB input"

**측정 조건**: Switchover 조건은 AVB loss of lock(AVB→XLR), XLR AB→XLR CD는 no clock/loss of lock/CRC error/bipolar encoding error/data slip(OM p.81).

**[14] AVB_Certification/Redundancy_Type — 하드웨어 버전 의존적, 확정적 비지원**: LA4X는 하드웨어 버전에 따라 AVB 지원 여부가 갈린다(OM p.15, p.29, p.57 반복 확인) — HARDWARE INFO ID1/ID2/ID3는 AVB 미지원(KR LA4XDSP2 구매·설치로 업그레이드 가능), ID4 이상은 AVB 지원. **다만 AVB를 지원하는 ID4 이상 하드웨어에서도 redundancy(이중화)는 어떤 버전에서도 지원하지 않는다**(OM 반복 명시: "support AVB but do not support redundancy"). 이는 LA1.16i/LA2Xi/LA7.16i가 기본적으로 정상/이중화 모드를 모두 지원하는 것과 근본적으로 다른 아키텍처 특성이다. Redundancy_Type을 다른 제품처럼 "seamless" 값으로 채우지 않고 "Not supported"로 명시했다.

**[신규][15] AES67_Support 확정적 비존재**: OM 89페이지 전량 텍스트 스캔 및 AE 전문 검색 결과 "AES67"이라는 용어가 단 한 번도 등장하지 않는다 — LA2Xi(v4.0에서 신규 추가)와 달리 LA4X는 AES67을 전혀 지원하지 않는 것으로 확정 판단했다(SKILL v1.9 "확정된 비존재" 원칙 적용, 전문 검색 근거 명시).

**[15a][구조 개편 v2.0] AVB_Device_Type**: v1.x까지 "d90_specific" 섹션에 Milan_Device_Type이라는 이름으로 있던 Key를 이 섹션의 명명 규칙(AVB_*)에 맞춰 AVB_Device_Type으로 개명하고 재배치했다. 같은 d90_specific 섹션에 있던 Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 3개 Key는 이 섹션의 기존 AVB_Channels/AVB_Stream_Count/Redundancy_Type Key와 개념이 중복되어 별도 Key로 신설하지 않고 흡수했다(3개 모두 애초에 LA4X 소스 기준 null이었으므로 흡수로 인한 값 손실 없음). LA4X는 d&b/Milan 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

---

## network (네트워크 설정, 구조 개편 v2.0 신규 섹션)

| Key | Value | Unit |
|---|---|---|
| Network_IP_Default [1] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: 해당 없음(D90_v1.0.md의 d90_specific 섹션으로부터 재배치).

**[1][구조 개편 v2.0] Network_IP_Default 및 신규 섹션 신설 근거**: v1.x까지 "d90_specific" 섹션에 있던 Key. IP 기본값/네트워크 설정은 AVB 오디오 스트림(input_avb)이나 물리적 커넥터(connectivity)와는 성격이 다른 별도 주제이므로, 이 재배치를 계기로 "network"라는 주제 기반 신규 섹션을 신설했다(D80_v2.0.md/D90_v2.0.md에도 동일 섹션이 반영됨). LA4X는 AVB/Milan/Dante 네트워크 기본 IP 개념에 대응하는 스펙이 확인되지 않아 null 유지.

---

## connectivity (커넥터)

| Key | Value | Unit |
|---|---|---|
| Input_Connectors | 4 x female XLR3 analog/AES-EBU input + 4 x male XLR3 link, 2 x etherCON RJ45 (Milan-AVB I/O) | - |
| Terminal_Block_Pinout | null (not applicable — XLR-based, no terminal blocks) | - |
| XLR_Pin_Polarity [16] | pin 1: shield, pin 2: + signal, pin 3: - signal (IEC 60268-12) | - |
| Speaker_Connectors [17] | 4 x 4-point speakON (Out 1-4) | - |
| SpeakON_Left_Pinout [17] | Pin 1+/1-: Out1, Pin 2+/2-: Out2 | - |
| SpeakON_Right_Pinout [17] | Pin 1+/1-: Out3, Pin 2+/2-: Out4 | - |
| CACOM_Pinout | null | - |
| SC32_Channel_Mapping | null | - |
| Speaker_Output_Accessories | null | - |
| Network_Connectors | 2x etherCON RJ45, 1 Gb/s | - |
| Service_Port_Type | null (not applicable — no USB service port) | - |
| Speaker_Terminal_Block_SE_BTL_Wiring | null (not applicable — no BTL/PBTL) | - |
| PBTL_Activation_Method | null (not applicable) | - |
| Output_Mode_Selectable [17a] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Front and rear panels", p.24-26 "Audio and network cabling > Connection panels, Speaker panel, Signal panels" (최우선) / AE "Technical requirements > Connectors"

**측정 조건**: 없음(커넥터 규격 및 결선표).

**[16] XLR_Pin_Polarity — 확보됨**: LA1.16i/LA2Xi/LA7.16 파일에서는 XLR 자체가 없거나(LA1.16i) 옵션 액세서리에서만 존재해(LA2Xi) null이었으나, LA4X는 본체에 XLR이 표준 탑재되어 있어 이번에 처음으로 실제 값을 채웠다: OM p.26 "The XLR connectors are wired according to IEC 60268-12: pin 1: shield, pin 2: + signal, pin 3: - signal"(OM/AE 없음이나 이는 국제표준 참조라 신뢰 가능, AE는 별도 언급 없음, 단일 소스).

**[17] Speaker_Connectors 및 SpeakON 핀맵**: LA4X는 4개의 4점 speakON 커넥터를 가지며, 좌측 커넥터는 Out1(핀1)/Out2(핀2), 우측 커넥터는 Out3(핀1)/Out4(핀2)로 배선된다(OM p.25 표 및 다이어그램). AE는 추가로 "2 speakON 2P for Out 2 and 4"라는 보조 2점 speakON 커넥터 존재를 언급하나, OM 본문에는 이에 대응하는 별도 커넥터 설명이나 다이어그램이 없다 — AE 단독 서술이며 검증하지 못해 Value에 반영하지 않고 여기 각주로만 남긴다.

**[17a][구조 개편 v2.0] Output_Mode_Selectable**: v1.x까지 "d80_specific" 섹션에 있던 Key를 connectivity로 재배치(Key/Value 및 근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

---

## control_monitoring (제어 및 모니터링)

| Key | Value | Unit |
|---|---|---|
| Remote_Software | LA Network Manager (Windows/Mac) | - |
| Network_Topologies | daisy-chain, star, hybrid | - |
| Third_Party_Control | Q-SYS, Crestron, Extron, SNMP | - |
| Front_Panel [18] | 1 status LED, 1 L-NET LED, 2x24 character LCD display, navigation/edition encoder wheel, power/standby key, channel selection keys, menu keys | - |
| Settings_Protection [19] | Yes — PIN code protected (4-digit) or fully locked per setting, enabled/disabled via LA Network Manager only | - |
| GPIO_Count [20] | 0 (confirmed absent) | ea |
| GPIO_Type | null | - |
| DSP_Backup_Power_Input [21] | null (not supported — no 24 V DC backup input) | V DC |
| Signal_Path_Management [21a] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.17 "Technical description > Monitoring and control", p.63 "Settings protection", p.82 "Specifications > Remote control and monitoring" (최우선) / AE "Technical requirements > Third-party management solutions, Display"

**측정 조건**: L-NET 네트워크는 최대 253대 제어 가능(OM p.17, 다른 제품과 동일).

**[18] Front_Panel — LA1.16i/LA2Xi와 정반대의 아키텍처**: LA1.16i/LA2Xi는 로컬 UI가 전혀 없는(LED만) 설치전용 구조였으나, LA4X는 완전한 로컬 UI(2x24자 LCD, 인코더 휠, 메뉴 버튼, 채널 선택 버튼)를 갖춘 터치 없는 전통형 앰프 인터페이스다(OM p.14, "Using the main menu" 절 p.37 이하 전체). 이는 LA4X가 설치전용 "i" 라인이 아니라는 근거이기도 하다.

**[신규][19] Settings_Protection — 구체적 메커니즘 확보**: LA1.16i/LA2Xi/LA7.16에서는 null이었던 항목인데, LA4X OM은 "Settings protection" 절(p.63)에서 상세히 서술한다 — LA Network Manager에서만 활성화/비활성화 가능하며, 활성화 시 일부 설정은 완전 잠금(locked), 일부는 4자리 PIN 코드로 일시 우회 가능(PIN code protected). 잠금 대상: quick access gain, DELETE PRESET, RESET TO FACTORY DEFAULT SETTINGS. PIN 보호 대상: LOAD PRESET FACTORY, STORE PRESET, PRESET PARAMETERS, CLEAR GROUP PARAMS, NETWORK ADDRESS. 이 신규 정보는 향후 다른 제품 재검토 시 참고할 만하다(다른 제품에서 null 처리된 것이 실제 비지원이 아니라 단순히 소스에 서술이 없었을 가능성 시사).

**[신규][20] GPIO_Count 확정적 비존재**: LA2Xi(4개), LA1.16i(3개)와 달리 LA4X는 OM 89페이지 전량 검색 결과 "GPIO"라는 용어가 전혀 등장하지 않는다 — LA4X에는 GPIO 기능 자체가 없는 것으로 확정 판단했다(SKILL v1.9 원칙 적용).

**[신규][21] DSP_Backup_Power_Input 확정적 비존재**: LA1.16i/LA2Xi에는 24V DC 백업 전원 입력이 있었으나, LA4X의 OM/AE 어디에도 24V DC 관련 서술이 전혀 없다 — 전량 검색 결과 확정적 비지원으로 판단.

**[21a][구조 개편 v2.0] Signal_Path_Management**: v1.x까지 "d80_specific" 섹션에 있던 Key를 control_monitoring으로 재배치(Key/Value 및 근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

---

## operating_conditions (동작 환경)

| Key | Value | Unit |
|---|---|---|
| Operating_Temp_Range [22] | 0 to 50 | degrees C |
| Cooling | 2 fans, temperature-controlled speed, front to rear airflow | - |
| Fan_Count | 2 | ea |
| Fan_Noise_Min | 20 | dBA |
| Fan_Noise_Max | 45 | dBA |
| EMC_Class [23] | E1 (residential), E2 (commercial/light industrial), E3 (urban outdoors), E4 (controlled EMC environment), per EN55103-2 | - |
| Max_Operating_Altitude | null | m |
| Storage_Temp_Range [23a] | null | degrees C |
| Storage_Humidity [23a] | null | % rel. |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "Additional important safety instructions", p.79 "Specifications > Power supply/Protection" (최우선) / AE "Technical requirements > Operating conditions"

**측정 조건**: Fan_Noise는 free field, 1m 거리 기준. Fan_Count(2)는 OM 스펙 표(p.79 "2 fans, temperature-controlled speed")와 AE("2 integrated, temperature-controlled fans")가 일치.

**[22] Operating_Temp_Range — 다른 제품과 다른 하한값**: LA4X는 0°C/32°F 하한이다(OM p.8, p.79 일치) — LA1.16i/LA2Xi/LA7.16의 -5°C 하한과 다르다. 제품 간 실제 사양 차이.

**[23] EMC_Class — 완전히 다른 분류 체계**: LA1.16i/LA2Xi는 EN55103-2가 아닌 자체 Class A/B(잔류자기/CISPR 스타일) 체계를 썼으나, LA4X의 안전 섹션(OM p.8)은 EN55103-2 표준의 E1~E4(환경 등급) 체계를 명시한다: "Conformed environments are: E1 (residential), E2 (commercial and light industrial), E3 (urban outdoors), E4 (controlled EMC environment, ex. TV studio)". 원문 분류 체계를 임의로 다른 제품의 Class A/B 표기로 변환하지 않고 그대로 보존했다. Max_Operating_Altitude는 OM/AE 어디에도 명시되지 않아 null.

**[23a][구조 개편 v2.0] Storage_Temp_Range/Storage_Humidity**: v1.x까지 "d80_specific" 섹션에 있던 Key를 operating_conditions로 재배치(Key/Value/Unit 및 근거는 변경 없음). LA4X는 d&b 브랜드 고유 개념에 대응하는 스펙이 없어 null 유지.

---

## physical (물리적 스펙)

| Key | Value | Unit |
|---|---|---|
| Width | 483 | mm |
| Height | 88 | mm |
| Depth [24] | 420 | mm |
| Weight | 11.3 | kg |
| Protection_Rating | IP3x | - |
| Finish | black | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.20 "Installation > Mounting > LA4X dimensions", p.82 "Specifications > Physical data" (최우선) / AE "Physical data"

**측정 조건**: Height(88mm)는 OM/AE 정확히 일치 — LA1.16i AE의 88mm 오기 의혹(각주 참조)과 달리 LA4X는 실제로 2U(88mm)가 맞는 제품이라 일치가 당연하다. Weight(11.3kg), Width(483mm) 모두 OM/AE 일치, 충돌 없음.

**[24] Depth — 여러 후보값 중 선택**: OM 치수 도면(p.20)에는 465mm/18.3in(측면도 전체 폭), 406mm/16in, 420mm/16.5in, 398mm/15.7in, 434mm/17in 등 다수의 치수가 혼재한다. AE는 "420 mm / 16.5 in"을 D(깊이) 값으로 명시하며, 이는 OM 도면에 동일하게 등장하는 수치와 일치하여 이를 채택했다(OM/AE 일치, 충돌 아님). 나머지 OM 도면 수치는 다른 측정 기준점(브래킷 포함/미포함 등)으로 추정되나 명확한 대응 관계를 확인할 수 없어 각주 대상에서 제외했다.

---

## protection_summary (보호 회로)

| Key | Value |
|---|---|
| Protection_Mains_PSU [25] | heat-sinks temperature monitoring |
| Protection_Outputs [25] | output over current protection |
| Protection_Transducer | L-DRIVE: excursion, temperature, over-voltage |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.79 "Specifications > Protection" (최우선) / AE에는 대응 소단락 없음(OM 단독 출처)

**[25] Protection_Mains_PSU/Outputs — 서술 간소화**: LA4X의 OM 보호 목록(p.79)은 "Circuits protection: heat-sinks temperature monitoring, output over current protection" / "Transducers protection: L-DRIVE"로만 구성되어 있으며, 다른 제품에 있는 "over/under voltage", "overcurrent (fuse protection, inrush current protection)", "short circuit", "DC" 같은 세분화된 항목이 명시적으로 나열되어 있지 않다. 원문 그대로 간략히 반영했으며, 다른 제품의 세부 항목을 임의로 이식하지 않았다(무결성 원칙).

---

## Null Report

이번 소스 집합에서 정의되지 않아 null 처리된 항목 (총 42건, v1.0의 45건에서 재계산 + D25 파싱 중 발견된 신규 Key Max_Output_Current_Peak 1건 소급 반영):

**비적용(제품 아키텍처상 해당 없음, 총 15건)**: Rated_Power_Per_Ch_BTL, Peak_Power_Per_Ch_BTL, Rated_Power_Per_Ch_PBTL, Peak_Power_Per_Ch_PBTL(구조 개편 v2.0으로 10개 세부 Key에서 4개로 통합, Bridging_Support 확정적 비존재에 연동), Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method(동일 브릿징 확정적 비존재 근거), Service_Port_Type, GPIO_Type(GPIO_Count=0 확정적 비존재에 연동), DSP_Backup_Power_Input, Terminal_Block_Pinout, Rated_Power_Per_Ch_2.7_Ohms, Rated_Power_Per_Ch_16_Ohms, Peak_Power_Per_Ch_4_Ohms, Peak_Power_Per_Ch_8_Ohms, Peak_Power_Per_Ch_16_Ohms(이 5건은 LA4X 소스에 해당 임피던스/피크 조건 자체가 제공되지 않는 구조, 각주 [1] 참조).

**미확인(소스에 명시 없음, 총 9건)**: Total_Power_Capability, Max_Output_Current_Peak(D25 파싱 중 발견된 신규 Key 소급 반영), EQ_Filters_Per_Output, Amplifier_Power_Management(L-SMART 없음), THD_N_4ohm, CACOM_Pinout, SC32_Channel_Mapping, Speaker_Output_Accessories, Max_Operating_Altitude.

**d&b/Milan 브랜드 고유 개념 재배치(구조 개편 v2.0, 총 18건)**: (구)d80_specific 12개 Key가 각 재배치된 섹션에서 null 유지 — CMRR_Analog_Input(input_analog), Digital_Input_Impedance(input_digital), SN_Ratio_Analog_Input/SN_Ratio_Digital_Input(audio_performance), System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check(dsp), Storage_Temp_Range/Storage_Humidity(operating_conditions), Signal_Path_Management(control_monitoring), Output_Mode_Selectable(connectivity), Mains_Current_Limiter_Range(power_supply). (구)d90_specific 9개 Key 중 Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 3개는 input_avb의 기존 AVB_Channels/AVB_Stream_Count/Redundancy_Type Key에 흡수되어 별도 null 카운트에서 제외되었고, 나머지 6개는 재배치된 위치에서 null 유지 — AVB_Device_Type(input_avb, Milan_Device_Type에서 개명), Network_IP_Default(신설 network 섹션), Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail(dsp), Output_Noise_Dynamic_Range_Detail(audio_performance). LA4X는 d&b audiotechnik 브랜드 고유 개념에 대응하는 스펙이 확인되지 않아 이 18건 전량 null이다.

확정적 비존재(0/No)로 명시한 항목은 Bridging_Support, AES67_Support, GPIO_Count, DSP_Backup_Power_Input, Redundancy_Type 등 5건이며 각각 전문 검색 근거를 각주에 명기했다(이 중 GPIO_Type/Rated·Peak_Power_Per_Ch_BTL·PBTL 등은 위 null 목록에도 포함되나, 이는 상위 확정적 비존재 판단에 연동된 하위 세부 Key이기 때문이다).

## 버전 변경 이력

v1.0: Phase 3-1 신규 제품 파싱. OM(89p) + AE(docx) 2개 소스를 교차 검증하여 마스터 스키마 최초 구축. LA1.16i/LA2Xi와 달리 LA7.16_v1.6.md(구형 XLR/speakON 계열)의 Key 목록/구조를 뼈대로 복제 — LA4X가 설치전용 "i" 라인이 아니라 전통형 2U 앰프(완전한 LCD/인코더 로컬 UI, XLR 커넥터, speakON 출력, 하드웨어 버전 의존적 AVB, redundancy 전면 미지원, AES67 전면 미지원)이기 때문이다. 신규 확보 정보: XLR 핀 극성(국제표준 근거), Settings_Protection 상세 메커니즘(PIN코드/잠금 구분), 확정적 비존재 5건(Bridging, AES67, GPIO, 24V DC 백업, Redundancy). 소스 간 데이터 충돌 2건(THD_N_8ohm 조건 서술 차이·값 일치, Noise_Level -70 vs -71 dBV, Latency_Low_Mode 0.84 vs 0.76 ms) 발견 및 각주로 보존.

v1.0 to v2.0: (구조 개편, Major) D80/D90에서 먼저 시행된 구조 개편을 동일하게 LA4X에 적용했다. d&b 제품군(D80/D90/D25 등)과의 양방향 스키마 동기화 과정에서 생겨난 "d80_specific"/"d90_specific" 그랩백(grab-bag) 섹션 2개를 폐지하고, 그 안의 21개 Key(d80_specific 12개 + d90_specific 9개)를 주제(스펙 영역) 기준 기존 섹션으로 재분배했다. d80_specific의 12개: CMRR_Analog_Input -> input_analog, Digital_Input_Impedance -> input_digital, SN_Ratio_Analog_Input/SN_Ratio_Digital_Input -> audio_performance, System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check -> dsp, Storage_Temp_Range/Storage_Humidity -> operating_conditions, Signal_Path_Management -> control_monitoring, Output_Mode_Selectable -> connectivity, Mains_Current_Limiter_Range -> power_supply로 재배치(Key/Value/Unit 및 근거는 변경 없음, 위치만 이동). d90_specific의 9개: Milan_Device_Type은 input_avb 섹션의 명명 규칙(AVB_*)에 맞춰 AVB_Device_Type으로 개명 후 재배치, Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 3개는 input_avb의 기존 AVB_Channels/AVB_Stream_Count/Redundancy_Type Key와 개념이 중복되어 별도 Key로 신설하지 않고 흡수(신규 Key 미생성, 값 손실 없음 — LA4X는 애초에 이 3개 모두 null이었음), Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail -> dsp, Output_Noise_Dynamic_Range_Detail -> audio_performance, Network_IP_Default -> 신설된 network 섹션(D80_v2.0.md/D90_v2.0.md와 동일한 신규 섹션, LA4X는 이 섹션도 전량 null)으로 재배치. 아울러 amplification 섹션의 BTL/PBTL 전력 Key 10개(부하 임피던스별 세분화: Rated/Peak_Power_Per_Ch_BTL_8/16_Ohms, Rated/Peak_Power_Per_Ch_PBTL_4/8/16_Ohms)를 4개(Rated_Power_Per_Ch_BTL, Peak_Power_Per_Ch_BTL, Rated_Power_Per_Ch_PBTL, Peak_Power_Per_Ch_PBTL)로 통합했다(LA4X는 브릿징을 확정적으로 지원하지 않아 10개 모두 null이었으므로 통합으로 인한 값 손실 없음). **amplification 섹션의 Bridging_Support Key 자체(Value: "No (not supported — no BTL/PBTL mode, no bridging procedure in OM)", 확정적 비존재 판단, 각주 [2])는 이번 구조 개편으로 전혀 변경하지 않았다** — 통폐합 대상은 어디까지나 그 하위 세부 전력 Key 10개→4개일 뿐이다. 이동한 Key마다 원래 위치(d80_specific/d90_specific)를 명시하는 각주를 각 섹션 내에서 기존 각주 번호와 충돌하지 않는 번호(letter-suffix 방식, 예: [11a], [9a]/[9b])로 신설했다. Null Report를 41건으로 재계산(v1.0의 45건에서 변경 — 산정 방식 자체를 비적용/미확인/d&b 재배치 3개 범주로 재구성하며 원본 v1.0의 집계 오류도 함께 바로잡음: 브릿징 관련 Key는 실제로는 10개였으나 v1.0 Null Report 문구는 "8개"로 오기되어 있었고, "총 24건"이라는 소계도 실제 항목 수와 맞지 않았다 — 이번 재계산은 정확한 실제 Key 개수 기준으로 처음부터 다시 집계한 값이다). 섹션 계층 구조 자체가 바뀌는 변경이므로 SKILL의 버저닝 규칙에 따라 Major 버전(v2.0)으로 상향했다.
