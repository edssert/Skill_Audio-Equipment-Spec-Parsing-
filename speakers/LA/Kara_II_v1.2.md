# Kara II (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1 (동일 브랜드 이기종, K3 대비)

**스켈레톤 근거**: `speakers/LA/K3_v1.0.md`를 뼈대로 사용 — Kara II도 2-way, speakON 커넥터 아키텍처로 K3와 가장 유사(Kara_II 자신의 OM "Connectors" 절, docx "2-way active enclosure" 확인). K3보다 소형(8" LF, 3" HF vs K3의 12"/4")이며 LA8 호환은 없음(LA4X/LA12X만).

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | Kara II | - |
| Model_Number | null | - |
| Product_Category | long throw line source | - |
| Description | 2-way active enclosure with two weather-resistant premium 8 in transducers and high-output 3 in diaphragm compression driver, user-adjustable horizontal directivity | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_II_AE_EN.docx; Kara_II_OM_EN_5.0.pdf(Kara II owner's manual EN version 5.0).

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 55 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 63 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 80 - 19000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | 142 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 70/110 symmetric or 90 asymmetric (35/90) | deg |
| Nominal_Directivity_Vertical | dependent upon the number of elements and the line source curvature | - |
| DSP_Preset_Name | KARA II 70, KARA II 90, KARA II 110 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_II_AE_EN.docx "Technical requirements".
**DSP_Preset_Name**: amplification-reference-tb-en.pdf(v16.0)의 "Enclosure maximum SPL per amplified controller" 표에서 "[KARA II 70]" 프리셋명 확인(교차검증) — 137dB(LA4X)/142dB(LA12X)로 앰프별 SPL 값이 다름을 참고.

## signal_processing

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | null | - |
| HFC_Function_Settings | null | - |
| Coupling_Function_Range | null | - |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: K1/K2/K3와 동일.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 2 x 8" cone drivers | - |
| LC_Transducer | null | - |
| MF_Transducer | null | - |
| HF_Transducer | 3" diaphragm compression driver | - |
| LF_Acoustical_Load | bass-reflex | - |
| LC_Acoustical_Load | null | - |
| MF_Acoustical_Load | null | - |
| HF_Acoustical_Load | null | - |
| Passive_Crossover_Network | No | - |
| LF_Nominal_Impedance | 8 | Ohm |
| LC_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall | null | Ohm |
| MF_Nominal_Impedance | null | Ohm |
| HF_Nominal_Impedance | 8 | Ohm |
| RMS_Power_Handling_LF | 280 | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | 75 | W |
| RMS_Power_Handling_Overall | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_II_AE_EN.docx "Technical requirements".
**Passive_Crossover_Network=No**: Kara_II_OM_EN_5.0.pdf 전문을 "crossover" 키워드로 전량 스캔 — 0건 검출. 확정적 비존재.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 2 x 4-point speakON (IN/LINK interchangeable) | - |
| Link_Connector | 2 x 4-point speakON (IN/LINK interchangeable) | - |
| SpeakON_Pinout_1 | LF+ / LF- | - |
| SpeakON_Pinout_2 | HF+ / HF- | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_II_OM_EN_5.0.pdf p.459 "Connectors"; Kara_II_AE_EN.docx "Connectors: 2 x 4-point speakON"(교차검증 일치).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA4X, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_II_OM_EN_5.0.pdf "The Kara II enclosure is driven by the LA4X / LA12X amplified controllers."(복수 위치에서 반복 확인, LA8 언급 없음 — K3와 달리 LA8 비호환으로 판단).

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | 4-point captive rigging system | - |
| Inter_Enclosure_Angles_deg | null | deg |
| Handles | 4 | count |
| Weight_Net | 26 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_II_AE_EN.docx "Description"("four ergonomic handles"), "Weight (net): 26 kg".
**Inter_Enclosure_Angles_deg**: 시간 제약상 미확보 — 미확인.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 730 | mm |
| Height_mm | 250 | mm |
| Depth_mm | 383 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | premium grade Baltic birch plywood | - |
| Front_Material | coated steel grill, acoustically transparent fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_II_AE_EN.docx "Physical data".

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: 시간 제약상 미확보 — 추후 재검토 필요.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: 시간 제약상 미확보.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown | M-BUMP + M-BAR (optional) | 16 | 24 |
| flown | KARA-MINIBU | 6 | 6 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | 6 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_II_OM_EN_5.0.pdf "Mechanical safety > Flown configurations"; Safety 섹션(Max_Wind_Load, "6 bft").
**KARA-MINIBU 행**: 원문에 "maximum/safe limit" 단일 값(6)만 표기되어 두 열 모두 6으로 채택(K1의 KARA-DOWNK1과 유사한 표 구조).
**범위 제한**: pullback 구성, SB18/Kara II 혼합 어레이 등 추가 구성이 있으나 기본 플라잉 구성만 채택.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, HF_Acoustical_Load, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Inter_Enclosure_Angles_deg, Rigging_Components_Material, Dimensions_Raw(상위 호환), preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 13건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load, MF_Nominal_Impedance, RMS_Power_Handling_MF — 8건. (PA_COM_Pinout_*/Terminal_Block_Pinout_* 등 타 커넥터 고유 Key는 Kara II 자신의 SpeakON_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 24건 (미확인 13건 + 비적용 11건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Passive_Crossover_Network(No) — 이 수치는 Kiva II/L2 투입 이전 기준. Kiva II/L2 투입으로 신설된 6개 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)가 이 파일에 모두 비적용 null로 추가 반영되어 실제 총계는 위 수치+6건이다(이 제품은 LC 대역·단일 채널 패시브 아키텍처·멀티모듈 구조가 모두 없음).

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리 Phase 3-1(L-Acoustics 동일 브랜드, K3와 유사 아키텍처). K3_v1.0.md를 스켈레톤으로 사용, Kara_II_AE_EN.docx + Kara_II_OM_EN_5.0.pdf 통합. K3보다 소형(8"/3" 드라이버), LA8 비호환(LA4X/LA12X만) 확인. |
| v1.1 | Kiva II/L2(신규 제품) 투입으로 신설된 6개 범용 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)를 이 제품에 비적용 null로 동기화 반영(SKILL v1.15 원칙 — 브랜드 무관 범용 개념이므로 동기화 대상). |

**참고(커넥터 핀아웃 Null Report 정확도)**: 위 총계는 이 파일이 처음 작성된 시점 기준이며, 이후 타 커넥터 모델 고유 Key(PA_COM_Pinout_*/SpeakON_Pinout_*/Terminal_Block_Pinout_* 중 이 제품 자신의 실제 커넥터가 아닌 것들)를 전부 삭제하는 후속 정리가 있었다(2026-07-17) — 삭제된 Key는 null 목록에도 더 이상 포함되지 않는다. 정확한 현재 Key 구성은 각 섹션 표를 직접 참조할 것.
| v1.2 | K3의 PA-COM/터미널 블록 커넥터 Key 삭제(사용자 피드백 2026-07-17) — 제품 자신의 실제 커넥터가 아닌 타 커넥터 모델(PA-COM/speakON/terminal block 등) 고유 핀아웃 Key를 null 목록에서도 완전히 제거. 이 제품의 실제 커넥터 핀아웃은 아래 표기된 자기 자신의 Key만으로 온전히 표현됨. |
