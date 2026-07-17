# SB6r (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(SB6i의 recessed/매입형 파생형)

**스켈레톤 근거**: `speakers/LA/SB6i_v1.0.md`를 뼈대로 사용 — SB6r은 원문이 명시적으로 "SB6r is the recessed version of the SB6i enclosure"라 서술하는 매입형 파생품으로, 스펙 표 수치(저역한계/Max SPL: 29Hz/110dB, 29Hz/111dB, 32Hz/115dB — 3개 프리셋 전부)가 SB6i와 완전히 일치함을 원문에서 직접 확인했다. A&E 시방서는 제공되지 않아 OM(SB6r owner's manual EN version 1.1) 단일 소스 기준.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | SB6r | - |
| Model_Number | null | - |
| Product_Category | ultra-shallow subwoofer (recessed version) | - |
| Description | Ultra-shallow subwoofer (recessed version): 2 x 6.5" cone drivers, amplified by LA2Xi / LA4X / LA7.16i / LA12X | - |
| Way_Count | 1 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SB6r_OM_EN.pdf(SB6r owner's manual EN version 1.1) p.45 "SB6r specifications"(A&E 시방서 미제공).

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [1] | [SB6_60]: 29 - null / [SB6_100]: 29 - null / [SB6_200]: 32 - null | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | [SB6_60]: 110 / [SB6_100]: 111 / [SB6_200]: 115 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | null | deg |
| Nominal_Directivity_Vertical | null | - |
| DSP_Preset_Name | SB6_60, SB6_100, SB6_200 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SB6r_OM_EN.pdf p.45 "SB6r specifications".
**[1] Usable_Bandwidth_Hz 상한 미확인**: OM 스펙 표는 "Low frequency limit (-10 dB)"만 제공하고 상한(예: 20kHz)을 명시하지 않음 — SB6i는 자체 A&E 시방서로 상한 및 -6dB/-3dB 세부값(예: 29-107Hz)을 확보했으나, SB6r은 A&E 미제공이라 원문에 없는 수치를 SB6i에서 끌어와 채우지 않음(SB6i와 저역한계·SPL이 완전히 동일하다는 사실은 확인되었으나, 상한/중간 dB 임계값까지 동일하다고 단정할 근거는 SB6r 자신의 문서에 없음).

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
| LF_Transducer | 2 x 6.5" cone driver | - |
| MF_Transducer | null | - |
| HF_Transducer | null | - |
| LF_Acoustical_Load | bass-reflex, L-Vents | - |
| MF_Acoustical_Load | null | - |
| HF_Acoustical_Load | null | - |
| Passive_Crossover_Network | No | - |
| LF_Nominal_Impedance | 4 | Ohm |
| MF_Nominal_Impedance | null | Ohm |
| HF_Nominal_Impedance | null | Ohm |
| Nominal_Impedance_Overall | null | Ohm |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: SB6r_OM_EN.pdf p.45 "SB6r specifications".
**RMS_Power_Handling_LF 미확인 사유**: SB6i는 AE로 85W를 확보했으나 SB6r은 A&E 미제공, OM 스펙 표에도 파워 핸들링 항목 자체가 없음 — 미확인.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x 4-point terminal block with push-in connection | - |
| Link_Connector | null | - |
| Terminal_Block_Pinout_1 | + / - | - |
| Terminal_Block_Pinout_2 | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SB6r_OM_EN.pdf "Connectors"("Internal pinout for L-Acoustics subwoofers" — SB6i와 동일 구조).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA2Xi, LA4X, LA7.16i, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (1-way, subwoofer) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SB6r_OM_EN.pdf "The SB6r subwoofer is driven by the LA2Xi / LA4X / LA7.16i / LA12X amplified controllers".

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | 8 x M6 threaded inserts for rigging accessories | - |
| Inter_Enclosure_Angles_deg | null | deg |
| Handles | null | count |
| Weight_Net | 7.6 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: SB6r_OM_EN.pdf p.45 "SB6r specifications"("Rigging and handling"). SB6i(8.6kg)보다 가벼움 — 매입형이라 전면 그릴 등 일부 부품이 없는 것으로 추정.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 360 | mm |
| Height_mm | 532 | mm |
| Depth_mm | 99 | mm |
| Dimensions_Raw [1] | 360 / 532 / 99 / 104.2 | mm |
| Cabinet_Material | premium grade Baltic beech and birch plywood | - |
| Front_Material | null | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C | - |
| IP_Rating [2] | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SB6r_OM_EN.pdf p.45-46 "SB6r specifications"/"SB6r dimensions"(치수 도면, SB6i와 완전 동일 수치).
**[1] Dimensions_Raw**: SB6i와 동일 도면 수치(360/532/99/104.2mm).
**Front_Material 비적용 사유**: 매입형(recessed) 제품이라 전면 그릴/패브릭 스펙이 원문 표에서 빠짐(X4r과 동일 패턴).
**Finish_Color 단순화**: SB6i는 3가지 마감을 제공하나 SB6r은 원문에 "dark grey brown Pantone 426 C" 1가지만 명시.
**[2] IP_Rating 조건부**: OM 각주 2 "When integrated in-wall or in-ceiling with screen and connector sealing plate".

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| SB6r standard configuration | [SB6_60] / [SB6_100] / [SB6_200] | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: OM 자체 스펙 표에 저역한계만 있고 전체 대역 범위(상한 포함)가 없어 Frequency_Range_10dB_Hz를 채울 수 없음. X6i/X4i 계열과의 조합 데이터는 원본에서 별도 확인하지 못함(X6i/X4i 매뉴얼에는 SB6i(r) 표기로 SB6i와 SB6r을 함께 지칭하는 조합 프리셋이 있었으나, SB6r 자신의 문서에는 상세 조합표가 없음).

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**미확인 사유(조사 완료 후 확정)**: SB6i와 동일한 구조적 이유 — SB6r은 항상 2차 엘리먼트로만 등장. X6i 매뉴얼의 "SB6i(r)" 표기가 SB6i와 SB6r을 공용으로 다루는 것으로 보이나, 정확한 SB6r 전용 딜레이 값은 X6i/X4i 파일에도 "SB6i" 명의로만 기록되어 있어(SB6r 명의 데이터 별도 확인 안 됨) 이 파일에서는 미확인으로 유지.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| null | null | null | null |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | null | - |
| Max_Wind_Load | null | Beaufort |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: SB6i와 동일 사유.

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Usable_Bandwidth_Hz(상한), Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, Nominal_Directivity_Horizontal_deg, Nominal_Directivity_Vertical, Link_Connector, Terminal_Block_Pinout_2, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Handles, Front_Material, Rigging_Components_Material, preset_guide_and_matching(전 항목), delay_defaults(전 항목), mechanical_safety(전 항목), Safety_Factor, Max_Wind_Load — 20건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, HF_Transducer, MF_Acoustical_Load, HF_Acoustical_Load, MF_Nominal_Impedance, HF_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_MF, RMS_Power_Handling_HF, RMS_Power_Handling_Overall — 13건. (PA_COM_Pinout_*/SpeakON_Pinout_* 등 타 커넥터 고유 Key는 SB6r 자신의 Terminal_Block_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 33건 (미확인 20건 + 비적용 13건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Passive_Crossover_Network(No).

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(SB6i의 recessed/매입형 파생형). SB6i_v1.0.md를 스켈레톤으로 사용, OM(SB6r owner's manual EN version 1.1) 단일 소스(A&E 시방서 미제공). 스펙 표 수치(저역한계/Max SPL)가 SB6i와 완전 동일함을 확인했으나, A&E 부재로 대역 상한/파워 핸들링/조합 데이터는 SB6i에서 끌어오지 않고 정직하게 미확인으로 유지(SKILL "미확인 원본성 요건" 원칙 준수). |
| v1.1 | delay_defaults 표의 컬럼명 `K1_Delay_ms`를 `Primary_Element_Delay_ms`로 전면 개명(SKILL v1.18) — 값 변경 없음(사용자 지적 2026-07-17). |
