# X4i (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(X6i/X8i와 동일 계열의 최소형 버전)

**스켈레톤 근거**: `speakers/LA/X6i_v1.0.md`를 뼈대로 사용 — X4i는 X6i/X8i와 같은 X 시리즈 설치형 2-way 패시브 동축 점음원이나 (1) **밀폐형(closed enclosure)** 음향 부하(X6i/X8i는 bass-reflex), (2) 임피던스 **16Ω**(X6i/X8i는 8Ω), (3) 커넥터가 terminal block(push-in)이 아닌 **screw terminal**(나사 단자), (4) 무대 모니터 틸트각 대신 별도 프리셋([X4_MO])만 존재(고정 틸트각 언급 없음), (5) 이중 프리셋명이 [X4i]/[X4i_XX]가 아닌 **[X4]/[X4_60]**(제품명 축약형)로 상이 — 아키텍처는 X4i 자신의 X4i_AE_EN.docx/X4i_OM_EN_6.0.pdf에서 독립 판정했다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | X4i | - |
| Model_Number | null | - |
| Product_Category | short throw point source (installation version) | - |
| Description | 2-way passive coaxial enclosure (installation version): 4" LF neodymium cone driver + 1.4" HF diaphragm compression driver, amplified by LA2Xi / LA4X / LA7.16i / LA12X | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | EN 62368-1:2014 Audio/video, information and communication technology equipment — Part 1: Safety requirements | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_AE_EN.docx; X4i_OM_EN_6.0.pdf(X4i owner's manual EN version 6.0) p.75 "X4i specifications", p.13 "Rigging system description".

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [1] | [X4_60]: 65 - 20000 / [X4]: 120 - 20000 | Hz |
| Frequency_Response_6dB_Hz [1] | [X4_60]: 77 - 20000 / [X4]: 145 - 20000 | Hz |
| Frequency_Response_3dB_Hz [1] | [X4_60]: 105 - 20000 / [X4]: 180 - 20000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak [1] | [X4]: 116 dB / [X4_60]: 110 dB | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 110 (axisymmetric) | deg |
| Nominal_Directivity_Vertical | 110 (axisymmetric) | deg |
| DSP_Preset_Name | X4, X4_60, X4_MO | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_AE_EN.docx "Technical requirements"; X4i_OM_EN_6.0.pdf p.75 "X4i specifications"("with preset [X4]"/"with preset [X4_60]" 표); p.25 "X4i point source"("[X4] preset ... Frequency range (-10 dB) 120 Hz").
**[1] 프리셋-수치 짝짓기 소스 간 충돌**: X4i_AE_EN.docx는 "Preset 1: 65Hz(-10dB).../116dB"과 "Preset 2: 120Hz(-10dB).../110dB"로 서술하나, X4i_OM_EN_6.0.pdf의 스펙 표는 반대로 "[X4](120Hz)=116dB, [X4_60](65Hz)=110dB"로 짝지음 — 두 저역한계값(65Hz/120Hz)과 두 SPL값(116dB/110dB) 자체는 두 출처가 동일하게 제공하나 짝짓기가 반대다. L-Acoustics 브랜드 OM 우선 원칙(SKILL 출력 포맷 규칙 4)에 따라 OM의 짝짓기를 채택([X4]=120Hz/116dB, [X4_60]=65Hz/110dB) — 저역 확장이 적을수록(120Hz) SPL이 높다는 물리적 경향과도 정합. AE의 반대 짝짓기는 오기재로 추정되나 확정할 수 없어 이 각주에 병기.
**DSP_Preset_Name**: 다른 X 시리즈 제품과 달리 프리셋명이 "X4i"가 아닌 "X4"(제품명 축약형)로 표기됨 — 원문 그대로 채택. [X4_MO]는 무대 모니터용(p.31 근처, 저지연 프리셋) — X6i/X8i의 틸트각 기반 모니터 모드와 달리 X4i는 별도 고정 틸트각 서술 없이 프리셋 전환만으로 모니터 모드 지원.

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
| LF_Transducer | 4" neodymium cone driver | - |
| MF_Transducer | null | - |
| HF_Transducer | 1.4" diaphragm compression driver | - |
| LF_Acoustical_Load [1] | closed enclosure | - |
| MF_Acoustical_Load | null | - |
| HF_Acoustical_Load | null | - |
| Passive_Crossover_Network | Yes | - |
| LF_Nominal_Impedance | null | Ohm |
| MF_Nominal_Impedance | null | Ohm |
| HF_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall | 16 | Ohm |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | 42 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_AE_EN.docx "Technical requirements"; X4i_OM_EN_6.0.pdf p.75 "X4i specifications".
**[1] LF_Acoustical_Load=closed enclosure**: X6i/X8i(bass-reflex)와 달리 X4i는 밀폐형 — 최소형 설계에 따른 차이로 원문 그대로 채택(임의 통일하지 않음).
**Nominal_Impedance_Overall=16Ω**: X6i/X8i(8Ω)와 다름 — 원문 그대로 채택.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector [1] | 1 x 2-point screw terminal | - |
| Link_Connector [1] | 1 x 2-point screw terminal | - |
| Screw_Terminal_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| Screw_Terminal_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_OM_EN_6.0.pdf p.13 "Connectors"("Internal pinout for L-Acoustics 2-way passive enclosures" — "Screw terminal points IN +/IN -"); X4i_AE_EN.docx "Connectors: 2 x 2-point screw terminal".
**[1] 신규 커넥터 모델 Key(Screw_Terminal_Pinout_*)**: X6i/X8i는 "terminal block with push-in connection"(스프링 방식 삽입 단자)인 반면 X4i는 원문이 명시적으로 "Screw terminal"(나사 조임 단자)로 구분 — 물리적으로 다른 커넥터 하드웨어이므로 기존 Terminal_Block_Pinout_*을 재사용하지 않고 신규 Key를 신설(SKILL v1.14/v1.16의 커넥터 모델 고유 Key 원칙 — 다른 제품 파일에 null 동기화하지 않음).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA2Xi, LA4X, LA7.16i, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Passive (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_OM_EN_6.0.pdf "X4i is driven by the LA2Xi / LA4X / LA7.16i / LA12X amplified controllers".

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | 1 x M5 insert + screw (X-U4i/X-B4i 마운트용), 2 x M6 inserts(리깅 액세서리용), 1 x M6 insert(보조 안전용) | - |
| Inter_Enclosure_Angles_deg | null | deg |
| Handles | 0 | count |
| Weight_Net | 1 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_OM_EN_6.0.pdf p.75 "X4i specifications"("Rigging and handling"); p.13 "Rigging system description".
**Handles=0(확정적 비존재)**: X4i_OM_EN_6.0.pdf/X4i_AE_EN.docx 전량 스캔 결과 "handle" 키워드 0건 검출 — 초소형(1kg) 설치용 제품 특성상 손잡이 없이 설계된 것으로 확정.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 116 | mm |
| Height_mm | 116 | mm |
| Depth_mm | 99 | mm |
| Dimensions_Raw [1] | 116 / 116 / 99 / 109 | mm |
| Cabinet_Material | premium grade Baltic birch plywood | - |
| Front_Material | coated steel grill, acoustically neutral 3D fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C, pure white RAL 9010, custom RAL code on special order | - |
| IP_Rating [2] | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_AE_EN.docx "Physical data" - "Dimensions (W, H, D): 116 mm, 116 mm, 99 mm"; X4i_OM_EN_6.0.pdf p.76 "X4i dimensions"(치수 도면).
**[1] Dimensions_Raw**: 도면 4개 숫자(116/116/99/109mm) — AE 확정 W/H/D(116/116/99)와 3개 일치, 109는 커넥터 실링 플레이트 포함 깊이 등 부가 치수로 추정.
**[2] IP_Rating 조건부**: OM 각주 2 "With connector sealing plate" — X8i/X6i와 동일하게 커넥터 실링 플레이트 장착이 전제된 조건.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| X4i standalone (고SPL) | [X4] | 120 - 20000 | null | null |
| X4i point source with SB6i, closely coupled(200Hz) | [X4] + [SB6_200] | 32 - 20000 | 1 X4i : 1 SB6i | null |
| X4i point source with SB6i, coupled(100Hz) | [X4] + [SB6_100] | 29 - 20000 | 1 X4i : 1 SB6i | null |
| X4i point source with SB6i, separated(60Hz) | [X4_60] + [SB6_60] | 29 - 20000 | 1 X4i : 1 SB6i | null |
| X4i point source with SB10i [1] | [X4]/[X4_60] + [SB10_200]/[SB10_100]/[SB10_60] | null | null | null |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_OM_EN_6.0.pdf p.25-30 "Loudspeaker configurations"("X4i point source with low-frequency element", "X4i point source with SB6i").
**[1] SB10i 조합 상세 생략**: SB6i와 동일 3단계(closely coupled/coupled/separated, 프리셋 [SB10_200]/[SB10_100]/[SB10_60]) 구조가 원문에 존재하나, 시간 배분상 SB6i 조합 위주로 상세 조사하고 SB10i는 프리셋 코드 존재만 확인 — 정확한 수치는 미확인.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [X4] or [X4_MO] + [SB6_200] | 0.6 | SB6i = 0 | X4i = + / SB6i = - |
| [X4] or [X4_MO] + [SB6_100] | 0 | SB6i = 0.4 | X4i = + / SB6i = + |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_OM_EN_6.0.pdf p.26-27 "Pre-alignment delays". 극성은 색상 아이콘 표기라 Windows.Data.Pdf WinRT API로 페이지 이미지 렌더링해 육안 확인.
**[X4_60] + [SB6_60] 딜레이값 미확인**: 원문에서 이 조합의 명시적 pre-alignment 딜레이 표를 발견하지 못함(다른 두 조합과 달리 지연값 서술 누락 또는 별도 페이지에 있으나 시간 배분상 미확보) — delay_defaults에서 제외, preset_guide_and_matching에는 반영.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| all configurations | X-U4i, X-B4i 등 (X6i/X8i와 유사 액세서리 체계) | 1 | 1 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 5:1 | - |
| Max_Wind_Load | null | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: X4i_OM_EN_6.0.pdf "The X4i rigging system complies with EN 62368-1: 2014...", "The deployments described in this manual achieve a safety factor of 5".
**Max_Wind_Load 미확인 사유**: X6i/X8i와 동일 사유 — 원문 전량 검색으로도 풍하중 수치 미발견.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/MF/HF(단일 통합값만 존재), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Inter_Enclosure_Angles_deg, Rigging_Components_Material, Max_Wind_Load, preset_guide_and_matching(SB10i 조합 상세, Minimum_Line_Length 전 행) — 16건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load, HF_Acoustical_Load — 6건. (PA_COM_Pinout_*/SpeakON_Pinout_*/Terminal_Block_Pinout_* 등 타 커넥터 고유 Key는 X4i 자신의 Screw_Terminal_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 22건 (미확인 16건 + 비적용 6건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Handles(0, 원문 전량 스캔 근거).

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(X6i/X8i와 동일 계열의 최소형 버전). X6i_v1.0.md를 스켈레톤으로 사용, X4i_AE_EN.docx + X4i_OM_EN_6.0.pdf 통합. 밀폐형 음향 부하, 16Ω 임피던스, screw terminal 커넥터(신규 Key Screw_Terminal_Pinout_*), [X4]/[X4_60] 프리셋명(제품명 축약형) 등 신규 사실 확인. AE와 OM 간 프리셋-SPL 짝짓기 충돌 발견 및 OM 우선 원칙으로 해결(양쪽 값 모두 보존). preset_guide_and_matching/delay_defaults는 SB6i 조합 원문을 직접 조사해 실값 확보(극성은 PDF 페이지 이미지 렌더링). |
