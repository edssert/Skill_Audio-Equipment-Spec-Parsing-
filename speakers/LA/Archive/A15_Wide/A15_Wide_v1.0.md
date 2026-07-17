# A15 Wide (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(A15 Focus의 30° 자매품)

**스켈레톤 근거**: `speakers/LA/A15_Focus_v1.0.md`를 뼈대로 사용 — A15 Wide는 A15 Focus와 완전히 동일한 아키텍처이며 고정 인클로저 각도만 30°(Focus는 10°)로 상이하다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | A15 Wide | - |
| Model_Number | null | - |
| Product_Category | medium throw line source | - |
| Description | 2-way passive constant curvature WST 30° enclosure: 15" LF cone driver + 3" HF diaphragm compression driver, amplified by LA2Xi / LA4X / LA7.16 / LA7.16i / LA12X | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_AE_EN.docx("A15 Wide" 섹션); A15_OM_EN.pdf(A15 owner's manual EN version 3.3) p.138 "A15 Wide specifications".

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 42 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 47 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 52 - 19000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | 141 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 30 (enclosure) / 70-110 symmetric or 90 asymmetric (L-Fins) | deg |
| Nominal_Directivity_Vertical | 30 | deg |
| DSP_Preset_Name | A15, A15_FI, A15_MO | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_AE_EN.docx "Technical requirements"; A15_OM_EN.pdf p.138 "A15 Wide specifications".
**Frequency_Response_3dB_Hz 상한 19000**: 원문 그대로 채택 — 다른 제품들의 상한(20000)과 달리 A15 Wide만 19kHz로 명시(오기재 가능성도 있으나 임의 정정하지 않음).

## signal_processing

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | null | - |
| HFC_Function_Settings | null | - |
| Coupling_Function_Range | null | - |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: K1 계열과 동일.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 15" neodymium cone driver | - |
| MF_Transducer | null | - |
| HF_Transducer | 3" neodymium diaphragm compression driver | - |
| LF_Acoustical_Load | bass-reflex, L-Vents | - |
| MF_Acoustical_Load | null | - |
| HF_Acoustical_Load | DOSC waveguide, L-Fins | - |
| Passive_Crossover_Network | Yes | - |
| LF_Nominal_Impedance | null | Ohm |
| MF_Nominal_Impedance | null | Ohm |
| HF_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall | 8 | Ohm |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | 446 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_AE_EN.docx "Technical requirements"; A15_OM_EN.pdf p.138 "A15 Wide specifications".

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 2 x 4-point speakON (IN/LINK interchangeable, only 1 channel carries signal) | - |
| Link_Connector | 2 x 4-point speakON (IN/LINK interchangeable, only 1 channel carries signal) | - |
| SpeakON_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| SpeakON_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf "Connectors"(A15 Wide/Focus 공용 표).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA2Xi, LA4X, LA7.16, LA7.16i, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Passive (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf "The A15 Wide/Focus enclosures are driven by the LA2Xi / LA4X / LA7.16 / LA7.16i / LA12X amplified controllers".

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | flush-fitting 2-point rigging system(rotating rigging arm + spring-loaded pin) | - |
| Inter_Enclosure_Angles_deg | 30 | deg |
| Handles | 2 | count |
| Weight_Net | 33 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf p.138 "A15 Wide specifications"("Rigging and handling").

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 762 | mm |
| Height_mm | 424 | mm |
| Depth_mm | 494 | mm |
| Dimensions_Raw [1] | 762 / 424 / 182 / 494 | mm |
| Cabinet_Material | premium grade Baltic beech and birch plywood | - |
| Front_Material | coated steel grill, acoustically neutral 3D fabric | - |
| Rigging_Components_Material | high grade steel with anti-corrosion coating | - |
| Finish_Color | dark grey brown Pantone 426 C | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_AE_EN.docx "Physical data" - "Dimensions (W, H/h, D): 762 mm, 424 mm/182 mm, 494 mm".
**[1] Height 이중 표기**: A10 Wide와 동일 사유 — 웨지형 인클로저의 앞/뒤 높이(424mm/182mm) 병기, Height_mm에는 대표값(424)만 채택.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| A15 Wide line source (단독) | [A15] | 42 - 20000 | null | null |
| A15 Wide line source element (단일) | [A15_FI] | 42 - 20000 | null | null |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf "Loudspeaker configurations"(A15 Focus와 동일 구조 공유). KS21 조합 상세는 시간 배분상 미확인.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: A15 Focus와 동일 사유.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| null | null | null | null |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | null | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf "Mechanical safety"(A15 Focus와 공용). 상세 표는 시간 배분상 미확인.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/MF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, preset_guide_and_matching(KS21 조합, Recommended_Ratio/Minimum_Line_Length), delay_defaults(전 항목), mechanical_safety(전 항목) — 16건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load — 5건. (PA_COM_Pinout_*/Terminal_Block_Pinout_* 등 타 커넥터 고유 Key는 A15 Wide 자신의 SpeakON_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 21건 (미확인 16건 + 비적용 5건). 확정적 비존재(0/No)로 명시한 항목은 0건.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(A15 Focus의 30° 자매품). A15_Focus_v1.0.md를 스켈레톤으로 사용, A15_AE_EN.docx("A15 Wide" 섹션) + A15_OM_EN.pdf(공용 매뉴얼) 통합. Focus 대비 인클로저 각도(30°)와 스펙 수치만 상이. |
