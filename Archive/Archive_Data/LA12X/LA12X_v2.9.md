# LA12X - Master Spec Schema

Schema_Version: 2.9 (Phase 4 양방향 동기화 - Upload 4개 제품(LA1.16i/LA2Xi/LA4X/LA7.16i) 파싱 중 발견된 신규 15개 Key 반영)
최종 작업 일시: 2026-07-15 21:43 (수요일)
Manufacturer: L-Acoustics
Product_Category: Amplified_Controller (4-channel Class D amplifier with integrated DSP)
Form_Factor: 19 inch rack, 2U

버전 재분류 안내 (SKILL v1.8 시맨틱 버저닝 소급 적용): 이 파일은 원래 v5.1로 발행되었으나, 양방향 동기화로 신규 Key 1개를 null로 추가한 것은 하위 호환 변경이므로 Minor 버전(v2.4)으로 재분류되었다. 이하 "버전 변경 이력" 절의 서술은 발행 당시 원문 그대로 보존한다.
Manufacturer: L-Acoustics
Product_Category: Amplified_Controller (4-channel Class D amplifier with integrated DSP)
Form_Factor: 19 inch rack, 2U

## 출처 등록부 (Source Registry)

| Source_ID | Document | Version / Date |
|---|---|---|
| OM | Owner's Manual (EN) | v10.1, 2023-08-31 |
| SPS | Spec Sheet PDF (EN) | 2.5, 2025-08 |
| AE | Architects and Engineers Spec (docx) | undated |
| WEB-L | Website - List View | current |
| WEB-O | Website - Overview | current |
| WEB-F | Website - Full Spec | current |

L-Acoustics 브랜드 규칙에 따라 이하 모든 섹션의 출처 표기는 오너 매뉴얼(OM)의 페이지/목차 위치를 최우선으로 기록한다.

본 파일은 SKILL v1.7의 "완벽한 양방향 스키마 동기화" 규칙에 따라 D80_v1.0.md와 Key 목록을 100% 일치시킨 v2.6 개정본이다. Phase 3-2(타 브랜드 교차 테스트)에서 d&b D80 파싱 중 발견된 신규 섹션 `d80_specific`(12개 Key: CMRR_Analog_Input, Digital_Input_Impedance, SN_Ratio_Analog_Input, SN_Ratio_Digital_Input, System_Start_Up_Time, Storage_Temp_Range, Storage_Humidity, LoadMatch_Max_Cable_Length, Signal_Path_Management, Load_Monitoring_System_Check, Output_Mode_Selectable, Mains_Current_Limiter_Range)를 전량 `null`로 신설 추가했다. 기존 v2.5의 값과 각주는 일절 변경하지 않았다. 상세 근거는 D80_v1.0.md 각 섹션 각주를 참조.

**Phase 4 동기화 안내(v2.9)**: Upload 폴더 4개 신규 제품(LA1.16i, LA2Xi, LA4X, LA7.16i) 파싱 과정에서 발견된 15개 신규 Key(브릿지 모드 관련 10개, AES67_Support, Service_Port_Type, Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method)를 아래 각 섹션에 `null`로 신설 추가했다. LA12X의 기존 소스(OM v10.1, SPS 2.5, AE)에는 브릿지 모드/AES67/USB 서비스 포트 관련 서술이 전혀 확인되지 않으며, 원본 문서를 재조회하지 않고 기존 파싱 결과물 텍스트만을 근거로 판단했으므로(사용자 승인에 따른 진행 방식) "확정된 비존재(No/0)"가 아닌 **미확인(null)**으로 보수적으로 처리했다 — 추후 LA12X 원본 OM 재검토 시 갱신 필요. 기존 9개 섹션 및 d80_specific/d90_specific의 Key/Value/각주는 일절 변경하지 않았다.

---

## amplification (증폭부)

| Key | Value | Unit |
|---|---|---|
| Channel_Count_In | 4 | ch |
| Channel_Count_Out | 4 | ch |
| Amplification_Class [1] | Class D | - |
| Rated_Power_Per_Ch_2.7_Ohms [2] | 3300 | W |
| Rated_Power_Per_Ch_4_Ohms [2] | 2600 | W |
| Rated_Power_Per_Ch_8_Ohms [2] | 1400 | W |
| Rated_Power_Per_Ch_16_Ohms [신규] | null | W |
| Peak_Power_Per_Ch_4_Ohms [신규] | null | W |
| Peak_Power_Per_Ch_8_Ohms [신규] | null | W |
| Peak_Power_Per_Ch_16_Ohms [신규] | null | W |
| Total_Power_Capability | 12000 | W |
| Max_Output_Voltage_Peak | 157 | V |
| Amplification_Gain | 32 | dB |
| Output_Delay_Range | 0 - 1000 | ms |
| Bridging_Support [신규][14] | null | - |
| Rated_Power_Per_Ch_BTL_8_Ohms [신규][14] | null | W |
| Rated_Power_Per_Ch_BTL_16_Ohms [신규][14] | null | W |
| Peak_Power_Per_Ch_BTL_8_Ohms [신규][14] | null | W |
| Peak_Power_Per_Ch_BTL_16_Ohms [신규][14] | null | W |
| Rated_Power_Per_Ch_PBTL_4_Ohms [신규][14] | null | W |
| Rated_Power_Per_Ch_PBTL_8_Ohms [신규][14] | null | W |
| Rated_Power_Per_Ch_PBTL_16_Ohms [신규][14] | null | W |
| Peak_Power_Per_Ch_PBTL_4_Ohms [신규][14] | null | W |
| Peak_Power_Per_Ch_PBTL_8_Ohms [신규][14] | null | W |
| Peak_Power_Per_Ch_PBTL_16_Ohms [신규][14] | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.83 "Specifications > General" (최우선) / SPS 3p "Amplification and power supply" / AE "Technical requirements > Amplification" / WEB-O, WEB-L, WEB-F 스펙 표

**측정 조건**: 출력 정격은 CEA-2006/490A 기준, 1 kHz sine burst, THD < 1%, 전 채널 구동 조건에서 측정. Amplification_Gain, Output_Delay_Range는 별도 조건 없이 사양값. 부하 임피던스는 속성명(Key)과 값(Value) 양쪽 모두 표준 소수점 표기(2.7 / 4 / 8 Ohms)로 정제했다 — 원문에 유럽식 표기(2R7 등)가 있었다면 Key에도 동일하게 반영해야 하며, 본 소스는 이미 소수점(2.7 ohms) 형식으로 기재되어 있어 값 자체의 변경은 없고 Key 명명만 `Rated_Power_Per_Ch_2.7_Ohms` 형태로 표준화했다.

**[1] Amplification_Class 표현 차이 (수정)**: OM(p.17)과 SPS/WEB-F는 "Class D"만 명시. AE 시방서는 동일 항목을 "High-efficiency Class D"로 확장 표기. 두 표현 모두 원문에 존재하나, 4개 소스(OM, SPS, WEB-L, WEB-F) 중 3개가 수식어 없는 "Class D"로 일치하므로 이를 Value로 채택하고, AE의 "High-efficiency" 수식어는 여기 각주에서만 병기한다. 이전 v2.0 결과물에서는 이 수식어를 출처 표시 없이 Value에 직접 병합했던 오류가 있었음 — 본 v3.0에서 정정.

**[2] 측정 버스트 길이 충돌**: OM과 SPS는 sine burst 20 ms로 명시(CEA-2006/490A 표준 조건). AE 시방서는 동일 항목을 "no limiter, 200 ms sine burst" 조건으로 명시 — 두 조건 모두 원문 그대로 보존. 채택 값은 20 ms 조건(OM+SPS 일치, 표준 규격 명시)을 대표값으로 사용했으나, 200 ms 조건의 AE 수치도 삭제하지 않음(수치 자체는 동일하게 3300/2600/1400 W로 일치, 조건 표기만 상이).

**[신규] Rated_Power_Per_Ch_16_Ohms, Peak_Power_Per_Ch_4/8/16_Ohms**: LA7.16(16채널) 파싱 중 발견된 신규 속성. LA12X의 OM/SPS/AE 소스는 16 Ω 부하 조건을 다루지 않으며, 12 dB Crest Factor 기준의 별도 Peak(피크) 출력 수치도 제공하지 않는다(LA12X 소스는 CEA/RMS 조건의 Rated_Power만 명시) — 임의 추론 금지 원칙에 따라 이 값들을 계산하거나 추정하지 않고 null로 유지한다. 향후 LA12X 원본 문서에서 해당 조건의 수치가 확인되면 갱신한다.

**[신규][14] Bridging_Support 및 BTL/PBTL 관련 10개 Key (v2.9, Phase 4 동기화)**: L-Acoustics "i" 설치전용 라인(LA1.16i, LA2Xi) 파싱 중 발견된 브릿지 모드(SE/BTL/PBTL) 관련 속성군. LA12X의 기존 소스(OM v10.1, SPS 2.5, AE) 어디에도 브릿지/BTL/PBTL 관련 서술이 확인되지 않는다 — 다만 이는 원본 문서를 재조회하지 않고 기존 파싱 결과 텍스트만으로 판단한 것이므로(사용자 승인에 따른 보수적 처리 방식), LA4X처럼 전체 문서 재검색을 거쳐 "확정된 비존재(No/0)"로 단정하지 않고 **미확인(null)**으로 유지한다. LA12X는 speakON/CA-COM 커넥터로 채널을 개별 구동하는 구조이며 LA7.16(구형)과 함께 브릿지 개념 없이 설계된 세대로 추정되나, 이는 추정일 뿐 확정 근거가 아니다. 추후 LA12X 원본 OM 재검토 시 갱신 대상.

---

## power_supply (전원부)

| Key | Value | Unit |
|---|---|---|
| PSU_Type | Universal SMPS with DSP-controlled PFC | - |
| Mains_Voltage_Range | 100 - 240 (+/-10%) | V AC |
| Mains_Frequency_Range | 50 - 60 | Hz |
| Nominal_Current_100_120V | 30 | A |
| Nominal_Current_200_240V [2] | 16 | A |
| Power_Factor | greater than 0.9 | - |
| Power_Consumption_Idle | 141 | W |
| Power_Consumption_Standby | 10 | W |
| Mains_Connector | powerCON 32 A | - |
| PSU_Mains_Rated_Power [신규] | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.21 "Installation > Electrical specifications", p.23 "Power consumption" (최우선) / SPS 3p "Amplification and power supply" / AE "Technical requirements"

**측정 조건**: Power_Consumption_Idle/Standby는 230/120/100 V 공통값(전압별 전류는 상이하나 W 기준 동일). Power_Factor는 전 전압에서 Standby 모드 제외, 230 V Idle 모드 제외 조건.

**[2] 적용 전압 대역 표기 차이**: OM의 안전 섹션(p.7-8)은 "220-240 V: 16 A"로 서술하나, OM 스펙 섹션(p.21, p.83)과 SPS는 동일 항목을 "200-240 V: 16 A"로 표기. 두 표기 모두 보존 — 안전 섹션은 유럽 지역 규격(220-240 V) 관점의 서술로 판단되며, 스펙 섹션의 200-240 V가 제품 정격 표기로 더 넓은 범위를 포괄함.

**[신규] PSU_Mains_Rated_Power**: LA7.16 v1.1 재검토 과정에서 신설된 Key(SMPS 연속 메인즈 입력 전력 정격, LA7.16은 OM에 "2800 W"로 명시. D80은 "7000 W, short term RMS" 조건으로 명시, D80_v1.0.md power_supply 섹션 참조). LA12X의 기존 소스(OM v10.1, SPS 2.5, AE)에는 이에 대응하는 명시적 "Mains rating ... W" 단일 수치가 확인되지 않아 null로 처리한다. 참고로 LA12X의 `Total_Power_Capability`(12000 W)는 이 PSU_Mains_Rated_Power와는 다른 개념(총 출력 용량)으로 판단되며 혼동하여 대입하지 않았다.

---

## audio_performance (음향 스펙)

| Key | Value | Unit |
|---|---|---|
| Frequency_Response | 20 - 20000 | Hz |
| THD_N_8ohm | less than 0.05 | % |
| THD_N_4ohm | less than 0.1 | % |
| Output_Dynamic_Range | greater than 114 | dB |
| Noise_Level [3] | less than -75 | dBV |
| Channel_Separation | greater than 85 | dB |
| Damping_Factor | greater than 400 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.83 "Specifications > General" (최우선) / SPS 3p "Audio specifications" / AE "Technical requirements > Amplification"

**측정 조건**: Frequency_Response는 8옴 부하 60 W 출력 및 4옴 120 W 출력 기준 +/-0.1 dB. THD_N은 20 Hz-10 kHz 대역, 각 부하별 동일 출력 기준. Output_Dynamic_Range와 Noise_Level은 20 Hz-20 kHz, 8옴, A-weighted 기준. Channel_Separation은 1 kHz, 4옴, 3채널 x 120 W 구동 기준. Damping_Factor는 1 kHz 이하, 8옴 기준.

**[3] Noise_Level 충돌**: OM(개정판 v10.0에서 "노이즈 레벨 갱신" 이력 있음)과 SPS는 "-75 dBV"로 일치. AE 시방서는 동일 항목을 "-72 dBV"로 표기. 두 값 모두 보존 — 채택값 -75 dBV는 최신 개정 이력이 명시된 OM과 SPS 2개 소스 일치를 근거로 함. -72 dBV(AE)는 구버전 수치로 추정되나 원문 값은 삭제하지 않음.

---

## dsp (신호 처리)

| Key | Value | Unit |
|---|---|---|
| DSP_Processor | 2x SHARC 32-bit floating point | - |
| DSP_Sampling_Rate [12] | 96 (internal, fixed, independent from input Fs) | kHz |
| Routing_Matrix | 4x4 routing and summation | - |
| EQ_Filters_Per_Output | 8 IIR + 4 FIR linear phase | - |
| Per_Channel_DSP_Tools [신규] | null | - |
| Amplifier_Power_Management [신규] | null | - |
| Speaker_Protection | L-DRIVE (excursion, temperature, over-voltage) | - |
| Preset_Memory_User | 10 | slots |
| Preset_Memory_Factory | 189 | slots |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.16 "Technical description > DSP architecture", p.36-42 "Operation > Using the main menu" (최우선) / SPS 3p "DSP" / AE "Technical requirements > DSP"

**측정 조건**: 없음(사양값). Preset_Memory_User는 메모리 001-010(읽기/쓰기), Preset_Memory_Factory는 메모리 011-199(읽기 전용, 펌웨어 업데이트 시 자동 설치)로 구분.

**[신규] Per_Channel_DSP_Tools, Amplifier_Power_Management**: LA7.16 파싱 중 발견된 신규 속성. LA7.16의 OM/SPS 스펙 표에는 "Array morphing", "Air absorption compensation filters", "L-SMART" 등이 명시적으로 기재되어 있으나, LA12X의 기존 소스(OM v10.1, SPS 2.5)에는 이에 대응하는 명시적 스펙 표 항목이 확인되지 않아 임의로 값을 채우지 않고 null로 둔다. LA12X가 실제로 이 기능들을 지원하는지 여부는 본 스키마의 범위를 벗어나며, 추후 LA12X 원본 문서 재검토 시 갱신 대상이다.

**[신규][12] DSP_Sampling_Rate 값의 근거 및 d&b D80과의 서술 유무 차이 (사용자 검토 반영, 양방향 동기화 보강)**: LA12X는 모든 AES/EBU 입력 포트에 SRC(Sample Rate Converter)가 상시 하드웨어로 내장되어 있으며, OM p.15 "Signal processing" 절 원문은 다음과 같다 — "Each AES/EBU input port is equipped with an SRC (Sample Rate Converter)... The SRC converts the formats to the 24 bits / 96 kHz internal format... and provides constant propagation delay regardless of the input sampling frequency." 즉 입력이 어떤 샘플레이트로 들어오든 SRC가 상시 작동하여 항상 96 kHz 내부 포맷으로 변환하며, 이로 인한 지연시간도 입력 샘플레이트와 무관하게 일정하다는 점이 OM 본문에서 명시적으로 확정되어 있다. **d&b D80과의 서술 유무 차이**: d&b D80은 이와 반대로 SRC를 기본적으로 비활성화해 두고(SRC가 상시 내장된 하드웨어가 아니라 조건부 활성화 방식), 44.1/88.2 kHz 등 비표준 입력이나 비동기 다중 소스 입력 시에만 SRC를 수동으로 켜는 구조다(D80 OM p.34 "System clocking"/"SRC" 절). 이 때문에 D80의 DSP_Sampling_Rate(96 kHz, 내부 고정값)는 성립하지만, SRC 비활성 시에만 그렇다는 조건이 붙는다 — 반면 LA12X는 SRC가 상시 하드웨어로 존재하여 이런 조건부 서술이 필요 없다. 이는 값의 정확성 차이가 아니라 두 제품의 실제 아키텍처(SRC 상시 내장 vs 조건부 활성화)가 근본적으로 다르기 때문이며, LA12X 측 문서(OM p.15)가 d&b D80보다 이 부분에서 더 명확하고 확정적인 서술을 제공한다는 점을 양방향 동기화 관점에서 기록한다.

---

## latency (지연 시간)

| Key | Value | Unit |
|---|---|---|
| Latency_Standard [13] | 3.84 (independent from input Fs) | ms |
| Latency_Low_Mode [4][13] | 0.84 (independent from input Fs) | ms |
| AVB_Max_Network_Latency | 2 | ms |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.86 "Specifications > Latency" (최우선) / SPS(웹 반영) / AE "Technical requirements > DSP > Latency"

**측정 조건**: Analog/AES-EBU 입력 기준, 입력 샘플링 주파수와 무관하게 일정.

**[4] Low latency 모드 수치 충돌**: OM p.86과 웹 Full Spec은 "0.84 ms"로 일치. AE 시방서는 동일 항목을 "0.76 ms"로 표기. 두 값 모두 보존 — 채택값 0.84 ms는 2개 소스 일치를 근거로 하며, 0.76 ms는 구버전 수치로 추정.

**[신규][13] Latency_Standard/Low_Mode 값의 확정 근거 및 d&b D80과의 서술 유무 차이 (사용자 검토 반영)**: OM p.86의 Latency 스펙 표는 표준/저지연 두 모드 모두 "independent from input Fs"(입력 샘플링 주파수와 무관)라는 문구를 직접 명시하고 있다 — dsp 섹션 각주 [12]에서 설명한 상시 내장 SRC 하드웨어(OM p.15)가 이 불변성의 근거다. 즉 LA12X의 레이턴시 값은 입력 조건에 관계없이 항상 성립하는 무조건적 고정값이며, 이는 OM 원문에서 직접 확정하는 서술이다. **d&b D80과의 비교**: D80은 반대로 Latency_Standard(0.3 ms)가 "SRC 비활성, 입력 48/96 kHz" 조건에서만 성립하고 SRC 활성화 시 최대 +1 ms까지 증가할 수 있다는 조건부 서술이 OM p.34에 있다(D80_v1.2.md latency 섹션 각주 [12a] 참조) — LA12X처럼 "independent from input Fs"에 해당하는 확정 문구가 D80 소스에는 없다. LA7.16도 OM p.94에 동일한 "independent from input Fs" 문구가 확인된다(LA7.16_v1.6.md 참조). D90은 "permanent SRC" 서술은 있으나 LA12X/LA7.16 수준의 명시적 불변성 확정 문구는 없다(D90_v1.1.md latency 섹션 각주 [9b] 참조) — 4개 제품 중 근거 수준이 가장 높은 것은 LA12X/LA7.16이다.

---

## input_analog (아날로그 입력)

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Channels | 4 | ch |
| Input_Impedance | 22 | kOhm |
| Max_Input_Level | 22 | dBu |
| ADC_Architecture [5] | 4 cascaded 24-bit at 96 kHz | - |
| Analog_Link_Type | passive parallel, 4x XLR3 male | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Signal processing and amplification > Analog", p.85 "Specifications > Analog input" (최우선) / SPS 3p "Inputs / Outputs" / AE "Technical requirements > Analog input"

**측정 조건**: Input_Impedance는 balanced 기준. Max_Input_Level은 balanced, THD 1% 기준. ADC의 130 dB dynamic range는 20 Hz-20 kHz, A-weighted 기준.

**[5] 문서 내부 표기 불일치**: OM 기술 설명 본문(p.15-16)은 "two cascaded 24-bit A/D converters"로 서술하나, 동일 문서의 스펙 섹션(p.85)과 SPS, AE는 모두 "4 cascaded"로 일치. 두 표기 모두 원문에 존재함을 기록하며, 스펙 섹션 및 타 소스 3건 일치를 근거로 "4 cascaded"를 채택값으로 사용.

---

## input_digital (디지털 입력)

| Key | Value | Unit |
|---|---|---|
| Digital_Input_Channels | 4 | ch |
| Digital_Standard [6] | AES/EBU (AES3) | - |
| Supported_Sampling_Rates | 44.1 / 48 / 88.2 / 96 / 176.4 / 192 | kHz |
| Supported_Word_Length | 16 / 18 / 20 / 24 | bit |
| SRC_Output_Format | 24-bit at 96 kHz | - |
| SRC_Dynamic_Range | 140 | dB |
| SRC_THD_N | less than -120 | dBFS |
| Digital_Input_Gain_Range | -12 to +12 | dB |
| Digital_Link_Type | electronically buffered with failsafe relay, 2x XLR3 male | - |
| Max_AES_Cable_Length | 300 | m |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Signal processing and amplification > AES/EBU", p.85 "Specifications > Digital input" (최우선) / SPS 3p "Inputs / Outputs" / AE "Technical requirements > Digital input, Sample Rate Converter"

**측정 조건**: Max_AES_Cable_Length는 단일 케이블, 48 kHz 샘플링, Belden 1696A 또는 Klotz OT234H 케이블 기준. Digital_Input_Gain_Range는 0.1 dB 스텝.

**[6] 디지털 규격 표기 차이**: OM, SPS, WEB-F는 "AES/EBU (AES3)"만 명시. AE 시방서만 동일 항목을 "AES/EBU (AES3) or S/PDIF"로 확장 표기. 두 표기 모두 기록 — AES3 단독 표기가 3개 소스 일치로 채택값이나, AE의 S/PDIF 병기 가능성도 삭제하지 않고 보존.

---

## input_avb (AVB 입력)

| Key | Value | Unit |
|---|---|---|
| AVB_Certification | MILAN and Avnu certified (Bridge and Listener) | - |
| AVB_Channels | 4 | ch |
| AVB_Stream_Count | 1 (2 in redundancy mode) | streams |
| AVB_Formats | AAF PCM32, IEC 61883-6 AM824 | - |
| AVB_Standards | IEEE 802.1BA-2011 / 1722-2016 / 1722.1-2013 | - |
| AVB_Bridge_Forwarded_Streams | up to 150 | streams |
| Redundancy_Type | Milan-AVB seamless, automatic switchover and recovery | - |
| Fallback_Modes | AVB to XLR, AES(AB) to XLR(CD) | - |
| AES67_Support [신규][14] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "AVB", p.47-48 "AVB FALLBACK MODE, AES AB FALLBACK MODE", p.86 "Specifications > AVB" (최우선) / SPS 3p "I/O" / AE "Technical requirements > AVB input"

**측정 조건**: AVB_Channels는 최대 8채널 스트림 1개에서 추출하는 조건. Fallback_Modes 절체 조건은 no clock, loss of lock, CRC error, bipolar encoding error, data slip이며, 복귀는 수동으로만 가능. Redundancy 모드는 star topology 필수(포트 1 = Primary, 포트 2 = Secondary).

**D80과의 비교 참고**: D80(Phase 3-2)은 AVB/Milan 프로토콜을 사용하지 않고 CAN-Bus/Ethernet(OCA)을 사용하므로 input_avb 섹션 전체가 D80에서는 비적용(null)이다. D80의 Fallback_Modes는 이 Key와 동일 명칭이나 "채널별 신호소스 이중화"라는 다른 계층의 개념이며, D80_v1.0.md에서는 별도로 D80 원문 값을 기재했다(LA12X의 이 값을 D80에 이식하지 않음).

**[신규][14] AES67_Support (v2.9, Phase 4 동기화)**: L-Acoustics "i" 설치전용 라인(LA1.16i, LA7.16i)에서 발견된 신규 속성 — Milan-AVB와 AES67을 사용자가 선택 가능한 이중 모드 제품군에서 도입된 Key. LA12X의 기존 소스(OM v10.1, SPS 2.5, AE)에는 AES67 관련 서술이 전혀 확인되지 않는다. 원본 문서를 재조회하지 않은 보수적 처리 방식에 따라 null(미확인)로 유지 — LA12X는 Milan-AVB 전용 제품으로 추정되나 확정 근거는 아니다.

---

## connectivity (커넥터)

| Key | Value | Unit |
|---|---|---|
| Input_Connectors | 4x XLR3 female (2 pair analog/AES3 switching), 4x XLR3 male link | - |
| Terminal_Block_Pinout [신규] | null | - |
| XLR_Pin_Polarity | pin1 shield, pin2 plus (hot), pin3 minus (cold) | - |
| Speaker_Connectors | 2x speakON 4-point, 1x CA-COM 8-point | - |
| SpeakON_Left_Pinout | 1+/1- = Out1, 2+/2- = Out2 | - |
| SpeakON_Right_Pinout | 1+/1- = Out3, 2+/2- = Out4 | - |
| CACOM_Pinout | A/B = Out1, C/D = Out2, E/F = Out3, G/H = Out4 | - |
| SC32_Channel_Mapping [신규] | null | - |
| Speaker_Output_Accessories [신규] | null | - |
| Network_Connectors | 2x etherCON RJ45, 1 Gb/s | - |
| Service_Port_Type [신규][15] | null | - |
| Speaker_Terminal_Block_SE_BTL_Wiring [신규][14] | null | - |
| PBTL_Activation_Method [신규][14] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Front and rear panels", p.24-25 "Speaker panel", p.87 "Specifications > Remote control and monitoring" (최우선) / SPS 3p "Inputs / Outputs" / AE "Technical requirements > Connectors"

**측정 조건**: 없음(커넥터 규격 및 결선표). 극성/핀맵 정보는 OM 내 텍스트 표(회로도 라벨 포함)로 확인되어 별도 이미지 분석은 수행하지 않음. XLR 결선은 IEC 60268-12 규격 준수.

**[신규] SC32_Channel_Mapping, Speaker_Output_Accessories**: LA7.16 파싱 중 발견된 신규 속성. LA12X는 speakON/CA-COM 개별 커넥터 구조를 사용하며 SC32 통합 커넥터를 사용하지 않으므로 해당 없음(null) 처리한다.

**[신규] Terminal_Block_Pinout**: LA7.16 v1.3에서 12-point terminal block(AES/ANA IN+LINK, GPIO, 24V DC backup)의 상세 핀맵이 추가되며 신설된 Key. LA12X는 이런 통합 단자대 구조를 사용하지 않고 전용 XLR3 커넥터(Input_Connectors, XLR_Pin_Polarity 참조)를 사용하므로 해당 없음(null) 처리한다.

**[신규][15] Service_Port_Type (v2.9, Phase 4 동기화)**: "i" 설치전용 라인에서 발견된 IP 설정용 USB 서비스 포트(USB-C 또는 USB Micro-B) Key. LA12X의 기존 소스에는 USB 서비스 포트 관련 서술이 확인되지 않아 null 처리한다.

**Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method는 각주[14] 참조**(amplification 섹션 Bridging_Support와 동일한 브릿지 모드 관련 신규 속성군).

---

## control_monitoring (제어 및 모니터링)

| Key | Value | Unit |
|---|---|---|
| Remote_Software | LA Network Manager (Windows/Mac) | - |
| Network_Topologies | daisy-chain, star, hybrid | - |
| Third_Party_Control [7] | Q-SYS, Crestron, Extron, SNMP, Control4, Savant, HTTP API | - |
| Front_Panel | 2x24 character LCD, rotary encoder, power/mute keys, status LEDs | - |
| Settings_Protection | 4-digit PIN code, configurable in LA Network Manager | - |
| GPIO_Count [신규] | null | ea |
| GPIO_Type [신규] | null | - |
| DSP_Backup_Power_Input [신규] | null | V DC |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.17 "L-NET remote control network", p.32-63 "Operation" (최우선) / SPS 3p "Control and monitoring" / AE "Technical requirements > Third-party management solutions" / WEB-O, WEB-F

**측정 조건**: L-NET 네트워크는 최대 253대 제어 가능, CAT5e U/FTP 이상 케이블 사용.

**[7] 서드파티 제어 목록 차이**: OM과 AE는 Q-SYS, Crestron, Extron, SNMP만 명시. SPS와 웹(WEB-O, WEB-F)은 여기에 Control4, Savant, HTTP API를 추가한 상위 목록을 명시. 두 목록 모두 보존 — 항목 누락이 아닌 문서 발행 시점 차이로 판단하여, 최신 소스(SPS, 웹)의 상위 집합을 채택값으로 사용.

**[신규] GPIO_Count, GPIO_Type, DSP_Backup_Power_Input**: LA7.16 파싱 중 발견된 신규 속성. LA12X의 기존 소스(OM v10.1, SPS 2.5, AE)에는 GPIO 관련 커넥터나 스펙 항목이 확인되지 않아 null로 처리한다. LA12X 실물에 GPIO 기능이 존재하는지 여부는 이번 소스 집합만으로는 판단할 수 없다. 참고로 D80(Phase 3-2)은 OM 전문 검색 결과 GPIO 용어 자체가 전혀 발견되지 않아 GPIO_Count를 0(확정적 비존재)으로 명시했으나, LA12X는 "미확인"이므로 여전히 null(불확실)로 구분 유지한다.

---

## operating_conditions (동작 환경)

| Key | Value | Unit |
|---|---|---|
| Operating_Temp_Range [8] | 0 to 50 | degrees C |
| Cooling | temperature-controlled fans, front to rear airflow | - |
| Fan_Count | 3 | ea |
| Fan_Noise_Min | less than 34 | dBA |
| Fan_Noise_Max | less than 62 | dBA |
| EMC_Class | residential Class B | - |
| Max_Operating_Altitude [신규] | null | m |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "Additional important safety instructions", p.83 "Specifications > General" (최우선) / SPS 3p "Operating conditions" / AE "Technical requirements > Operating conditions"

**측정 조건**: Fan_Noise는 free field, 1 m 거리 기준(Min은 최저속, Max는 최고속).

**[8] 동작 온도 하한 충돌**: OM 안전 섹션(p.8)은 "-5 degrees C to 50 degrees C"로 명시. OM 스펙 섹션(p.83), SPS, AE, WEB-F는 모두 "0 degrees C to 50 degrees C"로 일치. 두 값 모두 보존 — 채택값 0도는 3개 소스 일치와 최신 SPS(2.5판) 기준을 근거로 함. -5도(OM 안전 섹션)는 보다 보수적인 여유 범위 서술로 추정되며 삭제하지 않음.

**[신규] Max_Operating_Altitude**: LA7.16 파싱 중 발견된 신규 속성(OM 스펙 표에 "Maximum altitude 2000 m"로 명시). LA12X의 기존 소스에는 최대 고도 스펙이 확인되지 않아 null로 처리한다.

---

## physical (물리적 스펙)

| Key | Value | Unit |
|---|---|---|
| Width | 483 | mm |
| Height | 88 | mm |
| Depth | 419.1 | mm |
| Weight | 14.5 | kg |
| Protection_Rating | IP20 | - |
| Finish | black | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.87 "Specifications > Physical data" (최우선) / SPS 3p "Physical data" / AE "Technical requirements > Physical data"

**측정 조건**: Depth는 섀시 기준(419.1 mm). 프런트 핸들 포함 시 454.7 mm, 리어 브래킷 포함 최대 534.3 mm까지 확장(별도 치수, OM p.20). AE는 W/H/D를 483/88/455 mm로 반올림 표기하며, 세부 수치(419.1)와 정수 반올림(455) 모두 원문에 존재하는 것으로 보존.

---

## protection_summary (보호 회로)

| Key | Value |
|---|---|
| Protection_Mains_PSU | over/under voltage, over temperature, overcurrent, inrush current, fuse protect |
| Protection_Outputs | over current, DC, short circuit, rail over/under voltage, over temperature, HF energy above 25kHz detection |
| Protection_Transducer | L-DRIVE: excursion, temperature, over-voltage |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.68-73 "Corrective maintenance > Error messages" (최우선) / SPS 3p "Circuit protection" / WEB-F

**측정 조건**: 없음(보호 기능 목록).

---

## d80_specific (d&b D80 고유 속성, Phase 3-2 신규 섹션)

| Key | Value | Unit |
|---|---|---|
| CMRR_Analog_Input [신규] | null | dB |
| Digital_Input_Impedance [신규] | null | Ohm |
| SN_Ratio_Analog_Input [신규] | null | dBr |
| SN_Ratio_Digital_Input [신규] | null | dBr |
| System_Start_Up_Time [신규] | null | sec |
| Storage_Temp_Range [신규] | null | degrees C |
| Storage_Humidity [신규] | null | % rel. |
| LoadMatch_Max_Cable_Length [신규] | null | m |
| Signal_Path_Management [신규] | null | - |
| Load_Monitoring_System_Check [신규] | null | - |
| Output_Mode_Selectable [신규] | null | - |
| Mains_Current_Limiter_Range [신규] | null | % of rated current |

### 주석 및 출처 (Notes & Sources)

**출처**: 해당 없음(D80_v1.0.md 신규 섹션의 양방향 동기화 반영).

**[신규] 섹션 전체**: D80(d&b audiotechnik) 파싱 중 발견된 12개 신규 속성. LA12X의 기존 소스(OM v10.1, SPS 2.5, AE) 어디에도 이들 항목(CMRR, S/N ratio dBr 표기, 시스템 기동시간, 보관 온습도, LoadMatch류 케이블 보상 기능, D80 특유의 Fallback/Override/AutoStandby 신호경로 관리, Load Monitoring/System check, 선택형 출력 모드, 메인즈 전류 제한기)에 대응하는 스펙이 확인되지 않는다. LA12X는 이런 기능/스펙 자체가 아키텍처상 없는 것으로 판단되나(예: LA12X는 출력 모드가 고정 구조이며 D80처럼 채널쌍 단위로 Dual Channel/Mix TOP-SUB/2-Way Active를 사용자가 선택하는 구조가 아님), 명시적 문서 근거로 "비적용"을 완전히 확정하기보다 보수적으로 null 처리하고 각 항목의 성격은 D80_v1.0.md 원 각주를 참조하도록 한다.

## d90_specific (d&b D90 고유 속성, Phase 3-1 신규 섹션)

| Key | Value | Unit |
|---|---|---|
| Milan_Device_Type [신규] | null | - |
| Milan_Input_Channel_Streams [신규] | null | - |
| Milan_Redundancy [신규] | null | - |
| Milan_Routable_Inputs [신규] | null | ch |
| Network_IP_Default [신규] | null | - |
| Time_To_Tone [신규] | null | sec |
| Energy_Saving_Detail [신규] | null | - |
| AmpPresets_Detail [신규] | null | - |
| Output_Noise_Dynamic_Range_Detail [신규] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: 해당 없음(D90_v1.0.md 신규 섹션의 양방향 동기화 반영).

**[신규] 섹션 전체**: D90(d&b audiotechnik) 파싱 중 발견된 9개 신규 속성. LA12X의 기존 소스(OM v10.1, SPS 2.5, AE) 어디에도 이들 항목(Milan 프로토콜 상세 동작, Time to tone 다단계 시나리오, EcoMode를 포함한 확장된 에너지 절약 기능, AmpPresets 3종 슬롯 체계, 절대 노이즈 전압 기반 다이나믹레인지 상세)에 대응하는 스펙이 확인되지 않는다. 각 항목의 성격은 D90_v1.0.md 원 각주를 참조.

## Null Report

이번 소스 집합에서 정의되지 않아 null 처리된 항목: Rated_Power_Per_Ch_16_Ohms, Peak_Power_Per_Ch_4_Ohms, Peak_Power_Per_Ch_8_Ohms, Peak_Power_Per_Ch_16_Ohms, Per_Channel_DSP_Tools, Amplifier_Power_Management, SC32_Channel_Mapping, Speaker_Output_Accessories, GPIO_Count, GPIO_Type, DSP_Backup_Power_Input, Max_Operating_Altitude, PSU_Mains_Rated_Power, Terminal_Block_Pinout (Phase 3-1(LA7.16), 총 14건), CMRR_Analog_Input, Digital_Input_Impedance, SN_Ratio_Analog_Input, SN_Ratio_Digital_Input, System_Start_Up_Time, Storage_Temp_Range, Storage_Humidity, LoadMatch_Max_Cable_Length, Signal_Path_Management, Load_Monitoring_System_Check, Output_Mode_Selectable, Mains_Current_Limiter_Range (Phase 3-2(D80), 총 12건), Milan_Device_Type, Milan_Input_Channel_Streams, Milan_Redundancy, Milan_Routable_Inputs, Network_IP_Default, Time_To_Tone, Energy_Saving_Detail, AmpPresets_Detail, Output_Noise_Dynamic_Range_Detail (Phase 3-1(D90), 총 9건), Bridging_Support, Rated/Peak_Power_Per_Ch_BTL_8/16_Ohms(4), Rated/Peak_Power_Per_Ch_PBTL_4/8/16_Ohms(6), AES67_Support, Service_Port_Type, Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method (Phase 4(Upload 4개 제품), 총 15건). 전체 50건.

## 버전 변경 이력

v1.0 to v2.0: 개별 셀 각주를 섹션 단위 "주석 및 출처"로 통합, 표에서 측정 조건/출처 컬럼 제거, 예외 충돌 항목만 각주 유지, L-Acoustics 브랜드 규칙에 따라 OM 위치 최우선 표기, 전체 문서에서 이모지 및 특수 아이콘 제거.

v2.0 to v2.1: 저항값 표기를 유럽식(2R7 등)이 아닌 표준 소수점(2.7)으로 정제하는 규칙을 지침에 추가(본 데이터셋에는 해당 표기가 없어 실질 변경 없음). 무결성 원칙에 "원본에 없는 수식어·마케팅 문구·괄호 설명 임의 첨가 금지" 조항 강화.

v2.1 to v2.2: 저항 조건이 포함된 Key 명명 표준화 — `Rated_Power_Per_Ch_2R7` -> `Rated_Power_Per_Ch_2.7_Ohms`, `Rated_Power_Per_Ch_4R` -> `Rated_Power_Per_Ch_4_Ohms`, `Rated_Power_Per_Ch_8R` -> `Rated_Power_Per_Ch_8_Ohms`로 Key 명명 전면 수정. 이후 모든 Phase에서 저항 조건이 포함된 Key는 예외 없이 이 표준을 따른다.

v2.2 to v2.3: (Phase 3-1 양방향 동기화) LA7.16 파싱 중 발견된 신규 Key(GPIO_Count, GPIO_Type, DSP_Backup_Power_Input, Max_Operating_Altitude 등)를 각 해당 섹션에 `null` 값으로 추가. 기존 값과 각주는 일절 변경하지 않았다(무결성 유지).

v2.3 to v2.4: (수정) 저항 표기 표준화 규칙이 Value에만 적용되고 Key에는 미적용되었던 오류를 정정.

v2.4 to v2.5: (Phase 3-1 양방향 동기화) LA7.16 v1.3에서 12-point terminal block 상세 핀맵이 추가되며 신설된 `Terminal_Block_Pinout` Key를 connectivity 섹션에 `null`로 추가. LA12X는 통합 단자대 구조를 사용하지 않아 해당 없음(비적용) 처리. 기존 값과 각주는 일절 변경하지 않았다.

v2.5 to v2.6: (Phase 3-2 양방향 동기화) d&b D80 파싱 중 발견된 신규 섹션 `d80_specific`(12개 Key)을 전량 `null`로 신설 추가. 기존 9개 섹션의 Key/Value/각주는 일절 변경하지 않았다.

v2.6 to v2.7: (Phase 3-1 양방향 동기화) d&b D90 파싱 중 발견된 신규 섹션 `d90_specific`(9개 Key)을 전량 `null`로 신설 추가. 기존 값/각주는 일절 변경하지 않았다.

v2.7 to v2.8: (사용자 검토 반영, D80 라운드에서 발견된 이슈의 전 제품 확장 적용) D80에서 DSP_Sampling_Rate/Latency_Standard 값의 성립 조건 근거 부족이 지적되어, LA12X도 재검토했다. OM p.15 "Signal processing" 절에서 "Each AES/EBU input port is equipped with an SRC... provides constant propagation delay regardless of the input sampling frequency"라는 상시 내장 SRC 서술을 확인했고, OM p.86 Latency 스펙 표에는 표준/저지연 모드 모두 "independent from input Fs" 확정 문구가 직접 명시되어 있음을 재확인했다. 이에 따라 dsp 섹션 DSP_Sampling_Rate에 각주 [12], latency 섹션 Latency_Standard/Low_Mode에 각주 [13]을 신설하여, LA12X는 SRC가 상시 하드웨어로 내장되어 있어 D80(SRC 조건부 활성화 구조)과 달리 이 값들이 입력 조건과 무관하게 항상 성립하는 무조건적 고정값임을 OM 원문이 직접 확정하고 있다는 점, 그리고 D80/D90 대비 근거 수준이 가장 높다는 점을 양방향 동기화 관점에서 명기했다. Value 자체(96, 3.84, 0.84)는 변경하지 않고 근거 문구만 병기했다.

v2.8 to v2.9: (Phase 4 양방향 동기화) Upload 폴더 4개 신규 제품(LA1.16i, LA2Xi, LA4X, LA7.16i) 파싱 중 발견된 신규 15개 Key(amplification 10개: Bridging_Support + BTL 전력 4개 + PBTL 전력 6개, input_avb 1개: AES67_Support, connectivity 3개: Service_Port_Type, Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method)를 각 해당 섹션에 `null`로 신설 추가. LA12X 기존 소스에는 브릿지 모드/AES67/USB 서비스 포트 관련 서술이 없어 "확정된 비존재"가 아닌 "미확인(null)"으로 보수적 처리(원본 문서 재조회 없이 기존 파싱 결과 텍스트 기반 사용자 승인 진행). 기존 9개 섹션 및 d80_specific/d90_specific의 Key/Value/각주는 일절 변경하지 않았다.

**파일 무결성 참고**: 본 버전 변경 이력의 v1.0~v2.7 항목은 세션 중 발생한 파일 저장 동기화 지연으로 인해 이전 버전(v2.6 이하)의 파일 말미가 반복적으로 문장 중간에서 잘려 저장되는 문제가 있었다. 이번 v2.8 작성 시 위 이력을 가능한 범위에서 재구성하여 복원했으며, 표 데이터(Key/Value/Unit)와 섹션 각주 등 스펙 데이터 자체는 영향받지 않았다.
