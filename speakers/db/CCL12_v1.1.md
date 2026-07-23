# CCL12 (d&b audiotechnik) — Master Schema

**Category**: speakers | **Brand**: d&b audiotechnik (db) | **Schema Phase**: Phase 4 (d&b 2번째 제품군 투입, CCL8과 동시)

**스켈레톤 근거**: `speakers/db/CCL8_v1.0.md`(형제 파일)와 동일 원본(Datasheet/AE/Manual/Rigging manual 모두 공유)에서 독립 확인 — 아키텍처는 완전히 동일(단일 채널 완전 패시브 2-way), **베리언트 간 차이는 수평 지향각(80° vs 120°)에 종속되는 소수 값뿐**: Nominal_Directivity_Horizontal_deg, Max_SPL_Peak, Max_SPL_4x_Array_Far_Field_Scaled_1m. 나머지 전 섹션은 CCL8과 완전히 동일값이다(원본 자체가 이 항목들 외에는 베리언트를 구분하지 않음).

**제품 계열**: CL-Series(CCL8과 동일). Model_Number는 Manual Chapter 3.1 "d&b Z0882 CCL12 loudspeaker"로 확인.

**아키텍처 판단(원본 근거)**: CCL8_v1.0.md와 동일 — 단일 앰프 채널로 구동되는 완전 패시브 2-way 구조(전방 7" LF x2 + 측면 5" LF x2 + 동축 HF x2, 내부 완전 패시브 크로스오버).

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | CCL12 | - |
| Model_Number | Z0882 | - |
| Product_Series | CL-Series | - |
| Product_Category | compact cardioid line array loudspeaker for small to medium-scale sound reinforcement | - |
| Product_Type | Line array loudspeaker | - |
| Description | 2-way line array loudspeaker; up to 24 cabinets flown per column via CCL Flying frame, producing 120 deg constant directivity dispersion in the horizontal plane; requires only one amplifier channel | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | in conformity with the provisions of the respective directives (specific directive names not enumerated in OM) | - |
| WEEE_Marking | Yes (EU), WEEE-Reg.-Nr. DE: 13421928 | - |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: CCL8_v1.0.md와 동일(공유 문서, CCL12 자신의 Model_Number/Description만 원문에서 독립 확인).
**Model_Number**: Manual Chapter 3.1 "This declaration applies to: d&b Z0882 CCL12 loudspeaker".

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 55 - 20000 (dB 기준 미표기) | Hz |
| Frequency_Response_5dB_Hz | 60 - 18000 | Hz |
| Frequency_Response_4dB_Hz | null | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Max_SPL_Peak [1] | 136 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m [1] | 148 | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 120 | deg |
| Nominal_Directivity_Vertical | null | - |
| Cardioid_Capability | Built-in (CCL8과 동일 근거, "compact cardioid line array loudspeaker" 자기 서술) | - |
| DSP_Preset_Name | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Manual Chapter 2.5 "Technical specifications" p.9(CCL8/CCL12 병기 표).
**[1] Max_SPL — CCL8과 다른 값(120° 확산으로 인한 저하)**: Manual "CCL12 with D25/D20/25D/30D: 134 dB / CCL12 with D90/D80/D40/40D: 136 dB / 4x CCL12(far field, scaled to 1m) with D90/D80/D40/40D: 148 dB" — CCL8(137/149dB)보다 각 1dB 낮음(더 넓은 수평 확산에 따른 축상 SPL 감소). Value에는 D90/D80/D40/40D 조건 채택, D25 계열(134dB)은 각주 보존(CCL8과 동일 처리 원칙).
**나머지 근거**: CCL8_v1.0.md와 동일.
**Frequency_Response_4dB_Hz(신규 Key)**: Meyer Sound 배치(750-LFC 등)에서 신설된 범용 Key(-4dB 기준 대역폭) — 이 제품 자신의 원본에서 아직 재확인되지 않아 미확인 유지.

## transducers

CCL8_v1.0.md와 완전 동일.

| Key | Value | Unit |
|---|---|---|
| Front_LF_Transducer | 2 x 7" neodymium, forward-firing | - |
| Side_LF_Transducer | 2 x 5" neodymium, side-firing | - |
| HF_Transducer | 2 x 10.2 x 63 mm exit compression drivers with 1.75" coil, coupled to dedicated wave shaping device | - |
| LF_Acoustical_Load | vented enclosure (front LF driver only) | - |
| HF_Acoustical_Load | dedicated wave shaping device | - |
| Passive_Crossover_Network | Yes | - |
| Nominal_Impedance_Overall | 10 | Ohm |
| LF_Nominal_Impedance | null | - |
| HF_Nominal_Impedance | null | - |
| RMS_Power_Handling_Overall | 400 | W |
| Peak_Power_Handling_10ms_Overall | 1200 | W |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: CCL8_v1.0.md와 동일(드라이버 구성/파워 핸들링 두 베리언트 공통).

## connectivity

CCL8_v1.0.md와 완전 동일.

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x NLT4 male | - |
| Link_Connector | 1 x NLT4 female | - |
| NLT4_Pinout_Pin1 | Full-range signal (front LF + side LF + HF, combined via internal passive crossover) | - |
| NLT4_Pinout_Pin2 | Not used by CCL12 itself — designated pass-through for downstream subwoofer (e.g., CCL-SUB) | - |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: CCL8_v1.0.md와 동일.

## signal_processing

CCL8_v1.0.md와 완전 동일.

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | Yes | - |
| CUT_Mode_Frequency_Response_5dB_Hz | 90 - 18000 | Hz |
| CUT_Mode_Frequency_Response_10dB_Hz | 80 - 20000 | Hz |
| HFC_Function_Settings | HFC1: 40 m additional distance compensation; HFC2: 80 m additional distance compensation (reference: 50% RH, 22 deg C) | - |
| Coupling_Function_Range | Low: +5 to -5; Mid: 0 to -8; increments of 0.5 | dB |
| HFA_Function_Settings | null | - |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: CCL8_v1.0.md와 동일(두 베리언트 공통).
**HFA_Function_Settings(신규 Key, 비적용)**: T10/Ti10L/Ti10P에서 신설된 db 고유 기능 Key(PS/point-source setup 전용 HF 감쇠) — 이 제품은 point-source setup이 없는 구조라 비적용.

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | D25/D40/D90/D80 | - |
| Max_Enclosures_Per_Controller_Output | 2 (Line/Arc mode); 1 (AP mode) | count |
| Max_Enclosures_Per_Controller_Total | null | - |
| Crossover_Type | Passive (2-way, single amplifier channel, front LF+side LF+HF combined via internal passive crossover network) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Manual Chapter 2.3 "Operation" p.6(Cabinets per channel 표 — CCL12 Line=2/Arc=2/AP=1, CCL8과 동일 구조).
**나머지 근거**: CCL8_v1.0.md와 동일.

## rigging_handling

CCL8_v1.0.md와 완전 동일(캐비닛 외형/중량 공통).

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | three point rigging system (strands on both sides of cabinet front + central strand at rear, fold/slide out when needed); Z5820 CCL Flying frame required for array assembly | - |
| Inter_Enclosure_Angles_deg | 0 - 14 (1° increments) | deg |
| Handles | 4 (1 per side panel x2, 2 at rear) | count |
| Weight_Net | 17.6 | kg |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: CCL8_v1.0.md와 동일 — CCL Rigging manual "Z0880/Z0882 CCL8/CCL12 cabinets ... 17.6 kg (38.8 lb)"로 두 모델 공용 중량 명시 확인.

## physical

CCL8_v1.0.md와 완전 동일(캐비닛 치수 공통).

| Key | Value | Unit |
|---|---|---|
| Width_mm | 593 | mm |
| Height_mm | 209 | mm |
| Depth_mm | 355 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | injection molded ABS Polycarbonate | - |
| Front_Material | rigid, perforated steel grill backed with acoustically transparent and water repellent fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | null | - |
| Finish_Type | 2K finish, impact resistant and weather protecting | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: Manual p.10 "CCL8/CCL12 cabinet dimensions in mm [inch]" — 도면 제목이 두 모델 공용임을 명시.
**나머지 근거**: CCL8_v1.0.md와 동일(IP_Rating 물 유입 경고 각주 포함).

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: CCL8과 동일.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: CCL8과 동일.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown | Z5820 CCL Flying frame | null | 24 cabinets (500 kg SWL total system weight incl. rigging components) |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | null | - |
| Max_Wind_Load | null | - |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: CCL8_v1.0.md와 동일(리깅 액세서리·SWL 두 모델 공용, AE "up to 24 cabinets" 동일 문구).

## Null Report

**미확인(정보 부족)**: Nominal_Directivity_Vertical, Max_SPL_Single_Module, AES75_Max_Linear_SPL, LF_Nominal_Impedance, HF_Nominal_Impedance, Max_Enclosures_Per_Controller_Total, Rigging_Components_Material, Finish_Color, IP_Rating, Frequency_Response_4dB_Hz, mechanical_safety(Safe_Limit 1건, Safety_Factor, Max_Wind_Load) — 13건.
**비적용(CCL12 아키텍처상 개념 자체 불성립)**: DSP_Preset_Name, HFA_Function_Settings, preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 4건. MF 관련 Key 및 GSL 고유 Front/Side_LF_MF_HF Key는 애초에 생성하지 않음(CCL8과 동일 원칙).

**총계**: null 17건 (미확인 13건 + 비적용 4건). 확정적 비존재(0/No)로 명시한 항목은 0건. CCL8과 총계까지 완전 일치.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — CCL8과 동시 투입, CCL8_v1.0.md를 스켈레톤으로 사용(형제 파일, 동일 원본에서 독립 확인). 베리언트 종속 3개 Key(Nominal_Directivity_Horizontal_deg=120°, Max_SPL_Peak=136dB, Max_SPL_4x_Array_Far_Field_Scaled_1m=148dB)만 CCL12 자신의 원문값으로 대입, 나머지 전 섹션은 CCL8과 완전 동일(원본 자체가 이 항목들 외에는 베리언트를 구분하지 않음). Null Report 15건(미확인 12건+비적용 3건), CCL8과 총계까지 일치. |
| v1.1 | speakers 카테고리 전체 일괄 동기화 라운드(2026-07-18, d&b 대량 배치 완료 후) — 신규 Key `Frequency_Response_4dB_Hz`(Meyer Sound 배치 유래, 미확인), `HFA_Function_Settings`(T10 유래, 비적용) 반영. Null Report 17건(미확인 13건+비적용 4건)으로 갱신. |
