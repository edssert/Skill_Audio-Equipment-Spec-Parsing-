# XSL8 (d&b audiotechnik) — Master Schema

**Category**: speakers | **Brand**: d&b audiotechnik (db) | **Schema Phase**: Phase 4 (d&b 6번째 제품군 투입)

**스켈레톤 근거**: `speakers/db/KSL8_v1.0.md`를 뼈대로 사용 — XSL8은 KSL8/GSL8과 **동일한 2채널 하이브리드 크로스오버** 구조(3-way, 전방 LF active + 측면 LF/MF/HF passive)를 공유하나, 캐비닛 소재는 CCL8과 동일하게 **injection molded ABS Polycarbonate**(KSL/GSL의 marine plywood와 다름) — 이 브랜드에서 "하이브리드 크로스오버 아키텍처"와 "캐비닛 소재"가 서로 독립적인 축임을 보여주는 사례(작은 XSL이 CCL과 같은 소재를 쓰면서도 KSL과 같은 크로스오버 방식을 씀).

**신규 발견 — XSL 전용 "2-in-1" 리깅 모드(이 브랜드 최초)**: `dbaudio-rigging-manual-xsl-1.5-en.pdf`(XSL 전용 Rigging manual, GSL/KSL 공용 매뉴얼과 별개) 확인 — "The XSL rigging system allows for two different rigging modes: Compression mode, Tension mode, or a combination of both, depending on the array length and the compression force required." 단일 캐비닛 후면 링크에 Compression/Tension 두 개의 전용 홀 그리드가 색상으로 구분되어 있어(inner=Compression/outer=Tension) 하나의 캐비닛으로 두 방식 모두 지원 — GSL/KSL Rigging manual에는 이런 이원 모드 구분 서술이 없었음(원본성 요건상 GSL/KSL에 이 정보를 소급하지 않음, XSL 자신의 원본에서만 확인).

**제품 계열**: SL-Series. Model_Number는 Manual Chapter 3.1 "d&b Z0770 XSL8 loudspeaker".

**XSL8/XSL12 관계**: KSL8/KSL12 전례와 동일하게 별도 두 파일로 분리.

**아키텍처 판단(원본 근거)**: AE "The loudspeaker system shall be 3-way, actively driven between the forward LF drivers and the sideward LF driver with mid/high sections. Passive crossovers shall be used between the sideward LF driver and the mid/high sections." Manual "It also serves as a supplement to other SL-Series systems for fill and/or delay purposes." — KSL과 동일하게 상위 시스템(GSL/KSL)의 필/딜레이 파트너 역할.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | XSL8 | - |
| Model_Number | Z0770 | - |
| Product_Series | SL-Series | - |
| Product_Category | line array loudspeaker for small to medium-scale sound reinforcement applications | - |
| Product_Type | Line array loudspeaker | - |
| Description | 3-way line array loudspeaker; up to 24 cabinets flown per column via XSL Flying frame (compression and/or tension mode), or up to 12 cabinets via XSL Top mounting frame (tension mode only), producing 80 deg constant directivity dispersion in the horizontal plane; supplements other SL-Series systems for fill and/or delay purposes | - |
| Way_Count | 3 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | in conformity with the provisions of the respective directives (specific directive names not enumerated in OM) | - |
| WEEE_Marking | Yes (EU), WEEE-Reg.-Nr. DE: 13421928 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS(Datasheet) v1.3 en p.1-2; AE v1.2; OM(XSL8/XSL12 Manual v1.4 en) Chapter "Intended use" p.6, "Manufacturer's declarations" p.12.
**Description — XSL Top mounting frame(신규 발견, KSL8에 없던 개념)**: OM "When the XSL Flying frame is used, up to 24 XSL8 cabinets can be flown in vertical columns in either compression and/or tension mode rigging... When the XSL Top mounting frame is used, up to 12 XSL8 cabinets can be flown in tension mode rigging." — KSL8에는 이런 2종 프레임 구분(Flying frame vs Top mounting frame)이 없었음, XSL 고유의 리깅 옵션 다양성.
**Model_Number**: OM "d&b Z0770 XSL8 loudspeaker".
**WEEE_Marking**: 브랜드 공통 등록번호.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [1] | 55 - 20000 | Hz |
| Frequency_Response_5dB_Hz | 60 - 18000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Max_SPL_Peak [2] | 141 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m [2] | 153 | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 80 | deg |
| Nominal_Directivity_Vertical | null | - |
| Cardioid_Capability [3] | Built-in (단일 인클로저, 카디오이드 기법을 저음역에서 사용 — 구체적 수렴 대역 조건은 XSL 원문에 명시 없음, GSL/KSL과 다른 근거 수준) | - |
| DSP_Preset_Name | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter "Technical specifications" p.10(XSL8/XSL12 병기 표).
**[1] Usable_Bandwidth_Hz**: -10dB 기준("55 Hz - 20 kHz") 채택.
**[2] Max_SPL**: OM "XSL8 with D90/D80/D40/40D: 141 dB / 4x XSL8: 153 dB".
**[3] Cardioid_Capability — GSL/KSL과 다른 근거 수준**: Manual "Constant directivity behavior over the entire operating range using cardioid techniques in the lower range"(Features and benefits) — GSL/KSL의 "merging into a cardioid dispersion down to the lowest frequency, above 150 Hz maintained"라는 구체적 대역 조건부 서술과 달리, XSL8은 3개 문서(SPS/AE/OM) 전량 스캔 결과 정성적 서술("cardioid techniques in the lower range")만 있고 150Hz 같은 구체적 전환점 수치가 없음 — CCL8과 유사한 근거 수준.

## signal_processing

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | Yes | - |
| CUT_Mode_Frequency_Response_5dB_Hz | 90 - 18000 | Hz |
| CUT_Mode_Frequency_Response_10dB_Hz | 68 - 20000 | Hz |
| HFC_Function_Settings | HFC1: 40 m additional distance compensation; HFC2: 80 m additional distance compensation (reference: 50% RH, 22 deg C) | - |
| Coupling_Function_Range | Low: +5 to -5; Mid: 0 to -8; increments of 0.5 | dB |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter "Controller settings" p.8.
**CUT mode**: 서브우퍼 파트너 모델명 특정 서술은 XSL8 원문에 없음(GSL/KSL의 SL-SUB/SL-GSUB, KSLi의 KSLi-SUB 같은 명시적 언급이 XSL8 3개 문서 전량 스캔 결과 없음) — 단순히 "the low frequency level of the cabinets is reduced" 정성적 서술만.
**HFC/Coupling 수치 — 4개 db 제품군 모두 완전 동일**: GSL/CCL/KSL/XSL 전부 HFC1=40m/HFC2=80m, Coupling Low ±5/Mid 0~-8(0.5 증분) — 4번째 확인으로 d&b 브랜드 표준 컨트롤러 기능임이 더욱 강하게 뒷받침됨.

## transducers

KSL8과 유사한 Key 구조이나 드라이버 구경 축소.

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | null | - |
| Front_LF_Transducer | 2 x 8" neodymium, forward-firing | - |
| Side_LF_Transducer | 2 x 6.5" neodymium, side-firing | - |
| MF_Transducer | 1 x 6.5" driver, horn-loaded | - |
| HF_Transducer | 2 x 1" exit compression drivers with 2" coil, mounted to dedicated wave shaping device | - |
| LF_Acoustical_Load | null | - |
| MF_Acoustical_Load | horn-loaded | - |
| HF_Acoustical_Load | dedicated wave shaping device | - |
| Passive_Crossover_Network | Yes | - |
| LF_Nominal_Impedance | null | - |
| Nominal_Impedance_Overall | null | Ohm |
| MF_Nominal_Impedance | null | - |
| HF_Nominal_Impedance | null | - |
| Front_LF_Nominal_Impedance | 8 | Ohm |
| Side_LF_MF_HF_Nominal_Impedance | 8 | Ohm |
| Power_Handling_Front_LF_RMS | 400 | W |
| Power_Handling_Front_LF_Peak_10ms | 1200 | W |
| Power_Handling_Side_LF_MF_HF_RMS | 300 | W |
| Power_Handling_Side_LF_MF_HF_Peak_10ms | 850 | W |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter "Technical specifications" p.10.
**Power_Handling — KSL8보다 완화된 비대칭**: KSL8(450/1800 vs 250/1000)보다 격차가 작음(400/1200 vs 300/850) — 소형 모델일수록 전방/측면 채널 파워 격차가 줄어드는 경향 관찰(단, 이 관찰을 일반화하지 않고 각 제품 자신의 원문값만 채택).
**Front/Side_LF_MF_HF_Nominal_Impedance=8Ω**: KSL8과 동일 수치.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x NLT4 F/M | - |
| Link_Connector | null | - |
| NLT4_Pinout_Pin1 | Front LF+ / Front LF- | - |
| NLT4_Pinout_Pin2 | Side LF/MF/HF+ / Side LF/MF/HF- | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter "Connections" p.7("NLT4 F/M Connector wiring"); SPS "Pin assignment" 행.
**Link_Connector=null**: KSL8과 동일 원칙 — F/M 병렬 배선 구조.

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | D90/D80/D40/40D | - |
| Max_Enclosures_Per_Controller_Output | 2 (Line/Arc mode); 1 (AP mode) | count |
| Max_Enclosures_Per_Controller_Total | null | - |
| Crossover_Type | Hybrid — active (front LF channel) + passive (side LF/MF/HF channel) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter "Intended use" p.6(NOTICE "Recommended amplifiers: D90/D80/D40/40D") — KSL8과 완전 동일.
**나머지 근거**: KSL8_v1.0.md와 동일.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type [1] | three point rigging system (front rigging strands + splay/rear link mechanism with dual hole grid for Compression/Tension mode); Z5771 XSL Flying frame (24 cabinets, compression and/or tension) or Z5772-equipped XSL Top mounting frame (12 cabinets, tension only) | - |
| Inter_Enclosure_Angles_deg | 0 - 14 (1° increments) | deg |
| Handles | 4 (1 per side panel x2, 2 at rear) | count |
| Weight_Net | 39 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter "Intended use" p.6; SPS "Loudspeaker data"(Weight 행); XSL Rigging manual v1.5 en Chapter 1.3 "Components and weights/Load capacity" p.5.
**[1] XSL 전용 "2-in-1" 리깅 모드(신규 발견, 파일 서두 참조)**: 이 브랜드에서 처음 확인된 단일 캐비닛의 Compression/Tension 이원 지원 구조 — GSL/KSL/CCL 모두 이런 명시적 이원 모드 구분이 원문에 없었음.
**Z5771 XSL Flying frame 하중 정격**: XSL Rigging manual "The Z5771 XSL Flying frame with the Z5772 XSL Load beam and the Z5707 SL Aiming plate is designed to support a total system weight of 1000 kg (2200 lb) - SWL including all rigging components." 캐비닛 중량(39kg) x 24대 = 936kg로 1000kg SWL 이내.
**Handles**: Manual "Each side panel incorporates a handle while two additional handles are provided at the rear" — CCL8과 동일 표현(recessed 아님, KSL8의 "recessed handle"과 다름).

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 700 | mm |
| Height_mm | 283 | mm |
| Depth_mm | 507 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material [1] | injection molded ABS Polycarbonate | - |
| Front_Material | rigid metal grill backed by acoustically transparent and water repellent fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | null | - |
| Finish_Type | 2K finish, impact and weather protected | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS/AE "The dimensions (W x H x D) shall not exceed 700 x 283 x 507 mm."
**[1] Cabinet_Material — CCL8과 동일 소재(KSL8과 다름)**: AE "The enclosure shall be injection molded (ABS polycarbonate) with an impact resistant and weather protecting 2K finish." — KSL8/GSL8의 marine plywood와 달리 CCL8과 동일한 사출성형 ABS 소재(파일 서두 아키텍처 판단 참조).
**IP_Rating/Finish_Color/Rigging_Components_Material**: 전량 스캔 결과 없음 — 미확인.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: GSL/KSL과 동일.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: GSL/KSL과 동일.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown, compression and/or tension mode | Z5771 XSL Flying frame + Z5772 XSL Load beam + Z5707 SL Aiming plate | null | 24 cabinets (1000 kg SWL total system weight incl. rigging) |
| flown, tension mode only | XSL Top mounting frame | null | 12 cabinets |
| SUB column (XSL-SUB, mixed) | Z5783 XSL-SUB Adapter frame | null | 1000 kg SWL total system weight incl. rigging (혼합 배열, XSL-TOP 아래 XSL-SUB) |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | null | - |
| Max_Wind_Load [1] | 6 Beaufort(비행 비권장 상한); 8 Beaufort 초과 시 반드시 하강·고정 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: XSL Rigging manual v1.5 en Chapter 1.3 "Load capacity" p.5, Chapter 1.3.1 "Wind loads" p.5.
**[1] Max_Wind_Load — GSL/KSL과 동일 수치**: "Flying loudspeakers overhead at wind forces higher than 6 bft... is not recommended. If the wind force exceeds 8 bft...: Make sure that no person remains in the vicinity of the array. Lower and secure the array." — GSL/KSL Rigging manual과 완전히 동일한 문구, d&b 투어링 SL-Series 전체(GSL/KSL/XSL, CCL은 미확인)의 공통 안전 기준으로 판단.
**Safety_Factor**: 리깅 매뉴얼 전량 스캔 결과 명시적 비율 수치 없음 — 미확인(GSL/KSL과 동일 사유).

## Null Report

**미확인(정보 부족)**: Nominal_Directivity_Vertical, Max_SPL_Single_Module, AES75_Max_Linear_SPL, LF_Nominal_Impedance, HF_Nominal_Impedance, Max_Enclosures_Per_Controller_Total, Rigging_Components_Material, Finish_Color, IP_Rating, mechanical_safety(Safe_Limit 3건), Safety_Factor — 13건.
**비적용(XSL8 아키텍처상 개념 자체 불성립)**: DSP_Preset_Name, LF_Transducer, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance, Link_Connector, preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 8건.

**총계**: null 21건 (미확인 13건 + 비적용 8건). 확정적 비존재(0/No)로 명시한 항목은 0건 — Passive_Crossover_Network는 "Yes"로 실값 확보.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — d&b audiotechnik 6번째 제품군(XSL8) 최초 투입, KSL8_v1.0.md를 스켈레톤으로 사용(동일 2채널 하이브리드 크로스오버 아키텍처, CCL8과 동일한 injection molded ABS 소재 — 크로스오버 방식과 캐비닛 소재가 서로 독립적인 축임을 확인). `upload/` 폴더 제공 Datasheet+AE+Manual(XSL8/XSL12 공용)+**XSL 전용 Rigging manual**(GSL/KSL 공용 매뉴얼과 별개 문서) 통합. 신규 발견: 이 브랜드 최초의 "2-in-1" Compression/Tension 이원 리깅 모드(단일 캐비닛 후면 링크에 색상 구분 이중 홀 그리드), XSL Top mounting frame(12대, tension 전용)이라는 Flying frame과 별개의 2번째 리깅 옵션(KSL8에 없던 개념). Max_Wind_Load는 GSL/KSL과 완전히 동일한 6/8 Beaufort 수치 확인. HFC/Coupling 수치가 4개 제품군(GSL/CCL/KSL/XSL) 전부 동일해 브랜드 표준 기능임이 더 강하게 뒷받침됨. Cardioid_Capability는 GSL/KSL의 구체적 150Hz 조건부 서술과 달리 CCL8과 유사한 정성적 서술만 확인. Null Report 21건(미확인 13건+비적용 8건). |
