# A15i Focus (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(A15 Focus의 install 파생형)

**스켈레톤 근거**: `speakers/LA/A15_Focus_v1.0.md`를 뼈대로 사용 — A15i Focus는 A15 Focus와 동일 아키텍처이나 커넥터가 4-point terminal block(push-in)이다. 앰프 호환성은 A15와 동일(LA2Xi/LA4X/LA7.16/LA7.16i/LA12X, A10i와 달리 LA1.16i 없음).

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | A15i Focus | - |
| Model_Number | null | - |
| Product_Category | medium throw line source (installation version) | - |
| Description | 2-way passive constant curvature WST 10° enclosure (installation version): 15" LF cone driver + 3" HF diaphragm compression driver, amplified by LA2Xi / LA4X / LA7.16 / LA7.16i / LA12X | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_AE_EN.docx("A15i Focus" 섹션); A15i_OM_EN.pdf(A15i owner's manual EN version 5.1) p.145 "A15i Focus specifications".

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 41 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 44 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 47 - 20000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak [1] | 144 dB(LA2Xi bridge/LA4X/LA7.16/LA7.16i/LA12X) / 139 dB(LA2Xi) | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 10 (enclosure) / 70-110 symmetric or 90 asymmetric (L-Fins) | deg |
| Nominal_Directivity_Vertical | 10 | deg |
| DSP_Preset_Name | A15, A15_FI, A15_MO | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_AE_EN.docx "Technical requirements"; A15i_OM_EN.pdf p.145 "A15i Focus specifications".
**[1] Max_SPL_Peak 앰프별 2단계**: A15(단일값 144dB)와 달리 A15i는 앰프 조건별 2개 값 명시.

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
| LF_Transducer | 15" cone driver | - |
| MF_Transducer | null | - |
| HF_Transducer | 3" diaphragm compression driver, neodymium | - |
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

**출처**: A15i_AE_EN.docx "Technical requirements"; A15i_OM_EN.pdf p.145 "A15i Focus specifications".

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x 4-point terminal block with push-in connection | - |
| Link_Connector | 1 x 4-point terminal block with push-in connection | - |
| Terminal_Block_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| Terminal_Block_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf "Connectors"(A15i Wide/Focus 공용 표, A10i와 동일 구조로 추정).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA2Xi, LA4X, LA7.16, LA7.16i, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Passive (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf "The A15i Wide/Focus enclosures are driven by the LA2Xi / LA4X / LA7.16 / LA7.16i / LA12X amplified controllers".

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | external rigging kits; M6 inserts(rigging plates), M8 inserts(A15KS-Ui), 4 M6 inserts(rigging accessory), 1 DIN580-compatible M8 insert(secondary safety) | - |
| Inter_Enclosure_Angles_deg | 10 | deg |
| Handles | null | count |
| Weight_Net [1] | 32 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf p.145 "A15i Focus specifications".
**[1] Weight_Net 소스 간 충돌**: AE_EN.docx는 33kg, OM은 32kg으로 서로 다름 — OM 스펙 표를 대표값으로 채택(L-Acoustics 브랜드 OM 우선 원칙), AE의 33kg은 이 각주에 병기.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 752 | mm |
| Height_mm | 427 | mm |
| Depth_mm | 490 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | premium grade Baltic beech and birch plywood | - |
| Front_Material | coated steel grill, acoustically neutral 3D fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C, pure white RAL 9010, custom RAL code on special order | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_AE_EN.docx "Physical data" - "Dimensions (W, H, D): 752 mm, 427 mm, 490 mm".

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| A15i Focus line source (단독) | [A15] | 41 - 20000 | null | null |
| A15i Focus line source element (단일) | [A15_FI] | 41 - 20000 | null | null |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf "Loudspeaker configurations"(KS21i 조합 상세는 시간 배분상 미확인).

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: 남은 제품 전체 조사 일정상 상세 조사 미수행.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| null | null | null | null |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | null | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf "Mechanical safety"("2006/42/EC Machinery Directive", "safety factor of 4"). 상세 표는 시간 배분상 미확인.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/MF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Handles, Dimensions_Raw, Rigging_Components_Material, preset_guide_and_matching(KS21i 조합, Recommended_Ratio/Minimum_Line_Length), delay_defaults(전 항목), mechanical_safety(전 항목) — 18건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load — 5건. (PA_COM_Pinout_*/SpeakON_Pinout_* 등 타 커넥터 고유 Key는 A15i Focus 자신의 Terminal_Block_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 23건 (미확인 18건 + 비적용 5건). 확정적 비존재(0/No)로 명시한 항목은 0건.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(A15 Focus의 install 파생형). A15_Focus_v1.0.md를 스켈레톤으로 사용, A15i_AE_EN.docx("A15i Focus" 섹션) + A15i_OM_EN.pdf(공용 매뉴얼) 통합. 커넥터(terminal block), 앰프별 2단계 Max SPL 확인. AE/OM 간 중량 값 충돌(33kg vs 32kg) 발견, OM 우선 원칙으로 해결(양쪽 값 보존). |
