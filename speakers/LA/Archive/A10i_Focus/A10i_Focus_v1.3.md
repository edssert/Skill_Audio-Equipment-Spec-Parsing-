# A10i Focus (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(A10 Focus의 install 파생형)

**스켈레톤 근거**: `speakers/LA/A10_Focus_v1.0.md`를 뼈대로 사용 — A10i Focus는 A10 Focus와 동일 아키텍처(단일 채널 패시브 크로스오버, 10° 고정 인클로저 각도)이나 커넥터가 speakON이 아닌 **4-point terminal block**(push-in)이며 앰프 호환성이 LA4X/LA8/LA12X가 아닌 **LA1.16i/LA2Xi/LA4X/LA7.16i/LA12X**(5종)로 확장된다. A10i Focus/Wide 별도 파일 분리는 A10과 동일 원칙(사용자 지시 2026-07-17).

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | A10i Focus | - |
| Model_Number | null | - |
| Product_Category | medium throw line source (installation version) | - |
| Description | 2-way passive constant curvature WST 10° enclosure (installation version): 10" LF cone driver + 2.5" HF diaphragm compression driver, amplified by LA1.16i / LA2Xi / LA4X / LA7.16i / LA12X | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_AE_EN.docx("A10i Focus" 섹션); A10i_OM_EN.pdf(A10i owner's manual EN version 5.0) p.157 "A10i Focus specifications".

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 66 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 70 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 75 - 20000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak [1] | 140 dB(LA2Xi bridge/LA4X/LA7.16i/LA12X) / 136 dB(LA2Xi) / 135 dB(LA1.16i bridge) | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 10 (enclosure) / 70-110 symmetric or 90 asymmetric (L-Fins) | deg |
| Nominal_Directivity_Vertical | 10 | deg |
| DSP_Preset_Name | A10, A10_FI, A10_MO | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_AE_EN.docx "Technical requirements"; A10i_OM_EN.pdf p.157 "A10i Focus specifications".
**[1] Max_SPL_Peak 앰프별 3단계**: A10(단일값 140dB)과 달리 A10i는 앰프 조건별 3개 값을 명시 — 전부 보존.

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
| HF_Transducer | 2.5" diaphragm compression driver, neodymium | - |
| LF_Acoustical_Load | bass-reflex, L-Vents | - |
| HF_Acoustical_Load | DOSC waveguide, L-Fins | - |
| Passive_Crossover_Network | Yes | - |
| LF_Nominal_Impedance | null | Ohm |
| HF_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall | 8 | Ohm |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | 296 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_AE_EN.docx "Technical requirements"; A10i_OM_EN.pdf p.21 "Connectors", p.157 "A10i Focus specifications".

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x 4-point terminal block with push-in connection + connector sealing plate with cable gland | - |
| Link_Connector | 1 x 4-point terminal block with push-in connection + connector sealing plate with cable gland | - |
| Terminal_Block_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| Terminal_Block_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.21 "Connectors"("Internal pinout for L-Acoustics 2-way passive enclosures" — A10i Wide/Focus 공용 표).

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
| Inter_Enclosure_Angles_deg | 10 | deg |
| Handles | null | count |
| Weight_Net | 19 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.157 "A10i Focus specifications".
**Handles 미확인 사유**: A10(2개 명시)와 달리 A10i 스펙 표에 핸들 개수 없음 — 설치용 제품이라 별도 손잡이가 없을 가능성이 있으나 확정적 서술 부재로 미확인.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 569 | mm |
| Height_mm | 350 | mm |
| Depth_mm | 339 | mm |
| Dimensions_Raw [1] | 569 / 350 / 339 / 366 / 294 / 367 | mm |
| Cabinet_Material | premium grade Baltic beech and birch plywood | - |
| Front_Material | coated steel grill, acoustically neutral 3D fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C, pure white RAL 9010, custom RAL code on special order | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_AE_EN.docx "Physical data" - "Dimensions (W, H, D): 569 mm, 350 mm, 339 mm"; A10i_OM_EN.pdf p.157 "A10i Focus dimensions"(치수 도면).
**[1] Dimensions_Raw**: 도면 6개 숫자 중 569/350/339는 AE와 일치, 나머지(366/294/367)는 부가 치수.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| A10i Focus line source (단독) | [A10] | 66 - 20000 | null | null |
| A10i Focus line source element (단일) | [A10_FI] | 66 - 20000 | null | null |
| A10i Focus with KS21i [1] | [A10] + [KS21_100] | 31 - 20000 | 1 A10i Focus : 1 KS21i | null |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.51-53 "Loudspeaker configurations"("A10i Wide/Focus line source", "...line source with low-frequency element").
**[1] 배치 간격**: coupled(2:1) 최대 1.7m 또는 separated(1:1) 조건 — 대표 1:1 비율 채택.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [A10] or [A10_FI] or [A10_MO] + [KS21_100] | 0 | KS21i = 0 | A10i Focus = + / KS21i = + |
| [A10] or [A10_FI] + [KS21_100_C] | 5.5 | KS21i = 0 | A10i Focus = + / KS21i = + |
| [A10] or [A10_FI] + [KS21_100_Cx] | 0 | KS21i = 0 | A10i Focus = + / KS21i = + |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.53 "Pre-alignment delays". 극성은 색상 아이콘 표기라 Windows.Data.Pdf WinRT API로 페이지 이미지 렌더링해 육안 확인(KS21i는 모든 조합에서 "+"로 일관, KS28/KS21 계열과 달리 반전이 필요 없음).
**원문 라벨 정정**: 원문 표는 "A10 Wide/Focus"/"KS21"로 표기(i 접미사 누락, A10 매뉴얼에서 복사된 것으로 추정) — A10i Focus/KS21i로 정정 채택(X4r에서 확인된 동일 라벨링 관행).

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| vertical array | A10i-BUMP + rigging plates | 8 | 8 |
| vertical array | A10-Ui | 1 | 1 |
| vertical array | A10-Ui + A10i-ULINK II | 2 | 2 |
| vertical array with pullback | A10i-BUMP + rigging plates + A10i-RIGBAR | 12 | 12 |
| vertical array with pullback | A10i-RIGBAR x2 + rigging plates | 12 | 12 |
| stacked vertical array | Ai-FIXBRACKET + rigging plates | 4 | 4 |
| stacked vertical array with angle adjustment | A10i-TILTBRACKET + rigging plates | 4 | 4 |
| stacked on KS21i [1] | Ai-FIXBRACKET + rigging plates | 4 A10i Focus | 4 KS21i |
| stacked on KS21i, angle adjustment [1] | Ai-FIXBRACKET + A10i-TILT + rigging plates | 4 A10i Focus | 4 KS21i |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | null | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: A10i_OM_EN.pdf p.49-50 "Mechanical safety"("2006/42/EC Machinery Directive", "safety factor of 4"). A10i-BUMP+rigging plates+A10i-RIGBAR 행은 원문 "A10i Wide: 8 / A10i Focus: 12 / A10i Wide/Focus: 12"에서 A10i Focus 값(12) 채택.
**[1] KS21i 스택 구성**: "4 KS21i / 4 A10i Wide/Focus" 원문 표기 — 제품 구분 없이 공통값(4/4)이라 Focus/Wide 동일 채택.
**Max_Wind_Load 미확인 사유**: 원문 전량 검색으로도 미발견(A10과 달리 이 수치는 별도 챕터에 없거나 발견되지 않음).
**벽/천장 마운트 구성 생략**: 원문에 Wall-mounted(horizontal/vertical)/Ceiling-mounted 조합도 있으나(A10-Ui/A10i-ULINK II 등, 값은 1~2) 대표적인 vertical array/stacked 구성 위주로 채택하고 이들은 생략(값 자체는 위 vertical array 행들과 대체로 중복).

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Handles, Rigging_Components_Material, Max_Wind_Load, preset_guide_and_matching(Recommended_Ratio 2행/Minimum_Line_Length 전 행) — 14건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range — 3건. (PA_COM_Pinout_*/SpeakON_Pinout_* 등 타 커넥터 고유 Key는 A10i Focus 자신의 Terminal_Block_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 17건 (미확인 14건 + 비적용 3건). 확정적 비존재(0/No)로 명시한 항목은 0건. (v1.1: delay_defaults와 mechanical_safety를 "시간 배분상 미확인"으로 방치하지 않고 원문(OM p.49-53) 직접 조사로 실값 채움 — 사용자 피드백 2026-07-17.)

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(A10 Focus의 install 파생형). A10_Focus_v1.0.md를 스켈레톤으로 사용, A10i_AE_EN.docx("A10i Focus" 섹션) + A10i_OM_EN.pdf(A10i Wide/Focus 공용 매뉴얼) 통합. 커넥터(terminal block), 앰프 호환성 확장(LA1.16i/LA7.16i 추가), 앰프별 3단계 Max SPL 확인. 남은 대량 제품 처리 일정상 preset_guide_and_matching/delay_defaults/mechanical_safety 상세는 A10 대비 축소(핵심 스펙 위주로 우선 확보). |
| v1.1 | 사용자 피드백(2026-07-17) — "시간 배분상 미확인" 플레이스홀더를 원문(A10i_OM_EN.pdf p.49-53) 직접 조사로 교체. KS21i 조합 delay 3건(극성은 PDF 페이지 이미지 렌더링, KS21i는 전 조합 "+"로 일관 확인) 및 mechanical_safety 9개 구성 실값 확보. 원문 딜레이 표의 "A10 Wide/Focus"/"KS21" 라벨(i 접미사 누락) 정정 채택. |
| v1.2 | delay_defaults 표의 컬럼명 `K1_Delay_ms`를 `Primary_Element_Delay_ms`로 전면 개명(SKILL v1.18) — 값 변경 없음(사용자 지적 2026-07-17). |
| v1.3 | MF_Transducer/MF_Acoustical_Load/MF_Nominal_Impedance/RMS_Power_Handling_MF 4개 Key 삭제(SKILL v1.19) — 이 제품은 확인된 2-way 구조라 MF 대역 드라이버 자체가 없으므로, null 동기화 대상이 아니라 삭제 대상으로 재분류(K1 v1.4의 기존 반대 판단을 뒤집는 정책 변경, GSL의 Front_LF_Transducer와 동일 원칙 적용). MF_Nominal_Impedance가 미확인 목록의 결합형 "RMS_Power_Handling_LF/MF/HF" 항목과 별도 표기되어 있어 실제 삭제분은 미확인 -1(15→14)/비적용 -2(5→3)임을 검증 후 Null Report 수치 정정. |
