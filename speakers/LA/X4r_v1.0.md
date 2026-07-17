# X4r (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1(X4i의 recessed/매입형 파생형)

**스켈레톤 근거**: `speakers/LA/X4i_v1.0.md`를 뼈대로 사용 — X4r은 X4i와 음향/전기 스펙이 완전히 동일한 "recessed version"(벽/천장 매입형)이다. 원문 자체에 "recessed version"으로 명시되어 있으며, 스펙 표 수치([X4]=120Hz/116dB, [X4_60]=65Hz/110dB, 110° axisymmetric, 4"/1.4" 트랜스듀서, 밀폐형, 16Ω, screw terminal)가 X4i와 완전히 일치함을 확인했다. 차이는 전면 그릴 유무(매입형이라 별도 전면 그릴 없음), 중량(0.94kg vs 1kg), 리깅 하드웨어(X4r-inCW 매입 액세서리) 정도다. A&E 시방서는 제공되지 않아 OM(X4r owner's manual EN version 1.0) 단일 소스 기준. **원문 데이터 품질 이슈**: OM의 Loudspeaker configurations 챕터 딜레이 표가 "X4i"/"SB6i"/"SB10i" 라벨을 그대로 사용(X4i 매뉴얼에서 복사된 것으로 추정되는 라벨링 오류) — 실제로는 X4r/SB6r/SB10r을 가리키는 것으로 판단해 정정 채택.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | X4r | - |
| Model_Number | null | - |
| Product_Category | short throw point source (recessed version) | - |
| Description | 2-way passive coaxial enclosure (recessed version): 4" LF neodymium cone driver + 1.4" HF diaphragm compression driver, amplified by LA2Xi / LA4X / LA7.16i / LA12X | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | EN 62368-1:2014 Audio/video, information and communication technology equipment — Part 1: Safety requirements | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf(X4r owner's manual EN version 1.0) p.37 "X4r specifications"(A&E 시방서 미제공).

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | [X4_60]: 65 - 20000 / [X4]: 120 - 20000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak | [X4]: 116 dB / [X4_60]: 110 dB | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 110 (axisymmetric) | deg |
| Nominal_Directivity_Vertical | 110 (axisymmetric) | deg |
| DSP_Preset_Name | X4, X4_60, X4_MO | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf p.37 "X4r specifications"(X4i와 수치 완전 일치, 독립 확인).
**Frequency_Response_6dB/3dB_Hz 미확인 사유**: A&E 시방서 미제공(X4i는 AE로 확보했으나 X4r은 OM만 제공되어 이 세부 임계값이 원문에 없음).

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
| LF_Acoustical_Load | closed enclosure | - |
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
| RMS_Power_Handling_Overall | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf p.37 "X4r specifications".
**RMS_Power_Handling_Overall 미확인 사유**: X4i는 AE 시방서로 42W를 확보했으나, X4r은 A&E 미제공에 OM 스펙 표에도 파워 핸들링 항목 자체가 없음 — X4i와 트랜스듀서가 동일해 실질적으로 같은 값일 가능성이 높으나(42W 추정), 확인되지 않은 값을 다른 제품에서 끌어와 채우지 않는다는 원칙에 따라 null로 유지.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x 2-point screw terminal | - |
| Link_Connector | 1 x 2-point screw terminal | - |
| Screw_Terminal_Pinout_1 | + / - (combined LF+HF signal, internally split by passive crossover) | - |
| Screw_Terminal_Pinout_2 | Not linked | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf "Connectors"("Internal pinout for L-Acoustics 2-way passive enclosures" — X4i와 동일 표 제목/구조).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA2Xi, LA4X, LA7.16i, LA12X | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Passive (2-way) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf "X4r is driven by the LA2Xi / LA4X / LA7.16i / LA12X amplified controllers".

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | 2 x M5 inserts(X4r-inCW/X-U4i 마운트용), 2 x M6 inserts(리깅 액세서리용), 1 x M6 insert(보조 안전용) | - |
| Inter_Enclosure_Angles_deg | null | deg |
| Handles | 0 | count |
| Weight_Net | 0.94 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf p.37 "X4r specifications"("Rigging and handling").
**Handles=0**: X4i와 동일 사유(원문 전량 스캔, "handle" 키워드 0건) — 매입형이라 손잡이 개념 자체가 X4i보다도 더 명확히 불필요.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 116 | mm |
| Height_mm | 116 | mm |
| Depth_mm | 99 | mm |
| Dimensions_Raw [1] | 116 / 116 / 99 / 109 | mm |
| Cabinet_Material | premium grade Baltic birch plywood | - |
| Front_Material | null | - |
| Rigging_Components_Material | null | - |
| Finish_Color | dark grey brown Pantone 426 C | - |
| IP_Rating [2] | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf p.37 "X4r specifications", "X4r dimensions"(치수 도면, X4i와 동일 수치).
**[1] Dimensions_Raw**: X4i와 동일 도면 수치(116/116/99/109mm).
**Front_Material 비적용 사유**: 매입형(recessed) 제품이라 전면 그릴/패브릭 스펙이 원문 표에서 아예 빠짐(X4i는 "coated steel grill, acoustically neutral 3D fabric" 명시) — X4r은 스크린/커버 액세서리(X4r-inCW 등)가 별도이며 인클로저 자체 스펙에는 전면 마감이 없음.
**Finish_Color 단순화**: X4i는 3가지 마감(dark grey brown/pure white/custom RAL)을 제공하나 X4r은 원문에 "dark grey brown Pantone 426 C" 1가지만 명시 — 매입형이라 마감 옵션이 적은 것으로 판단, 원문 그대로 채택(임의로 추가하지 않음).
**[2] IP_Rating 조건부**: OM 각주 2 "When integrated in-wall or in-ceiling with screen and connector sealing plate" — X4i와 유사하나 매입 시공 자체가 조건.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| X4r standalone (고SPL) | [X4] | 120 - 20000 | null | null |
| X4r with SB6r, closely coupled(200Hz) | [X4] + [SB6_200] | 32 - 20000 | 1 X4r : 1 SB6r | null |
| X4r with SB6r, coupled(100Hz) | [X4] + [SB6_100] | 29 - 20000 | 1 X4r : 1 SB6r | null |
| X4r with SB6r, separated(60Hz) | [X4_60] + [SB6_60] | 29 - 20000 | 2 X4r : 1 SB6r | null |
| X4r with SB10r, closely coupled(200Hz) | [X4] + [SB10_200] | 29 - 20000 | 2 X4r : 1 SB10r | null |
| X4r with SB10r, coupled(100Hz) | [X4] + [SB10_100] | 27 - 20000 | 2 X4r : 1 SB10r | null |
| X4r with SB10r, separated(60Hz) | [X4_60] + [SB10_60] | 25 - 20000 | 3 X4r : 1 SB10r | null |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf p.17-24 "Loudspeaker configurations"("X4r point source with SB6r", "X4r point source with SB10r"). X4i와 달리 이 6개 조합 모두 원문에서 Ratio가 명시적으로 상이함을 확인(closely coupled/coupled는 1:1(SB6r)/2:1(SB10r), separated는 2:1(SB6r)/3:1(SB10r)) — X4i 파일 작성 시 SB10i 조합을 상세 조사하지 않았던 것과 달리 X4r은 6개 조합 전부 조사.

## delay_defaults

| Preset_Combo | K1_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [X4] or [X4_MO] + [SB6_200] | 0.6 | SB6r = 0 | X4r = + / SB6r = - |
| [X4] or [X4_MO] + [SB6_100] | 0 | SB6r = 0.4 | X4r = + / SB6r = + |
| [X4_60] + [SB6_60] | 1.8 | SB6r = 0 | X4r = + / SB6r = - |
| [X4] + [SB10_200] | 1.9 | SB10r = 0 | X4r = + / SB10r = - |
| [X4_MO] + [SB10_200] | 0 | SB10r = 0 | X4r = + / SB10r = + |
| [X4] or [X4_MO] + [SB10_100] | 0.8 | SB10r = 0 | X4r = + / SB10r = + |
| [X4_60] + [SB10_60] | 7.2 | SB10r = 0 | null |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf p.19-23 "Pre-alignment delays". 극성은 색상 아이콘 표기라 Windows.Data.Pdf WinRT API로 페이지 이미지 렌더링해 육안 확인. 원문 표의 "X4i"/"SB6i"/"SB10i" 라벨은 X4r/SB6r/SB10r로 정정 채택(파일 서두 "원문 데이터 품질 이슈" 참조).
**[X4_60] + [SB10_60] Polarity 미확인**: 딜레이 수치(X4r=7.2ms, SB10r=0ms)는 텍스트로 확인했으나, 이 조합의 극성 아이콘 페이지를 렌더링하지 못해(시간 배분상 나머지 6개 조합 우선 확인) 극성만 null로 유지.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| all configurations | X4r-inCW, X-U4i 등 | 1 | 1 |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 5:1 | - |
| Max_Wind_Load | null | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: X4r_OM_EN.pdf "Mechanical safety"(X4i와 동일 서술 — EN 62368-1, safety factor 5).

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance(단일 통합값만 존재), RMS_Power_Handling_LF/MF/HF/Overall(A&E 미제공), Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Inter_Enclosure_Angles_deg, Front_Material, Rigging_Components_Material, Max_Wind_Load, preset_guide_and_matching(Minimum_Line_Length 전 행) — 18건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, MF_Transducer, MF_Acoustical_Load, HF_Acoustical_Load — 6건. (PA_COM_Pinout_*/SpeakON_Pinout_*/Terminal_Block_Pinout_* 등 타 커넥터 고유 Key는 X4r 자신의 Screw_Terminal_Pinout_*으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 24건 (미확인 18건 + 비적용 6건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Handles(0, 원문 전량 스캔 근거).

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리(X4i의 recessed/매입형 파생형). X4i_v1.0.md를 스켈레톤으로 사용, OM(X4r owner's manual EN version 1.0) 단일 소스(A&E 시방서 미제공). 음향/전기 스펙은 X4i와 완전 동일함을 확인, 물리적 차이(전면 그릴 없음, 중량, 마감 옵션 축소)만 반영. preset_guide_and_matching/delay_defaults는 SB6r/SB10r 6개 조합(closely coupled/coupled/separated × 2 서브우퍼) 전부 원문 직접 조사로 실값 확보(극성은 PDF 페이지 이미지 렌더링, 1개 조합만 시간 배분상 미확인) — X4i보다 더 상세한 조사. 원문 딜레이 표의 "X4i/SB6i/SB10i" 라벨링 오류(X4i 매뉴얼에서 복사된 것으로 추정)를 발견하고 정정. |
