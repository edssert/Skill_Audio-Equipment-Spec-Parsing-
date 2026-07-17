# LA7.16 - Master Spec Schema

Schema_Version: 2.4 (무결성 감사 후속 조치 — 기존에 원본 재조회 없이 null 처리되었던 브릿징/AES67/서비스포트 등 26개 Key를 LA7.16 자체 원본(OM v4.0/SPS 1.4/AE)에서 실제 재검색하여 갱신)
최종 작업 일시: 2026-07-18 (토요일)
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

**구조 개편 안내(v2.0)**: d&b 제품군이 D80/D90에 D25가 추가되며 3개로 늘어남에 따라, 사용자 요청으로 "d80_specific"/"d90_specific"처럼 특정 모델명을 딴 그랩백(grab-bag) 섹션을 전부 폐지하고 그 안의 Key들을 주제(스펙 영역) 기준 기존 섹션으로 재분배하는 구조 개편이 D80/D90 두 파일에 먼저 적용되었다(D80_v2.0.md, D90_v2.0.md 참조). 본 파일도 동일한 양방향 동기화 규칙에 따라 동일한 재배치를 적용한다. **d80_specific(12개 Key)**: CMRR_Analog_Input -> input_analog, Digital_Input_Impedance -> input_digital, SN_Ratio_Analog_Input/SN_Ratio_Digital_Input -> audio_performance, System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check -> dsp, Storage_Temp_Range/Storage_Humidity -> operating_conditions, Signal_Path_Management -> control_monitoring, Output_Mode_Selectable -> connectivity, Mains_Current_Limiter_Range -> power_supply. **d90_specific(9개 Key)**: Milan_Device_Type은 input_avb의 명명 규칙에 맞춰 AVB_Device_Type으로 개명 후 재배치, Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs는 input_avb의 기존 AVB_Channels/AVB_Stream_Count/Redundancy_Type과 중복되어 흡수(신규 Key 생성 없음), Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail -> dsp, Output_Noise_Dynamic_Range_Detail -> audio_performance, Network_IP_Default -> 신설된 **network** 섹션(D80_v2.0.md/D90_v2.0.md에도 동일 섹션 존재). 아울러 BTL/PBTL 전력 Key 10개(부하 임피던스별 세분화)를 4개(Rated/Peak_Power_Per_Ch_BTL, Rated/Peak_Power_Per_Ch_PBTL)로 통합했다. LA7.16(구형)은 d&b 브랜드 고유 개념 및 브릿지 모드에 대응하는 스펙이 확인되지 않으므로, 이번 재편으로 이동/통합된 모든 Key는 계속 `null`을 유지한다 — 실질 데이터(Value)는 단 하나도 변경되지 않으며 위치와 Key 이름, 개수(BTL/PBTL만 해당)만 바뀐다. Key 이름/Value/Unit과 각주 내용 자체는 변경하지 않고 위치만 이동했으며(BTL/PBTL과 Milan 통합 부분만 예외), 각주 번호는 이동 대상 섹션 내에서 기존 번호와 충돌하지 않도록 재부여했다. 섹션 계층 구조 자체가 바뀌는 변경이므로 SKILL v1.11 버저닝 규칙에 따라 Major 버전(v2.0)으로 상향했다.

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
| Rated_Power_Per_Ch_16_Ohms | 580 | W |
| Peak_Power_Per_Ch_4_Ohms | 1100 | W |
| Peak_Power_Per_Ch_8_Ohms | 1300 | W |
| Peak_Power_Per_Ch_16_Ohms | 700 | W |
| Total_Power_Capability [2] | null | W |
| Max_Output_Voltage_Peak | 152 | V |
| Max_Output_Current_Peak | null | A |
| Amplification_Gain | 32 | dB |
| Output_Delay_Range | 0 - 1000 | ms |
| Bridging_Support [12] | No | - |
| Rated_Power_Per_Ch_BTL [12a] | N/A | W |
| Peak_Power_Per_Ch_BTL [12a] | N/A | W |
| Rated_Power_Per_Ch_PBTL [12a] | N/A | W |
| Peak_Power_Per_Ch_PBTL [12a] | N/A | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.92 "Specifications > General", p.18 "Technical description > Power supply and amplifier section" (최우선) / SPS 7p "Amplification and power supply" / AE "Technical requirements > Amplification" / WEB-L, WEB-O, WEB-F 스펙 표

**측정 조건**: `Peak_Power_Per_Ch_*`는 12 dB Crest Factor, 2 ms, 1 kHz, all channels driven, sine burst 조건(OM/SPS/AE 일치). `Rated_Power_Per_Ch_*`는 CEA-2006/490A, 20 ms, THD ≤ 1%, 1 kHz, all channels driven, sine burst 조건(OM/SPS/AE 일치) — LA12X와 동일한 CEA 표준을 사용하므로 두 파일의 `Rated_Power_Per_Ch_*` 키는 동일 측정 기준으로 비교 가능하다.

**[1] Rated_Power_Per_Ch_2.7_Ohms (양방향 동기화, v1.1 신규 추가)**: LA12X 파일에만 존재하던 기존 Key. v1.0에서는 "LA7.16에 해당 조건이 없으므로 키 자체를 생략"하는 방식으로 처리했으나, SKILL v1.7의 양방향 스키마 동기화 규칙에 따라 v1.1에서 Key를 추가하고 값은 `null`로 처리했다. LA7.16의 OM/SPS/AE 어느 소스도 2.7 Ω 부하 조건의 출력을 측정/명시하지 않는다 — LA7.16은 4/8/16 Ω 세 부하 조건만 스펙 표에 존재하며, 2.7 Ω은 LA12X 계열(4채널, 낮은 부하 임피던스 지원)에 특화된 조건으로 판단된다. 즉 이 null은 "미확인"이 아니라 "제품 아키텍처상 해당 조건 자체가 없음(비적용)"을 의미한다.

**[2] Total_Power_Capability 정정 (v1.0 -> v1.1)**: v1.0에서는 이 Key에 OM/SPS/AE의 "Mains rating ... 2800 W" 수치를 대입했으나, 이는 오기재였다. 재검증 결과 "2800 W"는 SMPS가 AC 메인즈로부터 끌어오는 **입력 전력 정격**(mains input power rating)이며, LA12X의 `Total_Power_Capability`(12000 W)가 나타내는 개념 — 앰프가 전 채널에 걸쳐 동시에 공급 가능한 **총 출력 용량**(combined output capacity) — 과는 성격이 다른 값이다. LA7.16의 OM(107p 전량), SPS(7p), AE 어디에도 "총 출력 용량"에 해당하는 단일 수치가 명시적으로 기재되어 있지 않으며(채널 수 × 채널당 정격의 임의 곱셈은 무결성 원칙상 금지), 따라서 SKILL v1.7의 "총량/정격 Key 오염 금지" 조항에 따라 본 Key는 `null`로 정정한다. 정정 전 값이었던 "2800 W"는 성격에 맞는 별도 Key(`PSU_Mains_Rated_Power`)로 이관하여 power_supply 섹션에 기록했다(아래 참조).

**L-SMART 관련 팩트 체크**: SPS(1p, 2p)는 "The PSU can provide extremely high short-term peak power and 7000 W for longer hold times"라고 서술한다. 이는 L-SMART 동적 전력 배분 기술(예측 모델링 기반으로 PSU와 개별 채널의 전력을 실시간 재분배)에 의해 순간적으로 도달 가능한 PSU 총 출력이 2800 W(연속 정격)를 크게 상회할 수 있음을 의미하는 정성적 서술이다. 다만 "longer hold times"의 정확한 지속 시간, 측정 조건(부하 임피던스, 채널 수, 신호 종류)이 소스 어디에도 명시되어 있지 않아, 이 "7000 W"를 `Total_Power_Capability`나 별도의 정식 Key 값으로 채택하지 않는다(임의 추론/수식어 첨가 금지 원칙). 참고로 d&b D80(Phase 3-2)의 `PSU_Mains_Rated_Power`도 공교롭게 동일한 "7000 W" 수치이나(단 D80은 "short term RMS" 조건의 메인즈 입력 전력이며 LA7.16 SPS의 "7000 W for longer hold times"와는 완전히 다른 소스/제품/개념의 값이다), 우연의 일치로 판단되며 두 수치를 서로 연관짓지 않는다. 요약하면, LA7.16의 "총 출력 용량"에 대응하는 명확한 단일 스펙 수치는 현재 확보한 6개 소스 중 어디에도 존재하지 않는다 — 있는 것은 (a) 채널당 개별 정격(Peak/Rated_Power_Per_Ch_*), (b) PSU 연속 입력 전력 정격(2800 W, PSU_Mains_Rated_Power), (c) L-SMART에 의한 정의되지 않은 단기 피크(7000 W, 정성적 서술) 세 가지뿐이다.

**Rated/Peak_Power_Per_Ch_16_Ohms, Peak_Power_Per_Ch_4/8_Ohms**: LA12X 스키마에는 존재하지 않던 신규 속성. LA12X는 Peak(12 dB CF) 조건의 채널당 출력을 별도 명시하지 않고 CEA 조건 값만 제공했으나, LA7.16은 OM/SPS/AE 모두 Peak와 CEA(RMS) 두 조건의 수치를 별도로 명시하여 두 계열의 Key를 분리했다. 16 Ω 부하 조건 자체도 LA12X 소스에는 없던 신규 조건이다.

**[12] Bridging_Support 재검증 (v2.4, 원본 재조회 완료)**: v1.7~v2.3까지는 LA7.16(구형) 자체 원본을 재조회하지 않고 "기존 파싱 결과물 텍스트만을 근거로" 미확인(null)로 보수적 처리했던 항목이다. 이번에 LA7.16 자체 소스(OM v4.0 전문, SPS 1.4, AE)를 실제로 재검색했다. OM/AE 전문 검색 결과 "bridge"라는 단어는 전부 AVB 네트워크 브리지(Ethernet 스위치/AVB 장비를 가리키는 네트워크 용어, 예: "AVB bridges", "Milan-AVB Bridge and Listener")로만 등장하며, 앰프 출력을 묶어 구동하는 의미의 브릿지/BTL/PBTL 서술은 OM/AE 어디에도 없다. 결정적 근거는 SPS(1.4, 251125) 2p "AMPLIFIED CONTROLLERS – THE RANGE" 비교표다 — LA1.16i/LA2Xi/LA4X/LA7.16(i)/LA12X 5개 앰프 기종을 나란히 비교하는 표에서, Peak power 조건의 세 번째(최저 임피던스) 행에 LA1.16i 칸만 "8* x 300 W (at 8 ohms)"로 표기되고 표 하단에 "* Any odd/even pair of outputs can be bridged (BTL)"라는 각주가 붙어 있다. 반면 같은 행의 LA7.16(i) 칸은 "16 x 1100 W (at 4 ohms)"로 채널 수가 그대로 16이고 별표 표기가 전혀 없다 — 즉 L-Acoustics 자신의 공식 비교표에서 브릿지 지원은 LA1.16i에만 명시적으로 표기되어 있고 LA7.16(i)에는 표기가 없다. 이는 "언급이 전혀 없음"을 넘어 동일 문서·동일 표 안에서 다른 제품에는 명시된 기능이 LA7.16 칸에는 빠져 있는 적극적 반증(affirmative disconfirmation)에 해당하므로, SKILL v1.9 "확정된 비존재(0)와 미확인(null)의 구분" 원칙에 따라 `No`(확정적 비존재)로 처리한다. 이에 따라 SE/BTL 관련 하위 Key(Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method)도 개념 자체가 성립하지 않아 `N/A`로 처리한다(connectivity 섹션 각주 참조).

**[12a][구조 개편 v2.0, v2.4 재검증] BTL/PBTL 전력 Key 통폐합 및 값 확정**: v1.7까지는 부하 임피던스(8/16 Ohm, PBTL은 4/8/16 Ohm)별로 Rated/Peak를 전부 분리한 10개 Key(Rated/Peak_Power_Per_Ch_BTL_8/16_Ohms, Rated/Peak_Power_Per_Ch_PBTL_4/8/16_Ohms)였다. 브릿지 모드를 지원하지 않거나 미확인인 제품(D80/D90/LA12X/LA7.16/LA4X/LA7.16i 등)에서 이 10개 Key가 전부 null로 나열되어 가독성이 크게 떨어진다는 사용자 피드백에 따라, 4개 Key(Rated_Power_Per_Ch_BTL, Peak_Power_Per_Ch_BTL, Rated_Power_Per_Ch_PBTL, Peak_Power_Per_Ch_PBTL)로 통합했다(D80_v2.0.md/D90_v2.0.md와 동일 처리). 실값이 있는 제품(LA1.16i, LA2Xi)은 임피던스 조건을 Value 셀 안에 "값1 @ n Ohms / 값2 @ m Ohms" 형식으로 병기한다(Rated_Power_Per_Ch_4_Ohms 등 이 스키마의 기존 슬래시 병기 관례와 동일한 방식). LA7.16(구형)은 v2.4 재검증 결과 위 [12]에서 Bridging_Support 자체가 `No`(확정적 비존재)로 확정됨에 따라, BTL/PBTL 전력 Key 4개도 "미확인(null)"이 아니라 "비적용(N/A)"으로 변경한다 — 브릿지 모드가 없으므로 브릿지 조건의 전력 정격이라는 개념 자체가 LA7.16에는 성립하지 않는다.

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
| PSU_Mains_Rated_Power | 2800 | W |
| Mains_Current_Limiter_Range [3a] | null | % of rated current |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.93 "Specifications > Power supply", p.24 "Installation > Electrical specifications" (최우선) / SPS 7p "Amplification and power supply" / AE "Technical requirements > Connectors, Mains rating"

**측정 조건**: Power_Consumption_Idle/Standby는 230/120/100 V 공통 W 값(전압별 전류는 상이하나 W 기준 동일 — OM p.93 표: Idle 1.0 A/144 W(230 V), 1.3 A/144 W(120 V), 1.5 A/144 W(100 V); Standby 0.8 A/19 W(230 V), 0.5 A/19 W(120 V, 100 V)). Power_Factor는 full load 기준(OM/SPS 일치). PSU_Type Value는 소스에 명시된 "Power Factor Correction (PFC)"만 반영했으며, LA12X 파일의 "DSP-controlled PFC" 수식어는 LA7.16 소스 어디에도 없어 임의로 이식하지 않았다(무결성 원칙).

**[3] 적용 전압 대역 표기 차이**: OM 안전/설치 섹션(p.24)은 "220-240 V: 16 A"로 서술하나, OM 스펙 섹션(p.93)과 SPS는 동일 항목을 "200-240 V: 16 A"로 표기. AE도 "200-240 V AC: 16 A"로 스펙 섹션과 일치. 두 표기 모두 보존 — 스펙 섹션/SPS/AE 3개 소스 일치를 근거로 200-240 V 표기를 채택값 기준으로 삼되, 안전 섹션의 220-240 V 표기도 삭제하지 않음. LA12X 파일의 동일 유형 충돌([2])과 동일한 패턴이다.

**PSU_Mains_Rated_Power**: v1.1에서 신설된 Key. OM p.93 "Mains rating 100 V AC - 240 V AC ± 10%, 50 Hz - 60 Hz, 2800 W"에 명시된 SMPS 연속 입력 전력 정격이다(v1.0에서는 이 수치가 amplification 섹션의 Total_Power_Capability에 잘못 대입되어 있었음 — 위 [2] 참조). SPS/AE는 전압/주파수 정격만 재기술하며 2800 W 수치는 OM에만 명시되어 있다(단일 소스, 충돌 아님). LA12X 스키마에는 이에 대응하는 Key가 없어 LA12X_v2.4.md(구 LA12X_v5.1.md)에 null로 신규 반영했다.

**[3a][구조 개편 v2.0, v2.4 재검증] Mains_Current_Limiter_Range**: v1.x까지 "d80_specific" 섹션에 있던 Key를 power_supply로 재배치했다. v2.4에서 LA7.16 자체 원본(OM v4.0 전문, SPS 1.4, AE)을 "current limit", "inrush", "limiter" 키워드로 재검색했다. OM/SPS/AE 모두 보호 회로 목록에 "overcurrent (fuse protection, inrush current protection)"와 "power budget limiter"를 언급하지만(OM p.93 Protection 표, SPS 7p, AE Technical requirements), 이는 자동 보호 기능의 명칭일 뿐 사용자가 조정 가능한 "정격 전류 대비 제한 비율(% of rated current)" 형태의 수치화된 설정 범위가 아니다 — 즉 이 Key가 요구하는 "제한 범위" 개념에 대응하는 수치는 세 소스 어디에도 없다. 원본을 실제로 재검색했음에도 언급 자체가 없어 "미확인(null)"으로 유지하되(무결성 원칙상 자동보호 기능 명칭을 이 Key에 억지로 대입하지 않음), 종전과 달리 이번에는 원본 재조회에 근거한 미확인임을 명시한다.

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
| SN_Ratio_Analog_Input [5a] | null | dBr |
| SN_Ratio_Digital_Input [5a] | null | dBr |
| Output_Noise_Dynamic_Range_Detail [5b] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.92 "Specifications > General" (최우선) / SPS 7p "Audio specifications" / AE "Technical requirements > Amplification"

**측정 조건**: Frequency_Response는 ±0.05 dB 허용오차(OM/AE 일치). THD_N_8ohm은 20 Hz-20 kHz 대역, 8 Ω 부하, 60 W 출력 기준. Output_Dynamic_Range와 Noise_Level은 20 Hz-20 kHz, 8 Ω, A-weighted, digital input 기준. Channel_Separation은 1 kHz, 8 Ω, 60 W 기준. Damping_Factor는 20 Hz-1 kHz, 8 Ω 부하 기준(OM에만 명시, 타 소스 언급 없음). THD_N_4ohm은 세 소스 모두 4 Ω 조건의 THD 수치를 별도로 제공하지 않아 null 처리했다(LA12X는 해당 값이 존재하여 4 Ω 조건 THD 키 자체는 유지).

**[4] THD_N_8ohm 충돌**: OM(p.92)과 SPS(7p)는 "< 0.1%"로 일치. AE는 동일 항목을 "< 0.05%"로 표기. 두 값 모두 보존 — 채택값 0.1%는 OM+SPS 2개 소스 일치 및 L-Acoustics OM 최우선 원칙을 근거로 함. AE의 0.05%는 더 엄격한 수치로, 오기 또는 구버전 수치 가능성이 있으나 원문 값은 삭제하지 않음.

**[5] Noise_Level 충돌**: OM(p.92)과 SPS(7p, 6p 비교표)는 "< -79 dBV"로 일치. AE는 동일 항목을 "< -78 dBV"로 표기. 두 값 모두 보존 — 채택값 -79 dBV는 OM+SPS 2개 소스 일치를 근거로 함.

**[5a][구조 개편 v2.0, v2.4 재검증] SN_Ratio_Analog_Input/SN_Ratio_Digital_Input**: v1.x까지 "d80_specific" 섹션에 있던 Key를 audio_performance로 재배치했다. v2.4에서 LA7.16 자체 원본(OM v4.0 전문, SPS 1.4, AE)을 "signal to noise", "SNR", "S/N ratio" 키워드로 재검색했으나 세 소스 어디에도 일치하는 서술이 없다. LA7.16의 오디오 성능 스펙은 이미 위 Noise_Level(< -79 dBV, digital input 기준)과 Output_Dynamic_Range(> 119 dB, digital input 기준)라는 별도 명명 체계로만 제공되며, D80류의 상대적 dBr 단위 S/N ratio 항목 자체가 존재하지 않는다. 원본을 실제로 재검색했음에도 발견되지 않아 미확인(null)으로 유지한다.

**[5b][구조 개편 v2.0, v2.4 재검증] Output_Noise_Dynamic_Range_Detail**: v1.x까지 "d90_specific" 섹션에 있던 Key를 audio_performance로 재배치했다. v2.4에서 LA7.16 자체 원본을 재검색했으나 D90류의 "입력 유형(analog/digital) x 가중치(unweighted/A-weighted) 조합별 절대 노이즈 전압(uV RMS)" 세분화 데이터는 발견되지 않았다. OM p.93 스펙 표는 Output_Dynamic_Range/Noise_Level 두 항목 모두 "(Digital input)"이라는 단일 조건 라벨의 dB/dBV 값만 제공하며, 아날로그 입력 기준 별도 수치나 uV RMS 단위의 절대 노이즈 전압은 OM/SPS/AE 어디에도 명시되어 있지 않다. 이 Key가 요구하는 세분화된 데이터 구조 자체가 LA7.16 소스에 없어 원본 재조회 후에도 미확인(null)으로 유지한다.

---

## dsp (신호 처리)

| Key | Value | Unit |
|---|---|---|
| DSP_Processor | Gen. 5 Dual SHARC 32-bit, floating point | - |
| DSP_Sampling_Rate [10] | 96 (internal, fixed, independent from input Fs) | kHz |
| Routing_Matrix | 16x16 routing and summation matrix | - |
| EQ_Filters_Per_Output [6] | 8 IIR + 4 FIR linear phase | - |
| Per_Channel_DSP_Tools | Array morphing (LF contour, zoom factor), Air absorption compensation filters | - |
| Amplifier_Power_Management | L-SMART adaptive power management | - |
| Speaker_Protection | L-DRIVE (excursion, temperature, over-voltage) | - |
| Preset_Memory_User | 10 | slots |
| Preset_Memory_Factory | null | slots |
| System_Start_Up_Time [10a] | null | sec |
| LoadMatch_Max_Cable_Length [10a] | N/A | m |
| Load_Monitoring_System_Check [10a] | Enclosure check: measures loudspeaker impedance at reference frequencies for the connected loudspeaker family, compares to expected range for fast fault/continuity detection (status: IDLE/OK/NOK/NC/UNDF) | - |
| Time_To_Tone [10b] | null | sec |
| Energy_Saving_Detail [10b] | null | - |
| AmpPresets_Detail [10b] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.17 "Technical description > DSP architecture", p.94 "Specifications > Input signal distribution" (최우선) / SPS 3p "DSP", 7p "DSP" / AE "Technical requirements > DSP"

**측정 조건**: 없음(사양값). Preset_Memory_User는 OM p.50("one of the ten slots")과 AE("10 user memories") 일치로 10 확정. Preset_Memory_Factory는 OM p.44 부근에 공장 프리셋 슬롯 범위를 나타내는 표가 있으나("memory space number: from 001 to 010 for user layouts, from 001 to [숫자 판독 불가] for factory layouts") PDF 텍스트 추출 과정에서 표 셀 숫자가 누락되어 신뢰 가능한 상한값을 확인하지 못했다 — 임의 추론 금지 원칙에 따라 null로 처리했다(LA12X의 189와 동일하다고 가정하지 않음).

**[6] EQ_Filters_Per_Output 표기 차이**: OM(p.94)과 AE는 "8 IIR, 4 FIR linear phase EQ filters"만 명시. SPS(7p)는 동일 항목 뒤에 "Autofilter full-range"를 추가로 병기("8 IIR, 4 FIR EQ filters, Autofilter full-range"). 두 표기 모두 기록 — OM 최우선 원칙에 따라 SPS 단독 추가 문구는 Value에 병합하지 않고 본 각주에 병기함. SPS 서술(3p)에 따르면 Autofilter는 어레이 전 대역 주파수 응답을 채널 단위로 선형화하는 별도 명명된 도구이다.

**Per_Channel_DSP_Tools**: LA12X 스키마에는 없던 신규 속성. OM p.94 스펙 표의 "Per output channel" 항목을 원문 그대로 채택(Array morphing / Air absorption compensation filters). AE도 "contour filters, and filters to compensate for air absorption"으로 개념상 일치.

**Amplifier_Power_Management**: LA12X 스키마에는 없던 신규 속성. L-SMART는 SPS(1p, 2p)에 따르면 LA7.16(i)에서 처음 도입된 기술로, OM/SPS/AE 세 소스 모두 "L-SMART"라는 동일 명칭으로 확인됨. 참고로 d&b D80(Phase 3-2)의 이 Key에는 "Mains Current Limitation (MCL)"이 매핑되어 있으나, MCL은 메인즈 전류 상한 제한 기능이고 L-SMART는 채널 간 동적 전력 재분배 기능으로 작동 원리가 다르다(D80_v1.0.md 각주 참조) — 두 값의 성격 차이를 인지하되 각 파일의 원문 표현은 그대로 유지한다.

**[10] DSP_Sampling_Rate 값의 근거 및 d&b D80과의 서술 유무 차이 (사용자 검토 반영, 양방향 동기화 보강)**: LA7.16은 LA12X와 동일한 신호 처리 아키텍처를 공유하며, AES/EBU 입력에 SRC(Sample Rate Converter)가 상시 하드웨어로 내장되어 있다. OM p.16 "Technical description > Signal processing and amplification > AES/EBU" 절은 LA12X OM p.15와 동일한 구조로 "The AES/EBU input is equipped with an SRC (Sample Rate Converter)... converts the formats to the 24 bits / 96 kHz internal format... and provides constant propagation delay regardless of the input sampling frequency"를 서술한다. 즉 입력 샘플레이트에 관계없이 SRC가 상시 작동하여 항상 96 kHz 내부 포맷으로 처리하며, 이로 인한 지연시간도 입력 조건과 무관하게 일정함이 OM 본문에서 명시적으로 확정된다. **d&b D80과의 서술 유무 차이**: D80은 이와 반대로 SRC를 기본적으로 비활성화해 두고 44.1/88.2 kHz 등 비표준 입력이나 비동기 다중 소스 입력 시에만 SRC를 수동으로 활성화하는 조건부 구조다(D80 OM p.34 "System clocking"/"SRC" 절, D80_v1.2.md dsp 섹션 각주 [9a] 참조). 이 때문에 D80의 DSP_Sampling_Rate(96 kHz, 내부 고정값)는 SRC 비활성 조건에서만 무조건적으로 성립한다는 단서가 붙는 반면, LA7.16은 SRC가 상시 하드웨어로 내장되어 있어 이런 조건부 서술이 필요 없다. LA12X_v2.9.md dsp 섹션 각주 [12]와 동일한 근거 구조이며, LA7.16과 LA12X는 이 부분에서 근거 수준이 동일하게 높다.

**[10a][구조 개편 v2.0, v2.4 재검증] System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check**: v1.x까지 "d80_specific" 섹션에 있던 3개 Key를 dsp로 재배치했다. v2.4에서 LA7.16 자체 원본(OM v4.0 전문, SPS 1.4, AE)을 재검색한 결과 세 Key의 판단이 갈렸다. **System_Start_Up_Time**: OM p.21 "CHK - Normal start-up sequence"(정기 점검 절차)에 "Plug the amplified controller to mains. Check that fan noise can be heard for a few seconds during the start-up sequence."라는 서술이 있으나, "a few seconds"는 정성적 표현일 뿐 신뢰 가능한 초 단위 수치가 아니다 — 임의 추론 금지 원칙에 따라 수치화하지 않고 미확인(null)으로 유지한다. **LoadMatch_Max_Cable_Length**: "cable compensation"/"LoadMatch"에 해당하는 케이블 손실 보상 DSP 기능이 LA7.16 소스 어디에도 없다(LA7.16의 Per_Channel_DSP_Tools는 Array morphing과 Air absorption compensation filters뿐이며 케이블 보상 기능이 아니다) — d&b 고유 기술이 LA7.16 아키텍처에 대응 개념 자체가 없는 경우이므로 `N/A`(비적용)로 확정한다. **Load_Monitoring_System_Check**: OM p.60-61 "Enclosure check" 절에서 정확히 대응하는 기능을 확인했다 — "Enclosure check is a preliminary diagnosis tool for the loudspeaker enclosures connected to the amplified controller. It measures the impedance at the reference frequencies for the connected loudspeaker family. The measured impedance is compared to the expected range allowing for fast detection of loudspeakers presenting circuit continuity issues." 상태값은 IDLE/OK/NOK/NC/?(unsupported preset family)/UNDF 6종이나 Value에는 대표 5종(? 제외, 원문 그대로)만 병기했다. d&b D80/D90의 "System check and Load monitoring (LM)"과 동일 계열의 임피던스 기반 결선/고장 진단 기능으로 판단되어 실값으로 채택한다.

**[10b][구조 개편 v2.0, v2.4 재검증] Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail**: v1.x까지 "d90_specific" 섹션에 있던 3개 Key를 dsp로 재배치했다(System_Start_Up_Time과 같은 전원/프리셋 관련 성격이므로 인접 배치). v2.4에서 LA7.16 자체 원본을 "time to tone", "energy sav", "eco mode", "standby", "amp preset" 키워드로 재검색했으나 세 Key 모두 대응하는 서술을 찾지 못했다. Energy_Saving_Detail과 관련해서는 이미 power_supply 섹션에 Power_Consumption_Standby(19 W)가 별도 Key로 존재하나, "에너지 절약 모드의 상세 동작 로직"(예: 자동 진입/해제 조건, 웨이크업 트리거)에 해당하는 서술은 없다. AmpPresets_Detail과 관련해서도 LA7.16의 Preset_Memory_User(10 slots, 단순 슬롯 개수)와 D90류의 AmpPresets_Detail(입력/출력/채널구성/EQ/딜레이 전체 설정을 포함하는 프로파일 개념)은 구조가 근본적으로 다른 개념이므로 서로 병합하지 않는다(무결성 원칙). 원본을 실제로 재검색했음에도 발견되지 않아 3개 Key 모두 미확인(null)으로 유지한다.

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

**[11] Latency_Standard/Low_Mode 값의 확정 근거 및 d&b D80과의 서술 유무 차이 (사용자 검토 반영)**: OM p.94 Latency 스펙 표는 LA12X OM p.86과 동일하게 표준/저지연 두 모드 모두 "independent from input Fs"(입력 샘플링 주파수와 무관) 문구를 직접 명시한다 — dsp 섹션 각주 [10]에서 설명한 상시 내장 SRC 하드웨어(OM p.16)가 이 불변성의 근거다. 즉 LA7.16의 레이턴시 값(3.84 ms 표준, 1.18 ms 저지연)은 입력 조건과 무관하게 항상 성립하는 무조건적 고정값이며, 이는 OM 원문이 직접 확정하는 서술이다. **d&b D80과의 비교**: D80은 Latency_Standard(0.3 ms)가 "SRC 비활성, 입력 48/96 kHz" 조건에서만 성립하고 SRC 활성화 시 최대 +1 ms까지 증가할 수 있다는 조건부 서술이 OM p.34에 있다(D80_v1.2.md latency 섹션 각주 [12a] 참조) — LA7.16처럼 "independent from input Fs"에 해당하는 확정 문구가 D80 소스에는 없다. D90은 "permanent SRC" 서술은 있으나 LA12X/LA7.16 수준의 명시적 불변성 확정 문구는 없다(D90_v1.1.md latency 섹션 각주 [9b] 참조). LA7.16의 저지연 모드 수치(1.18 ms)는 LA12X(0.84 ms)와 다르지만, 두 제품 모두 "independent from input Fs" 확정 문구를 공유하므로 근거 수준 자체는 동일하다.

---

## input_analog (아날로그 입력)

| Key | Value | Unit |
|---|---|---|
| Analog_Input_Channels | 1 | ch |
| Input_Impedance | 22 | kOhm |
| Max_Input_Level | 22 | dBu |
| ADC_Architecture [7] | 1 x 32-bit A/D converter at 96 kHz sampling rate | - |
| Analog_Link_Type | active link with failsafe relay, shared 12-point terminal block (AES/ANA IN + AES/ANA LINK) | - |
| CMRR_Analog_Input [7a] | null | dB |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.16 "Technical description > Signal processing and amplification > Analog", p.94 "Specifications > Input signal distribution" (최우선) / AE "Technical requirements > Analog input"

**측정 조건**: Input_Impedance/Max_Input_Level은 balanced 기준, THD 1% 기준(AE). Analog_Input_Channels는 LA12X(채널당 전용 XLR 4개)와 달리 16개 증폭 채널 전체가 공유하는 보조(AUX) 입력 1채널 구조이며, 메인/보조/폴백 입력원으로 자유롭게 매핑 가능(OM p.15). 채널 수치 자체는 정확하나 LA12X와 아키텍처가 근본적으로 다르므로 단순 채널 수 비교는 주의가 필요함을 명기한다.

**[7] ADC dynamic range 충돌**: OM(p.16)은 "encoding dynamic range of 117 dB (A-weighted, 20 kHz bandwidth)"로 명시. AE는 동일 항목을 "121 dB dynamic range, 20 Hz - 20 kHz, A-weighted"로 표기. 두 값 모두 보존 — ADC_Architecture의 Value에는 다이나믹 레인지 수치를 넣지 않고 컨버터 구성만 기재했으며, 상충하는 117 dB(OM)/121 dB(AE) 수치는 본 각주에만 병기한다. OM 최우선 원칙상 117 dB를 채택 근거로 우선 고려하되, 두 수치의 우열을 판단할 추가 근거가 없어 각주 형태로 병존시켰다.

**[7a][구조 개편 v2.0, v2.4 재검증] CMRR_Analog_Input**: v1.x까지 "d80_specific" 섹션에 있던 Key를 input_analog로 재배치했다. v2.4에서 LA7.16 자체 원본(OM v4.0 전문, SPS 1.4, AE)을 "CMRR", "common mode", "common-mode" 키워드로 재검색했으나 세 소스 어디에도 일치하는 단어가 전혀 검출되지 않는다. 아날로그 입력 스펙은 Input_Impedance/Max_Input_Level/ADC_Architecture만 제공되며 CMRR 수치는 별도로 명시되지 않는다. 원본을 실제로 재검색했음에도 발견되지 않아 미확인(null)으로 유지한다.

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
| Digital_Input_Impedance [1] | null | Ohm |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Technical description > Signal processing and amplification > AES/EBU", p.94 "Specifications > Input signal distribution" (최우선) / AE "Technical requirements > Digital input, Sample Rate Converter"

**측정 조건**: Max_AES_Cable_Length는 단일 케이블, 48 kHz 샘플링, Belden 1696A 또는 Klotz OT234H 케이블 기준(LA12X와 동일 조건, 동일 값). Digital_Input_Gain_Range는 0.1 dB 스텝. Digital_Input_Channels(2)와 Digital_Standard는 LA12X(4채널, 2x AES3)와 달리 1x AES3(2채널)만 지원하며 아날로그 입력과 동일한 공유 단자를 사용한다 — LA12X의 각주 [6](S/PDIF 병기)에 해당하는 표기 차이는 LA7.16 소스에서는 발견되지 않았다.

**[1][구조 개편 v2.0, v2.4 재검증] Digital_Input_Impedance**: v1.x까지 "d80_specific" 섹션에 있던 Key를 input_digital로 재배치했다. v2.4에서 LA7.16 자체 원본(OM v4.0 전문, SPS 1.4, AE)을 "impedance" 키워드로 재검색했다. OM p.16 "Cables for AES/EBU digital audio" 절에서 "AES3 specifies that the nominal characteristic impedance of cables used for AES/EBU digital audio transmission shall be 110 Ω ± 20%..."라는 서술을 확인했으나, 이는 AES3 표준이 규정하는 **케이블**의 특성 임피던스를 소개하는 일반론이며, LA7.16 자신의 AES/EBU **수신단(입력 포트) 임피던스**를 스펙으로 명시한 문장이 아니다 — 두 개념을 혼동하여 110 Ω을 이 Key에 대입하지 않는다(무결성 원칙, 임의 추론 금지). OM p.94의 Digital input 스펙 표(Standards/Sampling frequency/Word length/Synchronization)에도 입력 임피던스 항목 자체가 없다. 원본을 실제로 재검색했음에도 기기 자체의 입력 임피던스 수치는 발견되지 않아 미확인(null)으로 유지한다.

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
| AES67_Support [12] | Yes | - |
| AVB_Device_Type [12a] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.15 "Milan-AVB", p.94-95 "Specifications > Milan-AVB" (최우선) / SPS 2p "I/O" / AE "Technical requirements > AVB input"

**측정 조건**: AVB_Channels(16)는 최대 16개 스트림(각 최대 8채널, 총 최대 128채널)에서 사용자가 선택적으로 매핑하는 조건(OM p.94-95, SPS 2p). AVB_Formats는 AAF PCM32(최대 8채널, 48/96 kHz), IEC 61883-6 AM824(8채널, 48/96 kHz) 조건. Switchover 조건은 AVB loss of lock(OM p.95). Fallback_Modes는 LA12X처럼 이중 AES(AB)/XLR(CD) 구조가 아니라 단일 공유 AES/ANA 입력을 통한 폴백이며, 사용자 정의 매핑이 가능하다.

**D80과의 비교 참고**: D80(Phase 3-2)은 AVB/Milan 프로토콜을 사용하지 않으므로 input_avb 섹션 전체가 D80에서는 비적용(null)이다. D80의 "Fallback"은 이 Key와 동일 명칭이나 완전히 다른 계층(채널별 신호소스 이중화)의 개념이다.

**[12] AES67_Support 재검증 (v2.4, 원본 재조회 완료)**: v1.7~v2.3까지는 LA7.16(구형) 자체 원본을 재조회하지 않고 미확인(null)으로 보수적 처리했던 항목이다. 이번에 LA7.16 자체 OM v4.0을 재검색한 결과, p.13 "Technical description > Main features > Internal components" 절에 다음과 같은 명시적 서술이 확인된다: "The core of the LA7.16 is a Gen. 5 dual DSP engine driving 16 channels of amplification from 16 AVB streams of up to eight channels... Alternatively, LA7.16 can operate in AES67 mode driving 16 channels of amplification from 16 AES67 streams of up to eight channels." 이는 LA7.16(구형) 자신을 주어로 한 1인칭 기술 서술이며 L-Acoustics 브랜드 우선 출처인 OM 본문에 명시되어 있으므로 `Yes`로 확정한다. **소스 간 충돌 주의**: 다만 SPS(1.4, 251125) 2p 비교표의 "Input channels" 행에서는 LA7.16(i) 칸이 "16 x AVB (i: or AES67)"로 표기되어 있어, 문자 그대로 읽으면 AES67 대안 지원이 "i"(신형 LA7.16i) 전용인 것처럼도 해석될 수 있다 — OM 본문의 명시적 1인칭 서술과 상충한다. 이 충돌은 삭제하지 않고 병기하되, L-Acoustics 브랜드 우선 출처 규칙(OM 최우선)에 따라 OM 본문 값을 채택값으로 사용한다. 또한 OM의 문제해결(Troubleshooting) 절(p.62 부근)은 입력 모드 선택지를 "Milan AVB, AES/EBU, analog" 3가지로만 나열하며 AES67을 별도 토글로 언급하지 않는데, 이는 AES67이 전면 패널 "AUX Mode" 같은 별도 선택 UI가 아니라 AVB와 동일한 Ethernet 물리 계층 위에서 스트림 단위로 동작하는 대체 프로토콜이기 때문으로 추정되나(OM에 이 부분을 직접 설명하는 문장은 없음), 이 추정 자체는 각주로만 남기고 Value에는 반영하지 않는다.

**[12a][구조 개편 v2.0] AVB_Device_Type**: v1.x까지 "d90_specific" 섹션에 Milan_Device_Type/Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 4개 Key로 흩어져 있던 내용을 정리했다. Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 3개는 이미 이 섹션의 AVB_Channels/AVB_Stream_Count/Redundancy_Type Key와 개념이 중복되므로 별도 Key로 만들지 않고 흡수했다(LA7.16은 이 3개 Key 모두 실값을 이미 보유하고 있어 데이터 손실 없음). Milan_Device_Type만 기존에 대응 Key가 없는 순수 신규 정보였으므로, 이 섹션의 명명 규칙(AVB_*)에 맞춰 AVB_Device_Type으로 이름을 바꾸어 새로 추가했다. LA7.16(구형)의 기존 소스에는 Milan Device Type(Endstation 등) 개념에 대응하는 명시적 서술이 확인되지 않아 null로 유지한다.

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

**섹션 전체 비적용**: LA7.16은 Dante가 아닌 Milan-AVB(L-Acoustics 고유 인증) 오디오 네트워크를 사용한다. 이 섹션은 5D(d&b audiotechnik Dante 설치용 라인) 파싱 중 신설되었으며, Milan-AVB 기준으로 설계된 input_avb 섹션과 별도로 Dante 프로토콜 전용 섹션으로 분리되었다. LA7.16의 기존 소스에는 이 개념에 대응하는 서술이 없어 전량 null로 소급 반영한다.

---

## network (네트워크 설정, 구조 개편 v2.0 신규 섹션)

| Key | Value | Unit |
|---|---|---|
| Network_IP_Default [1] | 192.168.1.100 (subnet 192.168.1.0/24, mask 255.255.255.0) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.32 "Installation > L-NET/AVB" (최우선), 동일 서술이 p.65 "Operation > IP settings"에도 반복됨.

**[1][구조 개편 v2.0, v2.4 재검증] Network_IP_Default 및 신규 섹션 신설 근거**: v1.x까지 "d90_specific" 섹션에 있던 Key. IP 기본값/네트워크 설정은 AVB 오디오 스트림(input_avb)이나 물리적 커넥터(connectivity)와는 성격이 다른 별도 주제이므로, 이 재배치를 계기로 "network"라는 주제 기반 신규 섹션을 신설했다(D80_v2.0.md/D90_v2.0.md에도 동일 섹션이 반영됨). v2.4에서 LA7.16 자체 원본(OM v4.0)을 "IP address", "DHCP", "default" 키워드로 재검색한 결과 OM p.32 "Installation > L-NET/AVB" 절(및 p.65 "Operation > IP settings"에 동일 문구 반복)에서 실값을 확인했다: "The factory default IP settings of all L-Acoustics devices are: IP address: 192.168.1.100; Subnet address: 192.168.1.0/24; IP broadcast address: 192.168.1.255; Subnet mask: 255.255.255.0." 이는 "모든 L-Acoustics 장비"에 공통 적용되는 공장 기본값이라는 문구로 LA7.16 자신도 포함되며, DHCP는 언급되지 않고 고정(static) IP만 서술되어 있다.

---

## connectivity (커넥터)

| Key | Value | Unit |
|---|---|---|
| Input_Connectors | 1 x 12-point terminal block (AES/ANA IN + LINK, GPIO, 24 V DC backup), 2 x etherCON RJ45 (Milan-AVB I/O) | - |
| Terminal_Block_Pinout | 12핀: 24V DC IN, GND, GPIO1-3, GPIO GND, AES/ANA IN(+/-/Shield), AES/ANA LINK(+/-/Shield) — 상세 핀맵은 하단 표 참조 | - |
| XLR_Pin_Polarity | null | - |
| Speaker_Connectors | 1 x SC32 female connector (37-pin, 32 conductors) | - |
| SpeakON_Left_Pinout | null | - |
| SpeakON_Right_Pinout | null | - |
| CACOM_Pinout | null | - |
| SC32_Channel_Mapping | Out 1-16 via single SC32 connector | - |
| Speaker_Output_Accessories | SC32 cable (5/10/25/50 m), SC32-4DO adaptor (to 4x CA-COM), BOB32 breakout box (to 2x CA-COM + 8x NL4) | - |
| Network_Connectors | 2x etherCON RJ45, 1 Gb/s | - |
| Service_Port_Type [13] | USB Micro-B or USB-C, 2.0 compliant | - |
| Speaker_Terminal_Block_SE_BTL_Wiring [12] | N/A | - |
| PBTL_Activation_Method [12] | N/A | - |
| Output_Mode_Selectable [13a] | N/A | - |
| Fault_Contact_Type [14] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.14 "Front and rear panels", p.23 "Installation > General Purpose I/O (GPIO)" (최우선) / SPS 2p "I/O", 4p "ACCESSORIES" / AE "Technical requirements > Connectors"

**측정 조건**: 없음(커넥터 규격 및 결선표). XLR_Pin_Polarity와 SpeakON/CACOM 관련 키는 LA7.16에 해당 커넥터 유형이 존재하지 않아 null 처리했다(비적용) — LA12X의 전용 XLR/speakON/CACOM 구조와 달리 LA7.16은 12-point terminal block(신호/GPIO/백업전원 통합)과 단일 SC32 커넥터(스피커 출력 16채널 통합)로 완전히 다른 커넥터 아키텍처를 사용한다. 극성 정보는 PDF 텍스트 레이어에 "+ / - / shield" 핀 명칭으로 이미 문자로 명시되어 있어(OM p.14, AE 커넥터 절) 별도 이미지 분석 없이 텍스트 추출만으로 확인했다(SKILL v1.5 PDF 분석 규칙 적용, 예외 이미지 분석 불요).

**SC32_Channel_Mapping, Speaker_Output_Accessories**: LA12X 스키마에는 없던 신규 속성. LA7.16의 16채널 출력이 개별 speakON/CACOM이 아닌 단일 SC32 커넥터로 통합되어 발생한 아키텍처 차이를 반영한다. Speaker_Output_Accessories는 SPS 4p "ACCESSORIES" 절에서만 확인되며 OM/AE에는 명시되지 않았다. 참고로 d&b D80(Phase 3-2)의 동일 Key에는 MC24 멀티코어/Touring rack 생태계가 매핑되어 있으며, LA7.16의 SC32 액세서리와는 완전히 다른 브랜드 고유 생태계이다.

**Terminal_Block_Pinout (v1.3 추가) — 12-point terminal block 상세 핀맵**:

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

**[13] Service_Port_Type 재검증 (v2.4, 원본 재조회 완료)**: v1.7~v2.3까지는 원본 미재조회 상태로 null 처리했던 항목이나, OM v4.0을 재검색한 결과 실값이 확인되었다. OM p.14 "Front and rear panels" 항목 7: "1 USB port for configuring IP settings (refer to the LA Network Manager Help). The USB port is either: USB Micro-B (units with serial number lower than 169000 6000), USB-C (units with serial number 169000 6000 or higher)." 및 OM p.93 스펙 표 "Service port: 1 USB Micro-B or USB-C, 2.0 compliant - for configuring IP settings using the USB Terminal tool of LA Network Manager"에서 동일 내용을 확인. 즉 LA7.16은 생산 시리얼 넘버 기준(169000 6000 미만/이상)으로 물리 커넥터 타입이 세대 전환되었으며, 두 세대 모두 IP 설정 전용(오디오 신호 아님)이라는 점은 공통이다.

**[12] Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method 재검증 (v2.4, 비적용 확정)**: amplification 섹션 각주[12](Bridging_Support 재검증)에서 LA7.16의 Bridging_Support가 `No`(확정적 비존재)로 확정됨에 따라, 이 두 Key도 `N/A`로 처리한다. 이유는 이중이다 — (1) 브릿지(BTL/PBTL) 자체가 존재하지 않으므로 브릿지 배선/활성화 방식이라는 개념이 원천적으로 성립하지 않는다. (2) 설령 브릿지가 있었더라도 LA7.16의 스피커 출력은 SE/BTL 배선이 가능한 개별 터미널 블록/speakON 방식이 아니라, 16채널이 통합된 단일 SC32 커넥터(37핀, 32도체) 구조다(Speaker_Connectors 참조) — 이 섹션 상단 각주에서 이미 확인했듯 LA7.16에는 XLR_Pin_Polarity/SpeakON_Left_Pinout/SpeakON_Right_Pinout/CACOM_Pinout도 전부 비적용(null)인 것과 동일한 아키텍처적 이유다.

**[13a] Output_Mode_Selectable 재검증 (v2.4, 원본 재조회 완료, 비적용 확정)**: v1.x까지는 "d80_specific" 섹션에서 이동해 온 Key로, 이동 당시 원본 재조회 없이 null 처리되어 있었다. 이번에 OM/SPS/AE를 재검색했으나 "output mode", "channel pair", "dual channel", "2-way active"(D90류의 선택형 출력 배선 모드에 해당하는 표현) 등 출력 배선을 사용자가 선택 가능한 모드로 전환하는 서술은 발견되지 않았다. OM Appendix E(BOB32 breakout box, p.104)에 "Two-channel speakON output (for 2-way active enclosures)"라는 배선 예시가 있으나, 이는 BOB32 액세서리를 통해 LA7.16의 서로 다른 두 개별 채널(예: Out 1, Out 2)을 2-way 능동형 인클로저의 LF/HF 두 드라이버에 각각 연결하는 배선 예시일 뿐, 앰프 자신의 출력 모드를 전환하는 설정이 아니다(각 채널은 항상 독립적으로 동작). SC32_Channel_Mapping Key가 이미 명시하듯 LA7.16은 "Out 1-16 via single SC32 connector"로 16채널이 고정 배치된 구조이며, D90류의 Dual Channel/Mix TOP-SUB/2-Way Active 같은 채널 쌍 단위 출력 모드 전환 개념 자체가 없다. 위 [12]의 Bridging_Support=No 확정과 함께 고려할 때, 이는 "언급이 없어서 모르는" 미확인이 아니라 SC32 고정 채널 아키텍처가 그런 선택 개념을 구조적으로 배제하는 경우이므로 `N/A`(비적용)로 확정한다.

**[14][구조 개편] Fault_Contact_Type**: 5D(d&b audiotechnik) 파싱 중 신설된 Key(FAULT 릴레이 접점, NO/C/NC). LA7.16의 기존 소스에는 이 개념에 대응하는 서술이 없어 null로 소급 반영한다.

---

## control_monitoring (제어 및 모니터링)

| Key | Value | Unit |
|---|---|---|
| Remote_Software | LA Network Manager (Windows/Mac) | - |
| Network_Topologies | daisy-chain, star, hybrid | - |
| Third_Party_Control [8] | Q-SYS, Crestron | - |
| Front_Panel | 1 TFT color touchscreen display (480 x 128 px), 1 encoding wheel with push button | - |
| Settings_Protection | null | - |
| GPIO_Count | 3 | ea |
| GPIO_Type | isolated optocoupler inputs, isolated relay contacts | - |
| DSP_Backup_Power_Input [9] | 24 | V DC |
| Signal_Path_Management [9a] | Automatic fallback: AVB to AES/EBU or analog, user-defined mapping; switchover on AVB loss of lock; delay and level held constant (independent from input Fs, level per manual gain selection); revert to initial input only by manual user selection | - |
| Web_Remote_Interface | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.18 "Technical description > Monitoring and control", p.23 "Installation > General Purpose I/O (GPIO)", p.95 "Specifications > Remote control and monitoring" (최우선) / SPS 4p "SOFTWARE AND NETWORK" / AE "Technical requirements > Third-party management solutions, Connectors"

**측정 조건**: L-NET 네트워크는 최대 253대 제어 가능, CAT5e U/FTP 이상 케이블 사용(LA12X와 동일). Settings_Protection(PIN 코드 등)은 세 소스 어디에도 LA7.16 관련 서술이 없어 null 처리했다(LA12X에는 존재하는 값이므로 임의로 이식하지 않음).

**[8] 서드파티 제어 목록 차이**: OM(p.19)과 AE는 "Q-SYS, Crestron"만 명시. SPS는 "Q-SYS® / Crestron® / HTTP API"로 HTTP API를 추가 병기. OM은 별도 서술(p.19)에서 "HTTP API is available on request after signing a memorandum of understanding"라고 조건부로 언급한다. 두 표기 모두 보존 — Value는 OM/AE 2개 소스 일치의 "Q-SYS, Crestron"을 채택하고, SPS의 HTTP API 병기 및 OM의 MOU 조건부 제공 서술을 본 각주에 기록한다.

**GPIO_Count, GPIO_Type**: LA12X 스키마에는 GPIO 관련 속성이 전혀 없었다(LA12X 소스 자체에 GPIO 기능 없음). OM p.23, AE "Connectors" 절에서 일치. 참고로 d&b D80(Phase 3-2)은 OM 전문 검색 결과 GPIO 용어 자체가 전혀 발견되지 않아 D80의 GPIO_Count는 0(확정적 비존재)으로 명시되었다 — LA7.16의 GPIO_Count=3(존재 확인)과 D80의 GPIO_Count=0(비존재 확인)은 둘 다 "확정값"이며 null(미확인)과는 구분된다.

**[9] DSP_Backup_Power_Input 충돌**: OM(p.95)은 "1 x 24 V DC (± 10%) 15 W minimum"으로 명시. SPS(7p)는 동일 항목을 "24 V DC (±15%) / 0.8 A"로 표기 — 허용오차(±10% vs ±15%)와 정격 표시 단위(15 W vs 0.8 A, 24 V 기준 0.8 A는 약 19.2 W로 15 W와도 정확히 일치하지 않음)가 모두 상이하다. AE는 "Backup power circuit for the DSP: 24 V DC 2-point terminal block"으로 전압값만 명시. Value에는 세 소스 공통값인 "24 V DC"만 채택하고, 세부 허용오차/전류·전력 정격은 본 각주에서 OM/SPS 두 값을 모두 병기한다. LA12X 스키마에는 이 속성 자체가 없었다.

**[9a][구조 개편 v2.0, v2.4 재검증] Signal_Path_Management**: v1.x까지 "d80_specific" 섹션에 있던 Key를 control_monitoring으로 재배치했다. input_avb 섹션의 Fallback_Modes(간략 요약: "AVB to AES/EBU or analog (shared input), user-defined mapping")와 개념적으로 관련되나, 상세 동작 로직은 이 Key에서 다룬다는 기존 방침에 따라 v2.4에서 LA7.16 자체 원본(OM v4.0)을 재검색해 상세 로직을 확인했다. OM p.94-95 "Specifications > Milan-AVB > Automatic fallback option" 스펙 표에 다음과 같이 명시되어 있다: "Mode: AVB to AES/EBU or analog, with user-defined mapping / Switchover conditions: AVB: loss of lock / Constant delay: independent from input Fs / Constant level: upon manual user selection of gain, independent from input Fs / Revert to initial input: upon manual user selection." 즉 AVB 신호 손실(loss of lock) 시 자동으로 AES/EBU 또는 아날로그로 전환되고, 전환 전후 지연시간은 항상 일정하게 유지되며, 레벨은 사용자가 수동으로 설정한 게인값을 기준으로 일정하게 유지되고, 원래 입력으로의 복귀는 자동이 아니라 반드시 사용자가 수동으로 선택해야 한다. OM p.60 "Enclosure check"(dsp 섹션 Load_Monitoring_System_Check 참조)와는 목적이 다른 별개 기능이다.

**Web_Remote_Interface (10D 파싱 중 신설, 양방향 동기화로 null 반영)**: 10D(d&b audiotechnik 차세대 설치용 라인) 파싱 중 발견된 신규 Key — 별도 소프트웨어(R1/ArrayCalc, L-Acoustics의 경우 LA Network Manager) 없이 표준 웹 브라우저로 앰프에 직접 접속하는 브라우저 기반 내장 웹 인터페이스 개념. LA7.16의 기존 소스에는 이 개념에 대응하는 서술이 확인되지 않아 null(미확인)로 소급 반영한다.

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
| Max_Operating_Altitude | 2000 | m |
| Storage_Temp_Range [1] | null | degrees C |
| Storage_Humidity [1] | null | % rel. |

### 주석 및 출처 (Notes & Sources)

**출처**: OM p.6 "Important safety instructions", p.92-93 "Specifications > Operating conditions" (최우선) / AE "Technical requirements > Operating conditions"

**측정 조건**: Operating_Temp_Range는 OM 안전 섹션(p.6: "-5°C/23°F to 50°C/122°F")과 스펙 섹션(p.93: 동일)이 정확히 일치하며 LA12X와 달리 충돌이 없다. Fan_Noise는 free field, 1 m 거리 기준(Min은 Idle 모드, Max는 최고속). Fan_Noise 수치는 OM 원문에 "less than" 등 수식어 없이 순수 수치로만 기재되어 있어("in Idle mode: 33 dBA", "at maximum speed: 62 dBA") LA12X 파일과 달리 "less than" 수식어를 붙이지 않았다(임의 수식어 첨가 금지 원칙 — 두 파일 간 표기 차이는 오기가 아니라 원문 차이를 그대로 반영한 것). Fan_Count(5)는 AE에서만 확인되며 OM 스펙 표에는 명시적 팬 개수가 없다(단일 소스 값, 충돌 아님).

**Max_Operating_Altitude**: LA12X 스키마에는 없던 신규 속성. OM p.93 스펙 표에만 명시("Maximum altitude 2000 m").

**[1][구조 개편 v2.0, v2.4 재검증] Storage_Temp_Range/Storage_Humidity**: v1.x까지 "d80_specific" 섹션에 있던 Key를 operating_conditions로 재배치했다. v2.4에서 LA7.16 자체 원본(OM v4.0 전문, SPS 1.4, AE)을 "storage", "humidity" 키워드로 재검색했다. "storage"는 OM p.10(플래시 메모리를 가리키는 "preset storage")과 안전 경고 문구("moisture... humidity")에서만 등장하며 보관 온습도 범위를 규정하는 문장이 아니다. "humidity"도 OM p.60 부근 "Temperature & Humidity" 모니터링 화면 설명(장비 가동 중 각 출력 채널/내부의 실측 온습도를 표시하는 기능)에서만 등장하며, 이는 운용 중 실시간 모니터링 항목이지 미가동/보관 시 허용 온습도 스펙이 아니다. Operating_Temp_Range(가동 온도)에 대응하는 별도의 "보관(Storage)" 조건 스펙 자체가 OM/SPS/AE 어디에도 없다. 원본을 실제로 재검색했음에도 발견되지 않아 미확인(null)으로 유지한다.

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

## Null Report

이번 소스 집합에서 정의되지 않아 null 처리된 항목 (총 32건 — v2.4에서 LA7.16 자체 원본 재조회를 거쳐 46건에서 32건으로 감소, 상세는 아래 "v2.4 재검증 결과" 참조):

**Phase 3-1까지(총 9건)**: Rated_Power_Per_Ch_2.7_Ohms(비적용, 양방향 동기화), Total_Power_Capability(v1.1 정정, 근거 부족), THD_N_4ohm, Preset_Memory_Factory, XLR_Pin_Polarity, SpeakON_Left_Pinout, SpeakON_Right_Pinout, CACOM_Pinout, Settings_Protection.

**d80_specific으로부터 재배치, v2.4 재검증 후에도 미확인 유지(총 8건, 원래 12건 중 4건은 v2.4에서 해소)**: CMRR_Analog_Input(input_analog), Digital_Input_Impedance(input_digital), SN_Ratio_Analog_Input/SN_Ratio_Digital_Input(audio_performance), System_Start_Up_Time(dsp), Storage_Temp_Range/Storage_Humidity(operating_conditions), Mains_Current_Limiter_Range(power_supply). 원래 이 그룹에 있던 LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check(dsp)/Signal_Path_Management(control_monitoring)/Output_Mode_Selectable(connectivity) 4건은 v2.4 재검증으로 null에서 해소되어(실값 또는 비적용 확정) 아래 "v2.4 재검증 결과"로 이동.

**d90_specific으로부터 재배치/흡수, v2.4 재검증 후에도 미확인 유지(총 5건, 원래 6건 중 1건은 v2.4에서 해소)**: AVB_Device_Type(input_avb, Milan_Device_Type에서 개명 — Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 3건은 input_avb의 기존 AVB_Channels/AVB_Stream_Count/Redundancy_Type Key로 흡수되어 별도 Key로 더 이상 존재하지 않음, Null Report 집계에서 제외), Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail(dsp), Output_Noise_Dynamic_Range_Detail(audio_performance). 원래 이 그룹에 있던 Network_IP_Default(신설 network 섹션) 1건은 v2.4 재검증으로 실값이 확인되어 아래 "v2.4 재검증 결과"로 이동.

**Phase 4(Upload 4개 제품 양방향 동기화, BTL/PBTL 통폐합 후 총 9건 -> v2.4에서 전건 해소, 0건 남음)**: Bridging_Support, Rated_Power_Per_Ch_BTL, Peak_Power_Per_Ch_BTL, Rated_Power_Per_Ch_PBTL, Peak_Power_Per_Ch_PBTL, AES67_Support, Service_Port_Type, Speaker_Terminal_Block_SE_BTL_Wiring, PBTL_Activation_Method — 9건 전부 v2.4 재검증으로 실값 또는 비적용/비존재 확정되어 더 이상 null이 아니다. 상세는 아래 "v2.4 재검증 결과" 참조.

**D25 소급 반영(총 1건)**: Max_Output_Current_Peak(amplification) — LA7.16 자체 원본에 대응 수치가 확인되지 않아 미확인(null) 유지, v2.4에서는 재검토 대상이 아니었음.

**Phase 5(5D 양방향 동기화, v2.1, 총 8건 — 비적용 7건 + 미확인 1건)**: Dante_RX_Channels/Dante_Sampling_Rates/Dante_SRC/Dante_Redundancy/Dante_Network_Flows/Dante_Latency/Dante_IP_Architecture(신설 input_dante 섹션, 비적용 — LA7.16은 Milan-AVB 전용이며 Dante를 사용하지 않음), Fault_Contact_Type(connectivity, 미확인 — LA7.16 기존 소스에 FAULT 릴레이 접점 관련 서술이 확인되지 않아 원본 재검토 없이는 확정 불가).

**Phase 6(10D 양방향 동기화, v2.2, 총 1건 — 미확인)**: Web_Remote_Interface(control_monitoring, 미확인 — 별도 소프트웨어 없이 표준 웹 브라우저로 앰프에 직접 접속하는 브라우저 기반 내장 웹 인터페이스 개념. LA7.16 기존 소스에 대응 서술이 확인되지 않아 원본 재검토 없이는 확정 불가).

**v2.4 재검증 결과 (원본 재조회 완료, 총 14건이 null에서 해소)**: SKILL v1.11의 "판단 근거의 원본성 요건" 위반 패턴(원본 미재조회 상태로 null 처리)을 시정하기 위해 LA7.16 자체 원본(OM v4.0 전문, SPS 1.4, AE)을 실제로 재검색했다. (1) **실값 확인(5건)**: AES67_Support(Yes — OM p.13 "LA7.16 can operate in AES67 mode..."), Service_Port_Type(USB Micro-B or USB-C, 2.0 compliant — OM p.14/p.93), Load_Monitoring_System_Check(Enclosure check 기능 — OM p.60-61), Network_IP_Default(192.168.1.100 — OM p.32/p.65), Signal_Path_Management(Automatic fallback 상세 로직 — OM p.94-95). (2) **확정적 비존재/비적용(9건)**: Bridging_Support(No — SPS 2p 비교표에서 LA1.16i만 브릿지 표기, LA7.16(i)은 미표기), Rated_Power_Per_Ch_BTL/Peak_Power_Per_Ch_BTL/Rated_Power_Per_Ch_PBTL/Peak_Power_Per_Ch_PBTL(N/A, 브릿지 비존재에 따른 연쇄), Speaker_Terminal_Block_SE_BTL_Wiring/PBTL_Activation_Method(N/A, 브릿지 비존재 + SC32 고정 채널 구조), Output_Mode_Selectable(N/A, SC32 고정 채널 구조상 선택형 출력 모드 개념 자체가 없음), LoadMatch_Max_Cable_Length(N/A, 케이블 보상 DSP 기능 자체가 LA7.16에 없음). 나머지 12개 Key(CMRR_Analog_Input, Digital_Input_Impedance, SN_Ratio_Analog_Input, SN_Ratio_Digital_Input, Output_Noise_Dynamic_Range_Detail, System_Start_Up_Time, Time_To_Tone, Energy_Saving_Detail, AmpPresets_Detail, Storage_Temp_Range, Storage_Humidity, Mains_Current_Limiter_Range)는 실제로 재검색했으나 발견되지 않아 미확인(null)으로 유지하되, 각주에 이번에 수행한 실제 검색 근거를 명기했다(과거의 "원본 미재조회" 문구는 전부 제거).

**증감 내역(45건 -> 36건 -> 37건 -> 45건 -> 46건 -> 32건)**: d90_specific의 Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs 3건이 기존 Key로 흡수되며 감소(-3), BTL/PBTL 10개 Key가 4개로 통폐합되며 감소(-6, 45 -> 36). 이후 D25 파싱 중 발견된 신규 Key Max_Output_Current_Peak(amplification)가 소급 반영되어 +1(36 -> 37). 이후 5D 파싱 중 발견된 신규 8건이 소급 반영되어 +8(37 -> 45). 이후 10D 파싱 중 발견된 신규 Key Web_Remote_Interface 1건이 소급 반영되어 +1(45 -> 46). 이후 v2.4에서 LA7.16 자체 원본 재조회를 통해 5건은 실값으로, 9건은 확정적 비존재/비적용(No/N/A)으로 전환되어 null 목록에서 제외, 총 -14(46 -> 32).

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

v1.7 to v2.0: (구조 개편, Major) d&b 제품군이 D25 투입으로 3개(D80/D90/D25)로 늘어남에 따라, 사용자 요청으로 "d80_specific"과 "d90_specific" 두 그랩백 섹션을 D80_v2.0.md/D90_v2.0.md에 이어 본 파일에서도 모두 폐지했다. d80_specific의 12개 Key는 CMRR_Analog_Input -> input_analog, Digital_Input_Impedance -> input_digital, SN_Ratio_Analog_Input/SN_Ratio_Digital_Input -> audio_performance, System_Start_Up_Time/LoadMatch_Max_Cable_Length/Load_Monitoring_System_Check -> dsp, Storage_Temp_Range/Storage_Humidity -> operating_conditions, Signal_Path_Management -> control_monitoring, Output_Mode_Selectable -> connectivity, Mains_Current_Limiter_Range -> power_supply로 재배치(Key/Value/Unit/각주 내용 유지, 위치만 이동). d90_specific의 9개 Key는 Milan_Device_Type -> input_avb(AVB_Device_Type으로 개명), Milan_Input_Channel_Streams/Milan_Redundancy/Milan_Routable_Inputs -> input_avb의 기존 AVB_Channels/AVB_Stream_Count/Redundancy_Type에 흡수(중복 제거, 신규 Key 미생성), Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail -> dsp, Output_Noise_Dynamic_Range_Detail -> audio_performance, Network_IP_Default -> 신설된 network 섹션으로 재배치했다. 아울러 사용자 피드백에 따라 BTL/PBTL 전력 Key 10개(부하 임피던스별 세분화)를 4개(Rated/Peak_Power_Per_Ch_BTL, Rated/Peak_Power_Per_Ch_PBTL)로 통합했다. LA7.16은 d&b 브랜드 고유 개념이나 브릿지 모드에 대응하는 실제 스펙을 애초에 보유하지 않으므로, 이번 재편으로 이동/개명/통합된 모든 Key는 계속 `null`이며 실질 데이터(Value) 손실은 전혀 없다 — 위치, Key 이름, 개수(BTL/PBTL만 해당)만 바뀌었다. 이동한 Key마다 원래 위치를 명시하는 각주를 신설했으며(각주 번호는 이동 대상 섹션 내 기존 번호와 충돌하지 않도록 재부여), Null Report 총 건수는 45건에서 36건으로 변경(Milan 중복 3개 Key 흡수로 -3, BTL/PBTL 통합으로 -6, 순감소 9건). 섹션 계층 구조 변경이므로 SKILL v1.11 버저닝 규칙에 따라 Major 버전(v2.0)으로 상향했다.

v2.0 to v2.1: (5D 양방향 동기화, Minor, null 전용) d&b audiotechnik 신규 제품 5D(Dante 설치용 라인) 파싱 중 발견된 신규 스키마 2건을 양방향 동기화 규칙에 따라 반영했다. (1) 신규 섹션 `input_dante`(7개 Key: Dante_RX_Channels, Dante_Sampling_Rates, Dante_SRC, Dante_Redundancy, Dante_Network_Flows, Dante_Latency, Dante_IP_Architecture)를 기존 `input_avb` 섹션 바로 뒤, `network` 섹션 앞에 신설 추가했다 — LA7.16은 Dante가 아닌 Milan-AVB 전용 제품이므로 전량 `null`(비적용)로 반영했다. (2) `connectivity` 섹션에 신규 Key `Fault_Contact_Type`(FAULT 릴레이 접점, NO/C/NC)을 기존 표의 마지막 행으로 추가했다 — LA7.16 기존 소스(OM v4.0, SPS 1.4, AE)에는 이에 대응하는 서술이 확인되지 않아 `null`(미확인)로 처리했다(원본 재검토 없이는 확정된 비존재로 볼 수 없어 보수적으로 미확인 처리, Service_Port_Type 등 기존 Phase 4 사례와 동일한 판단 논리). 두 추가 모두 LA7.16의 기존 9개 섹션 및 이전 재배치분(d80_specific/d90_specific 유래)의 Key/Value/각주는 일절 변경하지 않았으며, 실 데이터는 단 한 건도 영향받지 않는 순수 스키마 동기화(null 추가)다. Null Report 총 건수는 37건에서 45건으로 변경(+8: input_dante 7건 + Fault_Contact_Type 1건). 섹션 내부에 표/Key만 추가되었을 뿐 기존 섹션 구조나 파싱 규칙의 개편은 아니므로 SKILL v1.11 버저닝 규칙에 따라 Minor 버전(v2.1)으로 상향했다.

v2.1 to v2.2: (10D 양방향 동기화, Minor) d&b audiotechnik 신규 제품 10D(Dante 설치용 라인) 파싱 중 발견된 신규 스키마 1건을 양방향 동기화 규칙에 따라 반영했다. `control_monitoring` 섹션에 신규 Key `Web_Remote_Interface`(별도 소프트웨어 없이 표준 웹 브라우저로 앰프에 직접 접속하는 브라우저 기반 내장 웹 인터페이스)를 추가했다 — LA7.16 기존 소스(OM v4.0, SPS 1.4, AE)에는 이에 대응하는 서술이 확인되지 않아 `null`(미확인)로 처리했다. 기존 Key/Value/각주는 일절 변경하지 않았다. Null Report 총 건수는 45건에서 46건으로 변경(+1: Web_Remote_Interface 1건). 스키마 구조 변경이 아닌 null 추가만 있으므로 Minor 버전(v2.2)으로 상향했다.

v2.2 to v2.3: (표기 정리, Minor) 프로젝트 전체 재검토에서 각주 태그가 추가 시점 이후 버전이 계속 올라가면서 더 이상 "신규"가 아닌데도 방치되어 있던 문제가 발견되어, 각주 번호(예: [32])는 유지한 채 텍스트만 전면 제거했다. 데이터/Key/Value/Unit/Null Report는 전혀 변경되지 않았다.

v2.3 to v2.4: (무결성 감사 후속 조치, Minor) 프로젝트 전체 감사에서 SKILL v1.11 "판단 근거의 원본성 요건" 위반 패턴이 발견되었다 — v1.7~v2.3의 여러 각주가 "원본 문서를 재조회하지 않고 기존 파싱 결과물 텍스트만을 근거로 판단했다"고 명시하면서도 `null`로만 처리하고 실제 원본 재확인은 미루고 있었다. 이번 버전에서 해당 19개 Key를 LA7.16 자체 원본(OM v4.0 전문, SPS 1.4, AE)에서 실제로 재검색했다. **(1) 실값으로 확정된 5건**: AES67_Support(Yes — OM p.13 본문에 "LA7.16 can operate in AES67 mode driving 16 channels of amplification from 16 AES67 streams of up to eight channels"라는 1인칭 서술 확인. 다만 SPS 2p 비교표의 "16 x AVB (i: or AES67)" 표기와는 상충하며, 이 충돌은 삭제하지 않고 각주에 병기하되 L-Acoustics OM 최우선 원칙에 따라 OM 값을 채택함), Service_Port_Type(USB Micro-B(S/N 169000 6000 미만) 또는 USB-C(그 이상), 2.0 compliant — OM p.14/p.93), Load_Monitoring_System_Check(Enclosure check: 임피던스 측정 기반 스피커 결선/고장 진단 기능 — OM p.60-61, d&b D80/D90의 "System check and Load monitoring (LM)"과 동일 계열 기능으로 판단), Network_IP_Default(192.168.1.100, subnet 192.168.1.0/24, mask 255.255.255.0 — OM p.32/p.65 "The factory default IP settings of all L-Acoustics devices are..."), Signal_Path_Management(OM p.94-95 "Automatic fallback option" 스펙 표의 상세 로직 — Mode/Switchover conditions/Constant delay/Constant level/Revert to initial input 5개 하위 항목 전문 인용). **(2) 확정적 비존재/비적용(No/N/A)으로 전환된 9건**: Bridging_Support(No — SPS 1.4(251125) 2p "AMPLIFIED CONTROLLERS – THE RANGE" 비교표에서 LA1.16i 칸에만 "8* x 300 W (at 8 ohms)" + "* Any odd/even pair of outputs can be bridged (BTL)" 각주가 있고, 동일 표의 LA7.16(i) 칸은 별표 없이 16채널 그대로 — 동일 문서·동일 표 내 타 제품 대비 적극적 반증으로 판단해 확정적 비존재 처리), 이에 연쇄하는 Rated_Power_Per_Ch_BTL/Peak_Power_Per_Ch_BTL/Rated_Power_Per_Ch_PBTL/Peak_Power_Per_Ch_PBTL(N/A), Speaker_Terminal_Block_SE_BTL_Wiring/PBTL_Activation_Method(N/A — 브릿지 비존재 + SC32 고정 커넥터 구조라는 이중 근거), Output_Mode_Selectable(N/A — SC32 16채널 고정 구조상 D90류의 채널 쌍 단위 선택형 출력 모드 개념 자체가 없음을 OM/SPS/AE 재검색 및 Appendix E BOB32 배선 예시 검토로 확인), LoadMatch_Max_Cable_Length(N/A — 케이블 손실 보상 DSP 기능 자체가 LA7.16 소스에 없음, LA7.16의 DSP 툴은 Array morphing/Air absorption compensation뿐). **(3) 재검색했으나 여전히 미확인(null)인 12건**: CMRR_Analog_Input, Digital_Input_Impedance(AES3 케이블 특성 임피던스 110 Ω 서술은 있으나 기기 자신의 입력 임피던스 스펙이 아님을 확인해 채택하지 않음), SN_Ratio_Analog_Input/SN_Ratio_Digital_Input, Output_Noise_Dynamic_Range_Detail, System_Start_Up_Time(OM p.21에 "a few seconds"라는 정성적 서술만 있어 수치화 불가), Time_To_Tone/Energy_Saving_Detail/AmpPresets_Detail, Storage_Temp_Range/Storage_Humidity, Mains_Current_Limiter_Range(자동 보호 기능 명칭은 있으나 사용자 조정형 % 범위 스펙 없음) — 이 12건은 모두 각주 문구를 "원본 미재조회" 표현에서 "실제 재검색 후 미발견" 근거로 전면 교체했다. 실값 변경이 없는 기존 나머지 Key/Value/각주는 일절 건드리지 않았다(Surgical Edit 원칙). Null Report 총 건수는 46건에서 32건으로 변경(-14). 스키마 섹션 구조 개편이 아니라 기존 Key들의 값/각주만 갱신되었으므로 SKILL v1.11 버저닝 규칙에 따라 Minor 버전(v2.4)으로 상향했다.
