# 5DM - Master Spec Schema

Schema_Version: 1.1 (Phase 3-1, 10D 파싱 중 신설된 Web_Remote_Interface Key를 양방향 동기화로 null 반영 — 그 외 v1.0 대비 변경 없음)
최종 작업 일시: 2026-07-16 (목요일)
Manufacturer: d&b audiotechnik
Product_Category: Amplifier (4-channel Class D installation amplifier with integrated DSP, Milan-native)
Form_Factor: 9.5 inch half-rack (1U), left/right 19" mountable or side-by-side pair

## 출처 등록부 (Source Registry)

| Source_ID | Document | Version / Date |
|---|---|---|
| OM | Manual (EN, "- preliminary -" 표기) | 1.1 en, 01/2026, D2767.EN.01 |

**스켈레톤 재사용 근거 (SKILL v1.11 "신규 제품 스켈레톤 재사용 규칙")**: 본 파일은 5D_v1.0.md의 섹션 구조와 Value를 뼈대로 복제한 뒤 서지컬 교체하여 작성되었다 — 5DM은 5D와 물리적 플랫폼이 사실상 동일하다(동일 출력 전력 600W CF12dB/37.5W long term, 동일 THD/Crosstalk, 동일 물리 치수/무게, 동일 팬/GPI/FAULT 하드웨어, 동일 아날로그 입력 스펙, 동일 8밴드 EQ/딜레이 범위, "Bridge mode is not applicable" 동일 확정 문구). 유일한 근본적 차이는 네트워크 오디오 프로토콜이다 — 5D는 Dante, 5DM은 Milan.

**중요 — 소스 제약 사항 (5D보다 더 제한적)**: 이번 소스는 단일 문서, "5DM Manual"(OM, 23p) 하나뿐이며 별도 데이터시트(SPS)도 제공되지 않았다. 또한 이 매뉴얼 자체가 표지부터 "- preliminary -"(예비/미확정) 표기가 반복적으로 붙어 있고, 문서 버전 이력에도 "Version 1.1: Preliminary edition"이라고 명시되어 있다 — 즉 5DM은 아직 정식 출시 전 단계의 제품으로 판단된다. 결정적으로, 스펙 표 내 일부 수치가 제조사 자신에 의해 "-tbd-"(to be determined, 미정)로 명시되어 있다(Milan 입력 레이턴시, Milan 입력 노이즈/다이나믹레인지 4개 조건) — 이는 일반적인 "소스에 없어 미확인(null)"과는 다른, "제조사가 아직 확정하지 않은 값"이라는 더 강한 의미이므로 해당 Key의 각주에 "-tbd-(제조사 자체 표기)"임을 명시했다. 또한 5D의 A&E("Architectural specifications", "shall be" 서술) 절에서만 확인 가능했던 정보(ADC 비트 심도, Load monitoring/System check, Signal_Path_Management의 Fallback/Override/AutoStandby/AutoWakeup)는 5DM 매뉴얼에 A&E 절 자체가 없어 재확인이 불가능하다 — 5D와 동일한 하드웨어일 가능성이 높으나, 5DM 자신의 원본에 없는 서술을 다른 제품(5D) 파싱 결과에 근거해 옮겨오지 않는다는 원칙(SKILL v1.11 "판단 근거의 원본성 요건")에 따라 이 Key들은 5DM에서 null로 유지한다.

---

## amplification (증폭부)

| Key | Value | Unit |
|---|---|---|
| Channel_Count_In | 4 | ch |
| Channel_Count_Out | 4 | ch |
| Amplification_Class | Class D | - |
| Rated_Power_Per_Ch_2.7_Ohms [양방향 동기화] | null | W |
| Rated_Power_Per_Ch_4_Ohms [1] | 37.5 (long term) / 600 (CF 12 dB) | W |
| Rated_Power_Per_Ch_8_Ohms [1] | 37.5 (long term, 4 Ω 조건에서만 확인) / 600 (CF 12 dB) | W |
| Rated_Power_Per_Ch_16_Ohms [양방향 동기화] | null | W |
| Peak_Power_Per_Ch_4_Ohms [양방향 동기화] | null | W |
| Peak_Power_Per_Ch_8_Ohms [양방향 동기화] | null | W |
| Peak_Power_Per_Ch_16_Ohms [양방향 동기화] | null | W |
| Total_Power_Capability [2] | null | W |
| Max_Output_Voltage_Peak | 120 | V |
| Max_Output_Current_Peak | 20 | A |
| Amplification_Gain | 31 | dB |
| Output_Delay_Range [3] | 1.1 - 300 | ms |
| Bridging_Support [4] | No (not applicable — explicit statement in OM) | - |
| Rated_Power_Per_Ch_BTL | null | W |
| Peak_Power_Per_Ch_BTL | null | W |
| Rated_Power_Per_Ch_PBTL | null | W |
| Peak_Power_Per_Ch_PBTL | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "3 Technical specifications"

**측정 조건**: 전 채널 구동. Amplification_Gain은 "Linear mode @ 0 dB" 조건. 5D와 완전히 동일한 값(같은 플랫폼 공유).

**[1] Rated_Power_Per_Ch 표 구조 (5D와 완전히 동일)**: 5DM의 OM은 5D와 동일하게 "Output power rating EIA-426B noise CF 12 dB: 4 x 600 W/8, 4 x 600 W/4"와 "Sinus 1 kHz, long term, +40°C: 4 x 37.5 W/4"를 명시한다. 8 Ω 조건의 long term 수치는 소스에 별도로 명시되지 않아, 5D와 동일한 패턴으로 4 Ω 조건에서만 확인된 값(37.5W)을 8 Ω 행에도 병기했다. OM 3.1절의 CF 9dB/6dB 상세값(참고용, 표 미채택)도 5D와 동일: CF 9dB(8Ω=350W,4Ω=350W), CF 6dB(8Ω=175W,4Ω=175W).

**[2] Total_Power_Capability**: 5DM의 OM 어디에도 전 채널 동시 구동 시 총 출력 용량을 나타내는 단일 수치가 명시되어 있지 않다. null 처리(임의 계산 금지 원칙).

**[3] Output_Delay_Range**: OM "Delay 1.1 - 300 ms" — 5D와 완전히 동일한 범위. 하한이 5DM 자신의 Latency_Standard(analog, 1.1ms)와 일치한다.

**[4] Bridging_Support**: OM Chapter 5.2.4 "OUTPUTS"에 5D와 동일한 명시적 확정 문구 "Bridge mode is not applicable."이 있다 — 확정적 비존재(No)로 명시한다. BTL/PBTL 관련 4개 전력 Key는 null 유지.

---

## power_supply (전원부)

| Key | Value | Unit |
|---|---|---|
| PSU_Type | Wide range switched mode power supply with active Power Factor Correction (PFC) | - |
| Mains_Voltage_Range [1] | 100 - 240 | V AC |
| Mains_Frequency_Range | 50 - 60 | Hz |
| Nominal_Current_100_120V [2] | 5.7 | A |
| Nominal_Current_200_240V [2] | 2.4 | A |
| Power_Factor | null | - |
| Power_Consumption_Idle [3] | 49 | W |
| Power_Consumption_Standby [3] | 4 | W |
| Mains_Connector | IEC-60320 C14 | - |
| PSU_Mains_Rated_Power [4] | 450 | W |
| Mains_Current_Limiter_Range | null | % of rated current |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "3 Technical specifications", p.15 "5.2.1 Mains connection"

**측정 조건**: Power_Consumption 값은 OM Chapter 3.1의 "230 VAC/50 Hz" 상태별 상세 전류표(Standby/AutoWakeup/Idling)를 채택 — 5D와 완전히 동일한 표(같은 산술 검증 결과: Standby 0.1A x 0.17 x 230V ≈ 4W 일치, Idling 0.4A x 0.6 x 230V ≈ 49W 근사).

**[1] Mains_Voltage_Range**: 5DM도 5D와 동일하게 "wide range"(100-240V 단일 연속 범위) 단일 대역으로 명시된다.

**[2] Nominal_Current**: OM "Rated mains current 5.7A - 2.4A" — 5D와 완전히 동일한 값. Nominal_Current_100_120V=5.7A, Nominal_Current_200_240V=2.4A 매핑도 5D와 동일한 방식.

**Power_Factor**: 5DM 소스 어디에도 명시적 역률 수치가 없어 null 처리했다.

**[4] PSU_Mains_Rated_Power**: OM Chapter 5.2.1 "Mains connection" 본문에 5D와 동일한 "Mains voltage range: 100 to 240 VAC, ~50/60 Hz, 450 W" 단일 수치가 확인된다.

**Mains_Current_Limiter_Range**: 5DM 소스에는 Mains Current Limiter 챕터 자체가 없다(5D와 동일한 소스 제약).

---

## audio_performance (음향 스펙)

| Key | Value | Unit |
|---|---|---|
| Frequency_Response | 35 - 20000 | Hz |
| THD_N_8ohm [1] | less than -60 (0.1%) | dB |
| THD_N_4ohm [1] | less than -60 (0.1%) | dB |
| Output_Dynamic_Range | null | dB |
| Noise_Level | null | dBV |
| Channel_Separation [1] | less than -50 | dBr |
| Damping_Factor | null | - |
| SN_Ratio_Analog_Input | null | dBr |
| SN_Ratio_Digital_Input | null | dBr |
| Output_Noise_Dynamic_Range_Detail [2] | Analog input, unweighted: 330 uV RMS / 108 dB; Analog input, A-weighted: 240 uV RMS / 111 dB; Milan input, unweighted: -tbd-; Milan input, A-weighted: -tbd- | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "3 Technical specifications"

**측정 조건**: Frequency_Response는 -1 dB 허용오차, Linear mode 기준. THD_N/Crosstalk은 unweighted, 20-20 kHz 대역, "4 x 75 W into 8/4 Ω" 조건(long term 정격 기준) — 5D와 완전히 동일.

**[1] THD_N/Channel_Separation 값**: OM "THD+N (unweighted, 20-20 kHz) < -60 dB/0.1%"(8 Ω, 4 Ω 동일 수치), "Crosstalk (20-20 kHz) < -50 dBr" — 5D와 완전히 동일한 수치.

**Output_Dynamic_Range, Noise_Level, Damping_Factor, SN_Ratio_Analog/Digital_Input**: 5DM 소스에는 이 Key들에 정확히 대응하는 단순 dBr/dB 상대값 형식의 스펙이 확인되지 않는다 — 대신 아래 Output_Noise_Dynamic_Range_Detail Key에 절대 노이즈 전압(uV RMS) 기준 상세 데이터로 기록했다.

**[2][제조사 자체 "-tbd-" 표기] Output_Noise_Dynamic_Range_Detail**: Analog input 조건(330/240 uVRMS, 108/111 dB)은 5D와 완전히 동일한 값으로 확인되며, reference 전압(120 Vpk)도 5DM 자신의 Max_Output_Voltage_Peak(120V)와 정확히 일치한다(5D와 동일 패턴, D25에서 발견된 reference 불일치 사례와는 다름). 그러나 Milan input 조건(unweighted/A-weighted 2가지)은 OM 스펙 표에 각각 "-tbd- uVRMS/-tbd- dB"로 명시되어 있다 — 이는 소스에 정보가 없어 생기는 일반적인 미확인(null)과 다르다: 제조사가 스펙 표 자체에 "to be determined"라고 명시적으로 표기한 것으로, 이 preliminary(예비) 문서 작성 시점에 아직 확정되지 않은 값임을 뜻한다. 원문 그대로 "-tbd-"를 보존하여 이 특수한 상태를 기록했다(임의로 null이나 다른 값으로 대체하지 않음).

---

## dsp (신호 처리)

| Key | Value | Unit |
|---|---|---|
| DSP_Processor | null | - |
| DSP_Sampling_Rate [1] | 48 (internal, fixed) | kHz |
| Routing_Matrix | null | - |
| EQ_Filters_Per_Output [2] | 1 x 8-band PEQ/Notch/HiShlv/LoShlv/Asym | - |
| Per_Channel_DSP_Tools | null | - |
| Amplifier_Power_Management | null | - |
| Speaker_Protection | null | - |
| LoadMatch_Max_Cable_Length | null | m |
| Load_Monitoring_System_Check [3] | null | - |
| Preset_Memory_User | null | slots |
| Preset_Memory_Factory | null | slots |
| System_Start_Up_Time | null | sec |
| Time_To_Tone [4] | Off: less than 6 sec | sec |
| Energy_Saving_Detail | null | - |
| AmpPresets_Detail [5] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "3 Technical specifications"

**측정 조건**: 없음(사양값).

**[1] DSP_Sampling_Rate**: OM "Conversion 48 kHz" — 5D와 완전히 동일한 고정값.

**[2] EQ_Filters_Per_Output**: OM "user definable 8-band equalizer"(단수, 1개) — 5D와 완전히 동일.

**[3] Load_Monitoring_System_Check**: 5D는 A&E("Architectural specifications", "shall be" 서술) 절에서 이 기능을 확인할 수 있었으나, 5DM 매뉴얼에는 A&E 절 자체가 없다 — 5D와 동일한 하드웨어일 가능성이 높으나 5DM 자신의 원본에서 재확인되지 않아 null로 유지한다(SKILL v1.11 "판단 근거의 원본성 요건").

**[4] Time_To_Tone**: OM "Time to tone (Off) < 6 sec." — 5D와 완전히 동일.

**[5] AmpPresets_Detail**: 5DM 매뉴얼의 RESET(시스템 리셋) 절에 "All device settings will be set to factory defaults except for the network and fixed device settings such as AmpPresets."라는 문구가 있어, "AmpPresets"라는 기능 자체의 존재는 5D보다 오히려 더 직접적으로 확인된다 — 다만 슬롯 개수/구조 등 상세 스펙은 이 문구만으로 확인되지 않아 null로 유지한다.

**DSP_Processor, Routing_Matrix, Per_Channel_DSP_Tools, Amplifier_Power_Management, Speaker_Protection, LoadMatch_Max_Cable_Length, Preset_Memory_User/Factory, System_Start_Up_Time, Energy_Saving_Detail**: 5DM 소스에는 이 Key들에 대응하는 상세 서술이 없다 — 완전판 Reference Manual 미제공으로 인한 미확인(null).

---

## latency (지연 시간)

| Key | Value | Unit |
|---|---|---|
| Latency_Standard [1] | 1.1 | ms |
| Latency_Low_Mode | null | ms |
| AVB_Max_Network_Latency [2] | -tbd- | ms |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "3 Technical specifications"

**측정 조건**: OM "Latency analog/Milan input (48 kHz) 1.1/-tbd- ms" — 아날로그 입력은 1.1 ms로 5D(analog)와 동일하나, Milan 입력 지연은 제조사가 아직 "-tbd-"(미정)로 표기했다. Latency_Low_Mode는 별도 개념이 확인되지 않아 비적용(null).

**[1] Latency_Standard**: 아날로그 입력 기준 1.1 ms를 채택했다 — 5D와 완전히 동일한 값.

**[2][제조사 자체 "-tbd-" 표기] AVB_Max_Network_Latency (Milan 입력 지연)**: 통상 이 Key는 5DM처럼 Milan을 사용하지 않는 제품에서 비적용(null)으로 처리해 왔으나, 5DM은 실제로 Milan을 사용함에도 그 네트워크 지연 값 자체가 소스에 "-tbd-"로 명시되어 있다 — 일반적인 미확인(null)과 구분하기 위해 원문 "-tbd-"를 그대로 Value로 채택했다(preliminary 문서 특유의 상태). 정식 출시판 매뉴얼 발간 시 재확인 필요.

---

## input_analog (아날로그 입력)

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Channels | 4 | ch |
| Input_Impedance | 15 | kOhm |
| Max_Input_Level [1] | 18 / 12 | dBu |
| CMRR_Analog_Input [1] | greater than 54 / 54 / 50 (@ 100 Hz / 1 kHz / 10 kHz) | dB |
| ADC_Architecture [2] | null | - |
| Analog_Link_Type [3] | parallel to input (cable tap), 6-pin Euroblock male (3-pin used) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "3 Technical specifications", p.16 "5.2.2 Analog audio inputs/link connectors"

**측정 조건**: Input_Impedance는 "electronically balanced" 기준. CMRR은 "@ 100 Hz/1 kHz/10 kHz" 3개 주파수 조건. 5D와 완전히 동일한 값.

**[1] Max_Input_Level/CMRR 값**: OM "Maximum input level (balanced/unbalanced) +18/+12 dBu, +27.3 dBu @ 0 dBFS", CMRR ">54/>54/>50 dB @ 100 Hz/1 kHz/10 kHz" — 5D와 완전히 동일.

**[2] ADC_Architecture**: 5D는 A&E("Architectural specifications") 절에서 "24 Bit ADC/DAC conversion"을 확인할 수 있었으나, 5DM 매뉴얼에는 A&E 절이 없어 재확인이 불가능하다 — 5D와 동일한 하드웨어일 가능성이 높으나 5DM 자신의 원본에서 확인되지 않아 null로 유지한다.

**[3] Analog_Link_Type**: OM Chapter 5.2.2 — 5D와 완전히 동일한 구조(6핀 Euroblock 겸용 입력/링크 커넥터).

---

## input_digital (디지털 입력)

| Key | Value | Unit |
|---|---|---|
| Digital_Input_Channels | null | ch |
| Digital_Standard [1] | null (AES3 미사용, Dante 네트워크 오디오로 대체) | - |
| Digital_Input_Impedance | null | Ohm |
| Supported_Sampling_Rates | null | kHz |
| Supported_Word_Length | null | bit |
| SRC_Output_Format | null | - |
| SRC_Dynamic_Range | null | dB |
| SRC_THD_N | null | dBFS |
| Digital_Input_Gain_Range | null | dB |
| Digital_Link_Type | null | - |
| Max_AES_Cable_Length | null | m |

### 주석 및 출처 (Notes & Sources)

**출처**: 해당 없음.

**[1] input_digital 섹션 전체 비적용**: 5DM은 5D와 마찬가지로 AES/EBU(AES3) 디지털 입력 커넥터가 없다 — 유일한 디지털 오디오 입력 경로는 Milan 네트워크 오디오이며, 이는 아래 input_avb 섹션에서 다룬다. 이 섹션(input_digital)의 모든 Key는 비적용(null)이다.

---

## input_avb (AVB / Milan 입력)

| Key | Value | Unit |
|---|---|---|
| AVB_Certification | null | - |
| AVB_Device_Type [1] | Endstation | - |
| AVB_Channels [1] | 16 (2 streams x 8 ch) | ch |
| AVB_Stream_Count [1] | 2 streams with up to 8 channels @ 48/96 kHz each | streams |
| AVB_Formats | null | - |
| AVB_Standards | null | - |
| AVB_Bridge_Forwarded_Streams | null | streams |
| Redundancy_Type [2] | No (explicit — "Redundancy: no") | - |
| Fallback_Modes [3] | null | - |
| AES67_Support | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "3 Technical specifications", p.16 "5.2.3 ETH1/ETH2 - Milan" (최우선)

**측정 조건**: 이 섹션은 5D(input_dante 섹션 참조)와 달리 5DM에서 실값이 채워진다 — 5DM은 Milan 네트워크 오디오를 실사용하는 제품이다.

**[1] AVB_Device_Type/AVB_Channels/AVB_Stream_Count**: OM "Device type: Endstation", "Input channel streams: 2 streams with up to 8 channels @ 48/96 kHz", "Routable Milan inputs: M1-M4". D90/D25/D40(1 stream, 8ch, M1-M8 전부 라우팅 가능)과 달리 5DM은 2개 스트림(총 16채널 수신 가능)을 받되 실제로 앰프에 라우팅 가능한 것은 4채널(M1-M4)뿐이다 — OM 본문: "The device is Milan enabled and accepts two Milan streams each providing eight channels. Four of these 16 (2 x 8) channels can be routed to the signal processing of the 5DM." AVB_Channels에는 총 수신 가능 채널(16)을 채택하고, 실제 라우팅 가능 채널 수(4, 앰프 채널 수와 일치)는 이 각주에 병기한다.

**[2] Redundancy_Type**: OM 스펙 표에 "Redundancy: no"로 명시적으로 확인된다 — D90/D25/D40의 "Yes (always active)"와 정반대다. 5DM은 Milan 이중화를 지원하지 않는 제품으로 판단(preliminary 문서 시점 기준, 정식 출시판에서 변경될 가능성 있음).

**[3] Fallback_Modes**: 5DM 매뉴얼에는 A&E 절이 없어 Fallback/Override 관련 서술이 확인되지 않는다(5D와 동일한 소스 제약) — null 유지.

---

## input_dante (Dante 네트워크 오디오 입력)

| Key | Value | Unit |
|---|---|---|
| Dante_RX_Channels [1] | null | ch |
| Dante_Sampling_Rates [1] | null | kHz |
| Dante_SRC [1] | null | - |
| Dante_Redundancy [1] | null | - |
| Dante_Network_Flows [1] | null | flows |
| Dante_Latency [1] | null | ms |
| Dante_IP_Architecture [1] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: 해당 없음.

**[1] 섹션 전체 비적용**: 5DM은 Dante가 아닌 Milan 네트워크 오디오를 사용한다(OM 전량 검토 결과 "Dante"라는 용어 자체가 5DM 소스에 0건 검출) — 이 섹션 전체가 비적용이다. 5DM의 실제 네트워크 오디오 입력 스펙은 위 input_avb 섹션에서 실값으로 기록되어 있다.

---

## network (네트워크 설정)

| Key | Value | Unit |
|---|---|---|
| Network_IP_Default [1] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.16 "5.2.3 ETH1/ETH2 - Milan"

**[1] Network_IP_Default**: 5DM 소스에는 고정된 공장 기본 IP가 명시되지 않는다 — 대신 "SNMP IP addressing (Auto or Manual)"로 서술되며, µC(원격제어)와 Milan 오디오가 ETH1/ETH2에 "Single cable mode"(한 케이블로 통합) 또는 "Split mode"(포트별 분리)로 R1 소프트웨어를 통해 선택 구성되는 구조다(connectivity 섹션 각주 참조) — 5D의 이중 IP/MAC 구조와는 다른 방식이나, 마찬가지로 단일 "기본값" 개념이 명확하지 않아 null로 유지한다.

---

## connectivity (커넥터)

| Key | Value | Unit |
|---|---|---|
| Input_Connectors [1] | 4x 6-pin Euroblock male (A1-A4 pairs, analog, 3-pin used per channel, doubles as link/cable tap) | - |
| Terminal_Block_Pinout [2] | ( ) GND, neg., pos. (3-pin used of 6-pin Euroblock, analog input) | - |
| XLR_Pin_Polarity [3] | null (XLR 커넥터 미사용, Euroblock 전용) | - |
| Speaker_Connectors [4] | 2x 4-pin Euroblock female (OUTPUTS A/B, C/D pairs) | - |
| Output_Mode_Selectable | null | - |
| SpeakON_Left_Pinout [3] | null (speakON 커넥터 미사용) | - |
| SpeakON_Right_Pinout [3] | null (speakON 커넥터 미사용) | - |
| CACOM_Pinout [양방향 동기화] | null | - |
| SC32_Channel_Mapping [양방향 동기화] | null | - |
| Speaker_Output_Accessories | null | - |
| Network_Connectors [5] | 2x RJ45 (2 individual Ethernet ports, 1 Gbit/s each, no built-in switch; Single cable mode: OCA+Milan on ETH1, ETH2 unused; Split mode: OCA on ETH1, Milan on ETH2; mode selectable via R1) | - |
| Service_Port_Type | null | - |
| Speaker_Terminal_Block_SE_BTL_Wiring | null (Bridge mode not applicable, amplification 섹션 각주 [4] 참조) | - |
| PBTL_Activation_Method | null | - |
| Fault_Contact_Type [6] | NO (Normally Open) / C (Common) / NC (Normally Closed) relay contact, 1x 3-pin Euroblock 3.5 mm male; fixed software object assignment; switches to fault status during firmware update | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8, p.16-18 "5.2.2-5.2.6"

**측정 조건**: 없음(커넥터 규격 및 결선표).

**[1] Input_Connectors, [2] Terminal_Block_Pinout, [3] XLR_Pin_Polarity/SpeakON_Left/Right_Pinout, [4] Speaker_Connectors**: 5D와 완전히 동일한 구조 — 6핀 Euroblock 겸용 입력/링크 커넥터(3핀 실사용), 2x 4핀 Euroblock 스피커 출력(A/B, C/D 채널쌍), XLR/speakON 미사용.

**Output_Mode_Selectable**: 5DM 소스에는 선택형 출력 모드 서술이 확인되지 않는다(5D와 동일한 소스 제약).

**[5] Network_Connectors — 5D와 다른 네트워크 포트 구조**: OM Chapter 5.2.3 "Two individual Ethernet ports (1 Gbit/s) are provided... In Single cable mode, it allows star-wiring topology using one cable for both, Milan digital audio and d&b Remote network (OCA/AES70) ETH1. In Split mode, it allows star-wiring topology using d&b Remote network (OCA/AES70) on ETH1 and Milan digital audio on ETH2. The Ethernet port mode is adjustable using the d&b R1 Remote control software." — 5D의 "내장 2포트 스위치 + daisy-chain/star 선택" 구조와 달리, 5DM은 스위치가 없는 개별 포트 2개이며 Single cable/Split 모드를 R1으로 선택하는 방식이다. Milan 라인(D90/D25/D40)의 "ETH1/PRI(원격+Milan Primary)/ETH2/SEC(Milan 이중화 전용)" 고정 구조와도 다르다 — 5DM은 이중화가 없으므로(Redundancy_Type=No) ETH2가 이중화 용도가 아니라 단순 모드 선택에 따른 대체 경로다.

**[6] Fault_Contact_Type**: 5DM 매뉴얼 Chapter 5.2.6 "FAULT" — 5D와 완전히 동일한 문구/사양.

---

## control_monitoring (제어 및 모니터링)

| Key | Value | Unit |
|---|---|---|
| Remote_Software | d&b R1 Remote control software, d&b ArrayCalc (simulation) | - |
| Network_Topologies [1] | star (both Single cable mode and Split mode; no daisy-chain mentioned) | - |
| Third_Party_Control [양방향 동기화] | null | - |
| Front_Panel [2] | LED indicators only (POWER, Data, Mute A/B/C/D, ISP A/B/C/D, GR A/B/C/D, OVL/Error A/B/C/D); rear panel mains rocker switch; rear panel recessed RESET push-button | - |
| Settings_Protection | null | - |
| GPIO_Count [3] | 4 | ea |
| GPIO_Type [3] | Level (Hi/Lo active, non-latching) or edge (rising/falling, latching) triggering; VCA functionality (10 kOhm linear potentiometer input); onboard DC-Out 12 VDC/50 mA; 1x 6-pin Euroblock 3.5 mm male connector | - |
| DSP_Backup_Power_Input [양방향 동기화] | null | V DC |
| Signal_Path_Management [4] | null | - |
| Web_Remote_Interface | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8, p.16 "5.2.3", p.18 "5.2.5 GPI/DC"

**측정 조건**: GPI High-level 7-30 VDC, Low-level 0-5 VDC, Input impedance 100 kOhms. 5D와 완전히 동일.

**[1] Network_Topologies**: connectivity 섹션 각주 [5] 참조 — 5D와 달리 daisy-chain 언급이 없고 두 모드 모두 star topology만 명시된다.

**[2] Front_Panel**: 5D와 완전히 동일 — LED 표시등만 제공하며 설정은 d&b R1 Remote를 통해 이루어진다.

**[3] GPIO_Count/GPIO_Type**: OM Chapter 5.2.5 — 5D와 완전히 동일한 문구/사양(GPI 4개, level/edge triggering, VCA 기능).

**[4] Signal_Path_Management**: 5DM 매뉴얼에는 A&E 절이 없어 Fallback/Override/AutoStandby/AutoWakeup 관련 서술이 확인되지 않는다(5D와 동일한 소스 제약) — null 유지.

**[신규] Web_Remote_Interface (10D 파싱 중 신설, 양방향 동기화로 null 반영)**: 10D(d&b audiotechnik 차세대 설치용 라인) 파싱 중 발견된 신규 Key — 별도 소프트웨어(R1/ArrayCalc) 없이 표준 웹 브라우저로 앰프에 직접 접속하는 브라우저 기반 내장 웹 인터페이스 개념. 5DM의 기존 소스에는 이 개념에 대응하는 서술이 확인되지 않아 null(미확인)로 소급 반영한다.

---

## operating_conditions (동작 환경)

| Key | Value | Unit |
|---|---|---|
| Operating_Temp_Range [1] | -10 to 40 (continuous) / -10 to 50 (short-term) | degrees C |
| Storage_Temp_Range | -20 to 70 | degrees C |
| Storage_Humidity | less than 70 (non-condensing) | % rel. |
| Cooling [2] | Temperature-dependent fan, self-resetting overtemperature protection | - |
| Fan_Count [2] | 1 | ea |
| Fan_Noise_Min | null | dBA |
| Fan_Noise_Max | 42 | dBA |
| EMC_Class | residential Class B (EN 55032:2019) | - |
| Max_Operating_Altitude [양방향 동기화] | null | m |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.5 "1 Intended use", p.8 "3 Technical specifications", p.14 "5.1 Rack mounting and cooling"

**측정 조건**: 5D와 완전히 동일한 값.

**[1] Operating_Temp_Range**: 5D와 동일하게 continuous(-10~40)/short-term(-10~50) 조건을 병기했다.

**[2] Cooling/Fan_Count**: OM Chapter 5.1 "The amplifier is equipped with an internal fan"(단수) — 5D와 완전히 동일(팬 1개).

**Max_Operating_Altitude**: 5DM 소스 어디에도 최대 운용 고도가 명시되지 않아 null 처리했다(5D와 동일한 소스 제약).

---

## physical (물리적 스펙)

| Key | Value | Unit |
|---|---|---|
| Width [1] | 241 (9.5 inch half-rack) | mm |
| Height | 44.5 | mm |
| Depth [2] | 405 (435 with rack ears) | mm |
| Weight | 4.6 | kg |
| Protection_Rating | null | - |
| Finish | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "3 Technical specifications", "5DM enclosure dimensions"

**측정 조건**: "Dimensions and weight: 1 RU x 9.5" x 405 mm (16")"(Height x Width x Depth), rack ears 포함 시 Depth 435 mm(17.1"). Weight "4.6 kg/10 lb" — 5D와 완전히 동일한 물리 치수.

**[1] Width**: 5D와 동일한 9.5인치 하프랙 폼팩터.

**[2] Depth**: 5DM 매뉴얼에는 A&E 절이 없어 5D에서 발견된 "스펙 표 405mm vs A&E 435mm" 종류의 대조 확인은 불가능하다 — 스펙 표의 405mm(랙이어 미포함)/435mm(랙이어 포함) 두 값만 본문에서 확인되며 병기했다.

**Protection_Rating, Finish**: 5DM 소스 어디에도 명시되지 않아 null 처리했다.

---

## protection_summary (보호 회로)

| Key | Value |
|---|---|
| Protection_Mains_PSU [1] | overvoltage, inrush current limiter, internal fuse |
| Protection_Outputs | overcurrent, DC offset, HF voltage limiter, pop-noise suppression, self-resetting overtemperature protection |
| Protection_Transducer | null |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.8 "3 Technical specifications > Protection circuits"

**측정 조건**: 없음(보호 기능 목록). 5D와 완전히 동일한 목록.

**[1] Protection_Mains_PSU**: OM "Mains and power supply: Overvoltage, inrush current limiter, internal fuse." — 5D와 완전히 동일(undervoltage 항목 없음).

**Protection_Transducer**: 5DM 소스 어디에도 트랜스듀서 전용 보호 기술이 확인되지 않아 null 유지했다.

---

## Null Report

이번 소스 집합에서 정의되지 않아 null 처리된 항목 (총 75건):

**비적용(제품 아키텍처상 해당 없음, 총 36건)**: Rated_Power_Per_Ch_2.7_Ohms, Rated_Power_Per_Ch_16_Ohms, Peak_Power_Per_Ch_4_Ohms, Peak_Power_Per_Ch_8_Ohms, Peak_Power_Per_Ch_16_Ohms, Rated_Power_Per_Ch_BTL, Peak_Power_Per_Ch_BTL, Rated_Power_Per_Ch_PBTL, Peak_Power_Per_Ch_PBTL(브릿지 모드 확정적 비존재 연동, amplification 각주 [4] 참조), Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method, Output_Mode_Selectable, Latency_Low_Mode, Digital_Input_Channels, Digital_Standard, Digital_Input_Impedance, Supported_Sampling_Rates, Supported_Word_Length, SRC_Output_Format, SRC_Dynamic_Range, SRC_THD_N, Digital_Input_Gain_Range, Digital_Link_Type, Max_AES_Cable_Length(input_digital 섹션 전체, AES3 커넥터 없음), Dante_RX_Channels, Dante_Sampling_Rates, Dante_SRC, Dante_Redundancy, Dante_Network_Flows, Dante_Latency, Dante_IP_Architecture(input_dante 섹션 전체 — 5DM은 Dante가 아닌 Milan을 사용, 5D와 정반대 패턴), XLR_Pin_Polarity, SpeakON_Left_Pinout, SpeakON_Right_Pinout, CACOM_Pinout, SC32_Channel_Mapping(XLR/speakON 미사용, 전량 Euroblock).

**미확인(소스에 명시 없음 — 다수는 5DM 매뉴얼에 A&E 절이 없다는 소스 제약이며, 완전판 문서 확보 시 재검토 필요, 총 39건)**: Total_Power_Capability, Power_Factor, Mains_Current_Limiter_Range, Output_Dynamic_Range, Noise_Level, Damping_Factor, SN_Ratio_Analog_Input, SN_Ratio_Digital_Input, DSP_Processor, Routing_Matrix, Per_Channel_DSP_Tools, Amplifier_Power_Management, Speaker_Protection, LoadMatch_Max_Cable_Length, Load_Monitoring_System_Check, Preset_Memory_User, Preset_Memory_Factory, System_Start_Up_Time, Energy_Saving_Detail, AmpPresets_Detail, ADC_Architecture, AVB_Certification, AVB_Formats, AVB_Standards, AVB_Bridge_Forwarded_Streams, Fallback_Modes, AES67_Support(input_avb 섹션 일부 — Device_Type/Channels/Stream_Count/Redundancy_Type는 실값 있음), Network_IP_Default, Speaker_Output_Accessories, Service_Port_Type, Third_Party_Control, Settings_Protection, DSP_Backup_Power_Input, Signal_Path_Management, Fan_Noise_Min, Max_Operating_Altitude, Protection_Rating, Finish, Protection_Transducer.

**확정적 비존재(No)로 명시한 항목(Null Report에 미포함, 참고용)**: Bridging_Support — OM에 "Bridge mode is not applicable."라는 명시적 문구가 확인되어 null이 아닌 "No"로 값을 채웠다.

**제조사 자체 "-tbd-"(to be determined) 표기 항목(Null Report에 미포함, 별도 관리)**: Output_Noise_Dynamic_Range_Detail의 Milan input 조건 2개(unweighted/A-weighted), AVB_Max_Network_Latency(Milan 입력 지연) — 소스에 정보가 없는 일반적인 null과 달리, 제조사가 preliminary 문서 시점에 스펙 표 자체에 "-tbd-"라고 명시한 값이다. 정식 출시판 문서 확보 시 최우선 재확인 대상.

---

## 버전 변경 이력

v1.0: Phase 3-1, 5D의 Milan 버전 최초 파싱. OM(Manual 1.1, 23p — "- preliminary -" 표기, 별도 SPS/데이터시트 없음) 단일 소스. 5D_v1.0.md를 스켈레톤으로 복제(SKILL v1.11 "신규 제품 스켈레톤 재사용 규칙") — 5DM은 5D와 물리적 플랫폼이 사실상 동일(동일 출력 전력, THD/Crosstalk, 물리 치수/무게, GPI/FAULT 하드웨어, 아날로그 입력 스펙, 8밴드 EQ, "Bridge mode is not applicable")하며, 유일한 근본 차이는 네트워크 프로토콜이다(5D=Dante, 5DM=Milan). input_avb 섹션에 5DM의 실제 Milan 데이터를 채우고(AVB_Device_Type=Endstation, AVB_Channels=16(2 streams x 8ch), Redundancy_Type=No — D90/D25/D40의 "Yes, always"와 정반대), input_dante 섹션은 반대로 전량 null 처리(5D와 정반대 패턴). connectivity의 Network_Connectors도 5D의 "내장 스위치+daisy-chain 가능" 구조 대신 5DM 고유의 "개별 포트 2개, Single cable/Split mode 선택식" 구조로 별도 기록. 신규 스키마 확장 없음(5D가 이미 도입한 input_dante 섹션/Fault_Contact_Type Key를 그대로 사용). **preliminary 문서 특유의 데이터 품질 이슈**: 스펙 표에 제조사 자신이 "-tbd-"(미정)로 표기한 값 2건(Milan 입력 레이턴시, Milan 입력 노이즈/다이나믹레인지) 발견 — 일반 미확인(null)과 구분하여 원문 "-tbd-"를 그대로 보존했다. 또한 5DM 매뉴얼에는 5D의 A&E("Architectural specifications") 절에 해당하는 부분이 없어, 5D에서는 A&E로 확인되었던 ADC 비트심도/Load monitoring/Signal_Path_Management(Fallback/Override/AutoStandby/AutoWakeup) 등을 5DM 자신의 원본으로 재확인하지 못해 null로 유지했다(SKILL v1.11 "판단 근거의 원본성 요건" — 5D 파싱 결과를 근거로 5DM에 값을 옮기지 않음).
