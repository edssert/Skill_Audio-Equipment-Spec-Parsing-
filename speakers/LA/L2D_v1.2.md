# L2D (L-Acoustics) — Master Schema

**Category**: speakers | **Brand**: L-Acoustics (LA) | **Schema Phase**: Phase 3-1 (동일 브랜드 이기종 — L2의 자매품)

**스켈레톤 근거**: `speakers/LA/L2_v1.3.md`를 뼈대로 사용 — L2D는 L2와 동일한 원본 OM(L2 owner's manual EN version 5.0)에서 함께 다뤄지는 자매품이며, K1 매뉴얼이 K2를 함께 다뤘던 것과 동일한 패밀리 문서 구조다(K2가 K1과 별도 파일로 분리된 선례와 동일하게 처리). 사용자 지시(2026-07-17)로 L2와 별도 파일로 분리 파싱했다. L2D 전용 A&E 시방서(`L2D_AE_EN.docx`)가 이번에 함께 제공되어, L2D 고유 스펙(60° 커버리지, 저중량, 상이한 Directivity/치수/Max SPL)을 OM 부록 스펙 표와 A&E 양쪽에서 교차 확인했다. 트랜스듀서 구성(4x12" LC + 8x10" LF + 8x3" HF)·커넥터(37-point, 32핀)·앰프 호환성은 L2와 완전 동일 — 차이는 수직 커버리지(10° vs 60°), 하부 2개 모듈의 고정 프로그레시브 지향각(110°-140°), 중량(158kg vs 149kg), Max SPL(155/147dB vs 151/147dB)에 있다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | L2D | - |
| Model_Number | null | - |
| Product_Category | 16-channel active progressive curvature WST enclosure | - |
| Description | 16-channel active progressive curvature WST 60 deg enclosure: 4 x 12" LC + 8 x 10" LF + 8 x 3" HF, amplified by LA7.16 / LA7.16i | - |
| Way_Count | 3 (LC/LF/HF) | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | 2006/42/EC Machinery Directive (rigging system, designed per BGV-C1 guidelines) | - |
| WEEE_Marking | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf(L2 owner's manual EN version 5.0) p.181 "L2D specifications", p.6("Safety > Instructions", L2/L2D 공용 챕터); L2D_AE_EN.docx(`speakers/LA/Original_PDFs/L2D/`) "Description"/"Short description".
**Way_Count**: L2와 동일 사유 — LC/LF/HF 3개 트랜스듀서 그룹을 명확히 구분해 명시.
**Compliance_Standards**: L2와 공용되는 "Mechanical safety" 챕터("The L2 rigging system complies with 2006/42/EC...")에서 채택 — L2D 전용 별도 조항은 없음.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [1] | 45 - 20000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_5dB_Hz | null | Hz |
| Max_SPL_Peak [2] | 151 | dB |
| Max_SPL_Single_Module [2] | 147 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg [3] | (upper 2 modules) 70/110 symmetric or 90 asymmetric; (lower 2 modules) fixed progressive 110-140 | deg |
| Nominal_Directivity_Vertical | 60 | deg |
| DSP_Preset_Name | L2D 70 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf p.181 "L2D specifications"; L2D_AE_EN.docx "Technical requirements"(Usable_Bandwidth_Hz -10dB 확정, RMS_Power_Handling_* 출처).
**[1] Usable_Bandwidth_Hz -10dB 확정**: L2와 동일 사유 — OM 스펙 표에는 dB 임계값이 없으나 L2D_AE_EN.docx가 "Usable bandwidth: 45 Hz - 20 kHz (-10 dB)"로 명시.
**[2] Max_SPL_Peak/Max_SPL_Single_Module**: 원문(OM) "Maximum SPL: entire enclosure module 151 dB([L2D 70]) / 1 only 147 dB([L2D 70])" — L2D_AE_EN.docx도 "151 dB for the full element / 147 dB for the first module"로 동일 확인. L2(155/147dB)보다 entire-enclosure 값이 낮음 — 60° 커버리지로 인한 음향 출력 분산 차이로 추정(원문에 명시적 설명은 없음, 추정 표현임을 밝힘).
**[3] Nominal_Directivity_Horizontal_deg 구조 상이**: L2는 전 모듈이 동일한 수평 지향각 설정(70/110 또는 90 비대칭)을 공유하나, L2D는 상부 2개 모듈만 사용자 조정 가능(70/110/90)하고 하부 2개 모듈은 고정된 프로그레시브 지향각(110°→140°)을 가짐 — OM "Waveguide directivity (upper part) 70° / 110° symmetric or 90° asymmetric (lower part) progressive from 110° to 140°"와 L2D_AE_EN.docx "Waveguide directivity: upper modules 70° / 110° symmetric or 90° asymmetric, lower modules fixed progressive from 110° to 140°"가 일치. 이는 L2D가 어레이 최하단 전용으로 설계된 것과 관련(하부일수록 더 넓은 커버리지가 필요).
**Nominal_Directivity_Vertical=60**: L2(10°)와 구분되는 L2D의 핵심 아키텍처 차이 — 어레이 최하단에 배치되어 넓은 수직 커버리지를 담당하도록 설계됨(OM "Rigging system description" 챕터, "the 60° curvature of L2D is designed to make it the last enclosure at the bottom of the array").

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
| LF_Transducer | 8 x 10" neodymium cone drivers | - |
| HF_Transducer | 8 x 3" neodymium diaphragm compression drivers | - |
| LC_Transducer | 4 x 12" neodymium cone drivers | - |
| LF_Acoustical_Load | bass-reflex, L-Vents | - |
| HF_Acoustical_Load [1] | DOSC waveguide, L-Fins (upper part) | - |
| LC_Acoustical_Load | bass-reflex, L-Vents | - |
| Passive_Crossover_Network | No | - |
| LF_Nominal_Impedance | 8 | Ohm |
| HF_Nominal_Impedance | 8 | Ohm |
| LC_Nominal_Impedance | 8 | Ohm |
| Nominal_Impedance_Overall | null | Ohm |
| RMS_Power_Handling_LC | 561 | W |
| RMS_Power_Handling_LF | 644 | W |
| RMS_Power_Handling_HF | 381 | W |
| RMS_Power_Handling_Overall | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf p.181 "L2D specifications"; L2D_AE_EN.docx "Technical requirements"(Transducers/Acoustics).
**트랜스듀서 스펙 L2와 완전 동일**: 드라이버 구성(4x12" LC, 8x10" LF, 8x3" HF)·재질·임피던스(모두 8Ω)·RMS 파워 핸들링(LC 561W/LF 644W/HF 381W) 모두 L2와 동일값 — L2D_AE_EN.docx의 대응 항목과 L2_AE_EN.docx의 대응 항목이 문자 그대로 일치함을 직접 대조 확인.
**[1] HF_Acoustical_Load "(upper part)" 한정**: 원문(OM) "HF: DOSC waveguide, L-Fins (upper part)" — L2는 이 한정어가 없는 반면 L2D는 상부 2개 모듈에만 해당 웨이브가이드 구조가 적용됨을 명시(하부 2개 모듈은 고정 지향각이라 L-Fins 조정 메커니즘이 없는 것으로 추정, 원문 그대로 보존).
**Passive_Crossover_Network=No**: L2와 동일 사유(공용 OM 텍스트, 16채널 완전 개별 구동 구조).

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x 37-point male connector (32 points used) | - |
| Link_Connector | null | - |
| Connector_16Channel_Pinout [1] | A/B=LC1, C/D=LF1/LF2, E/F=HF1, G/H=HF2, J/K=LC2, L/M=LF3/LF4, N/P=HF3, R/S=HF4, T/U=LC3, V/W=LF5/LF6, X/Z=HF5, a/b=HF6, c/d=LC4, e/f=LF7/LF8, g/h=HF7, j/k=HF8, m/n/p/r/s=not used | - |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf p.24 "Connectors"("Internal pinout for L-Acoustics active 16-channel enclosures" 표) — L2/L2D 공용 페이지, "L2 ... 1 x 37-point male connector (32 points used) / L2D ... 1 x 37-point male connector (32 points used)"로 병기되고 핀아웃 표는 하나만 제공됨.
**[1] Connector_16Channel_Pinout 값 L2와 동일**: 원문이 L2/L2D 공용 단일 표로 제공 — 별도 L2D 전용 핀아웃 없음, L2_v1.3.md와 동일 값 채택.
**Link_Connector 비적용 사유**: L2와 동일 — IN 1개(37-point)만 명시.

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | LA7.16, LA7.16i | - |
| Max_Enclosures_Per_Controller_Output | null | count |
| Max_Enclosures_Per_Controller_Total | null | count |
| Crossover_Type | Active (16-channel) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf p.51 "Loudspeaker configurations"("L2/L2D can be driven by the LA7.16 / LA7.16i amplified controllers"), p.181 "L2D specifications" Description 행.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | flush-fitting 4-point captive rigging system compatible with L2; front rotating arm + rear sliding arm, automatic latch system | - |
| Inter_Enclosure_Angles_deg | null | deg |
| Handles | 4 | count |
| Weight_Net | 149 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf p.181 "L2D specifications"; p.24-25 "Rigging system description"; L2D_AE_EN.docx "Physical data"(Weight_Net 교차 확인).
**Handles=4, ground runner 없음**: 원문(OM) "Rigging and handling: flush-fitting 4-point captive rigging system compatible with L2 / 4 handles" — L2는 "4 handles / 4 ground runners"로 그라운드 러너가 별도 명시되나 L2D는 handles만 명시(L2D_AE_EN.docx도 "integrates four ergonomic handles"만 언급, ground runner 언급 없음) — L2D가 항상 어레이 최하단에 위치해 별도 지면 접지 러너가 불필요한 설계로 추정.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 850 | mm |
| Height_mm | 1252 | mm |
| Depth_mm | 559 | mm |
| Dimensions_Raw [1] | 850 / 1207 / 1252 / 559 | mm |
| Cabinet_Material | premium grade Baltic beech and birch plywood | - |
| Front_Material | coated steel grill, acoustically neutral 3D fabric | - |
| Rigging_Components_Material | high grade steel with anti-corrosion coating | - |
| Finish_Color | dark grey brown Pantone 426 C, pure white RAL 9010, custom RAL code on special order | - |
| IP_Rating | IP55 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf p.181-182 "L2D specifications"/"L2D dimensions"(치수 도면); L2D_AE_EN.docx "Physical data" - "Dimensions (W, H, D): 850 mm, 1252 mm, 559 mm".
**[1] Width/Height/Depth_mm 축 확정**: L2D_AE_EN.docx가 "Dimensions (W, H, D): 850 mm, 1252 mm, 559 mm"로 축을 명시적으로 확정. Dimensions_Raw는 OM 도면에서 추출된 4개 숫자(850/1207/1252/559, L2의 4개 숫자 850/1115/1197/559와 비교하면 1207/1252가 L2의 1115/1197 대비 더 큼 — L2D가 더 큰 높이 방향 치수를 가짐, 60° 커버리지를 위한 프로그레시브 모듈 구조 때문으로 추정)를 그대로 보존.
**Weight_Net=149kg**: L2(158kg)보다 9kg 가벼움 — OM/AE 양쪽 모두 149kg으로 일치.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| L2D line source (단독) | [L2D 70] / [L2D 90] / [L2D 110] / [L2D 70_S] / [L2D 90_S] / [L2D 110_S] | 45 - 20000 | null | null |
| L2D line source with coupled KS28 [1] | [L2D 70]/[L2D 90]/[L2D 110]/[L2D 70_S]/[L2D 90_S]/[L2D 110_S] + [KS28 L2_C]/[KS28 L2_Cx] | 25 - 20000 | null | null |
| L2D line source with separated KS28 [2] | [L2D 70]/[L2D 90]/[L2D 110]/[L2D 70_S]/[L2D 90_S]/[L2D 110_S] + [KS28 L2]/[KS28 L2_C]/[KS28 L2_Cx] | 25 - 20000 | null | null |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf p.51-53 "Loudspeaker configurations"(L2/L2D 공용 챕터 — "Enclosure L2 L2D" 표에 두 제품의 프리셋이 나란히 기재됨).
**Recommended_Ratio/Minimum_Line_Length null 사유**: L2와 동일 — 원문이 비율/최소 길이가 아닌 물리적 거리(coupled) 또는 최대 간격(separated)으로 정보를 제공해 두 컬럼에 정확히 대응되지 않음.
**[1] Coupled KS28 배치 거리**: L2와 완전 동일 값 — "KS28 behind: 1 m to 2 m(권장)" / "KS28 beside: 0.5 m to 1 m". 이 표는 L2/L2D 공용이라 L2D 단독 구성에도 동일하게 적용됨.
**[2] Separated KS28 간격**: L2와 동일 — "최대 인접 서브우퍼 간격 2.8 m(상한 주파수 60Hz 기준)".

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms | Polarity |
|---|---|---|---|
| [L2D] + [KS28 L2] | 0 | KS28 = 5 | L2D = + / KS28 = - |
| [L2D] + [KS28 L2_C] | 0 | KS28 = 0 | L2D = + / KS28 = - |
| [L2D] + [KS28 L2_Cx] | 0 | KS28 = 5 | L2D = + / KS28 = - |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf p.54 "Pre-alignment delays"("L2/L2D + KS28" 표, L2/L2D 공용). 극성 데이터는 색상 아이콘 표기라 Windows.Data.Pdf WinRT API로 해당 페이지를 직접 이미지 렌더링해 육안 확인(L2_v1.3.md와 동일 기법, 동일 페이지) — L2D도 항상 "+", KS28은 항상 "-"로 확인.
**Primary_Element_Delay_ms 컬럼명**: 스키마 원 명칭을 그대로 유지 — 실제로는 "1차 엘리먼트(이 경우 L2D) 자신의 딜레이"를 의미.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown [1] | L2-ROLL | 1 L2D | 1 L2D |
| stacked | L2D-CHARIOT + K2-JACK | 1 L2D | 1 L2D |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | 4:1 | - |
| Max_Wind_Load | 6 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: L2_OM_EN_5.0.pdf "Mechanical safety > Flown configurations / Other configurations"(L2/L2D 공용 챕터, "L2 or L2D or L2 + L2D" 표); Safety 섹션(Max_Wind_Load, "6 bft", L2와 공용).
**[1] 순수 L2D 단독 값만 채택**: 원문 표는 L2/L2D 혼합 배열까지 함께 표기하는 복잡한 구조("4 L2 or 3 L2 + 1 L2D" 등)이며, L2D는 설계상 항상 어레이 최하단 1개 엘리먼트로 사용되도록 되어 있어(OM "the 60° curvature of L2D is designed to make it the last enclosure at the bottom of the array") 순수 L2D만으로 구성된 다중 배열 숫자는 원문에 없음. 원문에서 애매함 없이 "L2D 단독" 값이 명시된 두 행만 채택(L2-ROLL: "1 L2 or 1 L2D", 스택 구성 "L2D-CHARIOT + K2-JACK: 1 L2D") — 나머지 혼합 배열 조합(L2-BUMP+L2-BAR, L2-BUMP+LA-RAKMOUNT+..., L2-RIGBAR 계열)은 L2와의 조합에서만 의미가 있어 생략(L2 파일의 동일 사유 각주 참조).

## Null Report

**미확인(정보 부족)**: Model_Number, WEEE_Marking, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, Frequency_Response_5dB_Hz, Max_SPL_4x_Array_Far_Field_Scaled_1m, AES75_Max_Linear_SPL, RMS_Power_Handling_Overall, Nominal_Impedance_Overall, Max_Enclosures_Per_Controller_Output, Max_Enclosures_Per_Controller_Total, Inter_Enclosure_Angles_deg, preset_guide_and_matching(Recommended_Ratio/Minimum_Line_Length 전 행, 원문이 비율/최소길이 대신 물리적 거리로 제공해 미확인) — 13건.
**비적용**: CUT_Mode_Available, HFC_Function_Settings, Coupling_Function_Range, Link_Connector — 4건. (PA_COM_Pinout_*/SpeakON_Pinout_*/Terminal_Block_Pinout_* 등 타 커넥터 고유 Key는 L2D 자신의 Connector_16Channel_Pinout으로 이미 표현되어 애초에 생성하지 않음, null 목록에서 제외.)

**총계**: null 17건 (미확인 13건 + 비적용 4건). 확정적 비존재(0/No)로 명시한 항목은 1건 — Passive_Crossover_Network(No). L2_v1.5.md와 Null Report 구성이 완전 동일(형제 제품으로서 아키텍처 특성이 동일하기 때문). delay_defaults는 OM p.54 데이터로 완전히 채워져 미확인 목록에서 제거.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리 Phase 3-1(L2의 자매품, 60° 커버리지 버전). L2_v1.3.md를 스켈레톤으로 사용, OM(L2 owner's manual EN version 5.0, L2/L2D 공용 문서) + L2D_AE_EN.docx(A&E 시방서, 신규 업로드) 통합. L2 대비 차이점(수직 지향각 60° vs 10°, 하부 2개 모듈 고정 프로그레시브 지향각, Max SPL 151/147dB vs 155/147dB, 중량 149kg vs 158kg, 치수)을 모두 OM/AE 교차 확인. 트랜스듀서/커넥터/앰프 호환성은 L2와 완전 동일. delay_defaults(OM p.54 "L2/L2D + KS28" 표, 극성은 Windows.Data.Pdf로 페이지 이미지 렌더링해 육안 확인)와 preset_guide_and_matching(OM p.51-53 "Loudspeaker configurations")도 "시간 제약상 미확보"로 방치하지 않고 원문을 직접 조사해 최초 작성 시점부터 반영(사용자 피드백 2026-07-17). |
| v1.1 | delay_defaults 표의 컬럼명 `K1_Delay_ms`를 `Primary_Element_Delay_ms`로 전면 개명(SKILL v1.18) — 관련 각주도 갱신, 값 변경 없음(사용자 지적 2026-07-17). |
| v1.2 | MF_Transducer/MF_Acoustical_Load/MF_Nominal_Impedance/RMS_Power_Handling_MF 4개 Key 삭제(SKILL v1.19) — 이 제품은 LC/LF/HF 대역 구조라 MF 대역 드라이버 자체가 없으므로, null 동기화 대상이 아니라 삭제 대상으로 재분류(K1 v1.4의 기존 반대 판단을 뒤집는 정책 변경, GSL의 Front_LF_Transducer와 동일 원칙 적용). |
