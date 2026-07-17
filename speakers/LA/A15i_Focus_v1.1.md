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
| A15i Focus line source element (단일) | [A15_FI] | 42 - 20000 | null | null |
| A15i Focus with KS21i [1] | [A15] + [KS21_60] | 29 - 20000 | 1 A15i Focus : 1 KS21i | null |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf p.47-50 "Loudspeaker configurations"("A15i Wide/Focus line source", "...line source with low-frequency element", "...line source element").
**[1] 배치 간격**: A15와 동일 사유 — coupled(3:2) 최대 2.8m 또는 separated(1:1), 대표 1:1 채택.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [A15] or [A15_FI] or [A15_MO] + [KS21_60] | 0 | KS21i = 2.3 | A15i Focus = + / KS21i = + |
| [A15] or [A15_FI] + [KS21_60_C] | 9 | KS21i = 0 | A15i Focus = + / KS21i = - |
| [A15] or [A15_FI] + [KS21_60_Cx] | 8 | KS21i = 0 | A15i Focus = + / KS21i = + |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf p.49-50 "Pre-alignment delays". 극성은 색상 아이콘 표기라 Windows.Data.Pdf WinRT API로 페이지 이미지 렌더링해 육안 확인(A15의 동일 수치와 일치 — 별도로 재확인했으며 임의로 값을 복사하지 않음).
**원문 라벨**: 원문 표는 "A15 Wide/Focus"/"KS21"로 표기(i 접미사 누락, A15 매뉴얼 재사용 흔적) — A15i Focus/KS21i로 정정 채택.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| vertical array | A15i-BUMP + M-BARi (optional) + rigging plates | 8 | 8 |
| vertical array | A15KS-Ui | 1 | 1 |
| vertical array | A15KS-Ui + A15i-ULINK II | 2 | 2 |
| vertical array with pullback | A15i-BUMP + rigging plates + A15i-RIGBAR | 12 | 12 |
| vertical array with pullback | A15i-RIGBAR x2 + rigging plates | 8 | 8 |
| stacked vertical array | Ai-FIXBRACKET + rigging plates | 4 | 4 |
| stacked vertical array with angle adjustment | A15i-TILTBRACKET + rigging plates | 4 | 4 |
| stacked on KS21i, pullback | A15i-BUMP + A15i-TILT (optional) + rigging plates + A15i-RIGBAR | 4 A15i Focus | 4 KS21i |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | null | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: A15i_OM_EN.pdf p.44-45 "Mechanical safety"("2006/42/EC Machinery Directive", "safety factor of 4"). A15i-BUMP+rigging plates+A15i-RIGBAR 행은 원문 "A15i Wide: 6 / A15i Focus: 12 / A15i Wide/Focus: 12"에서 A15i Focus 값(12) 채택.
**Max_Wind_Load 미확인 사유**: 원문 전량 검색으로도 미발견.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/MF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Handles, Dimensions_Raw, Rigging_Components_Material, Max_Wind_Load, preset_guide_and_matching(Minimum_Line_Length 전 행) — 16건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load — 5건. (PA_COM_Pinout_*/SpeakON_Pinout_* 등 타 커넥터 고유 Key는 A15i Focus 자신의 Terminal_Block_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 21건 (미확인 16건 + 비적용 5건). 확정적 비존재(0/No)로 명시한 항목은 0건. (v1.1: delay_defaults와 mechanical_safety를 원문(OM p.44-50) 직접 조사로 실값 채움 — 사용자 피드백 2026-07-17.)

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(A15 Focus의 install 파생형). A15_Focus_v1.0.md를 스켈레톤으로 사용, A15i_AE_EN.docx("A15i Focus" 섹션) + A15i_OM_EN.pdf(공용 매뉴얼) 통합. 커넥터(terminal block), 앰프별 2단계 Max SPL 확인. AE/OM 간 중량 값 충돌(33kg vs 32kg) 발견, OM 우선 원칙으로 해결(양쪽 값 보존). |
| v1.1 | 사용자 피드백(2026-07-17) — "시간 배분상 미확인" 플레이스홀더를 원문(A15i_OM_EN.pdf p.44-50) 직접 조사로 교체. KS21i 조합 delay 3건(극성은 PDF 페이지 이미지 렌더링으로 A15와 별도 재확인, 값이 A15와 일치함을 확인) 및 mechanical_safety 8개 구성 실값 확보. |
