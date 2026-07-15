# LA7.16 - Master Spec Schema

Schema_Version: 1.7 (Phase 4 양방향 동기화 - Upload 4개 제품(LA1.16i/LA2Xi/LA4X/LA7.16i) 파싱 중 발견된 신규 15개 Key 반영)
최종 작업 일시: 2026-07-15 21:43 (수요일)
Manufacturer: L-Acoustics
Product_Category: Amplified_Controller (16-channel Class D amplifier with integrated DSP)
Form_Factor: 19 inch rack, 2U

## 출처 등록부 (Source Registry)

| Source_ID | Document | Version / Date |
|---|---|---|
| OM | Owner's Manual (EN) | version 4.0 |
| SPS | Spec Sheet PDF (EN) | 1.4, 251125 |
| AE | Architects and Engineers Spec (docx) | undated |
| WEB-L | Website - List View | current |
| WEB-O | Website - Overview | current |
| WEB-F | Website - Full Spec | current |

L-Acoustics 브랜드 규칙에 따라 이하 모든 섹션의 출처 표기는 오너 매뉴얼(OM)의 페이지/목차 위치를 최우선으로 기록한다.

본 파일은 SKILL v1.7의 "완벽한 양방향 스키마 동기화" 규칙에 따라 LA12X_v2.6.md와 Key 목록을 100% 일치시킨 개정본이다. v1.3까지의 데이터/각주 내용은 전혀 바꾸지 않고, Phase 3-2(d&b D80 파싱)에서 발견된 신규 섹션 `d80_specific`(12개 Key)을 전량 `null`로 신설 추가했다.

**Phase 4 동기화 안내(v1.7)**: Upload 폴더 4개 신규 제품(LA1.16i, LA2Xi, LA4X, LA7.16i) 파싱 과정에서 발견된 15개 신규 Key(브릿지 모드 관련 10개, AES67_Support, Service_Port_Type, Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method)를 아래 각 섹션에 `null`로 신설 추가했다. LA7.16(구형)의 기존 소스(OM v4.0, SPS 1.4, AE)에는 브릿지 모드/AES67/USB 서비스 포트 관련 서술이 전혀 확인되지 않으며, 원본 문서를 재조회하지 않고 기존 파싱 결과물 텍스트만을 근거로 판단했으므로(사용자 승인에 따른 진행 방식) "확정된 비존재(No/0)"가 아닌 **미확인(null)**으로 보수적으로 처리했다 — 추후 LA7.16 원본 OM 재검토 시 갱신 필요. 기존 9개 섹션 및 d80_specific/d90_specific의 Key/Value/각주는 일절 변경하지 않았다.

---

## amplification (증폭부)

| Key | Value | Unit |
|---|---|---|
| Channel_Count_In | 16 | ch |
| Channel_Count_Out | 16 | ch |
| Amplification_Class | High-efficiency Class D | - |
| Rated_Power_Per_Ch_2.7_Ohms [양방향 동기화][1] | null | W |
| Rated_Power_Per_Ch_4_Ohms | 1000 | W |
| Rated_Power_Per_Ch_8_Ohms | 920 | W |
| Rated_Power_Per_Ch_16_Ohms [신규] | 580 | W |
| Peak_Power_Per_Ch_4_Ohms [신규] | 1100 | W |
| Peak_Power_Per_Ch_8_Ohms [신규] | 1300 | W |
| Peak_Power_Per_Ch_16_Ohms [신규] | 700 | W |
| Total_Power_Capability [2] | null | W |
| Max_Output_Voltage_Peak | 152 | V |
| Amplification_Gain | 32 | dB |
| Output_Delay_Range | 0 - 1000 | ms |
| Bridging_Support [신규][12] | null | - |
| Rated_Power_Per_Ch_BTL_8_Ohms [신규][12] | null | W |
| Rated_Power_Per_Ch_BTL_16_Ohms [신규][12] | null | W |
| Peak_Power_Per_Ch_BTL_8_Ohms [신규][12] | null | W |
| Peak_Power_Per_Ch_BTL_16_Ohms [신규][12] | null | W |
| Rated_Power_Per_Ch_PBTL_4_Ohms [신규][12] | null | W |
| Rated_Power_Per_Ch_PBTL_8_Ohms [신규][12] | null | W |
| Rated_Power_Per_Ch_PBTL_16_Ohms [신규][12] | null | W |
| Peak_Power_Per_Ch_PBTL_4_Ohms [신규][12] | null | W |
| Peak_Power_Per_Ch_PBTL_8_Ohms [신규][12] | null | W |
| Peak_Power_Per_Ch_PBTL_16_Ohms [신규][12] | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.92 "Specifications > General", p.18 "Technical description > Power supply and amplifier section" (최우선) / SPS 7p "Amplification and power supply" / AE "Technical requirements > Amplification" / WEB-L, WEB-O, WEB-F 스펙 표

**측정 조건**: `Peak_Power_Per_Ch_*`는 12 dB Crest Factor, 2 ms, 1 kHz, all channels driven, sine burst 조건(OM/SPS/AE 일치). `Rated_Power_Per_Ch_*`는 CEA-2006/490A, 20 ms, THD ≤ 1%, 1 kHz, all channels driven, sine burst 조건(OM/SPS/AE 일치) — LA12X와 동일한 CEA 표준을 사용하므로 두 파일의 `Rated_Power_Per_Ch_*` 키는 동일 측정 기준으로 비교 가능하다.

**[1] Rated_Power_Per_Ch_2.7_Ohms (양방향 동기화, v1.1 신규 추가)**: LA12X 파일에만 존재하던 기존 Key. v1.0에서는 "LA7.16에 해당 조건이 없으므로 키 자체를 생략"하는 방식으로 처리했으나, SKILL v1.7의 양방향 스키마 동기화 규칙에 따라 v1.1에서 Key를 추가하고 값은 `null`로 처리했다. LA7.16의 OM/SPS/AE 어느 소스도 2.7 Ω 부하 조건의 출력을 측정/명시하지 않는다 — LA7.16은 4/8/16 Ω 세 부하 조건만 스펙 표에 존재하며, 2.7 Ω은 LA12X 계열(4채널, 낮은 부하 임피던스 지원)에 특화된 조건으로 판단된다. 즉 이 null은 "미확인"이 아니라 "제품 아키텍처상 해당 조건 자체가 없음(비적용)"을 의미한다.

**[2] Total_Power_Capability 정정 (v1.0 -> v1.1)**: v1.0에서는 이 Key에 OM/SPS/AE의 "Mains rating ... 2800 W" 수치를 대입했으나, 이는 오기재였다. 재검증 결과 "2800 W"는 SMPS가 AC 메인즈로부터 끌어오는 **입력 전력 정격**(mains input power rating)이며, LA12X의 `Total_Power_Capability`(12000 W)가 나타내는 개념 — 앰프가 전 채널에 걸쳐 동시에 공급 가능한 **총 출력 용량**(combined output capacity) — 과는 성격이 다른 값이다. LA7.16의 OM(107p 전량), SPS(7p), AE 어디에도 "총 출력 용량"에 해당하는 단일 수치가 명시적으로 기재되어 있지 않으며(채널 수 × 채널당 정격의 임의 곱셈은 무결성 원칙상 금지), 따라서 SKILL v1.7의 "총량/정격 Key 오염 금지" 조항에 따라 본 Key는 `null`로 정정한다. 정정 전 값이었던 "2800 W"는 성격에 맞는 별도 Key(`PSU_Mains_Rated_Power`)로 이관하여 power_supply 섹션에 기록했다(아래 참조).

**L-SMART 관련 팩트 체크**: SPS(1p, 2p)는 "The PSU can provide extremely high short-term peak power and 7000 W for longer hold times"라고 서술한다. 이는 L-SMART 동적 전력 배분 기술(예측 모델링 기반으로 PSU와 개별 채널의 전력을 실시간 재분배)에 의해 순간적으로 도달 가능한 PSU 총 출력이 2800 W(연속 정격)를 크게 상회할 수 있음을 의미하는 정성적 서술이다. 다만 "longer hold times"의 정확한 지속 시간, 측정 조건(부하 임피던스, 채널 수, 신호 종류)이 소스 어디에도 명시되어 있지 않아, 이 "7000 W"를 `Total_Power_Capability`나 별도의 정식 Key 값으로 채택하지 않는다(임의 추론/수식어 첨가 금지 원칙). 참고로 d&b D80(Phase 3-2)의 `PSU_Mains_Rated_Power`도 공교롭게 동일한 "7000 W" 수치이나(단 D80은 "short term RMS" 조건의 메인즈 입력 전력이며 LA7.16 SPS의 "7000 W for longer hold times"와는 완전히 다른 소스/제품/개념의 값이다), 우연의 일치로 판단되며 두 수치를 서로 연관짓지 않는다. 요약하면, LA7.16의 "총 출력 용량"에 대응하는 명확한 단일 스펙 수치는 현재 확보한 6개 소스 중 어디에도 존재하지 않는다 — 있는 것은 (a) 채널당 개별 정격(Peak/Rated_Power_Per_Ch_*), (b) PSU 연속 입력 전력 정격(2800 W, PSU_Mains_Rated_Power), (c) L-SMART에 의한 정의되지 않은 단기 피크(7000 W, 정성적 서술) 세 가지뿐이다.

**[신규] Rated/Peak_Power_Per_Ch_16_Ohms, Peak_Power_Per_Ch_4/8_Ohms**: LA12X 스키마에는 존재하지 않던 신규 속성. LA12X는 Peak(12 dB CF) 조건의 채널당 출력을 별도 명시하지 않고 CEA 조건 값만 제공했으나, LA7.16은 OM/SPS/AE 모두 Peak와 CEA(RMS) 두 조건의 수치를 별도로 명시하여 두 계열의 Key를 분리했다. 16 Ω 부하 조건 자체도 LA12X 소스에는 없던 신규 조건이다.

**[신규][12] Bridging_Support 및 BTL/PBTL 관련 10개 Key (v1.7, Phase 4 동기화)**: L-Acoustics "i" 설치전용 라인(LA1.16i, LA2Xi) 파싱 중 발견된 브릿지 모드(SE/BTL/PBTL) 관련 속성군. LA7.16(구형)의 기존 소스(OM v4.0, SPS 1.4, AE) 어디에도 브릿지/BTL/PBTL 관련 서술이 확인되지 않는다 — 다만 이는 원본 문서를 재조회하지 않고 기존 파싱 결과 텍스트만으로 판단한 것이므로(사용자 승인에 따른 보수적 처리 방식), LA4X처럼 전체 문서 재검색을 거쳐 "확정된 비존재(No/0)"로 단정하지 않고 **미확인(null)**으로 유지한다. LA7.16(구형)은 단일 SC32 커넥터로 16채널을 통합 구동하는 구조이며 브릿지 개념 없이 설계된 세대로 추정되나, 이는 추정일 뿐 확정 근거가 아니다. 추후 LA7.16 원본 OM 재검토 시 갱신 대상.

---

## power_supply (전원부)

| Key | Value | Unit |
|---|---|---|
| PSU_Type | Universal SMPS with Power Factor Correction (PFC) | - |
| Mains_Voltage_Range | 100 - 240 (+/-10%) | V AC |
| Mains_Frequency_Range | 50 - 60 | Hz |
| Nominal_Current_100_120V | 30 | A |
| Nominal_Current_200_240V [3] | 16 | A |
| Power_Factor | greater than 0.95 (at full load) | - |
| Power_Consumption_Idle | 144 | W |
| Power_Consumption_Standby | 19 | W |
| Mains_Connector | powerCON 32 A | - |
| PSU_Mains_Rated_Power [신규] | 2800 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.93 "Specifications > Power supply", p.24 "Installation > Electrical specifications" (최우선) / SPS 7p "Amplification and power supply" / AE "Technical requirements > Connectors, Mains rating"

**측정 조건**: Power_Consumption_Idle/Standby는 230/120/100 V 공통 W 값(전압별 전류는 상이하나 W 기준 동일 — OM p.93 표: Idle 1.0 A/144 W(230 V), 1.3 A/144 W(120 V), 1.5 A/144 W(100 V); Standby 0.8 A/19 W(230 V), 0.5 A/19 W(120 V, 100 V)). Power_Factor는 full load 기준(OM/SPS 일치). PSU_Type Value는 소스에 명시된 "Power Factor Correction (PFC)"만 반영했으며, LA12X 파일의 "DSP-controlled PFC" 수식어는 LA7.16 소스 어디에도 없어 임의로 이식하지 않았다(무결성 원칙).

**[3] 적용 전압 대역 표기 차이**: OM 안전/설치 섹션(p.24)은 "220-240 V: 16 A"로 서술하나, OM 스펙 섹션(p.93)과 SPS는 동일 항목을 "200-240 V: 16 A"로 표기. AE도 "200-240 V AC: 16 A"로 스펙 섹션과 일치. 두 표기 모두 보존 — 스펙 섹션/SPS/AE 3개 소스 일치를 근거로 200-240 V 표기를 채택값 기준으로 삼되, 안전 섹션의 220-240 V 표기도 삭제하지 않음. LA12X 파일의 동일 유형 충돌([2])과 동일한 패턴이다.

**[신규] PSU_Mains_Rated_Power**: v1.1에서 신설된 Key. OM p.93 "Mains rating 100 V AC - 240 V AC ± 10%, 50 Hz - 60 Hz, 2800 W"에 명시된 SMPS 연속 입력 전력 정격이다(v1.0에서는 이 수치가 amplification 섹션의 Total_Power_Capability에 잘못 대입되어 있었음 — 위 [2] 참조). SPS/AE는 전압/주파수 정격만 재기술하며 2800 W 수치는 OM에만 명시되어 있다(단일 소스, 충돌 아님). LA12X 스키마에는 이에 대응하는 Key가 없어 LA12X_v2.4.md(구 LA12X_v5.1.md)에 null로 신규 반영했다.

---

## audio_performance (음향 스펙)

| Key | Value | Unit |
|---|---|---|
| Frequency_Response | 20 - 20000 | Hz |
| THD_N_8ohm [4] | less than 0.1 | % |
| THD_N_4ohm | null | % |
| Output_Dynamic_Range | greater than 119 | dB |
| Noise_Level [5] | less than -79 | dBV |
| Channel_Separation | greater than 65 | dB |
| Damping_Factor | 500 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.92 "Specifications > General" (최우선) / SPS 7p "Audio specifications" / AE "Technical requirements > Amplification"

**측정 조건**: Frequency_Response는 ±0.05 dB 허용오차(OM/AE 일치). THD_N_8ohm은 20 Hz-20 kHz 대역, 8 Ω 부하, 60 W 출력 기준. Output_Dynamic_Range와 Noise_Level은 20 Hz-20 kHz, 8 Ω, A-weighted, digital input 기준. Channel_Separation은 1 kHz, 8 Ω, 60 W 기준. Damping_Factor는 20 Hz-1 kHz, 8 Ω 부하 기준(OM에만 명시, 타 소스 언급 없음). THD_N_4ohm은 세 소스 모두 4 Ω 조건의 THD 수치를 별도로 제공하지 않아 null 처리했다(LA12X는 해당 값이 존재하여 4 Ω 조건 THD 키 자체는 유지).

**[4] THD_N_8ohm 충돌**: OM(p.92)과 SPS(7p)는 "< 0.1%"로 일치. AE는 동일 항목을 "< 0.05%"로 표기. 두 값 모두 보존 — 채택값 0.1%는 OM+SPS 2개 소스 일치 및 L-Acoustics OM 최우선 원칙을 근거로 함. AE의 0.05%는 더 엄격한 수치로, 오기 또는 구버전 수치 가능성이 있으나 원문 값은 삭제하지 않음.

**[5] Noise_Level 충돌**: OM(p.92)과 SPS(7p, 6p 비교표)는 "< -79 dBV"로 일치. AE는 동일 항목을 "< -78 dBV"로 표기. 두 값 모두 보존 — 채택값 -79 dBV는 OM+SPS 2개 소스 일치를 근거로 함.

---

## dsp (신호 처리)

| Key | Value | Unit |
|---|---|---|
| DSP_Processor | Gen. 5 Dual SHARC 32-bit, floating point | - |
| DSP_Sampling_Rate [10] | 96 (internal, fixed, independent from input Fs) | kHz |
| Routing_Matrix | 16x16 routing and summation matrix | - |
| EQ_Filters_Per_Output [6] | 8 IIR + 4 FIR linear phase | - |
| Per_Channel_DSP_Tools [신규] | Array morphing (LF contour, zoom factor), Air absorption compensation filters | - |
| Amplifier_Power_Management [신규] | L-SMART adaptive power management | - |
| Speaker_Protection | L-DRIVE (excursion, temperature, over-voltage) | - |
| Preset_Memory_User | 10 | slots |
| Preset_Memory_Factory | null | slots |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.17 "Technical description > DSP architecture", p.94 "Specifications > Input signal distribution" (최우선) / SPS 3p "DSP", 7p "DSP" / AE "Technical requirements > DSP"

**측정 조건**: 없음(사양값). Preset_Memory_User는 OM p.50("one of the ten slots")과 AE("10 user memories") 일치로 10 확정. Preset_Memory_Factory는 OM p.44 부근에 공장 프리셋 슬롯 범위를 나타내는 표가 있으나("memory space number: from 001 to 010 for user layouts, from 001 to [숫자 판독 불가] for factory layouts") PDF 텍스트 추출 과정에서 표 셀 숫자가 누락되어 신뢰 가능한 상한값을 확인하지 못했다 — 임의 추론 금지 원칙에 따라 null로 처리했다(LA12X의 189와 동일하다고 가정하지 않음).

**[6] EQ_Filters_Per_Output 표기 차이**: OM(p.94)과 AE는 "8 IIR, 4 FIR linear phase EQ filters"만 명시. SPS(7p)는 동일 항목 뒤에 "Autofilter full-range"를 추가로 병기("8 IIR, 4 FIR EQ filters, Autofilter full-range"). 두 표기 모두 기록 — OM 최우선 원칙에 따라 SPS 단독 추가 문구는 Value에 병합하지 않고 본 각주에 병기함. SPS 서술(3p)에 따르면 Autofilter는 어레이 전 대역 주파수 응답을 채널 단위로 선형화하는 별도 명명된 도구이다.

**[신규] Per_Channel_DSP_Tools**: LA12X 스키마에는 없던 신규 속성. OM p.94 스펙 표의 "Per output channel" 항목을 원문 그대로 채택(Array morphing / Air absorption compensation filters). AE도 "contour filters, and filters to compensate for air absorption"으로 개념상 일치.

**[신규] Amplifier_Power_Management**: LA12X 스키마에는 없던 신규 속성. L-SMART는 SPS(1p, 2p)에 따르면 LA7.16(i)에서 처음 도입된 기술로, OM/SPS/AE 세 소스 모두 "L-SMART"라는 동일 명칭으로 확인됨. 참고로 d&b D80(Phase 3-2)의 이 Key에는 "Mains Current Limitation (MCL)"이 매핑되어 있으나, MCL은 메인즈 전류 상한 제한 기능이고 L-SMART는 채널 간 동적 전력 재분배 기능으로 작동 원리가 다르다(D80_v1.0.md 각주 참조) — 두 값의 성격 차이를 인지하되 각 파일의 원문 표현은 그대로 유지한다.

**[신규][10] DSP_Sampling_Rate 값의 근거 및 d&b D80과의 서술 유무 차이 (사용자 검토 반영, 양방향 동기화 보강)**: LA7.16은 LA12X와 동일한 신호 처리 아키텍처를 공유하며, AES/EBU 입력에 SRC(Sample Rate Converter)가 상시 하드웨어로 내장되어 있다. OM p.16 "Technical description > Signal processing and amplification > AES/EBU" 절은 LA12X OM p.15와 동일한 구조로 "The AES/EBU input is equipped with an SRC (Sample Rate Converter)... converts the formats to the 24 bits / 96 kHz internal format... and provides constant propagation delay regardless of the input sampling frequency"를 서술한다. 즉 입력 샘플레이트에 관계없이 SRC가 상시 작동하여 항상 96 kHz 내부 포맷으로 처리하며, 이로 인한 지연시간도 입력 조건과 무관하게 일정함이 OM 본문에서 명시적으로 확정된다. **d&b D80과의 서술 유무 차이**: D80은 이와 반대로 SRC를 기본적으로 비활성화해 두고 44.1/88.2 kHz 등 비표준 입력이나 비동기 다중 소스 입력 시에만 SRC를 수동으로 활성화하는 조건부 구조다(D80 OM p.34 "System clocking"/"SRC" 절, D80_v1.2.md dsp 섹션 각주 [9a] 참조). 이 때문에 D80의 DSP_Sampling_Rate(96 kHz, 내부 고정값)는 SRC 비활성 조건에서만 무조건적으로 성립한다는 단서가 붙는 반면, LA7.16은 SRC가 상시 하드웨어로 내장되어 있어 이런 조건부 서술이 필요 없다. LA12X_v2.9.md dsp 섹션 각주 [12]와 동일한 근거 구조이며, LA7.16과 LA12X는 이 부분에서 근거 수준이 동일하게 높다.

---

## latency (지연 시간)

| Key | Value | Unit |
|---|---|---|
| Latency_Standard [11] | 3.84 (independent from input Fs) | ms |
| Latency_Low_Mode [11] | 1.18 (independent from input Fs) | ms |
| AVB_Max_Network_Latency | 2 | ms |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.94 "Specifications > Latency", p.95 "Specifications > Milan-AVB" (최우선) / AE "Technical requirements > Latency, AVB input"

**측정 조건**: Analog/AES-EBU 입력 기준, 입력 샘플링 주파수와 무관하게 일정(OM/AE 일치, 충돌 없음). LA12X의 Latency_Low_Mode(0.84/0.76 ms)와는 다른 제품 고유 수치이며 소스 간 충돌이 아니다.

**[신규][11] Latency_Standard/Low_Mode 값의 확정 근거 및 d&b D80과의 서술 유무 차이 (사용자 검토 반영)**: OM p.94 Latency 스펙 표는 LA12X OM p.86과 동일하게 표준/저지연 두 모드 모두 "independent from input Fs"(입력 샘플링 주파수와 무관) 문구를 직접 명시한다 — dsp 섹션 각주 [10]에서 설명한 상시 내장 SRC 하드웨어(OM p.16)가 이 불변성의 근거다. 즉 LA7.16의 레이턴시 값(3.84 ms 표준, 1.18 ms 저지연)은 입력 조건과 무관하게 항상 성립하는 무조건적 고정값이며, 이는 OM 원문이 직접 확정하는 서술이다. **d&b D80과의 비교**: D80은 Latency_Standard(0.3 ms)가 "SRC 비활성, 입력 48/96 kHz" 조건에서만 성립하고 SRC 활성화 시 최대 +1 ms까지 증가할 수 있다는 조건부 서술이 OM p.34에 있다(D80_v1.2.md latency 섹션 각주 [12a] 참조) — LA7.16처럼 "independent from input Fs"에 해당하는 확정 문구가 D80 소스에는 없다. D90은 "permanent SRC" 서술은 있으나 LA12X/LA7.16 수준의 명시적 불변성 확정 문구는 없다(D90_v1.1.md latency 섹션 각주 [9b] 참조). LA7.16의 저지연 모드 수치(1.18 ms)는 LA12X(0.84 ms)와 다르지만, 두 제품 모두 "independent from input Fs" 확정 문구를 공유하므로 근거 수준 자체는 동일하다.

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

**출처**: OM p.16 "Technical description > Signal processing and amplification > Analog", p.94 "Specifications > Input signal distribution" (최우선) / AE "Technical requirements > Analog input"

**측정 조건**: Input_Impedance/Max_Input_Level은 balanced 기준, THD 1% 기준(AE). Analog_Input_Channels는 LA12X(채널당 전용 XLR 4개)와 달리 16개 증폭 채널 전체가 공유하는 보조(AUX) 입력 1채널 구조이며, 메인/보조/폴백 입력원으로 자유롭게 매핑 가능(OM p.15). 채널 수치 자체는 정확하나 LA12X와 아키텍처가 근본적으로 다르므로 단순 채널 수 비교는 주의가 필요함을 명기한다.

**[7] ADC dynamic range 충돌**: OM(p.16)은 "encoding dynamic range of 117 dB (A-weighted, 20 kHz bandwidth)"로 명시. AE는 동일 항목을 "121 dB dynamic range, 20 Hz - 20 kHz, A-weighted"로 표기. 두 값 모두 보존 — ADC_Architecture의 Value에는 다이나믹 레인지 수치를 넣지 않고 컨버터 구성만 기재했으며, 상충하는 117 dB(OM)/121 dB(AE) 수치는 본 각주에만 병기한다. OM 최우선 원칙상 117 dB를 채택 근거로 우선 고려하되, 두 수치의 우열을 판단할 추가 근거가 없어 각주 형태로 병존시켰다.

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

**출처**: OM p.15 "Technical description > Signal processing and amplification > AES/EBU", p.94 "Specifications > Input signal distribution" (최우선) / AE "Technical requirements > Digital input, Sample Rate Converter"

**측정 조건**: Max_AES_Cable_Length는 단일 케이블, 48 kHz 샘플링, Belden 1696A 또는 Klotz OT234H 케이블 기준(LA12X와 동일 조건, 동일 값). Digital_Input_Gain_Range는 0.1 dB 스텝. Digital_Input_Channels(2)와 Digital_Standard는 LA12X(4채널, 2x AES3)와 달리 1x AES3(2채널)만 지원하며 아날로그 입력과 동일한 공유 단자를 사용한다 — LA12X의 각주 [6](S/PDIF 병기)에 해당하는 표기 차이는 LA7.16 소스에서는 발견되지 않았다.

---

## input_avb (AVB / Milan-AVB 입력)

| Key | Value | Unit |
|---|---|---|
| AVB_Certification | MILAN and Avnu certified (Bridge and Listener) | - |
| AVB_Channels | 16 | ch |
| AVB_Stream_Count | 16 (in normal or redundancy mode) | streams |
| AVB_Formats | AAF PCM32, IEC 61883-6 AM824 | - |
| AVB_Standards | IEEE 802.1BA-2011 / 1722-2016 / 1722.1-2013 | - |
| AVB_Bridge_Forwarded_Streams | up to 150 | streams |
| Redundancy_Type | Milan-AVB seamless, automatic switchover and recovery | - |
| Fallback_Modes | AVB to AES/EBU or analog (shared input), user-defined mapping | - |
| AES67_Support [신규][12] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Milan-AVB", p.94-95 "Specifications > Milan-AVB" (최우선) / SPS 2p "I/O" / AE "Technical requirements > AVB input"

**측정 조건**: AVB_Channels(16)는 최대 16개 스트림(각 최대 8채널, 총 최대 128채널)에서 사용자가 선택적으로 매핑하는 조건(OM p.94-95, SPS 2p). AVB_Formats는 AAF PCM32(최대 8채널, 48/96 kHz), IEC 61883-6 AM824(8채널, 48/96 kHz) 조건. Switchover 조건은 AVB loss of lock(OM p.95). Fallback_Modes는 LA12X처럼 이중 AES(AB)/XLR(CD) 구조가 아니라 단일 공유 AES/ANA 입력을 통한 폴백이며, 사용자 정의 매핑이 가능하다.

**D80과의 비교 참고**: D80(Phase 3-2)은 AVB/Milan 프로토콜을 사용하지 않으므로 input_avb 섹션 전체가 D80에서는 비적용(null)이다. D80의 "Fallback"은 이 Key와 동일 명칭이나 완전히 다른 계층(채널별 신호소스 이중화)의 개념이다.

**[신규][12] AES67_Support (v1.7, Phase 4 동기화)**: L-Acoustics "i" 설치전용 라인(LA1.16i, LA7.16i)에서 발견된 신규 속성 — Milan-AVB와 AES67을 사용자가 선택 가능한 이중 모드 제품군에서 도입된 Key. LA7.16(구형)의 기존 소스(OM v4.0, SPS 1.4, AE)에는 AES67 관련 서술이 전혀 확인되지 않는다. 원본 문서를 재조회하지 않은 보수적 처리 방식에 따라 null(미확인)로 유지 — LA7.16(구형)은 Milan-AVB 전용 제품으로 추정되나 확정 근거는 아니다. 흥미롭게도 신형 LA7.16i(LA7.16i_v1.0.md)는 동일 제품명 계열이지만 AES67을 명시적으로 지원한다(OM p.9) — 구형/신형 세대 간 실질적 기능 차이일 가능성이 있으나, 이는 LA7.16(구형) OM 재검토 없이는 확정할 수 없다.

---

## connectivity (커넥터)

| Key | Value | Unit |
|---|---|---|
| Input_Connectors | 1 x 12-point terminal block (AES/ANA IN + LINK, GPIO, 24 V DC backup), 2 x etherCON RJ45 (Milan-AVB I/O) | - |
| Terminal_Block_Pinout [신규] | 12핀: 24V DC IN, GND, GPIO1-3, GPIO GND, AES/ANA IN(+/-/Shield), AES/ANA LINK(+/-/Shield) — 상세 핀맵은 하단 표 참조 | - |
| XLR_Pin_Polarity | null | - |
| Speaker_Connectors | 1 x SC32 female connector (37-pin, 32 conductors) | - |
| SpeakON_Left_Pinout | null | - |
| SpeakON_Right_Pinout | null | - |
| CACOM_Pinout | null | - |
| SC32_Channel_Mapping [신규] | Out 1-16 via single SC32 connector | - |
| Speaker_Output_Accessories [신규] | SC32 cable (5/10/25/50 m), SC32-4DO adaptor (to 4x CA-COM), BOB32 breakout box (to 2x CA-COM + 8x NL4) | - |
| Network_Connectors | 2x etherCON RJ45, 1 Gb/s | - |
| Service_Port_Type [신규][13] | null | - |
| Speaker_Terminal_Block_SE_BTL_Wiring [신규][12] | null | - |
| PBTL_Activation_Method [신규][12] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Front and rear panels", p.23 "Installation > General Purpose I/O (GPIO)" (최우선) / SPS 2p "I/O", 4p "ACCESSORIES" / AE "Technical requirements > Connectors"

**측정 조건**: 없음(커넥터 규격 및 결선표). XLR_Pin_Polarity와 SpeakON/CACOM 관련 키는 LA7.16에 해당 커넥터 유형이 존재하지 않아 null 처리했다(비적용) — LA12X의 전용 XLR/speakON/CACOM 구조와 달리 LA7.16은 12-point terminal block(신호/GPIO/백업전원 통합)과 단일 SC32 커넥터(스피커 출력 16채널 통합)로 완전히 다른 커넥터 아키텍처를 사용한다. 극성 정보는 PDF 텍스트 레이어에 "+ / - / shield" 핀 명칭으로 이미 문자로 명시되어 있어(OM p.14, AE 커넥터 절) 별도 이미지 분석 없이 텍스트 추출만으로 확인했다(SKILL v1.5 PDF 분석 규칙 적용, 예외 이미지 분석 불요).

**[신규] SC32_Channel_Mapping, Speaker_Output_Accessories**: LA12X 스키마에는 없던 신규 속성. LA7.16의 16채널 출력이 개별 speakON/CACOM이 아닌 단일 SC32 커넥터로 통합되어 발생한 아키텍처 차이를 반영한다. Speaker_Output_Accessories는 SPS 4p "ACCESSORIES" 절에서만 확인되며 OM/AE에는 명시되지 않았다. 참고로 d&b D80(Phase 3-2)의 동일 Key에는 MC24 멀티코어/Touring rack 생태계가 매핑되어 있으며, LA7.16의 SC32 액세서리와는 완전히 다른 브랜드 고유 생태계이다.

**[신규] Terminal_Block_Pinout (v1.3 추가) — 12-point terminal block 상세 핀맵**:

사용자 확인 결과 LA7.16은 XLR 커넥터를 아날로그/AES 입력에 전혀 사용하지 않으며(입력 3의 "XLR 4개, A/B/C/D" 구성은 LA12X의 것과 혼동된 것으로 확인, 앞선 대화에서 정정됨), 대신 아래와 같은 단일 12핀 단자대(male terminal block) 하나로 아날로그 1채널과 AES/EBU 2채널(1개 스테레오 페어)을 겸용한다. 출처: OM p.14 "Front and rear panels"(핀 목록, 최우선), p.23/p.28/p.30 "Installation"(핀 배치 다이어그램 및 기능 설명), p.31 "Analog audio"(데이지체인 다이어그램).

| Pin 그룹 | Pin 이름 | 기능 |
|---|---|---|
| DSP 백업 전원 | 24V IN | DSP 백업 전원 입력(+), 24 V DC(±10%), 15 W minimum, 정전 시 네트워크/DSP 유지용(OM p.28) |
| DSP 백업 전원 | GND | 24V DC 백업 회로 그라운드 |
| GPIO | GPIO 1 | General Purpose I/O 1 |
| GPIO | GPIO 2 | General Purpose I/O 2 |
| GPIO | GPIO 3 | General Purpose I/O 3 |
| GPIO | GPIO GND | GPIO 회로 전용 그라운드(24V DC용 GND와 별도) |
| AES/ANA IN | + | 입력 신호 +(hot) — 모드에 따라 아날로그 오디오 또는 AES3 데이터 |
| AES/ANA IN | - | 입력 신호 -(cold) — 모드에 따라 아날로그 오디오 또는 AES3 데이터 |
| AES/ANA IN | Shield | 입력 실드/그라운드 |
| AES/ANA LINK | + | 데이지체인 출력 신호 +(다음 유닛으로 전달) |
| AES/ANA LINK | - | 데이지체인 출력 신호 -(다음 유닛으로 전달) |
| AES/ANA LINK | Shield | 출력 실드/그라운드 |

**아날로그/AES 겸용 방식**: AES/ANA IN과 AES/ANA LINK는 물리적으로 각각 3핀(+/-/Shield)뿐인 단일 회로이며, LA12X처럼 여러 XLR 쌍이 물리적으로 스위칭되는 구조가 아니다. 대신 LA Network Manager(또는 전면 패널 AUX input settings, OM p.55)에서 입력 모드를 "Analog" 또는 "AES/EBU" 중 하나로 소프트웨어 선택하면, 동일한 +/-/Shield 3핀이 그 모드에 맞는 신호를 실어 나른다(OM p.30 "Analog/Digital connectors"). Analog 모드에서는 AES/ANA IN이 아날로그 오디오 1채널(최대 22 dBu)을 받고, AES/EBU 모드에서는 동일 핀이 AES3 스테레오 페어(2채널)를 받는다. AES/ANA LINK는 daisy-chain 상 다음 유닛으로 동일 신호를 전달하는 버퍼드 출력이며(AES/EBU 모드에서는 failsafe relay 내장), IN과 동일하게 아날로그/AES 모드를 공유한다(OM p.30-31). 데이지체인 상의 모든 유닛은 동일한 입력 모드로 맞춰야 한다(OM p.31 "Risk of sound issues").

이 정보는 input_analog/input_digital 섹션의 `Analog_Link_Type`, `Digital_Link_Type` 값("shared 12-point terminal block")이 구체적으로 무엇을 의미하는지 보강 설명한다.

**[신규][13] Service_Port_Type (v1.7, Phase 4 동기화)**: "i" 설치전용 라인에서 발견된 IP 설정용 USB 서비스 포트(USB-C 또는 USB Micro-B) Key. LA7.16(구형)의 기존 소스에는 USB 서비스 포트 관련 서술이 확인되지 않아 null 처리한다.

**Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method는 각주[12] 참조**(amplification 섹션 Bridging_Support와 동일한 브릿지 모드 관련 신규 속성군).

---

## control_monitoring (제어 및 모니터링)

| Key | Value | Unit |
|---|---|---|
| Remote_Software | LA Network Manager (Windows/Mac) | - |
| Network_Topologies | daisy-chain, star, hybrid | - |
| Third_Party_Control [8] | Q-SYS, Crestron | - |
| Front_Panel | 1 TFT color touchscreen display (480 x 128 px), 1 encoding wheel with push button | - |
| Settings_Protection | null | - |
| GPIO_Count [신규] | 3 | ea |
| GPIO_Type [신규] | isolated optocoupler inputs, isolated relay contacts | - |
| DSP_Backup_Power_Input [신규][9] | 24 | V DC |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.18 "Technical description > Monitoring and control", p.23 "Installation > General Purpose I/O (GPIO)", p.95 "Specifications > Remote control and monitoring" (최우선) / SPS 4p "SOFTWARE AND NETWORK" / AE "Technical requirements > Third-party management solutions, Connectors"

**측정 조건**: L-NET 네트워크는 최대 253대 제어 가능, CAT5e U/FTP 이상 케이블 사용(LA12X와 동일). Settings_Protection(PIN 코드 등)은 세 소스 어디에도 LA7.16 관련 서술이 없어 null 처리했다(LA12X에는 존재하는 값이므로 임의로 이식하지 않음).

**[8] 서드파티 제어 목록 차이**: OM(p.19)과 AE는 "Q-SYS, Crestron"만 명시. SPS는 "Q-SYS® / Crestron® / HTTP API"로 HTTP API를 추가 병기. OM은 별도 서술(p.19)에서 "HTTP API is available on request after signing a memorandum of understanding"라고 조건부로 언급한다. 두 표기 모두 보존 — Value는 OM/AE 2개 소스 일치의 "Q-SYS, Crestron"을 채택하고, SPS의 HTTP API 병기 및 OM의 MOU 조건부 제공 서술을 본 각주에 기록한다.

**[신규] GPIO_Count, GPIO_Type**: LA12X 스키마에는 GPIO 관련 속성이 전혀 없었다(LA12X 소스 자체에 GPIO 기능 없음). OM p.23, AE "Connectors" 절에서 일치. 참고로 d&b D80(Phase 3-2)은 OM 전문 검색 결과 GPIO 용어 자체가 전혀 발견되지 않아 D80의 GPIO_Count는 0(확정적 비존재)으로 명시되었다 — LA7.16의 GPIO_Count=3(존재 확인)과 D80의 GPIO_Count=0(비존재 확인)은 둘 다 "확정값"이며 null(미확인)과는 구분된다.

**[신규][9] DSP_Backup_Power_Input 충돌**: OM(p.95)은 "1 x 24 V DC (± 10%) 15 W minimum"으로 명시. SPS(7p)는 동일 항목을 "24 V DC (±15%) / 0.8 A"로 표기 — 허용오차(±10% vs ±15%)와 정격 표시 단위(15 W vs 0.8 A, 24 V 기준 0.8 A는 약 19.2 W로 15 W와도 정확히 일치하지 않음)가 모두 상이하다. AE는 "Backup power circuit for the DSP: 24 V DC 2-point terminal block"으로 전압값만 명시. Value에는 세 소스 공통값인 "24 V DC"만 채택하고, 세부 허용오차/전류·전력 정격은 본 각주에서 OM/SPS 두 값을 모두 병기한다. LA12X 스키마에는 이 속성 자체가 없었다.

---

## operating_conditions (동작 환경)

| Key | Value | Unit |
|---|---|---|
| Operating_Temp_Range | -5 to 50 | degrees C |
| Cooling | fans with temperature-controlled speed, front to rear airflow | - |
| Fan_Count | 5 | ea |
| Fan_Noise_Min | 33 | dBA |
| Fan_Noise_Max | 62 | dBA |
| EMC_Class | non-residential (Class A) | - |
| Max_Operating_Altitude [신규] | 2000 | m |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.6 "Important safety instructions", p.92-93 "Specifications > Operating conditions" (최우선) / AE "Technical requirements > Operating conditions"

**측정 조건**: Operating_Temp_Range는 OM 안전 섹션(p.6: "-5°C/23°F to 50°C/122°F")과 스펙 섹션(p.93: 동일)이 정확히 일치하며 LA12X와 달리 충돌이 없다. Fan_Noise는 free field, 1 m 거리 기준(Min은 Idle 모드, Max는 최고속). Fan_Noise 수치는 OM 원문에 "less than" 등 수식어 없이 순수 수치로만 기재되어 있어("in Idle mode: 33 dBA", "at maximum speed: 62 dBA") LA12X 파일과 달리 "less than" 수식어를 붙이지 않았다(임의 수식어 첨가 금지 원칙 — 두 파일 간 표기 차이는 오기가 아니라 원문 차이를 그대로 반영한 것). Fan_Count(5)는 AE에서만 확인되며 OM 스펙 표에는 명시적 팬 개수가 없다(단일 소스 값, 충돌 아님).

**[신규] Max_Operating_Altitude**: LA12X 스키마에는 없던 신규 속성. OM p.93 스펙 표에만 명시("Maximum altitude 2000 m").

---

## physical (물리적 스펙)

| Key | Value | Unit |
|---|---|---|
| Width | 483 | mm |
| Height | 88 | mm |
| Depth | 510 | mm |
| Weight | 15.8 | kg |
| Protection_Rating | IP2X | - |
| Finish | black | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS 7p "Physical data", AE "Physical data" / OM p.96 "Specifications > LA7.16 dimensions" (치수 도면, 보조)

**측정 조건**: W x H x D = 483 x 88 x 510 mm은 SPS와 AE가 정확히 일치하며, OM p.96/p.22 치수 도면에도 동일한 510 mm 수치가 나타난다. 단, OM의 치수 도면은 벡터 그래픽 라벨 형태로 되어 있어 텍스트 추출 시 24.4 mm, 465 mm, 407 mm, 433 mm 등 추가 수치가 함께 검출되었으나 각 수치가 정확히 어느 기준점(핸들 포함/미포함, 레일 위치 등)을 가리키는지 도면 상에서 명확히 대응시킬 수 없어 임의 추론 금지 원칙에 따라 Value에는 반영하지 않았다. 리어 브래킷 포함 시 최대 깊이는 534.3 mm로 별도 명시되어 있다(OM p.22, LA12X의 534.3 mm와 동일 수치). Protection_Rating은 OM/AE 모두 "IP2X"로 일치하며 LA12X의 "IP20"과는 다른 값이다(제품 간 실제 차이로 판단, 충돌 아님).

---

## protection_summary (보호 회로)

| Key | Value |
|---|---|
| Protection_Mains_PSU | over and under voltage, over temperature, L-SMART, overcurrent (fuse protection, inrush current protection), power budget limiter |
| Protection_Outputs | over current, DC, short circuit, over temperature |
| Protection_Transducer | L-DRIVE: excursion, temperature, over-voltage |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.93 "Specifications > Protection" (최우선) / SPS 7p "Circuits protection"

**측정 조건**: 없음(보호 기능 목록). AE 문서에는 본 항목에 대응하는 별도 "Protection" 소단락이 발견되지 않아 OM/SPS만을 출처로 사용했다. Protection_Mains_PSU에 L-SMART가 포함된 것은 OM 원문 목록(p.93)의 표기를 그대로 따른 것이며, 개념상 전력 관리 기술이지만 원문 분류를 임의로 재배치하지 않았다(임의 추론 금지 원칙).

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

**[신규] 섹션 전체**: D80(d&b audiotechnik) 파싱 중 발견된 12개 신규 속성. LA7.16의 기존 소스(OM v4.0, SPS 1.4, AE) 어디에도 이들 항목에 대응하는 스펙이 확인되지 않는다. LA7.16 고유의 L-SMART/Array morphing 등은 이미 dsp 섹션(Amplifier_Power_Management, Per_Channel_DSP_Tools)에 반영되어 있어 이 섹션과는 중복되지 않는다. 각 항목의 성격은 D80_v1.0.md 원 각주를 참조.

---

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

**[신규] 섹션 전체**: D90(d&b audiotechnik) 파싱 중 발견된 9개 신규 속성. LA7.16의 기존 소스(OM v4.0, SPS 1.4, AE) 어디에도 이들 항목(Milan 프로토콜 상세, Time to tone, Energy saving 상세, AmpPresets 상세, Output noise 상세)에 대응하는 스펙이 확인되지 않는다. LA7.16의 AmpPresets 유사 개념인 Preset_Memory_User(10)와 D90의 AmpPresets_Detail(User 9 + Alarm 3 + Backup 3)은 슬롯 구조와 개념이 상이하여 서로 다른 Key로 유지한다(D90_v1.0.md 각주 [27] 참조).

## Null Report

이번 소스 집합에서 정의되지 않아 null 처리된 항목: Rated_Power_Per_Ch_2.7_Ohms(비적용, 양방향 동기화), Total_Power_Capability(v1.1 정정, 근거 부족), THD_N_4ohm, Preset_Memory_Factory, XLR_Pin_Polarity, SpeakON_Left_Pinout, SpeakON_Right_Pinout, CACOM_Pinout, Settings_Protection (Phase 3-1까지, 총 9건), CMRR_Analog_Input, Digital_Input_Impedance, SN_Ratio_Analog_Input, SN_Ratio_Digital_Input, System_Start_Up_Time, Storage_Temp_Range, Storage_Humidity, LoadMatch_Max_Cable_Length, Signal_Path_Management, Load_Monitoring_System_Check, Output_Mode_Selectable, Mains_Current_Limiter_Range (Phase 3-2(D80), 총 12건), Milan_Device_Type, Milan_Input_Channel_Streams, Milan_Redundancy, Milan_Routable_Inputs, Network_IP_Default, Time_To_Tone, Energy_Saving_Detail, AmpPresets_Detail, Output_Noise_Dynamic_Range_Detail (Phase 3-1(D90), 총 9건), Bridging_Support, Rated/Peak_Power_Per_Ch_BTL_8/16_Ohms(4), Rated/Peak_Power_Per_Ch_PBTL_4/8/16_Ohms(6), AES67_Support, Service_Port_Type, Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method (Phase 4(Upload 4개 제품), 총 15건). 전체 45건.

## 버전 변경 이력

v1.0: Phase 3-1 신규 제품 파싱. OM(107p, 텍스트 레이어 전량 추출), SPS(7p), AE(docx), 웹 3계층(리스트뷰/오버뷰/Full Spec) 총 6개 소스를 교차 검증하여 마스터 스키마 최초 구축. LA12X 대비 12개 신규 속성을 발견하여 LA12X_v5.0.md에 null로 소급 반영함. 소스 간 데이터 충돌 7건 발견 및 전부 각주로 보존.

v1.0 to v1.1: (사용자 검토 반영) (1) SKILL v1.7의 양방향 스키마 동기화 규칙에 따라 LA12X 전용 Key였던 `Rated_Power_Per_Ch_2.7_Ohms`를 `null`로 추가하여 두 파일의 Key 목록을 100% 일치시킴. (2) `Total_Power_Capability` 오기재 정정 — v1.0에서 대입했던 "2800 W"는 실제로는 SMPS 메인즈 입력 전력 정격이며 LA12X의 동일 Key가 의미하는 "총 출력 용량"과 성격이 다른 값임을 확인, 해당 수치는 신규 Key `PSU_Mains_Rated_Power`(power_supply 섹션)로 이관하고 `Total_Power_Capability`는 근거 부족으로 `null` 처리함. L-SMART의 "7000 W for longer hold times" 마케팅 서술은 지속시간 미정의로 정식 Key화하지 않음(각주로만 기록).

v1.1 to v1.2: (파일명 참조 갱신) LA12X 파트너 파일이 SKILL v1.8 시맨틱 버저닝 규칙의 소급 재분류(v5.1 -> v2.4)로 파일명이 변경됨에 따라, 본 파일 내 3건의 상호 참조 텍스트만 갱신했다. Key, Value, 각주 등 실질 데이터는 v1.1과 완전히 동일하다.

v1.2 to v1.3: (사용자 요청 반영) 12-point terminal block(AES/ANA IN + LINK)의 상세 핀맵을 connectivity 섹션에 신규 Key(`Terminal_Block_Pinout`)와 보조 표로 추가하여, 아날로그와 AES/EBU가 동일한 12핀 단자대의 IN/LINK 회로를 소프트웨어 모드 선택으로 겸용한다는 사실을 명확히 했다(OM p.14/p.23/p.28/p.30/p.31 근거). 이 과정에서 사용자가 언급한 "4x XLR, A/B/C/D" 구조는 LA7.16이 아니라 LA12X의 실제 구조임을 상호 확인했다(LA7.16 OM/SPS/AE 3개 소스 어디에도 XLR이 물리 커넥터로 등장하지 않음). 기존 Key/Value/각주는 일절 변경하지 않았다(Minor 업데이트).

v1.3 to v1.4: (Phase 3-2 양방향 동기화) d&b D80 파싱 중 발견된 신규 섹션 `d80_specific`(12개 Key)을 전량 `null`로 신설 추가. 기존 9개 섹션의 Key/Value/각주는 일절 변경하지 않았다.

v1.4 to v1.5: (Phase 3-1 양방향 동기화) d&b D90 파싱 중 발견된 신규 섹션 `d90_specific`(9개 Key)을 전량 `null`로 신설 추가. 기존 값/각주는 일절 변경하지 않았다.

v1.5 to v1.6: (사용자 검토 반영, D80 라운드에서 발견된 이슈의 전 제품 확장 적용) D80에서 DSP_Sampling_Rate/Latency_Standard 값의 성립 조건 근거 부족이 지적되어, LA7.16도 재검토했다. OM p.16 "Signal processing and amplification > AES/EBU" 절에서 LA12X와 동일한 상시 내장 SRC 서술("provides constant propagation delay regardless of the input sampling frequency")을 확인했고, OM p.94 Latency 스펙 표에는 표준/저지연 모드 모두 "independent from input Fs" 확정 문구가 직접 명시되어 있음을 재확인했다. 이에 따라 dsp 섹션 DSP_Sampling_Rate에 각주 [10], latency 섹션 Latency_Standard/Low_Mode에 각주 [11]을 신설하여, LA7.16은 SRC가 상시 하드웨어로 내장되어 있어 D80(SRC 조건부 활성화 구조)과 달리 이 값들이 입력 조건과 무관하게 항상 성립하는 무조건적 고정값임을 OM 원문이 직접 확정하고 있다는 점, LA12X와 근거 수준이 동일하다는 점을 양방향 동기화 관점에서 명기했다. Value 자체(96, 3.84, 1.18)는 변경하지 않고 근거 문구만 병기했다.

v1.6 to v1.7: (Phase 4 양방향 동기화) Upload 폴더 4개 신규 제품(LA1.16i, LA2Xi, LA4X, LA7.16i) 파싱 중 발견된 신규 15개 Key(amplification 10개: Bridging_Support + BTL 전력 4개 + PBTL 전력 6개, input_avb 1개: AES67_Support, connectivity 3개: Service_Port_Type, Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method)를 각 해당 섹션에 `null`로 신설 추가. LA7.16(구형) 기존 소스에는 브릿지 모드/AES67/USB 서비스 포트 관련 서술이 없어 "확정된 비존재"가 아닌 "미확인(null)"으로 보수적 처리(원본 문서 재조회 없이 기존 파싱 결과 텍스트 기반 사용자 승인 진행). 기존 9개 섹션 및 d80_specific/d90_specific의 Key/Value/각주는 일절 변경하지 않았다.

**파일 무결성 참고**: 본 버전 변경 이력의 v1.0~v1.4 항목은 세션 중 발생한 파일 저장 동기화 지연으로 인해 이전 버전(v1.5 이하)의 파일 말미가 반복적으로 문장 중간에서 잘려 저장되는 문제가 있었다. 이번 v1.6 작성 시 Archive의 LA7.16_v1.4.md 원문을 대조하여 위 이력을 복원했으며, 표 데이터(Key/Value/Unit)와 섹션 각주 등 스펙 데이터 자체는 영향받지 않았다.
