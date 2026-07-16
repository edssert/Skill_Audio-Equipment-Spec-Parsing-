# Kiva II (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1 (동일 브랜드 이기종, Kara II 대비 — 단, 아키텍처 축 하나가 근본적으로 다름)

**스켈레톤 근거**: `speakers/LA/Kara_II_v1.0.md`를 뼈대로 사용하되, **핵심 아키텍처가 다르다** — Kiva II는 이 프로젝트에서 처음 등장한 **passive(패시브) 크로스오버** L-Acoustics 제품이다. K1/K2/K3/Kara II/Kara IIi는 모두 자체 OM 커넥터 표에 "Internal pinout for L-Acoustics 2-way **active** enclosures"로 명시된 반면, Kiva II는 "Internal pinout for L-Acoustics 2-way **passive** enclosures"로 명시되며, speakON 2개 채널 중 1개(1+/1-)만 LF+HF 신호를 함께 실어나르고 2번째 채널은 "Not linked"(LINK 전용, 신호 없음)이다 — 즉 앰프가 대역 분리 없이 1채널만 공급하고, 인클로저 내부의 패시브 크로스오버가 LF/HF로 나눈다. 이 때문에 Nominal impedance와 RMS power handling도 대역별이 아닌 단일 통합값으로 보고된다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | Kiva II | - |
| Model_Number | null | - |
| Product_Category | long throw line source (colinear) | - |
| Description | 2-way passive enclosure with two weather-resistant premium 6.5 in transducers and high output 1.75 in diaphragm compression driver, 110 deg horizontal coverage | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kiva_II_AE_EN.docx; Kiva_II_OM_EN_3.0.pdf(Kiva II owner's manual EN version 3.0).
**Product_Category**: docx short description "2-way passive colinear source" — "colinear"(동일 수직축 정렬 방식) 표현은 K1/K2/K3/Kara 계열에는 없던 용어, Kiva II 고유 설계 개념으로 원문 그대로 채택.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 70 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 75 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 84 - 20000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | 138 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 100 symmetrical | deg |
| Nominal_Directivity_Vertical | 15 (single), depending on the number of elements and array curvature | deg |
| DSP_Preset_Name | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kiva_II_AE_EN.docx "Technical requirements".
**Nominal_Directivity_Horizontal_deg 표기 차이**: docx short description은 "100° horizontal waveguide directivity"라 하고 본문 Description은 "110 degrees of horizontal coverage"라 하며, Technical requirements의 Coverage 항목은 "Waveguide directivity: 100° symmetrical"이라 한다 — 100°(waveguide 고유값, Technical requirements 채택)와 110°(전체 coverage 서술값) 두 수치가 문서 내에서 다르게 등장하는 것으로 보이나, Technical requirements 섹션이 이 프로젝트의 구조화 데이터 채택 기준(스펙 표 우선)이므로 100°를 채택하고 110° 언급은 이 각주에 병기.
**DSP_Preset_Name**: docx/OM 어디에도 [KIVA II ...] 형태의 명명 프리셋이 명시적으로 발견되지 않음(시간 제약상 전량 확인은 못함) — 미확인.

## signal_processing

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | null | - |
| HFC_Function_Settings | null | - |
| Coupling_Function_Range | null | - |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: K1/K2/K3/Kara II와 동일.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 6.5" cone driver | - |
| MF_Transducer | null | - |
| HF_Transducer | 1.75" diaphragm compression driver | - |
| LF_Acoustical_Load | bass-reflex | - |
| MF_Acoustical_Load | null | - |
| HF_Acoustical_Load | null | - |
| Passive_Crossover_Network [1] | Yes | - |
| LF_Nominal_Impedance | null | Ohm |
| MF_Nominal_Impedance | null | Ohm |
| HF_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall [2] | 16 | Ohm |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall [2] | 186 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: Kiva_II_AE_EN.docx "Technical requirements"; Kiva_II_OM_EN_3.0.pdf p.12 "Connectors"("Internal pinout for L-Acoustics 2-way passive enclosures").
**[1] Passive_Crossover_Network=Yes**: OM 커넥터 표가 "2-way passive enclosures"로 명시하고, speakON 2채널 중 1채널(1+/1-)만 신호를 나르며 2채널은 "Not linked"(연결 없음, LINK 전용) — 앰프는 대역 분리 없이 단일 채널만 공급하고 인클로저 내부에서 패시브 크로스오버가 LF/HF로 분리하는 구조로 확인. K1/K2/K3/Kara II(모두 "active enclosures" 표기 + LF/HF 별도 채널)와 명확히 대조.
**[2] Nominal_Impedance_Overall/RMS_Power_Handling_Overall(신규 Key)**: Kiva II는 단일 채널로 LF+HF를 함께 구동하므로 임피던스와 파워 핸들링이 대역별이 아닌 통합값 하나로만 보고된다(docx 원문: "Nominal impedance: 16 Ohm", "RMS power handling: 186 W" — LF/HF 구분 없음). 이는 K1 계열의 LF/MF/HF Key 구조로 표현할 수 없어 신규 Key를 만들었다 — 이 Key는 "단일 채널 패시브 크로스오버 아키텍처"라는 브랜드 무관 범용 개념(어느 브랜드든 이런 구조면 통합값으로 보고할 것)이므로 다른 제품 파일에도 null로 동기화 대상이다(GSL의 Front_LF류처럼 브랜드 고유 배선명이 아님).
**LF_Nominal_Impedance/MF/HF 및 RMS_Power_Handling_LF/MF/HF 비적용 사유**: Kiva II 자신은 대역별 값을 보고하지 않아(단일 통합값만 존재) 이 Key들은 비적용.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 2 x 4-point speakON (IN/LINK interchangeable, only 1 channel carries signal) | - |
| Link_Connector | 2 x 4-point speakON (IN/LINK interchangeable, only 1 channel carries signal) | - |
| SpeakON_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| SpeakON_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kiva_II_OM_EN_3.0.pdf p.12 "Connectors"; Kiva_II_AE_EN.docx "Connectors: 2 x 4-point speakON"(교차검증 일치).
**SpeakON_Pinout_1 표기**: 원문 표는 대역 라벨 없이 단순 "+ / -"로만 표기(K1/K3의 "LF+/LF-" 같은 대역 라벨이 없음) — 패시브 크로스오버로 두 대역이 함께 실리므로 대역별 라벨을 붙일 수 없어 원문 그대로 보존.

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA2Xi, LA4X, LA8, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Passive (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kiva_II_OM_EN_3.0.pdf "Kiva II is driven by the LA2Xi / LA4X / LA8 / LA12X amplified controllers"(복수 위치 확인).
**Crossover_Type=Passive**: transducers 섹션의 Passive_Crossover_Network=Yes 판정과 정합.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | 3-point captive rigging system (rigging arm + spring-loaded pin at back, two pairs of rigging axis at front) | - |
| Inter_Enclosure_Angles_deg | null | deg |
| Handles | 2 | count |
| Weight_Net | 14 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: Kiva_II_OM_EN_3.0.pdf p.13 "Rigging system description"; Kiva_II_AE_EN.docx "Description"("two handles"), "Weight (net): 14 kg".
**Rigging_System_Type**: K1/K2/K3/Kara II 모두 "4-point" 리깅인 반면 Kiva II는 "3-point"(3점) — 소형 제품 특성 반영, 원문 그대로 보존.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 525 | mm |
| Height_mm | 202 | mm |
| Depth_mm | 357 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | composite sandwich structure (moisture-resistant composite material) | - |
| Front_Material | composite grill, acoustically transparent fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C, pure white RAL 9010, custom RAL code on special order | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kiva_II_AE_EN.docx "Physical data".
**Cabinet_Material**: K1~Kara IIi가 모두 "Baltic birch plywood"(자작나무 합판) 계열인 반면 Kiva II는 "composite"(복합소재) — 소형/경량 설계를 위한 재질 차이로 보이며, 원문 그대로 보존(임의로 통일하지 않음).

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: 시간 제약상 미확보.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: 시간 제약상 미확보.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown | KIBU-SB | 8 | 20 |
| flown | KIBU II | 8 | 20 |
| ceiling-mounted | KIET II | null | 3 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | 6 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: Kiva_II_OM_EN_3.0.pdf "Mechanical safety > Flown configurations"; Safety 섹션(Max_Wind_Load, "6 bft").
**KIET II 행**: 원문에 상한(3)만 명시, safe limit 별도 없음 — null.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, DSP_Preset_Name, HF_Acoustical_Load, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Inter_Enclosure_Angles_deg, Rigging_Components_Material, Dimensions_Raw(상위 호환), preset_guide_and_matching(전 항목), delay_defaults(전 항목), mechanical_safety(KIET II Safe_Limit) — 15건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load, MF_Nominal_Impedance, LF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/MF/HF(단일 통합값만 존재) — 11건. (PA_COM_Pinout_*/Terminal_Block_Pinout_* 등 타 커넥터 고유 Key는 Kiva II 자신의 SpeakON_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 28건 (미확인 15건 + 비적용 13건). 확정적 비존재(0/No)로 명시한 항목은 0건 — Passive_Crossover_Network는 "Yes"로 실값 확보.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리 Phase 3-1(L-Acoustics 동일 브랜드, Kara II를 스켈레톤으로 사용). **이 카테고리 내 최초의 패시브 크로스오버 제품** — K1~Kara IIi가 모두 "active enclosures"(대역별 독립 채널)인 반면 Kiva II는 "passive enclosures"(단일 채널 + 내부 패시브 크로스오버)로 확인, Passive_Crossover_Network=Yes(K1~Kara IIi는 전부 No였음). 신규 Key Nominal_Impedance_Overall/RMS_Power_Handling_Overall 도입 — 단일 채널 패시브 아키텍처라는 범용 개념이므로 타 제품 파일에도 null로 동기화 필요(다음 커밋에서 일괄 반영 예정). |

**참고(커넥터 핀아웃 Null Report 정확도)**: 위 총계는 이 파일이 처음 작성된 시점 기준이며, 이후 타 커넥터 모델 고유 Key(PA_COM_Pinout_*/SpeakON_Pinout_*/Terminal_Block_Pinout_* 중 이 제품 자신의 실제 커넥터가 아닌 것들)를 전부 삭제하는 후속 정리가 있었다(2026-07-17) — 삭제된 Key는 null 목록에도 더 이상 포함되지 않는다. 정확한 현재 Key 구성은 각 섹션 표를 직접 참조할 것.
| v1.1 | PA-COM/터미널 블록 커넥터 Key 삭제(사용자 피드백 2026-07-17) — 제품 자신의 실제 커넥터가 아닌 타 커넥터 모델(PA-COM/speakON/terminal block 등) 고유 핀아웃 Key를 null 목록에서도 완전히 제거. 이 제품의 실제 커넥터 핀아웃은 아래 표기된 자기 자신의 Key만으로 온전히 표현됨. |
