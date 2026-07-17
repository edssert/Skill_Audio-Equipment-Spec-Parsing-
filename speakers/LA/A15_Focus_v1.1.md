# A15 Focus (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(A10 Focus의 대형 버전, 15" LF)

**스켈레톤 근거**: `speakers/LA/A10_Focus_v1.0.md`를 뼈대로 사용 — A15 Focus는 A10 Focus와 완전히 동일한 아키텍처(단일 채널 패시브 크로스오버, speakON, 10° 고정 각도)이나 더 큰 트랜스듀서(15" LF + 3" HF, medium throw 45m)와 다른 앰프 호환성(LA2Xi/LA4X/LA7.16/LA7.16i/LA12X — LA8 없음, LA2Xi/LA7.16 계열 추가)을 가진다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | A15 Focus | - |
| Model_Number | null | - |
| Product_Category | medium throw line source | - |
| Description | 2-way passive constant curvature WST 10° enclosure: 15" LF cone driver + 3" HF diaphragm compression driver, amplified by LA2Xi / LA4X / LA7.16 / LA7.16i / LA12X | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_AE_EN.docx("A15 Focus" 섹션); A15_OM_EN.pdf(A15 owner's manual EN version 3.3) p.136 "A15 Focus specifications".

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 41 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 44 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 47 - 20000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | 144 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 10 (enclosure) / 70-110 symmetric or 90 asymmetric (L-Fins) | deg |
| Nominal_Directivity_Vertical | 10 | deg |
| DSP_Preset_Name | A15, A15_FI, A15_MO | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_AE_EN.docx "Technical requirements"; A15_OM_EN.pdf p.136 "A15 Focus specifications".

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

**출처**: A15_AE_EN.docx "Technical requirements"; A15_OM_EN.pdf p.136 "A15 Focus specifications".

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 2 x 4-point speakON (IN/LINK interchangeable, only 1 channel carries signal) | - |
| Link_Connector | 2 x 4-point speakON (IN/LINK interchangeable, only 1 channel carries signal) | - |
| SpeakON_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| SpeakON_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf "Connectors"("Internal pinout for L-Acoustics 2-way passive enclosures" — A10과 동일 표 제목/구조).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA2Xi, LA4X, LA7.16, LA7.16i, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Passive (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf "The A15 Wide/Focus enclosures are driven by the LA2Xi / LA4X / LA7.16 / LA7.16i / LA12X amplified controllers". A10(LA8 포함, LA2Xi/LA7.16 계열 없음)와 앰프 매칭이 다름 — 더 큰 트랜스듀서로 인한 전력 요구량 차이로 추정, 원문 그대로 채택.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | flush-fitting 2-point rigging system(rotating rigging arm + spring-loaded pin) | - |
| Inter_Enclosure_Angles_deg | 10 | deg |
| Handles | 2 | count |
| Weight_Net | 35 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf p.136 "A15 Focus specifications"("Rigging and handling").

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 762 | mm |
| Height_mm | 427 | mm |
| Depth_mm | 490 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | premium grade Baltic beech and birch plywood | - |
| Front_Material | coated steel grill, acoustically neutral 3D fabric | - |
| Rigging_Components_Material | high grade steel with anti-corrosion coating | - |
| Finish_Color | dark grey brown Pantone 426 C | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_AE_EN.docx "Physical data" - "Dimensions (W, H, D): 762 mm, 427 mm, 490 mm".
**Dimensions_Raw 미확인**: OM 도면 세부 수치는 시간 배분상 별도 추출하지 않음.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| A15 Focus line source (단독) | [A15] | 41 - 20000 | null | null |
| A15 Focus line source element (단일) | [A15_FI] | 42 - 20000 | null | null |
| A15 Focus with KS21 [1] | [A15] + [KS21_60] | 29 - 20000 | 1 A15 Focus : 1 KS21 | null |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf p.49-52 "Loudspeaker configurations"("A15 Wide/Focus line source", "...line source with low-frequency element", "...line source element"). "line source element" 단독 구성의 Frequency_Range는 A15 Focus 42Hz(원문 그대로), A15 line source 단독 구성은 41Hz — 두 구성이 서로 다른 하한을 가짐을 원문 그대로 반영(오기재 아님, 서로 다른 프리셋/구성).
**[1] 배치 간격**: coupled(3 A15:2 KS21) 최대 2.8m 또는 separated(1:1) 조건 — 원문에 두 배치 방식이 있으나 Recommended_Ratio 컬럼에는 대표 1:1 비율만 채택.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [A15] or [A15_FI] or [A15_MO] + [KS21_60] | 0 | KS21 = 2.3 | A15 Focus = + / KS21 = + |
| [A15] or [A15_FI] + [KS21_60_C] | 9 | KS21 = 0 | A15 Focus = + / KS21 = - |
| [A15] or [A15_FI] + [KS21_60_Cx] | 8 | KS21 = 0 | A15 Focus = + / KS21 = + |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf p.51-52 "Pre-alignment delays"("A15 Wide/Focus line source with low-frequency element"). 극성은 색상 아이콘 표기라 Windows.Data.Pdf WinRT API로 해당 페이지(PDF 51-52페이지)를 직접 이미지 렌더링해 육안 확인.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown | X-BAR | 1 | 1 |
| vertical array | A15-BUMP + M-BAR (optional) | 8 | 8 |
| vertical array | A15-RIGBAR | 4 | 4 |
| vertical array with pullback | A15-BUMP + M-BAR (optional) + A15-RIGBAR | 8 | 8 |
| vertical array with pullback | 2 x A15-RIGBAR | 4 | 4 |
| stacked vertical array | no rigging accessory | 1 | 1 |
| stacked vertical array | KS21-OUTRIG | 4 | 4 |
| pole-mounted | A-MOUNT | 1 | 1 |
| stacked on KS21, angle adjustment [1] | A-TILT + KS21-OUTRIG or KS21-CHARIOT with K2-JACK | 4 (KS21 포함) | 4 A15 Focus + 4 KS21 |
| stacked on KS21 [1] | KS21-OUTRIG or KS21-CHARIOT with K2-JACK | 3 A15 Focus | 3 KS21 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | 6 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: A15_OM_EN.pdf p.47-48 "Mechanical safety"("2006/42/EC Machinery Directive", "safety factor of 4"); Safety 섹션(Max_Wind_Load, "6 bft", K1 계열과 동일 관례로 확인).
**A15-BUMP+M-BAR+A15-RIGBAR 행**: 원문 "A15 Wide: 5 / A15 Focus: 8 / A15 Wide/Focus: 8" — A15 Focus 자신의 값(8)만 채택.
**[1] KS21 스택 구성**: "A15 Wide/Focus on KS21" 표 — Safe_Limit/Maximum_Limit이 제품별로 다른 값을 가지는 복합 표기(예: "3 A15 Focus / 2 A15 Wide")라 A15 Focus 자신의 값만 채택.
**Radial array(A15-LIFT) 행 생략**: 원문에 A15-LIFT 1개/2개/3개 조합별 세부 배치 각도(1,3 / 2,4,5,6 / 7,8,9 등)가 있으나 안전 한계 숫자가 아닌 배치 위치 인덱스라 이 표 구조에 대응되지 않아 생략.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/MF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Dimensions_Raw, preset_guide_and_matching(Recommended_Ratio 2행/Minimum_Line_Length 전 행) — 13건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load — 5건. (PA_COM_Pinout_*/Terminal_Block_Pinout_* 등 타 커넥터 고유 Key는 A15 Focus 자신의 SpeakON_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 18건 (미확인 13건 + 비적용 5건). 확정적 비존재(0/No)로 명시한 항목은 0건. (v1.1: delay_defaults와 mechanical_safety를 "시간 배분상 미확인"으로 방치하지 않고 원문(OM p.47-52)을 직접 조사해 실값으로 채움 — 사용자 피드백 2026-07-17. preset_guide_and_matching도 KS21 조합 실값 추가.)

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(A10 Focus의 대형 버전). A10_Focus_v1.0.md를 스켈레톤으로 사용, A15_AE_EN.docx("A15 Focus" 섹션) + A15_OM_EN.pdf(A15 Wide/Focus 공용 매뉴얼) 통합. 15"/3" 트랜스듀서, medium throw 45m, 다른 앰프 호환성(LA2Xi/LA7.16/LA7.16i 추가, LA8 없음) 확인. 남은 대량 제품 처리 일정상 preset_guide/delay/mechanical_safety 상세는 A10 대비 축소. |
| v1.1 | 사용자 피드백(2026-07-17) — "시간 배분상 미확인"으로 남겨둔 delay_defaults/mechanical_safety/preset_guide_and_matching을 원문(A15_OM_EN.pdf p.47-52) 직접 조사로 실값 채움. KS21 조합 delay 3건(극성은 PDF 페이지 이미지 렌더링으로 확인) 및 mechanical_safety 10개 구성(flown/vertical array/stacked/pole-mounted/KS21 스택) 실값 확보. |
