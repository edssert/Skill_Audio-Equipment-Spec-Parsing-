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
| HF_Transducer | 3" neodymium diaphragm compression driver | - |
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
| A15 Wide line source element (단일) | [A15_FI] | 43 - 20000 | null | null |
| A15 Wide with KS21 [1] | [A15] + [KS21_60] | 29 - 20000 | 1 A15 Wide : 1 KS21 | null |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf p.49-52 "Loudspeaker configurations"(A15 Focus와 동일 구조 공유, "A15 Wide/Focus line source with low-frequency element" 챕터).
**[1] 배치 간격**: A15 Focus와 동일 사유 — coupled(3:2) 최대 2.8m 또는 separated(1:1) 조건, 대표 1:1 비율 채택.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [A15] or [A15_FI] or [A15_MO] + [KS21_60] | 0 | KS21 = 2.3 | A15 Wide = + / KS21 = + |
| [A15] or [A15_FI] + [KS21_60_C] | 9 | KS21 = 0 | A15 Wide = + / KS21 = - |
| [A15] or [A15_FI] + [KS21_60_Cx] | 8 | KS21 = 0 | A15 Wide = + / KS21 = + |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf p.51-52 "Pre-alignment delays"(A15 Wide/Focus 공용 표, A15 Focus와 동일 수치). 극성은 A15 Focus와 동일 페이지에서 이미지 렌더링으로 확인.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown | X-BAR | 1 | 1 |
| vertical array | A15-BUMP + M-BAR (optional) | 8 | 8 |
| vertical array | A15-RIGBAR | 4 | 4 |
| vertical array with pullback | A15-BUMP + M-BAR (optional) + A15-RIGBAR | 5 | 5 |
| vertical array with pullback | 2 x A15-RIGBAR | 4 | 4 |
| stacked vertical array | no rigging accessory | 1 | 1 |
| stacked vertical array | KS21-OUTRIG | 4 | 4 |
| pole-mounted | A-MOUNT | 1 | 1 |
| stacked on KS21, angle adjustment [1] | A-TILT + KS21-OUTRIG or KS21-CHARIOT with K2-JACK | 4 (KS21 포함) | 4 A15 Wide + 4 KS21 |
| stacked on KS21 [1] | KS21-OUTRIG or KS21-CHARIOT with K2-JACK | 2 A15 Wide | 3 KS21 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | 6 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf p.47-48 "Mechanical safety"(A15 Focus와 공용 챕터).
**A15-BUMP+M-BAR+A15-RIGBAR 행**: 원문 "A15 Wide: 5 / A15 Focus: 8 / A15 Wide/Focus: 8" — A15 Wide 자신의 값(5)만 채택(Focus의 8과 다름).
**[1] KS21 스택 구성**: "3 A15 Focus / 2 A15 Wide" — A15 Wide 자신의 값(2)만 채택.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, preset_guide_and_matching(Recommended_Ratio 2행/Minimum_Line_Length 전 행) — 11건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range — 3건. (PA_COM_Pinout_*/Terminal_Block_Pinout_* 등 타 커넥터 고유 Key는 A15 Wide 자신의 SpeakON_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 14건 (미확인 11건 + 비적용 3건). 확정적 비존재(0/No)로 명시한 항목은 0건. (v1.1: delay_defaults와 mechanical_safety를 "시간 배분상 미확인"으로 방치하지 않고 원문 직접 조사로 실값 채움 — 사용자 피드백 2026-07-17.)

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(A15 Focus의 30° 자매품). A15_Focus_v1.0.md를 스켈레톤으로 사용, A15_AE_EN.docx("A15 Wide" 섹션) + A15_OM_EN.pdf(공용 매뉴얼) 통합. Focus 대비 인클로저 각도(30°)와 스펙 수치만 상이. |
| v1.1 | 사용자 피드백(2026-07-17) — delay_defaults/mechanical_safety/preset_guide_and_matching을 원문 직접 조사로 실값 채움(A15 Focus v1.1과 동일 라운드). A15 Wide 고유값(A15-BUMP+M-BAR+A15-RIGBAR=5, KS21 스택=2 A15 Wide)을 Focus와 구분해 반영. |
| v1.2 | delay_defaults 표의 컬럼명 `K1_Delay_ms`를 `Primary_Element_Delay_ms`로 전면 개명(SKILL v1.18) — 값 변경 없음(사용자 지적 2026-07-17). |
| v1.3 | MF_Transducer/MF_Acoustical_Load/MF_Nominal_Impedance/RMS_Power_Handling_MF 4개 Key 삭제(SKILL v1.19) — 이 제품은 확인된 2-way 구조라 MF 대역 드라이버 자체가 없으므로, null 동기화 대상이 아니라 삭제 대상으로 재분류(K1 v1.4의 기존 반대 판단을 뒤집는 정책 변경, GSL의 Front_LF_Transducer와 동일 원칙 적용). MF_Nominal_Impedance가 미확인 목록의 결합형 "RMS_Power_Handling_LF/MF/HF" 항목과 별도 표기되어 있어 실제 삭제분은 미확인 -1(12→11)/비적용 -2(5→3)임을 검증 후 Null Report 수치 정정. |
