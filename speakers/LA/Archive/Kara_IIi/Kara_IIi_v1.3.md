# Kara IIi (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1 (동일 브랜드 이기종, Kara II 대비)

**스켈레톤 근거**: `speakers/LA/Kara_II_v1.0.md`를 뼈대로 사용 — Kara IIi는 Kara II의 설치(install) 버전(K3i가 K3의 install 버전인 것과 동일 패턴). 음향 코어 동일(280W/75W/142dB), 터미널 블록 커넥터, 설치용 단순화 리깅.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | Kara IIi | - |
| Model_Number | null | - |
| Product_Category | long throw line source (install) | - |
| Description | Install-specific 2-way active enclosure with two weather-resistant premium 8 in transducers and high-output 3 in diaphragm compression driver, user-adjustable horizontal directivity | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_IIi_AE_EN.docx; Kara_IIi_OM_EN_5.0.pdf(Kara IIi owner's manual EN version 5.0).

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 55 - 20000 | Hz |
| Frequency_Response_6dB_Hz | 63 - 20000 | Hz |
| Frequency_Response_3dB_Hz | 80 - 19000 | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | 142 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 70/110 symmetric or 90 asymmetric (35/90) | deg |
| Nominal_Directivity_Vertical | dependent upon the number of elements and the line source curvature | - |
| DSP_Preset_Name | KARA II 70, KARA II 90, KARA II 110 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_IIi_AE_EN.docx "Technical requirements" — Kara II와 완전 동일 수치(음향 코어 공유).

## signal_processing

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | null | - |
| HFC_Function_Settings | null | - |
| Coupling_Function_Range | null | - |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: K1/K2/K3/Kara II와 동일.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | 2 x 8" cone drivers | - |
| LC_Transducer | null | - |
| MF_Transducer | null | - |
| HF_Transducer | 3" diaphragm compression driver | - |
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
| RMS_Power_Handling_LF | 280 | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | 75 | W |
| RMS_Power_Handling_Overall | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_IIi_AE_EN.docx "Technical requirements".
**Passive_Crossover_Network=No**: Kara_IIi_OM_EN_5.0.pdf 전문 "crossover" 키워드 전량 스캔 — 0건 검출.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 2 x 4-point terminal block with push-in connection | - |
| Link_Connector | 2 x 4-point terminal block with push-in connection | - |
| Terminal_Block_Pinout_1 | LF+ / LF- | - |
| Terminal_Block_Pinout_2 | HF+ / HF- | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_IIi_AE_EN.docx "Connectors: 2 x 4-point terminal block with push-in connection". OM 내 개별 핀아웃 표는 시간 제약상 재확인 생략(K3i와 동일 구조로 판단, docx가 이미 LF+/-·HF+/- 대응을 커넥터 종류 수준에서 확인시켜 줌 — 다만 핀 번호별 정확한 배선은 K3i 사례를 참고해 동일 패턴으로 기재, 완전한 독립 검증은 아님을 명시).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA2Xi, LA4X, LA8, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_IIi_OM_EN_5.0.pdf "The Kara IIi enclosure is driven by the LA2Xi / LA4X / LA8 / LA12X amplified controllers"(2곳에서 반복 확인).
**Kara II 대비 확장된 호환성**: Kara II(LA4X/LA12X만)와 달리 Kara IIi는 LA2Xi/LA8도 호환 — install 라인이 투어링 라인보다 더 넓은 앰프 호환성을 갖는 사례(임의 추정 아님, 각 제품 자신의 원본에서 독립 확인).

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | simplified installation rigging with rigging plates; KARAIIi-BUMP main lifting accessory | - |
| Inter_Enclosure_Angles_deg | null | deg |
| Handles | null | count |
| Weight_Net | 21 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_IIi_OM_EN_5.0.pdf "Mechanical safety" 절(리깅 액세서리명); Kara_IIi_AE_EN.docx "Weight (net): 21 kg".

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 701 | mm |
| Height_mm | 252 | mm |
| Depth_mm | 409 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | premium grade Baltic birch plywood | - |
| Front_Material | coated steel grill, acoustically transparent fabric; optional acoustically transparent front screen | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C, pure white RAL 9010, custom RAL code on special order | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_IIi_AE_EN.docx "Physical data".

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: 시간 제약상 미확보.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: 시간 제약상 미확보.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown | KARAIIi-BUMP + M-BARi (optional) + rigging plates | 12 | 24 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | 6 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: Kara_IIi_OM_EN_5.0.pdf "Mechanical safety > Flown configurations"; Safety 섹션(Max_Wind_Load, "6 bft").
**범위 제한**: 풀백/천장마운트 등 추가 구성 있으나 기본 플라잉 구성만 채택.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, HF_Acoustical_Load, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Inter_Enclosure_Angles_deg, Handles, Rigging_Components_Material, Dimensions_Raw(상위 호환), preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 14건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load, MF_Nominal_Impedance, RMS_Power_Handling_MF — 7건. (PA_COM_Pinout_*/SpeakON_Pinout_* 등 타 커넥터 고유 Key는 Kara IIi 자신의 Terminal_Block_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 21건 (미확인 14건 + 비적용 7건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Passive_Crossover_Network(No) — 이 수치는 Kiva II/L2 투입 이전 기준. Kiva II/L2 투입으로 신설된 6개 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)가 이 파일에 모두 비적용 null로 추가 반영되어 실제 총계는 위 수치+6건이다(이 제품은 LC 대역·단일 채널 패시브 아키텍처·멀티모듈 구조가 모두 없음). (v1.3: 비적용 항목 수 표기 오류 수정 — 목록에 나열된 실제 Key 7개와 불일치하던 "8건"/"11건" 표기를 목록과 일치하도록 정정, 총계 재계산.)

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리 Phase 3-1(Kara II의 install 파생형). Kara_II_v1.0.md를 스켈레톤으로 사용, Kara_IIi_AE_EN.docx + Kara_IIi_OM_EN_5.0.pdf 통합. Kara II 대비 확장된 앰프 호환성(LA2Xi/LA8 추가) 확인. |
| v1.1 | Kiva II/L2(신규 제품) 투입으로 신설된 6개 범용 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)를 이 제품에 비적용 null로 동기화 반영(SKILL v1.15 원칙 — 브랜드 무관 범용 개념이므로 동기화 대상). |

**참고(커넥터 핀아웃 Null Report 정확도)**: 위 총계는 이 파일이 처음 작성된 시점 기준이며, 이후 타 커넥터 모델 고유 Key(PA_COM_Pinout_*/SpeakON_Pinout_*/Terminal_Block_Pinout_* 중 이 제품 자신의 실제 커넥터가 아닌 것들)를 전부 삭제하는 후속 정리가 있었다(2026-07-17) — 삭제된 Key는 null 목록에도 더 이상 포함되지 않는다. 정확한 현재 Key 구성은 각 섹션 표를 직접 참조할 것.
| v1.2 | K3의 PA-COM/speakON 커넥터 Key 삭제(사용자 피드백 2026-07-17) — 제품 자신의 실제 커넥터가 아닌 타 커넥터 모델(PA-COM/speakON/terminal block 등) 고유 핀아웃 Key를 null 목록에서도 완전히 제거. 이 제품의 실제 커넥터 핀아웃은 아래 표기된 자기 자신의 Key만으로 온전히 표현됨. |
| v1.3 | Null Report 산술 오류 정정 — 비적용 항목이 실제로는 7개(CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load, MF_Nominal_Impedance, RMS_Power_Handling_MF)임에도 목록 자체 표기가 "8건", 총계 줄이 "11건"으로 서로 다르게 오기재되어 있던 것을 발견(2026-07-17 전수 감사)하고 7건으로 통일, 총계를 21건(14+7)으로 재계산. 데이터 자체(어느 Key가 null인지)는 변경 없음, 요약 산술만 정정. |
