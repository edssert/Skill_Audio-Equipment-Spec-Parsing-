# A10i Wide (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(A10i Focus의 30° 자매품)

**스켈레톤 근거**: `speakers/LA/A10i_Focus_v1.0.md`를 뼈대로 사용 — A10 Wide/Focus와 동일한 관계로, A10i Wide는 A10i Focus와 완전히 동일한 아키텍처(terminal block, 5종 앰프 호환)이며 고정 인클로저 각도만 30°(Focus는 10°)로 상이하다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | A10i Wide | - |
| Model_Number | null | - |
| Product_Category | medium throw line source (installation version) | - |
| Description | 2-way passive constant curvature WST 30° enclosure (installation version): 10" LF cone driver + 2.5" HF diaphragm compression driver, amplified by LA1.16i / LA2Xi / LA4X / LA7.16i / LA12X | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_AE_EN.docx("A10i Wide" 섹션); A10i_OM_EN.pdf(A10i owner's manual EN version 5.0) p.159 "A10i Wide specifications".

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 67 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 72 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 78 - 20000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | 137 dB(LA2Xi bridge/LA4X/LA7.16i/LA12X) / 133 dB(LA2Xi) / 132 dB(LA1.16i bridge) | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 30 (enclosure) / 70-110 symmetric or 90 asymmetric (L-Fins) | deg |
| Nominal_Directivity_Vertical | 30 | deg |
| DSP_Preset_Name | A10, A10_FI, A10_MO | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_AE_EN.docx "Technical requirements"; A10i_OM_EN.pdf p.159 "A10i Wide specifications".

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
| LF_Transducer | 10" cone driver | - |
| MF_Transducer | null | - |
| HF_Transducer | 2.5" diaphragm compression driver, neodymium | - |
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
| RMS_Power_Handling_Overall | 296 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_AE_EN.docx "Technical requirements"; A10i_OM_EN.pdf p.159 "A10i Wide specifications".

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x 4-point terminal block with push-in connection + connector sealing plate with cable gland | - |
| Link_Connector | 1 x 4-point terminal block with push-in connection + connector sealing plate with cable gland | - |
| Terminal_Block_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| Terminal_Block_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.21 "Connectors"(A10i Wide/Focus 공용 표).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA1.16i, LA2Xi, LA4X, LA7.16i, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Passive (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf "The A10i Wide/Focus enclosures are driven by the LA1.16i / LA2Xi / LA4X / LA7.16i / LA12X amplified controllers".

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | external rigging kits; M6 inserts(rigging plates), M8 inserts(A10-Ui), 4 M6 inserts(rigging accessory), 1 DIN580-compatible M8 insert(secondary safety) | - |
| Inter_Enclosure_Angles_deg | 30 | deg |
| Handles | null | count |
| Weight_Net | 18 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.159 "A10i Wide specifications".

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 569 | mm |
| Height_mm | 347 | mm |
| Depth_mm | 345 | mm |
| Dimensions_Raw [1] | 569 / 347 / 180 / 371 / 345 / 366 | mm |
| Cabinet_Material | premium grade Baltic beech and birch plywood | - |
| Front_Material | coated steel grill, acoustically neutral 3D fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C, pure white RAL 9010, custom RAL code on special order | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_AE_EN.docx "Physical data" - "Dimensions (W, H, D): 569 mm, 347 mm, 345 mm"; A10i_OM_EN.pdf p.160 "A10i Wide dimensions"(치수 도면).
**[1] Dimensions_Raw**: 도면 6개 숫자 중 569/347/345는 AE와 일치, 나머지(180=후면 리깅 플레이트 폭, 371/366=부가 치수)는 도면에서 직접 확인.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| A10i Wide line source (단독) | [A10] | 67 - 20000 | null | null |
| A10i Wide line source element (단일) | [A10_FI] | 67 - 20000 | null | null |
| A10i Wide with KS21i | [A10] + [KS21_100] | 31 - 20000 | 1 A10i Wide : 1 KS21i | null |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.51-53 "Loudspeaker configurations"(A10i Focus와 동일 구조 공유).

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [A10] or [A10_FI] or [A10_MO] + [KS21_100] | 0 | KS21i = 0 | A10i Wide = + / KS21i = + |
| [A10] or [A10_FI] + [KS21_100_C] | 5.5 | KS21i = 0 | A10i Wide = + / KS21i = + |
| [A10] or [A10_FI] + [KS21_100_Cx] | 0 | KS21i = 0 | A10i Wide = + / KS21i = + |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.53 "Pre-alignment delays"(A10i Focus와 공용 표, 동일 수치). 극성은 A10i Focus와 동일 페이지에서 이미지 렌더링으로 확인.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| vertical array | A10i-BUMP + rigging plates | 8 | 8 |
| vertical array | A10-Ui | 1 | 1 |
| vertical array | A10-Ui + A10i-ULINK II | 2 | 2 |
| vertical array with pullback | A10i-BUMP + rigging plates + A10i-RIGBAR | 8 | 8 |
| vertical array with pullback | A10i-RIGBAR x2 + rigging plates | 12 | 12 |
| stacked vertical array | Ai-FIXBRACKET + rigging plates | 4 | 4 |
| stacked vertical array with angle adjustment | A10i-TILTBRACKET + rigging plates | 4 | 4 |
| stacked on KS21i | Ai-FIXBRACKET + rigging plates | 4 A10i Wide | 4 KS21i |
| stacked on KS21i, angle adjustment | Ai-FIXBRACKET + A10i-TILT + rigging plates | 4 A10i Wide | 4 KS21i |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | null | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.49-50 "Mechanical safety"(A10i Focus와 공용 챕터).
**A10i-BUMP+rigging plates+A10i-RIGBAR 행**: 원문 "A10i Wide: 8 / A10i Focus: 12 / A10i Wide/Focus: 12"에서 A10i Wide 값(8) 채택(Focus의 12와 다름).

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/MF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Handles, Rigging_Components_Material, Max_Wind_Load, preset_guide_and_matching(Minimum_Line_Length 전 행) — 15건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load — 5건. (PA_COM_Pinout_*/SpeakON_Pinout_* 등 타 커넥터 고유 Key는 A10i Wide 자신의 Terminal_Block_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 20건 (미확인 15건 + 비적용 5건). 확정적 비존재(0/No)로 명시한 항목은 0건.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(A10i Focus의 30° 자매품). A10i_Focus_v1.0.md를 스켈레톤으로 사용, A10i_AE_EN.docx("A10i Wide" 섹션) + A10i_OM_EN.pdf(공용 매뉴얼) 통합. Focus 대비 인클로저 각도(30°)와 스펙 수치만 상이. |
| v1.1 | 사용자 피드백(2026-07-17) — delay_defaults/mechanical_safety/preset_guide_and_matching을 원문 직접 조사로 실값 채움(A10i Focus v1.1과 동일 라운드). A10i Wide 고유값(A10i-BUMP+rigging plates+A10i-RIGBAR=8)을 Focus(12)와 구분해 반영. |
| v1.2 | Dimensions_Raw의 "시간 배분상 별도 추출하지 않음" 방치를 수정(SKILL v1.17 위반) — A10i_OM_EN.pdf p.160 "A10i Wide dimensions" 도면을 이미지 렌더링해 6개 수치(569/347/180/371/345/366mm) 확보. |
| v1.3 | delay_defaults 표의 컬럼명 `K1_Delay_ms`를 `Primary_Element_Delay_ms`로 전면 개명(SKILL v1.18) — 값 변경 없음(사용자 지적 2026-07-17). |
