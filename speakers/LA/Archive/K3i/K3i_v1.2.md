# K3i (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1 (동일 브랜드 이기종, K3 대비)

**스켈레톤 근거**: `speakers/LA/K3_v1.0.md`를 뼈대로 사용 — K3i는 K3의 설치(install) 버전이며 음향 코어(대역폭/파워핸들링/Max SPL)는 K3와 동일하나, 커넥터가 speakON이 아닌 **2 x 4-point terminal blocks with push-in connection**이고 리깅 시스템이 설치용으로 단순화되어 있다(K3i 자신의 OM p.17-18, docx "Install-specific 2-way active enclosure" 확인).

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | K3i | - |
| Model_Number | null | - |
| Product_Category | long throw line source (install) | - |
| Description | Install-specific 2-way active enclosure with two weather-resistant premium 12 in transducers and one high-output 4 in diaphragm compression driver, user-adjustable horizontal directivity | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: K3i_AE_EN.docx; K3i_OM_EN_3.1.pdf p.5-6("Safety > Instructions").

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 42 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 46 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 50 - 20000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | 143 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 70/110 symmetric or 90 asymmetric | deg |
| Nominal_Directivity_Vertical | dependent upon the number of elements and the line source curvature | - |
| DSP_Preset_Name | K3 70, K3 90, K3 110 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: K3i_AE_EN.docx "Technical requirements".
**음향 코어 동일성**: K3i의 대역폭/Max SPL/파워핸들링 수치가 K3와 완전히 동일(700W/130W/143dB) — 동일 트랜스듀서·앰프 세대를 공유하는 install 파생형으로 판단(원문에 직접적 "동일 코어" 서술은 없으나 수치 완전 일치로 추정, 각주로 명시).
**DSP_Preset_Name**: K3i OM에도 [K3 70]/[K3 90]/[K3 110] 프리셋명이 그대로 사용됨(별도 K3i 전용 프리셋명 없음).

## signal_processing

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | null | - |
| HFC_Function_Settings | null | - |
| Coupling_Function_Range | null | - |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: K1/K2/K3와 동일.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 12" cone driver | - |
| LC_Transducer | null | - |
| MF_Transducer | null | - |
| HF_Transducer | 4" diaphragm compression driver | - |
| LF_Acoustical_Load | bass-reflex | - |
| LC_Acoustical_Load | null | - |
| MF_Acoustical_Load | null | - |
| HF_Acoustical_Load | null | - |
| Passive_Crossover_Network | No | - |
| LF_Nominal_Impedance | 8 | Ohm |
| LC_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall | null | Ohm |
| MF_Nominal_Impedance | null | Ohm |
| HF_Nominal_Impedance | 8 | Ohm |
| RMS_Power_Handling_LF | 700 | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | 130 | W |
| RMS_Power_Handling_Overall | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: K3i_AE_EN.docx "Technical requirements".
**MF_* 비적용, Passive_Crossover_Network=No**: K3와 동일 사유(2-way, K3i_OM_EN_3.1.pdf 전량 "crossover" 스캔 0건).

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 2 x 4-point terminal blocks with push-in connection | - |
| Link_Connector | 2 x 4-point terminal blocks with push-in connection | - |
| Terminal_Block_Pinout_1 | LF+ / LF- | - |
| Terminal_Block_Pinout_2 | HF+ / HF- | - |

### 주석 및 출처 (Notes & Sources)

**출처**: K3i_OM_EN_3.1.pdf p.17 "Connectors"("Internal pinout for L-Acoustics 2-way active enclosures"); K3i_AE_EN.docx "Connectors: 2 x 4-point terminal blocks with push-in connection"(교차검증 일치).
**PA_COM_Pinout_*/SpeakON_Pinout_* 비적용 사유**: K3i는 터미널 블록 커넥터를 사용하며 PA-COM(K1/K2)이나 speakON(K3) 개념이 없음 — Terminal_Block_Pinout_1/2 신규 Key로 대체(K3의 SpeakON_Pinout_*과 동일 원칙, 타 파일에 강제 동기화하지 않음).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA4X, LA8, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: K3i_OM_EN_3.1.pdf p.723 부근 "K3i is driven by the LA4X / LA8 / LA12X amplified controllers" — K3와 동일 호환성.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | simplified installation rigging with K3i-LINK(standard)/K3i-ENDLINK(end) rigging plates; 8x M8 inserts for flying/stacking, 2x M6 inserts for screen | - |
| Inter_Enclosure_Angles_deg | 0.25, 1, 2, 3, 4, 5, 7.5, 10 | deg |
| Handles | null | count |
| Weight_Net | 35 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: K3i_OM_EN_3.1.pdf p.17-18 "Rigging system description"; K3i_AE_EN.docx "Weight (net): 35 kg".
**Handles**: docx/OM에 핸들 개수 서술 없음(설치용 제품 특성상 핸들 대신 인서트 기반 취급으로 설계된 것으로 보이나, 명시적 서술 없어 임의 추정하지 않음) — 미확인.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 907 | mm |
| Height_mm | 357 | mm |
| Depth_mm | 429 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | premium grade Baltic birch plywood | - |
| Front_Material | coated steel grill, acoustically transparent fabric; optional acoustically transparent front screen | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C, pure white RAL 9010, custom RAL code on special order | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: K3i_AE_EN.docx "Physical data".
**Finish_Color**: K3(단일 색상)와 달리 K3i는 설치 환경에 맞춘 3가지 옵션(표준 다크그레이, 화이트, 커스텀 RAL) — install 라인 특성 반영, 원문 그대로 병기.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: 시간 제약상 K3i 전용 프리셋 가이드(서브우퍼 매칭 등)를 확보하지 못함 — 추후 재검토 필요.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: 시간 제약상 미확보.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown | K3i-BUMP + K3i-BAR + rigging plates | 12 | 24 |
| flown and pullback | K3i-RIGBAR x2 + rigging plates | 12 | 16 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | 6 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: K3i_OM_EN_3.1.pdf "Mechanical safety > Flown configurations"; Safety 섹션(Max_Wind_Load 원문 동일 "6 bft").
**범위 제한**: 천장 마운트(ceiling-mounted, 상한 3), Kara IIi 다운필 조합 등 추가 구성이 있으나 기본 플라잉 구성만 채택.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, HF_Acoustical_Load, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Handles, Rigging_Components_Material, Dimensions_Raw(상위 호환), preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 13건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load, MF_Nominal_Impedance, RMS_Power_Handling_MF — 8건. (PA_COM_Pinout_*/SpeakON_Pinout_* 등 타 커넥터 고유 Key는 K3i 자신의 Terminal_Block_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 24건 (미확인 13건 + 비적용 11건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Passive_Crossover_Network(No) — 이 수치는 Kiva II/L2 투입 이전 기준. Kiva II/L2 투입으로 신설된 6개 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)가 이 파일에 모두 비적용 null로 추가 반영되어 실제 총계는 위 수치+6건이다(이 제품은 LC 대역·단일 채널 패시브 아키텍처·멀티모듈 구조가 모두 없음).

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리 Phase 3-1(K3의 install 파생형). K3_v1.0.md를 스켈레톤으로 사용, K3i_AE_EN.docx + K3i_OM_EN_3.1.pdf 통합. 음향 코어는 K3와 완전 동일, 커넥터(터미널 블록)·리깅(설치용 단순화)·마감(화이트/커스텀 옵션)이 K3와 상이. 신규 Key(Terminal_Block_Pinout_1/2)는 SpeakON_Pinout_*과 동일 원칙으로 타 파일 비동기화. |
| v1.1 | Kiva II/L2(신규 제품) 투입으로 신설된 6개 범용 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)를 이 제품에 비적용 null로 동기화 반영(SKILL v1.15 원칙 — 브랜드 무관 범용 개념이므로 동기화 대상). |

**참고(커넥터 핀아웃 Null Report 정확도)**: 위 총계는 이 파일이 처음 작성된 시점 기준이며, 이후 타 커넥터 모델 고유 Key(PA_COM_Pinout_*/SpeakON_Pinout_*/Terminal_Block_Pinout_* 중 이 제품 자신의 실제 커넥터가 아닌 것들)를 전부 삭제하는 후속 정리가 있었다(2026-07-17) — 삭제된 Key는 null 목록에도 더 이상 포함되지 않는다. 정확한 현재 Key 구성은 각 섹션 표를 직접 참조할 것.
| v1.2 | K3의 speakON 관련 커넥터 Key 삭제(사용자 피드백 2026-07-17) — 제품 자신의 실제 커넥터가 아닌 타 커넥터 모델(PA-COM/speakON/terminal block 등) 고유 핀아웃 Key를 null 목록에서도 완전히 제거. 이 제품의 실제 커넥터 핀아웃은 아래 표기된 자기 자신의 Key만으로 온전히 표현됨. |
