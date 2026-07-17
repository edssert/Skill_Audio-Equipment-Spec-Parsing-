# A10 Focus (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(A 시리즈 최초 투입, 10° 고정 커버리지 버전)

**스켈레톤 근거**: `speakers/LA/Kiva_II_v1.2.md`를 뼈대로 사용 — A10은 K1/K3처럼 "constant curvature WST" 라인소스 엘리먼트이자 L-Fins 조정형 웨이브가이드를 갖지만, 커넥터 핀아웃 표가 "Internal pinout for L-Acoustics 2-way **passive** enclosures"로 명시되고(K1/K3는 "active") 임피던스/파워 핸들링이 대역별이 아닌 통합값(8Ω/296W)으로만 보고되어 Kiva II와 동일한 단일 채널 패시브 크로스오버 아키텍처임을 확인했다 — 겉보기엔 K3와 비슷해 보이지만 실제 구동 방식은 Kiva II 계열이라는 점이 핵심 판정 근거다(SKILL v1.11 "이름과 아키텍처는 무관" 원칙 재확인 사례). **A10 Focus/A10 Wide 별도 파일 분리**: 원본 OM이 두 제품을 "A10 Wide/Focus" 공용 챕터로 함께 다루지만 전용 스펙 표(p.124/122)와 페이지가 별도이며 고정 인클로저 각도(10°/30°)가 서로 다른 별개 금형 제품이라 L2/L2D와 동일한 원칙으로 분리 파일 처리(사용자 지시 2026-07-17).

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | A10 Focus | - |
| Model_Number | null | - |
| Product_Category | medium throw line source | - |
| Description | 2-way passive constant curvature WST 10° enclosure: 10" LF cone driver + 2.5" HF diaphragm compression driver, amplified by LA4X / LA8 / LA12X | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10_AE_EN.docx("A10 Focus" 섹션); A10_OM_EN.pdf(A10 owner's manual EN version 2.1) p.124 "A10 Focus specifications".

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 66 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 70 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 75 - 20000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | 140 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 10 (enclosure) / 70-110 symmetric or 90 asymmetric (L-Fins) | deg |
| Nominal_Directivity_Vertical | 10 | deg |
| DSP_Preset_Name | A10, A10_FI, A10_MO | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10_AE_EN.docx "Technical requirements"; A10_OM_EN.pdf p.124 "A10 Focus specifications".
**Nominal_Directivity_Horizontal_deg 이중 개념**: 원문이 "enclosure: 10°"(고정 인클로저 각도)와 "L-Fins: 70°/110° symmetric or 90° asymmetric"(조정형 웨이브가이드)를 별도로 명시 — K1의 Nominal_Directivity_Horizontal 표기 관례를 따라 둘 다 병기.
**DSP_Preset_Name**: [A10](라인소스), [A10_FI](단독 라인소스 엘리먼트), [A10_MO](무대 모니터) — 용도별 3개 프리셋 확인.

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
| LF_Transducer | 10" neodymium cone driver | - |
| MF_Transducer | null | - |
| HF_Transducer | 2.5" neodymium diaphragm compression driver | - |
| LF_Acoustical_Load | L-Vents, bass-reflex | - |
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

**출처**: A10_AE_EN.docx "Technical requirements"; A10_OM_EN.pdf p.20 "Connectors"("Internal pinout for L-Acoustics 2-way passive enclosures"), p.124 "A10 Focus specifications".
**Passive_Crossover_Network=Yes/통합값**: Kiva II와 동일 구조 — speakON 2채널 중 1채널만 신호, 통합값(8Ω/296W).

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 2 x 4-point speakON (IN/LINK interchangeable, only 1 channel carries signal) | - |
| Link_Connector | 2 x 4-point speakON (IN/LINK interchangeable, only 1 channel carries signal) | - |
| SpeakON_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| SpeakON_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10_OM_EN.pdf p.20 "Connectors"("Internal pinout for L-Acoustics 2-way passive enclosures" — A10 Wide/Focus 공용 표).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA4X, LA8, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Passive (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10_OM_EN.pdf "The A10 Wide/Focus enclosures are driven by the LA4X / LA8 / LA12X amplified controllers".

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | flush-fitting 2-point rigging system(rotating rigging arm + spring-loaded pin) | - |
| Inter_Enclosure_Angles_deg | 10 | deg |
| Handles | 2 | count |
| Weight_Net | 22 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: A10_OM_EN.pdf p.124 "A10 Focus specifications"("Rigging and handling"); p.20 "A10 system rigging".
**Inter_Enclosure_Angles_deg=10**: 원문 "The line source directivity is equal to N x 10 degree" — 고정 인클로저 각도가 곧 엘리먼트 간 각도.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 581 | mm |
| Height_mm | 354 | mm |
| Depth_mm | 339 | mm |
| Dimensions_Raw [1] | 581 / 350 / 569 / 339 / 367 | mm |
| Cabinet_Material | premium grade Baltic beech and birch plywood | - |
| Front_Material | coated steel grill, acoustically neutral 3D fabric | - |
| Rigging_Components_Material | high grade steel with anti-corrosion coating | - |
| Finish_Color | dark grey brown Pantone 426 C | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10_AE_EN.docx "Physical data" - "Dimensions (W, H, D): 581 mm, 354 mm, 339 mm"; A10_OM_EN.pdf p.125 "A10 Focus dimensions"(치수 도면).
**[1] Dimensions_Raw**: 도면 5개 숫자 중 581/339는 AE와 일치, 354는 AE에 있으나 도면엔 350으로 근사 표기, 나머지(569/367)는 부가 치수로 추정.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| A10 Focus line source (단독) | [A10] | 66 - 20000 | null | null |
| A10 Focus line source element (단일) | [A10_FI] | 66 - 20000 | null | null |
| A10 Focus with KS21 | [A10] + [KS21_100] | 31 - 20000 | 1 A10 Focus : 1 KS21 | null |

### 주석 및 출처 (Notes & Sources)

**출처**: A10_OM_EN.pdf p.49-52 "Loudspeaker configurations"("A10 Wide/Focus line source", "...line source element", "...line source with low-frequency element"). A10 Wide/Focus 공용 챕터라 A10 Wide와 동일 조합 구조 공유(수치는 각 제품 고유).

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [A10] or [A10_FI] or [A10_MO] + [KS21_100] | 0 | KS21 = 0 | A10 = + / KS21 = + |
| [A10] or [A10_FI] + [KS21_100_C] | 5.5 | KS21 = 0 | A10 = + / KS21 = + |
| [A10] or [A10_FI] + [KS21_100_Cx] | 0 | KS21 = 0 | A10 = + / KS21 = + |

### 주석 및 출처 (Notes & Sources)

**출처**: A10_OM_EN.pdf p.50 "A10 Wide/Focus line source with low-frequency element"("Pre-alignment delays" 표, PowerShell+Windows.Data.Pdf 렌더링으로 폴라리티 아이콘 육안 확인). 3개 조합 전부 A10/KS21 양측 폴라리티가 "+"로 동일.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown | X-BAR | 1 | 1 |
| vertical array | A10-BUMP | 8 | 8 |
| vertical array | A10-RIGBAR | 4 | 4 |
| vertical array with pullback | A10-BUMP + A10-RIGBAR | 8 | 8 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | 6 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: A10_OM_EN.pdf "Mechanical safety"("2006/42/EC Machinery Directive", "safety factor of 4"); Safety 섹션(Max_Wind_Load, "6 bft", K1 계열과 동일 관례로 확인).
**A10-BUMP+A10-RIGBAR 행**: 원문이 "A10 Wide: 4 / A10 Focus: 8 / A10 Wide/Focus: 8"로 세분화 — A10 Focus 자신의 값(8)만 채택.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/MF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, preset_guide_and_matching(Minimum_Line_Length 전 행) — 12건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load — 5건. (PA_COM_Pinout_*/Terminal_Block_Pinout_* 등 타 커넥터 고유 Key는 A10 Focus 자신의 SpeakON_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 17건 (미확인 12건 + 비적용 5건). 확정적 비존재(0/No)로 명시한 항목은 0건.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리, A 시리즈 최초 투입(2026-07-17). Kiva_II_v1.2.md를 스켈레톤으로 사용, A10_AE_EN.docx("A10 Focus" 섹션) + A10_OM_EN.pdf(A10 Wide/Focus 공용 매뉴얼) 통합. 겉보기엔 K3와 유사한 constant curvature WST 라인소스이나 실제로는 Kiva II와 동일한 단일 채널 패시브 크로스오버 아키텍처(통합 임피던스/파워 핸들링)임을 커넥터 핀아웃 표로 확인. 사용자 지시(2026-07-17)로 A10 Wide와 별도 파일 분리. |
| v1.1 | delay_defaults의 Polarity를 "시간 배분상" 사유로 null 방치했던 것을 사용자 지적(SKILL v1.17 위반)으로 수정 — A10_OM_EN.pdf p.50 페이지를 PowerShell+Windows.Data.Pdf로 이미지 렌더링해 육안 확인, 3개 조합 전부 A10=+/KS21=+로 확정. |
