# A15i Wide (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(A15i Focus의 30° 자매품)

**스켈레톤 근거**: `speakers/LA/A15i_Focus_v1.0.md`를 뼈대로 사용 — A15 Wide/Focus와 동일 관계.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | A15i Wide | - |
| Model_Number | null | - |
| Product_Category | medium throw line source (installation version) | - |
| Description | 2-way passive constant curvature WST 30° enclosure (installation version): 15" LF cone driver + 3" HF diaphragm compression driver, amplified by LA2Xi / LA4X / LA7.16 / LA7.16i / LA12X | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_AE_EN.docx("A15i Wide" 섹션); A15i_OM_EN.pdf(A15i owner's manual EN version 5.1) p.147 "A15i Wide specifications".

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 42 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 47 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 52 - 19000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | 141 dB(LA2Xi bridge/LA4X/LA7.16/LA7.16i/LA12X) / 136 dB(LA2Xi) | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 30 (enclosure) / 70-110 symmetric or 90 asymmetric (L-Fins) | deg |
| Nominal_Directivity_Vertical | 30 | deg |
| DSP_Preset_Name | A15, A15_FI, A15_MO | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_AE_EN.docx "Technical requirements"; A15i_OM_EN.pdf p.147 "A15i Wide specifications"(정확한 페이지 번호는 인접 Focus 표(p.145) 기준 추정).

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
| HF_Transducer | 3" diaphragm compression driver, neodymium | - |
| LF_Acoustical_Load | bass-reflex, L-Vents | - |
| HF_Acoustical_Load | DOSC waveguide, L-Fins | - |
| Passive_Crossover_Network | Yes | - |
| LF_Nominal_Impedance | null | Ohm |
| HF_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall | 8 | Ohm |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | 446 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_AE_EN.docx "Technical requirements"; A15i_OM_EN.pdf "A15i Wide specifications".

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x 4-point terminal block with push-in connection | - |
| Link_Connector | 1 x 4-point terminal block with push-in connection | - |
| Terminal_Block_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| Terminal_Block_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf "Connectors"(A15i Wide/Focus 공용 표).

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
| Inter_Enclosure_Angles_deg | 30 | deg |
| Handles | null | count |
| Weight_Net | 29 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf "A15i Wide specifications". AE_EN.docx도 동일하게 29kg 명시(A15i Focus의 AE/OM 충돌과 달리 여기는 일치).

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 752 | mm |
| Height_mm | 424 | mm |
| Depth_mm | 494 | mm |
| Dimensions_Raw [1] | 752 / 424 / 180 / 494 | mm |
| Cabinet_Material | premium grade Baltic beech and birch plywood | - |
| Front_Material | coated steel grill, acoustically neutral 3D fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C, pure white RAL 9010, custom RAL code on special order | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_AE_EN.docx "Physical data" - "Dimensions (W, H/h, D): 752 mm, 424 mm/180 mm, 494 mm".
**[1] Height 이중 표기**: A15 Wide와 동일 사유(웨지형 인클로저 앞/뒤 높이 424mm/180mm).

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| A15i Wide line source (단독) | [A15] | 42 - 20000 | null | null |
| A15i Wide line source element (단일) | [A15_FI] | 43 - 20000 | null | null |
| A15i Wide with KS21i | [A15] + [KS21_60] | 29 - 20000 | 1 A15i Wide : 1 KS21i | null |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf p.47-50 "Loudspeaker configurations"(A15i Focus와 동일 구조 공유).

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [A15] or [A15_FI] or [A15_MO] + [KS21_60] | 0 | KS21i = 2.3 | A15i Wide = + / KS21i = + |
| [A15] or [A15_FI] + [KS21_60_C] | 9 | KS21i = 0 | A15i Wide = + / KS21i = - |
| [A15] or [A15_FI] + [KS21_60_Cx] | 8 | KS21i = 0 | A15i Wide = + / KS21i = + |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf p.49-50 "Pre-alignment delays"(A15i Focus와 공용 표, 동일 수치). 극성은 A15i Focus와 동일 페이지에서 이미지 렌더링으로 확인.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| vertical array | A15i-BUMP + M-BARi (optional) + rigging plates | 8 | 8 |
| vertical array | A15KS-Ui | 1 | 1 |
| vertical array | A15KS-Ui + A15i-ULINK II | 2 | 2 |
| vertical array with pullback | A15i-BUMP + rigging plates + A15i-RIGBAR | 6 | 6 |
| vertical array with pullback | A15i-RIGBAR x2 + rigging plates | 8 | 8 |
| stacked vertical array | Ai-FIXBRACKET + rigging plates | 4 | 4 |
| stacked vertical array with angle adjustment | A15i-TILTBRACKET + rigging plates | 4 | 4 |
| stacked on KS21i, pullback | A15i-BUMP + A15i-TILT (optional) + rigging plates + A15i-RIGBAR | 4 A15i Wide | 4 KS21i |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | null | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf p.44-45 "Mechanical safety"(A15i Focus와 공용 챕터).
**A15i-BUMP+rigging plates+A15i-RIGBAR 행**: 원문 "A15i Wide: 6 / A15i Focus: 12 / A15i Wide/Focus: 12"에서 A15i Wide 값(6) 채택(Focus의 12와 다름).

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Handles, Rigging_Components_Material, Max_Wind_Load, preset_guide_and_matching(Minimum_Line_Length 전 행) — 14건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range — 3건. (PA_COM_Pinout_*/SpeakON_Pinout_* 등 타 커넥터 고유 Key는 A15i Wide 자신의 Terminal_Block_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 17건 (미확인 14건 + 비적용 3건). 확정적 비존재(0/No)로 명시한 항목은 0건. (v1.1: delay_defaults와 mechanical_safety를 원문 직접 조사로 실값 채움 — 사용자 피드백 2026-07-17.)

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(A15i Focus의 30° 자매품). A15i_Focus_v1.0.md를 스켈레톤으로 사용, A15i_AE_EN.docx("A15i Wide" 섹션) + A15i_OM_EN.pdf(공용 매뉴얼) 통합. |
| v1.1 | 사용자 피드백(2026-07-17) — delay_defaults/mechanical_safety/preset_guide_and_matching을 원문 직접 조사로 실값 채움(A15i Focus v1.1과 동일 라운드). A15i Wide 고유값(A15i-BUMP+rigging plates+A15i-RIGBAR=6)을 Focus(12)와 구분해 반영. |
| v1.2 | delay_defaults 표의 컬럼명 `K1_Delay_ms`를 `Primary_Element_Delay_ms`로 전면 개명(SKILL v1.18) — 값 변경 없음(사용자 지적 2026-07-17). |
| v1.3 | MF_Transducer/MF_Acoustical_Load/MF_Nominal_Impedance/RMS_Power_Handling_MF 4개 Key 삭제(SKILL v1.19) — 이 제품은 확인된 2-way 구조라 MF 대역 드라이버 자체가 없으므로, null 동기화 대상이 아니라 삭제 대상으로 재분류(K1 v1.4의 기존 반대 판단을 뒤집는 정책 변경, GSL의 Front_LF_Transducer와 동일 원칙 적용). MF_Nominal_Impedance가 미확인 목록의 결합형 "RMS_Power_Handling_LF/MF/HF" 항목과 별도 표기되어 있어 실제 삭제분은 미확인 -1(15→14)/비적용 -2(5→3)임을 검증 후 Null Report 수치 정정. |
