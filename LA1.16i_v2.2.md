# LA1.16i - Master Spec Schema

Schema_Version: 2.2 (양방향 동기화 - 5D(d&b audiotechnik Dante 설치용 라인) 파싱 중 신설된 input_dante 섹션(7개 Key) 및 connectivity 섹션 Fault_Contact_Type Key + 10D(d&b audiotechnik 차세대 설치용 라인) 파싱 중 신설된 control_monitoring 섹션 Web_Remote_Interface Key를 null로 소급 반영, 구조 변경 없는 Minor 버전)
최종 작업 일시: 2026-07-16 (목요일)
Manufacturer: L-Acoustics
Product_Category: Amplified_Controller (16-channel install-specific Class D amplifier with integrated DSP)
Form_Factor: 19 inch rack, 1U

## 출처 등록부 (Source Registry)

| Source_ID | Document | Version / Date |
|---|---|---|
| OM | Owner's Manual (EN) | version 2.0, distribution Jan. 22, 2026 |
| AE | Architects and Engineers Spec (docx) | undated |

**소스 범위에 대한 참고**: 기존 제품(LA12X, LA7.16, D80, D90)은 OM/SPS/AE/웹 3계층 등 최대 6개 소스로 교차 검증되었으나, LA1.16i는 `Upload` 폴더에 OM PDF와 AE docx 2개 소스만 제공되어 이 2개만으로 파싱했다. SPS(스펙시트)나 웹 데이터가 추후 제공되면 교차 검증 및 각주가 보강되어야 한다. L-Acoustics 브랜드 규칙에 따라 출처 표기는 OM의 페이지/목차 위치를 최우선으로 기록한다.

본 파일은 LA7.16_v1.6.md의 Key 목록 및 마크다운 구조를 뼈대로 복제하여 작성되었다(SKILL v1.10 작업공간 관리 규칙에 따른 신규 제품 스켈레톤 재사용 방식). LA1.16i는 기존 LA7.16(구형, 2U, SC32 커넥터, 고출력 80-1000W대)과 완전히 다른 제품군 — L-Acoustics의 신형 "i" 설치전용(install-specific) 라인(1U, 터미널 블록 커넥터, 저출력 40-160W대, SE/BTL 브릿징 지원) — 이므로 Value 대부분이 다르며, 일부 Key는 신규 추가되었다(BTL 출력, AES67 겸용, USB 서비스 포트 등, 아래 각 섹션 각주 참조).

**구조 개편 안내(v2.0)**: d&b 제품군(D80/D90)에서 먼저 적용된 구조 개편을 사용자 요청에 따라 L-Acoustics 제품군에도 동일하게 적용한다. "d80_specific"/"d90_specific"처럼 타 브랜드 모델명을 딴 그랩백(grab-bag) 섹션 2개를 전부 폐지하고 그 안의 Key들을 주제(스펙 영역) 기준 기존 섹션으로 재분배했다. **d80_specific(12개 Key)**: CMRR_Analog_Input -> input_analog, Digital_Input_Impedance -> input_digital, SN_Ratio_Analog_Input/SN_Ratio_Digital_Input -> audio_performance, System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check -> dsp, Storage_Temp_Range/Storage_Humidity -> operating_conditions, Signal_Path_Management -> control_monitoring, Output_Mode_Selectable -> connectivity, Mains_Current_Limiter_Range -> power_supply. **d90_specific(9개 Key)**: Milan_Device_Type은 input_avb의 명명 규칙에 맞춰 AVB_Device_Type으로 개명 후 재배치, Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs는 input_avb의 기존 AVB_Channels/AVB_Stream_Count/Redundancy_Type과 중복되어 흡수(신규 Key 생성 없음), Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail -> dsp, Output_Noise_Dynamic_Range_Detail -> audio_performance, Network_IP_Default -> 신설된 **network** 섹션(D80_v2.0.md/D90_v2.0.md와 동일 섹션). 모든 이동 대상 Key는 LA1.16i 소스에 대응 스펙이 확인되지 않아 이동 후에도 null을 유지한다(Key/Value/Unit과 각주 내용 자체는 변경 없이 위치만 이동, Milan 흡수 부분만 예외). 아울러 amplification 섹션의 BTL/PBTL 전력 Key 10개(부하 임피던스별 세분화)를 4개(Rated/Peak_Power_Per_Ch_BTL, Rated/Peak_Power_Per_Ch_PBTL)로 통합했다 — **LA1.16i는 D80/D90/LA12X/LA7.16과 달리 BTL 실측값(230/160/300/150 W)이 존재하는 유일한 케이스이므로, 통합 시 이 실값을 삭제하지 않고 Value 셀에 "값 @ 임피던스" 형식으로 슬래시 병기하여 그대로 보존했다**(PBTL은 기존과 동일하게 null 유지). 섹션 계층 구조 자체가 바뀌는 변경이므로 SKILL 버저닝 규칙에 따라 Major 버전(v2.0)으로 상향했다.

---

## amplification (증폭부)

| Key | Value | Unit |
|---|---|---|
| Channel_Count_In | 16 | ch |
| Channel_Count_Out | 16 | ch |
| Amplification_Class | High-efficiency Class D | - |
| Rated_Power_Per_Ch_2.7_Ohms | null | W |
| Rated_Power_Per_Ch_4_Ohms | 120 | W |
| Rated_Power_Per_Ch_8_Ohms | 80 | W |
| Rated_Power_Per_Ch_16_Ohms | 40 | W |
| Peak_Power_Per_Ch_4_Ohms | 160 | W |
| Peak_Power_Per_Ch_8_Ohms | 80 | W |
| Peak_Power_Per_Ch_16_Ohms | 40 | W |
| Total_Power_Capability | null | W |
| Max_Output_Voltage_Peak [1] | 36 (SE) | V |
| Max_Output_Current_Peak [신규] | null | A |
| Amplification_Gain [1] | 26 (SE) | dB |
| Output_Delay_Range | 0 - 1000 | ms |
| Bridging_Support [신규][2] | Yes - SE/BTL selectable per output pair (odd/even bridging) | - |
| Rated_Power_Per_Ch_BTL [신규][2][2a] | 230 @ 8 Ohms / 160 @ 16 Ohms | W |
| Peak_Power_Per_Ch_BTL [신규][2][2a] | 300 @ 8 Ohms / 150 @ 16 Ohms | W |
| Rated_Power_Per_Ch_PBTL [23][2a] | null | W |
| Peak_Power_Per_Ch_PBTL [23][2a] | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.43 "Specifications > General > Output power" (최우선) / AE "Technical requirements > Amplification"

**측정 조건**: `Peak_Power_Per_Ch_*`는 12 dB Crest Factor, 2 ms, 1 kHz, all channels driven, sine burst 조건(OM/AE 일치). `Rated_Power_Per_Ch_*`는 CEA-2006/490A, 20 ms, ≤1% THD, 1 kHz, all channels driven, sine burst 조건(OM/AE 일치) — LA12X/LA7.16과 동일한 CEA 표준이므로 세 파일의 Rated_Power_Per_Ch_* 키는 동일 측정 기준으로 비교 가능하다. Rated_Power_Per_Ch_2.7_Ohms, Total_Power_Capability는 기존 제품과 동일한 사유(비적용/근거 부족)로 null 유지.

**[1] SE/BTL 값 분리**: Max_Output_Voltage_Peak와 Amplification_Gain은 OM이 SE/BTL 두 조건을 별도로 명시한다(SE: 36 Vpk / 26 dB, BTL: 70 Vpk / 32 dB). 표 순수성 유지를 위해 Value에는 SE(단일 엔드, 8개 터미널 블록을 개별 채널로 쓰는 기본 모드) 조건값만 채택하고, BTL(브릿지) 조건값은 각주로 병기한다: Max_Output_Voltage_Peak BTL = 70 V, Amplification_Gain BTL = 32 dB.

**[신규][2] BTL(Bridge-Tied Load) 관련 5개 Key**: 기존 스키마(LA12X, LA7.16, D80, D90) 어디에도 SE/BTL 브릿징 개념 및 관련 Key가 없었다 — LA1.16i에서 처음 발견된 아키텍처다. LA1.16i는 8개의 female 4-point terminal block(16 출력 채널)을 홀수/짝수 쌍으로 브릿지하여 BTL로 운용할 수 있으며(OM p.15, p.25, p.31), 이 경우 채널 수는 절반(8)이 되고 채널당 출력은 증가한다(8Ω 기준 80W(SE)→230W(BTL) RMS). 이 Key군(Bridging_Support, Rated/Peak_Power_Per_Ch_BTL — v1.0 당시 5개 Key로 세분화되어 있었으나 v2.0에서 3개로 통합됨, 상세는 [2a] 참조)은 신규 발견 속성이므로 SKILL의 양방향 스키마 동기화 규칙에 따라 기존 4개 제품 파일(LA12X, LA7.16, D80, D90)에도 null로 소급 반영이 필요하다 — 이번 업로드 4개 제품(LA1.16i/LA2Xi/LA4X/LA7.16i) 파싱을 모두 마친 뒤, Phase 4 기준(누적 제품 5개 이상)에 따라 사용자 확인을 받고 일괄 동기화되었다(D80_v1.3/D90_v1.2 참조).

**[2a][구조 개편 v2.0] BTL/PBTL 전력 Key 통폐합 (가독성 개선, 실값 보존)**: v1.0까지는 부하 임피던스(BTL은 8/16 Ohm, PBTL은 4/8/16 Ohm)별로 Rated/Peak를 전부 분리한 10개 Key(Rated/Peak_Power_Per_Ch_BTL_8/16_Ohms, Rated/Peak_Power_Per_Ch_PBTL_4/8/16_Ohms)였다. 브릿지 모드를 지원하지 않거나 미확인인 제품(D80/D90/LA12X/LA7.16/LA4X/LA7.16i)에서 이 10개 Key가 전부 null로 나열되어 가독성이 크게 떨어진다는 사용자 피드백에 따라(D80_v2.0.md/D90_v2.0.md에서 선반영), 4개 Key(Rated_Power_Per_Ch_BTL, Peak_Power_Per_Ch_BTL, Rated_Power_Per_Ch_PBTL, Peak_Power_Per_Ch_PBTL)로 통합했다. **LA1.16i는 D80/D90/LA12X/LA7.16과 달리 BTL 실측값이 존재하는 유일한 케이스이므로, 통합 과정에서 값을 삭제하지 않고 Rated_Power_Per_Ch_4_Ohms의 CF6dB/CF12dB 슬래시 병기 관례와 동일한 방식으로 Value 셀에 "값 @ 임피던스 조건" 형식으로 병기해 보존했다**(Rated_Power_Per_Ch_BTL = "230 @ 8 Ohms / 160 @ 16 Ohms" W, Peak_Power_Per_Ch_BTL = "300 @ 8 Ohms / 150 @ 16 Ohms" W — 원본 4개 Key의 수치 자체는 전혀 변경되지 않았고 표기 위치만 한 셀로 병합됨). PBTL은 LA1.16i 소스에서도 미확인이므로 Rated/Peak_Power_Per_Ch_PBTL 2개 Key 모두 null로 유지한다(상세는 [23] 참조).

---

## power_supply (전원부)

| Key | Value | Unit |
|---|---|---|
| PSU_Type | 2 universal Switched Mode Power Supplies (SMPS) with Power Factor Correction (PFC) | - |
| Mains_Voltage_Range | 100 - 240 (+/-10%) | V AC |
| Mains_Frequency_Range | 50 - 60 | Hz |
| Nominal_Current_100_120V [3] | 20 A (100 V) / 15 A (120 V) | A |
| Nominal_Current_200_240V | 10 | A |
| Power_Factor | greater than 0.9 (at full load) | - |
| Power_Consumption_Idle | 70 | W |
| Power_Consumption_Standby | 12 | W |
| Mains_Connector | V-Lock compatible IEC | - |
| PSU_Mains_Rated_Power | 430 | W |
| Mains_Current_Limiter_Range [24] | null | % of rated current |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.44 "Specifications > Power supply", p.21 "Installation > Electrical specifications" (최우선) / AE "Technical requirements > Connectors, Mains rating"

**[24][구조 개편 v2.0] Mains_Current_Limiter_Range**: v1.0까지 "d80_specific" 섹션에 있던 Key를 power_supply로 재배치(Key/Value/Unit 및 근거는 변경 없음). PSU_Mains_Rated_Power와 같은 성격(메인즈 전류 관리)의 Key라 이 섹션이 더 적합하다고 판단(D80_v2.0.md와 동일 처리). LA1.16i는 d&b 브랜드 고유 개념(Mains Current Limitation, MCL)에 대응하는 스펙이 확인되지 않아 null 유지.

**측정 조건**: Power_Consumption Idle/Standby는 230V 기준 값(OM p.23: Idle 0.4A/70W, Standby 0.2A/12W; 100V/120V/200V는 전류만 배율 환산, W값은 명시 없음 — LA7.16처럼 전압별 W값이 별도 표기되지 않아 230V 기준값만 채택). PSU 2개는 각각 채널 1-8, 9-16을 담당(OM p.12).

**[3] Nominal_Current_100_120V 표기 방식 변경**: 기존 LA7.16 스키마는 이 Key에 100V/120V 통합 단일 수치(30A)를 사용했으나, LA1.16i의 OM(p.21, p.44)과 AE는 100V(20A)와 120V(15A)를 명확히 별개 수치로 구분 명시하며 두 전압을 하나로 묶은 통합값이 존재하지 않는다. 임의로 두 수치를 합산하거나 하나만 채택하는 것은 무결성 원칙 위반이므로, Value 칸에 두 조건을 병기하는 텍스트 표기로 대체했다(Unit 컬럼의 "A"는 형식상 유지). 향후 사용자 검토 시 Key를 `Nominal_Current_100V`/`Nominal_Current_120V`로 분리할지 논의가 필요하다 — 분리할 경우 LA12X/LA7.16/D80/D90에도 양방향 동기화가 필요하다.

**PSU_Mains_Rated_Power**: OM p.44 "Mains rating 100 V AC - 240 V AC ± 10%, 50 Hz - 60 Hz, 430 W"에서 직접 채택. 총 출력 용량(Total_Power_Capability)과는 성격이 다른 메인즈 입력 전력 정격이며, LA7.16의 동일 Key(2800W)와 마찬가지로 오염 없이 구분 기록했다.

---

## audio_performance (음향 스펙)

| Key | Value | Unit |
|---|---|---|
| Frequency_Response | 20 - 20000 | Hz |
| THD_N_8ohm | less than 0.003 | % |
| THD_N_4ohm | null | % |
| Output_Dynamic_Range [4] | greater than 114 (SE) | dB |
| Noise_Level [5] | less than -83 (SE) | dBu |
| Channel_Separation | greater than 90 | dB |
| Damping_Factor [4] | greater than 900 (SE) | - |
| SN_Ratio_Analog_Input [25] | null | dBr |
| SN_Ratio_Digital_Input [25] | null | dBr |
| Output_Noise_Dynamic_Range_Detail [26] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.43 "Specifications > General" (최우선) / AE "Technical requirements > Amplification"

**측정 조건**: Frequency_Response는 ±0.25dB 허용오차(OM). THD_N_8ohm은 1kHz, 8Ω, unweighted 기준(OM/AE 일치, 충돌 없음 — 두 소스 모두 "< 0.003%"). Output_Dynamic_Range/Noise_Level/Damping_Factor는 20Hz-20kHz, 8Ω, A-weighted, digital input 기준(SE). Channel_Separation은 1kHz, 8Ω 기준. THD_N_4ohm은 두 소스 모두 4Ω 조건 수치를 제공하지 않아 null 처리.

**[4] SE/BTL 값 분리**: Output_Dynamic_Range(BTL: >116dB)와 Damping_Factor(BTL: >800)도 OM이 SE/BTL을 구분 명시한다. amplification 섹션 각주[1]과 동일한 원칙으로 Value에는 SE 조건값만 채택하고 BTL값은 여기 병기한다.

**[5] Noise_Level 충돌 (단위 불일치 포함)**: OM(p.43)은 "< -83 dBu (SE, 20Hz-20kHz, 8Ω, A-weighted, digital input)"로 명시(BTL은 -79dBu). AE는 동일 항목을 "Noise level < -85 dBV"로 표기 — 수치(-83 vs -85)뿐 아니라 **단위 자체가 dBu vs dBV로 다르다**(dBu와 dBV는 기준 임피던스가 달라 동일 수치라도 실제 레벨이 다름). 두 값 모두 보존 — Value는 OM 최우선 원칙에 따라 "-83 dBu"를 채택하고, AE의 "-85 dBV" 원문은 임의로 단위 환산하지 않고 그대로 각주에 병기한다(SKILL v1.9 "표기 기준이 다른 동일 물리량의 임의 변환 금지" 원칙 적용).

**[25][구조 개편 v2.0] SN_Ratio_Analog_Input/SN_Ratio_Digital_Input**: v1.0까지 "d80_specific" 섹션에 있던 Key를 audio_performance로 재배치(Key/Value/Unit 및 근거는 변경 없음, D80_v2.0.md와 동일 처리). Output_Dynamic_Range/Noise_Level과는 물리량 기준이 달라 별도 Key로 유지한다. LA1.16i는 d&b 브랜드 고유 개념에 대응하는 스펙이 확인되지 않아 null 유지.

**[26][구조 개편 v2.0] Output_Noise_Dynamic_Range_Detail**: v1.0까지 "d90_specific" 섹션에 있던 Key를 audio_performance로 재배치(Output_Dynamic_Range/Noise_Level과 인접 배치, 근거는 변경 없음, D80_v2.0.md와 동일 처리). LA1.16i는 이 상세 절대 노이즈 전압 기반 데이터 구조에 대응하는 서술이 확인되지 않아 null 유지.

---

## dsp (신호 처리)

| Key | Value | Unit |
|---|---|---|
| DSP_Processor [6] | Gen. 5 dual DSP engine, 32-bit floating point, 96 kHz sampling rate | - |
| DSP_Sampling_Rate [7] | 96 (internal, fixed, independent from input Fs) | kHz |
| Routing_Matrix | 16x16 routing and summation matrix | - |
| EQ_Filters_Per_Output [8] | null | - |
| Per_Channel_DSP_Tools | Multiband EQ, Array morphing, Air absorption compensation filter | - |
| Amplifier_Power_Management | L-SMART adaptive power management | - |
| Speaker_Protection | L-DRIVE (excursion, temperature, over-voltage) | - |
| Preset_Memory_User [9] | null | slots |
| Preset_Memory_Factory | null | slots |
| System_Start_Up_Time [27] | null | sec |
| LoadMatch_Max_Cable_Length [27] | null | m |
| Load_Monitoring_System_Check [27] | null | - |
| Time_To_Tone [28] | null | sec |
| Energy_Saving_Detail [28] | null | - |
| AmpPresets_Detail [28] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.12 "Technical description > Main features > Internal components", p.15 "DSP architecture" (최우선) / AE "Technical requirements > DSP"

**측정 조건**: 없음(사양값). Per_Channel_DSP_Tools는 OM p.15 "audio path parameters" 다이어그램의 채널별 처리 블록("MULTIBAND EQ + ARRAY MORPHING + AIR ABSORPTION COMPENSATION FILTER")을 그대로 채택.

**[6] DSP_Processor 명칭 근거 차이**: AE는 "Gen. 5 Dual SHARC 32-bit"로 칩 브랜드명("SHARC")까지 명시하나, OM은 LA1.16i 관련 어디에도 "SHARC"라는 명칭을 사용하지 않고 "Gen. 5 dual DSP engine"(p.12), "32-bit floating point DSP"(p.15)로만 서술한다. LA7.16/LA12X 스키마는 이미 "SHARC"를 Value에 채택해 두었으나, LA1.16i는 OM 최우선 원칙과 임의 추론 금지 원칙에 따라 OM에 없는 "SHARC" 명칭을 Value에 넣지 않고 OM 서술로 채택했다. AE의 "SHARC" 언급은 본 각주에만 기록한다.

**[7] DSP_Sampling_Rate 근거**: OM p.13-14 "AES/EBU" 절: "There is no AES/EBU external synchronization mode. The amplified controller's clock always runs at 96 kHz... This ensures low jitter and high audio quality... while preventing phase shift" — LA12X/LA7.16과 동일하게 SRC가 상시 내장되어 입력 조건과 무관하게 96kHz 고정임을 OM이 직접 확정한다. AES67 모드에서도 "the amplified controller's clock always runs at 96 kHz, referenced to the PTPv2 network clock. The AES67 streams at 48 kHz are automatically upsampled to 96 kHz"(OM p.14)로 동일 원칙이 재확인된다.

**[8] EQ_Filters_Per_Output null 처리**: LA7.16/LA12X는 OM에 "8 IIR + 4 FIR" 등 필터 개수가 명시되어 있었으나, LA1.16i의 OM(p.15)은 "A dedicated engineering approach combining IIR and FIR filters generates perfectly linearized phase curves..."로만 서술하며 정확한 필터 개수를 밝히지 않는다. AE도 필터 개수를 언급하지 않는다. 임의 추론 금지 원칙에 따라 null 처리 — LA7.16의 "8 IIR+4 FIR"을 임의로 이식하지 않았다.

**[9] Preset_Memory_User null 처리**: OM(p.15)은 "complete factory preset library and the possibility to create additional user presets"로만 서술하고 구체적 슬롯 개수를 밝히지 않는다. AE도 사용자 프리셋 개수를 언급하지 않는다(LA7.16 AE의 "10 user memories"와 같은 명시적 문구가 LA1.16i AE에는 없음). 따라서 LA7.16의 10을 임의로 이식하지 않고 null 처리했다.

**[27][구조 개편 v2.0] System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check**: v1.0까지 "d80_specific" 섹션에 있던 3개 Key를 dsp로 재배치(Key/Value/Unit 및 근거는 변경 없음, D80_v2.0.md와 동일 처리). LA1.16i는 d&b 브랜드 고유 개념(LoadMatch 케이블 보정, 시스템 부팅 시간)에 대응하는 스펙이 확인되지 않아 null 유지.

**[28][구조 개편 v2.0] Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail**: v1.0까지 "d90_specific" 섹션에 있던 3개 Key를 dsp로 재배치(Preset_Memory_User/Factory, System_Start_Up_Time과 같은 전원/프리셋 관련 성격이므로 인접 배치, Key/Value 및 근거는 변경 없음, D80_v2.0.md와 동일 처리). LA1.16i는 이 3개 개념에 대응하는 서술이 확인되지 않아 null 유지.

---

## latency (지연 시간)

| Key | Value | Unit |
|---|---|---|
| Latency_Standard [10] | 3.84 (independent from input Fs) | ms |
| Latency_Low_Mode [10] | 1.18 (independent from input Fs) | ms |
| AVB_Max_Network_Latency | 2 | ms |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.46 "Specifications > Latency", p.46 "Specifications > Milan-AVB" (최우선) / AE "Technical requirements > Latency"

**측정 조건**: Analog/AES-EBU 입력 기준, 입력 샘플링 주파수와 무관(OM/AE 일치).

**[10] LA7.16과 수치 일치**: Latency_Standard(3.84ms)와 Latency_Low_Mode(1.18ms) 모두 LA7.16_v1.6.md와 정확히 동일한 수치다(OM/AE 교차 확인). 동일 세대 DSP 플랫폼을 공유하는 것으로 추정되나, 이는 추론이며 OM/AE 어디에도 "LA7.16과 동일 플랫폼"이라는 명시적 서술은 없다 — 우연의 일치일 가능성도 배제하지 않고 사실(수치)만 기록한다.

---

## input_analog (아날로그 입력)

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Channels | 1 | ch |
| Input_Impedance | 22 | kOhm |
| Max_Input_Level | 22 | dBu |
| ADC_Architecture [11] | 1 x 32-bit A/D converter at 96 kHz sampling rate | - |
| Analog_Link_Type | active link with failsafe relay, shared 12-point terminal block (AES/ANA IN + AES/ANA LINK) | - |
| CMRR_Analog_Input [29] | null | dB |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Technical description > Signal processing and amplification > Analog", p.45 "Specifications > Input signal distribution" (최우선) / AE "Technical requirements > Analog input"

**측정 조건**: Input_Impedance/Max_Input_Level은 balanced 기준(AE, THD 1%). Analog_Input_Channels(1)는 LA7.16과 동일하게 16개 증폭 채널 전체가 공유하는 보조(AUX) 입력 구조.

**[11] ADC 다이나믹레인지 충돌**: OM(p.14)은 "encoding dynamic range of 99 dB (A-weighted, 20 kHz bandwidth)"로 명시. AE는 동일 항목을 "121 dB dynamic range, 20 Hz - 20 kHz, A-weighted"로 표기 — 두 값의 차이(99 vs 121 dB)가 매우 크다. 두 값 모두 보존 — ADC_Architecture Value에는 다이나믹레인지 수치를 넣지 않고 컨버터 구성만 기재했으며, 상충 수치는 본 각주에만 병기한다. 참고로 AE의 "121 dB"는 LA7.16 AE의 동일 항목 수치와 정확히 일치하는데, LA7.16과 LA1.16i는 서로 다른 제품이므로 이는 AE 문서 작성 시 템플릿 값이 갱신되지 않았을 가능성을 시사하나, 이는 추정일 뿐 확정할 근거가 없어 임의로 어느 값을 배제하지 않는다.

**[29][구조 개편 v2.0] CMRR_Analog_Input**: v1.0까지 "d80_specific" 섹션에 있던 Key를 input_analog로 재배치(Key/Value/Unit 및 근거는 변경 없음, D80_v2.0.md와 동일 처리). LA1.16i는 d&b 브랜드 고유 개념에 대응하는 스펙이 확인되지 않아 null 유지.

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
| Digital_Input_Impedance [30] | null | Ohm |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Technical description > Signal processing and amplification > AES/EBU", p.45 "Specifications > Input signal distribution" (최우선) / AE "Technical requirements > Digital input, Sample Rate Converter"

**측정 조건**: Max_AES_Cable_Length는 단일 케이블, 48kHz 샘플링, Belden 1696A 또는 Klotz OT234H 케이블 기준(OM p.14) — LA7.16/LA12X와 동일 조건, 동일 케이블 레퍼런스, 동일 값(300m). Digital_Input_Gain_Range는 0.1dB 스텝. 모든 항목 OM/AE 일치, 충돌 없음.

**[30][구조 개편 v2.0] Digital_Input_Impedance**: v1.0까지 "d80_specific" 섹션에 있던 Key를 input_digital로 재배치(Key/Value/Unit 및 근거는 변경 없음, D80_v2.0.md와 동일 처리). LA1.16i는 d&b 브랜드 고유 개념에 대응하는 스펙이 확인되지 않아 null 유지.

---

## input_avb (AVB / Milan-AVB 입력)

| Key | Value | Unit |
|---|---|---|
| AVB_Certification | MILAN and Avnu certified (Bridge and Listener) | - |
| AVB_Device_Type [31] | null | - |
| AVB_Channels | 16 | ch |
| AVB_Stream_Count | 16 (in normal or redundancy mode) | streams |
| AVB_Formats | AAF PCM32, IEC 61883-6 AM824 | - |
| AVB_Standards | IEEE 802.1BA-2011 / 1722-2016 / 1722.1-2013 | - |
| AVB_Bridge_Forwarded_Streams | up to 150 | streams |
| Redundancy_Type | Milan-AVB seamless, automatic switchover and recovery | - |
| Fallback_Modes | AVB or AES67 to AES/EBU or analog (shared input), user-defined mapping | - |
| AES67_Support [신규][12] | Yes - AES67-2023, 16 streams up to 8 ch each, L16/L24 at 48 kHz, PTPv2 clock, user-selectable alternative to Milan-AVB | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.13 "Signal inputs, Milan-AVB, AES67", p.46-47 "Specifications > Milan-AVB, AES67" (최우선) / AE "Technical requirements > AVB input mode, AES67 input mode"

**측정 조건**: AVB_Channels(16)는 최대 16개 스트림(각 최대 8채널, 총 최대 128채널)에서 사용자 매핑(OM p.13). Switchover 조건은 AVB 또는 AES67 loss of lock(OM p.47).

**[신규][12] AES67_Support**: 기존 스키마(LA12X, LA7.16)는 AVB 전용이며 AES67 개념 자체가 없었다. LA1.16i는 Milan-AVB와 AES67 중 사용자가 네트워크 프로토콜을 선택할 수 있는 이중 모드 제품이다(OM p.13: "Alternatively, LA1.16i can operate in AES67 mode driving 16 channels of amplification from 16 AES67 streams of up to eight channels"). d&b D90의 `d90_specific` 섹션에 유사한 Milan 관련 Key가 있으나 그와는 다른 계층의 정보(D90은 Milan 세부사항, 본 Key는 AES67 겸용 여부)이므로 별도 Key로 신설했다. 이 신규 Key도 amplification 섹션 각주[2]와 마찬가지로 4개 기존 제품 파일에 양방향 동기화가 필요하며(대부분 null 예상, LA12X/LA7.16 OM 재확인 필요), Phase 4 사용자 확인 후 일괄 반영되었다.

**[31][구조 개편 v2.0] AVB_Device_Type**: v1.0까지 "d90_specific" 섹션의 Milan_Device_Type이었던 Key를 이 섹션의 명명 규칙(AVB_*)에 맞춰 이름을 바꾸고 재배치했다(D80_v2.0.md/D90_v2.0.md와 동일 처리). 같은 d90_specific 섹션에 있던 Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 3개 Key는 이미 이 섹션의 기존 AVB_Channels/AVB_Stream_Count/Redundancy_Type Key와 개념이 중복되어 별도 Key로 만들지 않고 흡수했다(신규 Key 미생성, 데이터 손실 없음 — 해당 3개 Key는 LA1.16i에서도 애초에 전량 null이었다). LA1.16i는 d&b/Milan Alliance의 "Endstation" 등 장치 유형 분류 개념에 대응하는 스펙이 확인되지 않아 AVB_Device_Type도 null 유지.

---

## input_dante (Dante 네트워크 오디오 입력)

| Key | Value | Unit |
|---|---|---|
| Dante_RX_Channels | null | ch |
| Dante_Sampling_Rates | null | kHz |
| Dante_SRC | null | - |
| Dante_Redundancy | null | - |
| Dante_Network_Flows | null | flows |
| Dante_Latency | null | ms |
| Dante_IP_Architecture | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: 해당 없음(5D_v1.0.md 신규 섹션의 양방향 동기화 반영).

**섹션 전체 비적용**: LA1.16i는 Dante가 아닌 Milan-AVB(L-Acoustics 고유 인증)/AES67 오디오 네트워크를 사용한다. 이 섹션은 5D(d&b audiotechnik Dante 설치용 라인) 파싱 중 신설되었으며, Milan-AVB 기준으로 설계된 input_avb 섹션과 별도로 Dante 프로토콜 전용 섹션으로 분리되었다. LA1.16i의 기존 소스에는 이 개념에 대응하는 서술이 없어 전량 null로 소급 반영한다.

---

## network (네트워크 설정, 구조 개편 v2.0 신규 섹션)

| Key | Value | Unit |
|---|---|---|
| Network_IP_Default [1] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: 해당 없음(D90_v1.0.md의 d90_specific 섹션으로부터 재배치).

**[1][구조 개편 v2.0] Network_IP_Default 및 신규 섹션 신설 근거**: v1.x까지 "d90_specific" 섹션에 있던 Key. IP 기본값/네트워크 설정은 AVB 오디오 스트림(input_avb)이나 물리적 커넥터(connectivity)와는 성격이 다른 별도 주제이므로, 이 재배치를 계기로 "network"라는 주제 기반 신규 섹션을 신설했다(D80_v2.0.md/D90_v2.0.md에도 동일 섹션이 반영됨). LA1.16i는 AVB/Milan/Dante 네트워크 기본 IP 개념에 대응하는 스펙이 확인되지 않아 null 유지.

---

## connectivity (커넥터)

| Key | Value | Unit |
|---|---|---|
| Input_Connectors | 1 x 12-point terminal block (AES/ANA IN + LINK, GPIO, 24 V DC backup), 2 x etherCON RJ45 (Milan-AVB/AES67 I/O) | - |
| Terminal_Block_Pinout [13] | 12핀: AES/ANA IN(+/-/Shield), GPIO 1, GPIO 3, +24V IN / AES/ANA LINK(+/-/Shield), GPIO 2, GPIO RTN — 상세 핀맵은 하단 표 참조 | - |
| XLR_Pin_Polarity | null | - |
| Speaker_Connectors [14] | 8 x female 4-point terminal block (pitch 5.08 mm) | - |
| SpeakON_Left_Pinout | null | - |
| SpeakON_Right_Pinout | null | - |
| CACOM_Pinout | null | - |
| SC32_Channel_Mapping | null | - |
| Speaker_Output_Accessories | null | - |
| Network_Connectors | 2x etherCON RJ45, 1 Gb/s | - |
| Service_Port_Type [신규][15] | 1 x USB-C, 2.0 compliant (IP configuration via USB Terminal tool of LA Network Manager) | - |
| Speaker_Terminal_Block_SE_BTL_Wiring [신규][14] | Each pair of terminal blocks (e.g. CH1-2) wired as 4x SE outputs or 1x BTL output per pair; unused pins not required to be connected | - |
| PBTL_Activation_Method [23] | null | - |
| Output_Mode_Selectable [32] | null | - |
| Fault_Contact_Type [신규][35] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.12 "Front and rear panels", p.20 "Installation > General Purpose I/O (GPIO)", p.25 "Audio and network cabling > Connection panels, Speaker connectors" (최우선) / AE "Technical requirements > Connectors"

**측정 조건**: 없음(커넥터 규격 및 결선표). XLR/SpeakON/CACOM/SC32 관련 Key는 LA1.16i에 해당 커넥터가 전혀 존재하지 않아 null 처리(비적용) — LA1.16i는 LA7.16처럼 12-point terminal block(신호/GPIO/백업전원 통합)을 쓰지만, 스피커 출력은 SC32 단일 커넥터가 아니라 LA12X처럼 개별 4-point terminal block 8개를 사용하는 제3의 커넥터 아키텍처다. 극성 정보는 PDF 텍스트 레이어에 문자로 명시되어 있어(OM p.12, p.20, p.25) 별도 이미지 분석 없이 텍스트 추출만으로 확인했다(SKILL v1.5 규칙 적용).

**[13] Terminal_Block_Pinout — LA7.16과의 명칭 차이**: 구조는 LA7.16의 12핀 단자대와 동일한 12핀(24V DC 백업 전원, GPIO x3 + 리턴, AES/ANA IN 3핀, AES/ANA LINK 3핀)이나, LA1.16i OM(p.20)은 GPIO 공통 리턴 핀을 "GPIO RTN"으로 표기하는 반면 LA7.16 OM은 "GPIO GND"로 표기한다. 기능은 동일한 것으로 판단되나 원문 표기가 다르므로 임의로 통일하지 않고 각 제품 파일에 원문 그대로 보존한다(SKILL v1.9 "표기 기준이 다른 동일 물리량의 임의 변환 금지" 원칙 적용). 상세 핀 배치:

| Pin 그룹 | Pin 이름 | 기능 |
|---|---|---|
| DSP 백업 전원 | +24V IN | DSP 백업 전원 입력(+), 24 V DC(±10%), 17 W minimum |
| DSP 백업 전원 | GND | 24V DC 백업 회로 그라운드 |
| GPIO | GPIO 1 | General Purpose I/O 1 |
| GPIO | GPIO 2 | General Purpose I/O 2 |
| GPIO | GPIO 3 | General Purpose I/O 3 |
| GPIO | GPIO RTN | GPIO return (공통 리턴) |
| AES/ANA IN | + | 입력 신호 +(hot) |
| AES/ANA IN | - | 입력 신호 -(cold) |
| AES/ANA IN | Shield | 입력 실드/그라운드 |
| AES/ANA LINK | + | 데이지체인 출력 신호 + |
| AES/ANA LINK | - | 데이지체인 출력 신호 - |
| AES/ANA LINK | Shield | 출력 실드/그라운드 |

출처: OM p.12(핀 목록), p.20(GPIO 다이어그램 및 표), p.24(24V DC 다이어그램), p.26(analog/digital connectors 다이어그램).

**[14] Speaker_Connectors 및 SE/BTL 배선**: LA1.16i는 SC32(LA7.16 구형) 대신 8개의 female 4-point terminal block을 사용하며, 각 블록 쌍(CH1-2, CH3-4 등)은 SE 모드에서 4개의 개별 출력(Out1+,Out1-,Out2+,Out2-)으로, BTL 모드에서 1개의 브릿지 출력(Out+,Out-, 나머지 2핀 미사용)으로 배선된다(OM p.25 표, p.31 배선도). 이 배선 방식은 LA7.16/LA12X에는 없던 개념으로 신규 Key(Speaker_Terminal_Block_SE_BTL_Wiring)로 기록했으며, amplification 섹션의 BTL 출력 Key들과 함께 향후 양방향 동기화 대상이다.

**[신규][15] Service_Port_Type**: LA7.16/LA12X 스키마에는 USB 서비스 포트 Key가 없었다(구형 제품은 USB 포트 자체가 없음). LA1.16i는 IP 설정 전용 USB-C 포트를 신규로 갖추고 있다(OM p.12 "5. 1 USB-C port for configuring IP settings"). 이 신규 Key도 향후 양방향 동기화 대상이다.

---

## control_monitoring (제어 및 모니터링)

| Key | Value | Unit |
|---|---|---|
| Remote_Software [16] | LA Network Manager | - |
| Network_Topologies | daisy-chain, star, hybrid | - |
| Third_Party_Control [17] | Q-SYS, Crestron | - |
| Front_Panel [18] | LED indicators only (power, L-NET, status, 16 signal LEDs) - no display or encoder wheel | - |
| Settings_Protection | null | - |
| GPIO_Count | 3 | ea |
| GPIO_Type | isolated optocoupler inputs, isolated relay contacts | - |
| DSP_Backup_Power_Input [19] | 24 | V DC |
| Signal_Path_Management [33] | null | - |
| Web_Remote_Interface [신규][36] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.16 "Technical description > Monitoring and control", p.20 "Installation > General Purpose I/O (GPIO)", p.47 "Specifications > Remote control and monitoring" (최우선) / AE "Technical requirements > Third-party management solutions, Connectors"

**측정 조건**: L-NET 네트워크는 최대 253대 제어 가능, CAT5e U/FTP 이상 케이블 사용(OM p.16, LA7.16/LA12X와 동일). Settings_Protection은 소스에 LA1.16i 관련 서술이 없어 null 처리.

**[16] Remote_Software OS 정보 생략**: LA7.16 스키마는 "LA Network Manager (Windows/Mac)"로 OS를 명시했으나, LA1.16i의 OM/AE 어디에도 지원 OS가 명시되어 있지 않다(OM p.16은 단순히 "a single control computer"로만 서술). LA7.16 소스의 OS 정보를 임의로 이식하지 않고 OS 미표기 상태로 남긴다.

**[17] Third_Party_Control**: OM(p.16)과 AE 모두 "Crestron, QSC Q-SYS"를 명시. AE는 별도로 "HTTP"도 목록에 병기하며, OM(p.16)은 "For other control platforms, an HTTP API is available on request after signing a memorandum of understanding"로 조건부 서술한다 — LA7.16 각주[8]와 동일 패턴. Value는 Q-SYS/Crestron만 채택하고 HTTP API의 MOU 조건부 제공 사실은 본 각주에 기록한다.

**[18] Front_Panel — LA7.16과의 아키텍처 차이**: LA7.16(구형)은 "1 TFT color touchscreen display, 1 encoding wheel with push button"을 갖추고 있으나, LA1.16i의 OM(p.12, p.33-34)에는 터치스크린이나 인코딩 휠에 대한 언급이 전혀 없고 LED 표시등(power/L-NET/status + 16개 signal LED)만 존재한다. 이는 LA1.16i가 설치전용(install-specific) 제품으로서 로컬 UI 없이 전적으로 LA Network Manager 또는 embedded Web interface로만 설정하도록 설계되었기 때문으로 판단되며(OM 전체에 로컬 설정 메뉴 서술이 없음), 실제 제품 아키텍처 차이이지 데이터 누락이 아니다.

**[19] DSP_Backup_Power_Input**: OM(p.23-24)은 "24 V DC (± 10%) 17 W minimum"으로 명시. AE는 "24 V DC 2-point terminal block"으로 전압값만 명시(세부 정격 언급 없음, 충돌 아닌 단순 생략). LA7.16과 달리 소스 간 수치 불일치는 없다. OM은 추가로 "LS10 24 V DC output is not powerful enough to supply LA1.16i DSP"라는 운용 주의사항을 명시한다(참고용, Key화하지 않음).

**[33][구조 개편 v2.0] Signal_Path_Management**: v1.0까지 "d80_specific" 섹션에 있던 Key를 control_monitoring으로 재배치(Key/Value 및 근거는 변경 없음, D80_v2.0.md와 동일 처리). input_avb 섹션의 Fallback_Modes(간략 요약)와 개념적으로 관련될 수 있으나, LA1.16i는 d&b 브랜드 고유의 Fallback/Override/AutoStandby/AutoWakeup 상세 동작 로직에 대응하는 스펙이 확인되지 않아 null 유지.

**[23] PBTL 관련 3개 Key(v1.0 당시 7개에서 통폐합으로 감소, [2a] 참조) — LA2Xi 파싱 이후 소급 반영**: LA1.16i 최초 파싱(본 문서 작성) 시점에는 아직 LA2Xi가 파싱되지 않아 PBTL(Parallel Bridge-Tied Load) 개념 자체가 스키마에 없었다. 이후 LA2Xi 파싱 과정에서 PBTL이 신규 Key로 발견되어(LA2Xi_v1.0.md 각주[3][24] 참조), Upload 폴더 4개 제품 간 Key 구조 100% 동일성 유지를 위해 LA1.16i 파일에도 소급 추가했다(당시에는 임피던스별로 세분화된 Rated/Peak_Power_Per_Ch_PBTL_4/8/16_Ohms 6개 Key + PBTL_Activation_Method 1개 Key, 총 7개). v2.0 구조 개편에서 amplification 섹션의 PBTL 전력 Key가 Rated_Power_Per_Ch_PBTL/Peak_Power_Per_Ch_PBTL 2개로 통합되어(각주[2a] 참조), 이 그룹은 이제 2개 전력 Key + PBTL_Activation_Method 1개, 총 3개다. LA1.16i의 Bridging_Support Value("Yes - SE/BTL selectable per output pair")는 SE/BTL 2가지 모드만 언급하며 PBTL을 언급하지 않는다 — 다만 이는 최초 파싱 시점 OM 재확인이 아닌 기존 서술에 근거한 판단이므로, PBTL 2개 전력 Key와 PBTL_Activation_Method 모두 "확정된 비존재(0)"가 아닌 **미확인(null)**으로 보수적으로 처리했다(추후 LA1.16i OM 재검토 시 PBTL 지원 여부를 명시적으로 재확인 필요).

**[32][구조 개편 v2.0] Output_Mode_Selectable**: v1.0까지 "d80_specific" 섹션에 있던 Key를 connectivity로 재배치(Key/Value 및 근거는 변경 없음, D80_v2.0.md와 동일 처리). Speaker_Connectors/Speaker_Terminal_Block_SE_BTL_Wiring의 출력 구성과 성격이 유사하여 이 섹션이 더 적합하다고 판단. LA1.16i는 d&b 브랜드 고유의 채널쌍 단위 출력 모드 선택(Dual Channel/Mix TOP-SUB/2-Way Active 등) 개념에 대응하는 스펙이 확인되지 않아 null 유지 — LA1.16i 자체의 SE/BTL 출력 모드 선택은 별도 Key(Speaker_Terminal_Block_SE_BTL_Wiring, 각주[14])로 이미 기록되어 있다.

**[신규][35] Fault_Contact_Type**: 5D(d&b audiotechnik) 파싱 중 신설된 Key(FAULT 릴레이 접점, NO/C/NC). LA1.16i의 기존 소스에는 이 개념에 대응하는 서술이 없어 null로 소급 반영한다.

**[신규][36] Web_Remote_Interface**: 10D(d&b audiotechnik 차세대 설치용 라인) 파싱 중 발견된 신규 Key — 별도 소프트웨어(LA Network Manager) 없이 표준 웹 브라우저로 기기에 직접 접속하는 브라우저 기반 내장 웹 인터페이스 개념. LA1.16i의 기존 소스에는 이 개념에 대응하는 서술이 확인되지 않아 null(미확인)로 소급 반영한다.

---

## operating_conditions (동작 환경)

| Key | Value | Unit |
|---|---|---|
| Operating_Temp_Range | -5 to 50 | degrees C |
| Cooling | fans with temperature-controlled speed, front to rear airflow | - |
| Fan_Count | null | ea |
| Fan_Noise_Min | 26 | dBA |
| Fan_Noise_Max | 52 | dBA |
| EMC_Class | non-residential (Class A) | - |
| Max_Operating_Altitude | 3000 | m |
| Storage_Temp_Range [34] | null | degrees C |
| Storage_Humidity [34] | null | % rel. |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.6 "Important safety instructions", p.44-45 "Specifications > Operating conditions" (최우선) / AE "Technical requirements > Operating conditions"

**측정 조건**: Operating_Temp_Range는 안전 섹션(p.6)과 스펙 섹션(p.44) 일치, 충돌 없음. Fan_Noise는 free field, 1m 거리 기준(Min=Idle모드, Max=최고속). OM은 추가로 "at 1/8 output power: 44 dBA" 중간값을 제공하나 기존 스키마의 Min/Max 2단 구조에 대응하는 Key가 없어 반영하지 못했다 — 필요 시 향후 `Fan_Noise_1_8_Power` Key 신설 검토. Fan_Count는 OM/AE 어디에도 팬 개수가 명시되어 있지 않아 null 처리(LA7.16은 AE에서 5로 확인되었으나 LA1.16i AE에는 해당 서술 없음).

**Max_Operating_Altitude**: OM p.44 "Maximum altitude 3000 m" — LA7.16의 2000m과 다른 값이나, 서로 다른 제품의 실제 스펙 차이이며 소스 충돌이 아니다. 추가로 OM p.24는 잔류자기 페라이트 설치 시 residential(Class B) 환경에서도 사용 가능함을 명시하나(Würth Elektronik 74271221 레퍼런스), 이는 EMC_Class Key의 보조 설명으로 Value를 바꾸지 않고 여기 참고 기록만 남긴다.

**[34][구조 개편 v2.0] Storage_Temp_Range/Storage_Humidity**: v1.0까지 "d80_specific" 섹션에 있던 Key를 operating_conditions로 재배치(Key/Value/Unit 및 근거는 변경 없음, D80_v2.0.md와 동일 처리). LA1.16i는 d&b 브랜드 고유 개념에 대응하는 스펙이 확인되지 않아 null 유지.

---

## physical (물리적 스펙)

| Key | Value | Unit |
|---|---|---|
| Width | 483 | mm |
| Height [20] | 44.45 | mm |
| Depth [21] | 371 | mm |
| Weight [22] | 5.9 | kg |
| Protection_Rating | IP2x | - |
| Finish | black | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.19 "Installation > Mounting > LA1.16i dimensions", p.47 "Specifications > Physical data" (최우선) / AE "Physical data"

**측정 조건**: OM은 1U(44.45mm) 랙 마운트 제품임을 본문에서 명시적으로 반복 확인한다("The LA1.16i is one rack unit high (1U)", p.19).

**[20] Height 충돌**: OM은 여러 위치에서 "1U"(44.45mm)를 명확히 확정한다(p.19 본문 및 치수 도면). 그러나 AE는 "(W,H,D): 483mm, 88mm, 434mm"로 H=88mm를 명시 — 이는 2U에 해당하는 수치이며 LA1.16i의 실제 1U 사양과 모순된다. 두 값 모두 보존 — OM 최우선 원칙 및 OM 본문의 명시적 반복 확인을 근거로 44.45mm를 채택하고, AE의 88mm는 각주에 병기한다. 참고로 AE의 88mm는 LA7.16 AE의 Height 수치와 정확히 일치하여 AE 문서 작성 시 템플릿 값이 LA1.16i용으로 갱신되지 않았을 가능성이 있으나, 이는 추정이며 원문 값 자체는 임의로 배제하지 않는다(input_analog 섹션 각주[11]의 121dB 사례와 동일 패턴).

**[21] Depth 값 선택 근거 불확실**: OM의 치수 도면(p.19)에는 여러 깊이 관련 수치가 혼재한다 — 측면도 총 깊이 371mm/14.6in, 바닥면 몸체 길이(전후) 365mm/14.4in, 리어브래킷 장착 시 최대 480mm/18.9in. 이 중 측면도 총 깊이(371mm, 커넥터 돌출부 포함 전체 깊이로 판단)를 대표값으로 채택했다. AE는 "D": 434mm/17.1in를 명시하나, 이는 OM의 어느 깊이 수치와도 정확히 일치하지 않으며 오히려 OM 바닥면 도면의 폭(width) 수치인 435mm/17.1in와 근접하다(AE가 W/D를 착각했을 가능성 — LA7.16 파일의 유사 사례와 같은 패턴). 임의로 대응시키지 않고 AE의 434mm를 각주에만 기록한다.

**[22] Weight 충돌**: OM(p.47) "Weight 5.9 kg / 13 lb" vs AE "Weight (net): 5.6 kg / 12.3 lb". 두 값 모두 보존 — OM 최우선 원칙에 따라 5.9kg 채택, AE의 5.6kg은 각주 병기.

---

## protection_summary (보호 회로)

| Key | Value |
|---|---|
| Protection_Mains_PSU | over and under voltage, over temperature, L-SMART, overcurrent (fuse protection, inrush current protection), power budget limiter |
| Protection_Outputs | overcurrent, DC, short circuit, over temperature |
| Protection_Transducer | L-DRIVE: excursion, temperature, over-voltage |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.45 "Specifications > Protection" (최우선) / AE에는 대응 소단락 없음(OM 단독 출처)

**측정 조건**: 없음(보호 기능 목록). 세 항목 모두 OM 원문 표기를 그대로 채택했으며 LA7.16과 문구가 거의 동일하다(임의 통일이 아니라 OM 원문 자체가 유사한 표준 문구를 사용).

---

## Null Report

이번 소스 집합에서 정의되지 않아 null 처리된 항목 (총 45건, D25 파싱 중 발견된 신규 Key Max_Output_Current_Peak 1건, 5D 파싱 중 발견된 신규 Key 8건(input_dante 7개 + Fault_Contact_Type) 및 10D 파싱 중 발견된 신규 Key 1건(Web_Remote_Interface) 소급 반영 포함):

**LA1.16i 자체 소스 근거 부족 (총 14건)**: Rated_Power_Per_Ch_2.7_Ohms, Total_Power_Capability, THD_N_4ohm, EQ_Filters_Per_Output, Preset_Memory_User, Preset_Memory_Factory, XLR_Pin_Polarity, SpeakON_Left_Pinout, SpeakON_Right_Pinout, CACOM_Pinout, SC32_Channel_Mapping, Speaker_Output_Accessories, Settings_Protection, Fan_Count.

**구조 개편 v2.0으로 재배치된 옛 d80_specific 항목 (총 12건, 재배치된 섹션 내에서 null 상태 그대로 유지)**: CMRR_Analog_Input(input_analog, 각주[29]), Digital_Input_Impedance(input_digital, 각주[30]), SN_Ratio_Analog_Input/SN_Ratio_Digital_Input(audio_performance, 각주[25]), System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check(dsp, 각주[27]), Storage_Temp_Range/Storage_Humidity(operating_conditions, 각주[34]), Signal_Path_Management(control_monitoring, 각주[33]), Output_Mode_Selectable(connectivity, 각주[32]), Mains_Current_Limiter_Range(power_supply, 각주[24]).

**구조 개편 v2.0으로 재배치된 옛 d90_specific 항목 (총 6건 — Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 3건은 input_avb 기존 Key로 흡수되어 별도 Key가 아니게 되었으므로 목록에서 제외)**: AVB_Device_Type(input_avb, 옛 Milan_Device_Type, 각주[31]), Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail(dsp, 각주[28]), Output_Noise_Dynamic_Range_Detail(audio_performance, 각주[26]), Network_IP_Default(network, 신설 섹션, 각주[1]).

**PBTL 관련 (총 3건, v1.0의 7건에서 통폐합으로 감소 — 각주[2a][23] 참조)**: Rated_Power_Per_Ch_PBTL, Peak_Power_Per_Ch_PBTL(amplification — v1.0의 Rated/Peak_Power_Per_Ch_PBTL_4/8/16_Ohms 6개 Key가 2개로 통합됨), PBTL_Activation_Method(connectivity — 변경 없음).

**D25 파싱 중 발견된 신규 Key (1건)**: Max_Output_Current_Peak(amplification) — D25 OM/SPS "Maximum output voltage/current 120 Vpeak/35 Apeak"에서 확인되어 신설, LA1.16i 기존 소스에는 대응 전류 값이 없어 null로 소급 반영.

**5D 파싱 중 발견된 신규 input_dante 섹션 (총 7건, 비적용)**: Dante_RX_Channels, Dante_Sampling_Rates, Dante_SRC, Dante_Redundancy, Dante_Network_Flows, Dante_Latency, Dante_IP_Architecture(input_dante, 신설 섹션) — LA1.16i는 Dante가 아닌 Milan-AVB/AES67 오디오 네트워크를 사용하므로 섹션 전체가 비적용이다.

**5D 파싱 중 발견된 신규 Key (1건, 미확인)**: Fault_Contact_Type(connectivity, 각주[35]) — 5D의 FAULT 릴레이 접점(NO/C/NC) Key가 신설되어 소급 반영되었으나, LA1.16i의 기존 소스(OM/AE)에는 이 개념에 대응하는 서술이 없어 "확정된 비존재"가 아닌 미확인(null)으로 보수적 처리한다.

**10D 파싱 중 발견된 신규 Key (1건, 미확인)**: Web_Remote_Interface(control_monitoring, 각주[36]) — 브라우저 기반 내장 웹 인터페이스 개념이 신설되어 소급 반영되었으나, LA1.16i의 기존 소스(OM/AE)에는 이 개념에 대응하는 서술이 없어 미확인(null)으로 보수적 처리한다.

**참고**: BTL(Rated_Power_Per_Ch_BTL, Peak_Power_Per_Ch_BTL)은 실값(230 @ 8 Ohms / 160 @ 16 Ohms W, 300 @ 8 Ohms / 150 @ 16 Ohms W)이 존재하여 v1.0과 마찬가지로 Null Report에 포함하지 않는다. 총 42건(v1.0) -> 36건(v2.0)으로 감소한 것은 실값 손실이 아니라 (1) d90_specific의 Milan 중복 3개 Key가 기존 Key로 흡수되어 소멸(-3), (2) BTL/PBTL 10개 Key가 4개로 통합되면서 그중 null이던 PBTL 6개가 2개로 줄어듦(-4)에 따른 순감소다(v2.0 시점 grep 검증 결과 36건이 정확한 실측치이며, 이번 v2.1 편집 이전 본 Null Report 서두에 있던 "35건" 표기는 실제 테이블 대비 1건 과소 기재된 오기였다). v2.0의 36건에 5D 신규 스키마 확장분(input_dante 7건 + Fault_Contact_Type 1건) 8건을 더해 v2.1은 44건, 10D 신규 스키마 확장분(Web_Remote_Interface 1건)을 더해 v2.2는 45건이다(테이블 내 null 값 셀을 grep으로 실측 검증함).

## 버전 변경 이력

v1.0: Phase 3-1 신규 제품(L-Acoustics "i" 설치전용 라인) 최초 투입. OM(52p, 텍스트 레이어 전량 추출) + AE(docx, zip 압축 해제 후 텍스트 추출) 2개 소스를 교차 검증하여 마스터 스키마 최초 구축(LA7.16_v1.6.md의 Key 목록/구조를 뼈대로 복제 후 서지컬 교체). LA7.16(구형)과는 완전히 다른 제품 아키텍처(1U, 4-point terminal block 스피커 출력, SE/BTL 브릿징, AVB/AES67 겸용, USB 서비스 포트)로 인해 신규 Key 7개(BTL 출력 5개, AES67_Support, Service_Port_Type) 및 배선 신규 Key 1개(Speaker_Terminal_Block_SE_BTL_Wiring) 발견 — 기존 4개 제품 파일로의 양방향 동기화는 Upload 폴더 4개 제품(LA1.16i/LA2Xi/LA4X/LA7.16i) 파싱 완료 후 Phase 4 규칙에 따라 사용자 확인을 받아 일괄 진행 예정. 소스 간 데이터 충돌 5건(Noise_Level 단위+수치, ADC dynamic range, Height, Depth 대응불가, Weight) 발견, 전부 각주로 보존. SPS/웹 데이터 미제공으로 6개 기존 제품 대비 교차검증 소스가 2개(OM, AE)로 적어 향후 추가 소스 확보 시 재검토 필요.

v1.0 to v2.0: (구조 개편, Major — D80_v2.0.md/D90_v2.0.md와 동일 개편을 L-Acoustics 라인에도 적용) 사용자 요청에 따라 "d80_specific"과 "d90_specific" 두 그랩백 섹션을 모두 폐지했다. d80_specific의 12개 Key는 CMRR_Analog_Input -> input_analog[29], Digital_Input_Impedance -> input_digital[30], SN_Ratio_Analog_Input/SN_Ratio_Digital_Input -> audio_performance[25], System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check -> dsp[27], Storage_Temp_Range/Storage_Humidity -> operating_conditions[34], Signal_Path_Management -> control_monitoring[33], Output_Mode_Selectable -> connectivity[32], Mains_Current_Limiter_Range -> power_supply[24]로 재배치(Key/Value/Unit/각주 내용 유지, 위치만 이동, 전량 null 그대로). d90_specific의 9개 Key는 Milan_Device_Type -> input_avb(AVB_Device_Type으로 개명[31]), Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs -> input_avb의 기존 AVB_Channels/AVB_Stream_Count/Redundancy_Type에 흡수(중복 제거, 신규 Key 미생성), Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail -> dsp[28], Output_Noise_Dynamic_Range_Detail -> audio_performance[26], Network_IP_Default -> 신설된 network 섹션[1]으로 재배치. 이동한 Key마다 원래 위치를 명시하는 각주를 신설했다.

아울러 amplification 섹션의 BTL/PBTL 전력 Key 10개(부하 임피던스별 세분화: Rated/Peak_Power_Per_Ch_BTL_8/16_Ohms 4개 + Rated/Peak_Power_Per_Ch_PBTL_4/8/16_Ohms 6개)를 4개(Rated_Power_Per_Ch_BTL, Peak_Power_Per_Ch_BTL, Rated_Power_Per_Ch_PBTL, Peak_Power_Per_Ch_PBTL)로 통합했다(각주[2a]). **LA1.16i는 D80/D90/LA12X/LA7.16과 달리 BTL 실측값(Rated: 230W@8Ω/160W@16Ω, Peak: 300W@8Ω/150W@16Ω)이 존재하는 유일한 케이스이므로, 이 실값을 삭제하지 않고 Rated_Power_Per_Ch_4_Ohms의 CF6dB/CF12dB 슬래시 병기 관례와 동일한 방식으로 Value 셀에 "값 @ 임피던스" 형식으로 병기하여 데이터 손실 없이 보존했다** — Rated_Power_Per_Ch_BTL = "230 @ 8 Ohms / 160 @ 16 Ohms" W, Peak_Power_Per_Ch_BTL = "300 @ 8 Ohms / 150 @ 16 Ohms" W (원본 수치 자체는 전혀 변경되지 않았고 표기 위치만 병합됨). PBTL 2개 Key는 기존과 동일하게 null 유지. 이에 따라 connectivity 섹션 각주[23](PBTL 관련 Key 그룹, LA2Xi 소급 반영)도 7건 -> 3건으로 갱신했다.

Null Report 총 건수는 42건(v1.0)에서 35건(v2.0)으로 변경 — (1) d90_specific의 Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 3개 Key가 input_avb 기존 Key로 흡수되어 소멸(-3), (2) PBTL 전력 Key 6개가 2개로 통합되며 null 건수 감소(-4). BTL 실값 2개(통합 전 4개)는 애초에 Null Report 대상이 아니었으므로 이번 건수 변동에 영향이 없다. 섹션 계층 구조 변경이므로 Major 버전(v2.0)으로 상향했다.

v2.0 to v2.1: (양방향 동기화, Minor — null 전용 추가, 실제 LA1.16i 데이터 영향 없음) d&b audiotechnik 신규 제품 5D(Dante 설치용 라인, 5D_v1.0.md) 파싱 중 발견된 스키마 확장분을 SKILL의 양방향 스키마 동기화 규칙에 따라 소급 반영했다. (1) input_avb 섹션 바로 뒤, network 섹션 앞에 신규 섹션 "input_dante (Dante 네트워크 오디오 입력)"를 신설하고 7개 Key(Dante_RX_Channels, Dante_Sampling_Rates, Dante_SRC, Dante_Redundancy, Dante_Network_Flows, Dante_Latency, Dante_IP_Architecture)를 전부 null로 추가 — LA1.16i는 Milan-AVB/AES67을 사용하고 Dante를 사용하지 않아 섹션 전체가 비적용이다. (2) connectivity 섹션 표 마지막 행(Output_Mode_Selectable 다음)에 신규 Key `Fault_Contact_Type`[신규][35]를 null로 추가 — 5D의 FAULT 릴레이 접점(NO/C/NC) 개념이며, LA1.16i 기존 소스에는 대응 서술이 없어 미확인(null)으로 보수적 처리했다. 기존 9개 섹션(및 이미 재배치된 옛 d80_specific/d90_specific 항목)의 Key/Value/Unit/각주는 일절 변경하지 않았다. Null Report 총 건수는 v2.0의 실측 36건(테이블 내 null 값 셀을 grep으로 재검증, 기존 서두 표기 "35건"은 오기로 확인되어 이번에 바로잡음)에서 신규 8건(input_dante 7개 + Fault_Contact_Type 1개)이 추가되어 v2.1은 44건이다. 섹션 계층 구조나 파싱 규칙의 실질 변경이 없는 순수 추가이므로 Minor 버전(v2.1)으로 상향했다.

v2.1 to v2.2: (양방향 동기화, Minor — null 전용 추가, 실제 LA1.16i 데이터 영향 없음) d&b audiotechnik 신규 제품 10D(차세대 설치용 라인, 10D_v1.0.md) 파싱 중 발견된 신규 Key `Web_Remote_Interface`[신규][36]를 control_monitoring 섹션 표 마지막 행(Signal_Path_Management 다음)에 null로 추가했다 — 별도 소프트웨어(LA Network Manager) 없이 표준 웹 브라우저로 기기에 직접 접속하는 브라우저 기반 내장 웹 인터페이스 개념이며, LA1.16i 기존 소스에는 대응 서술이 없어 미확인(null)으로 보수적 처리했다. 기존 Key/Value/Unit/각주는 일절 변경하지 않았다. Null Report 총 건수는 44건 -> 45건(신규 1건)으로 갱신했다. 섹션 내부 Key 1건 추가에 불과하므로 Minor 버전(v2.2)으로 상향했다.
