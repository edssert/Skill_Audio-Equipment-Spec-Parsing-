# XSL12 (d&b audiotechnik) — Master Schema

**Category**: speakers | **Brand**: d&b audiotechnik (db) | **Schema Phase**: Phase 4 (d&b 6번째 제품군 투입, XSL8과 동시)

**스켈레톤 근거**: `speakers/db/XSL8_v1.0.md`(형제 파일)와 동일 원본(자체 Datasheet+AE 개별, Manual/XSL Rigging manual 공유)에서 독립 확인 — **베리언트 간 차이는 수평 지향각(80° vs 120°)에 종속되는 값뿐**: Nominal_Directivity_Horizontal_deg, Max_SPL_Peak, Max_SPL_4x_Array_Far_Field_Scaled_1m.

**제품 계열**: SL-Series. Model_Number는 Manual Chapter 3.1 "d&b Z0772 XSL12 loudspeaker".

**아키텍처 판단(원본 근거)**: XSL8_v1.0.md와 동일.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | XSL12 | - |
| Model_Number | Z0772 | - |
| Product_Series | SL-Series | - |
| Product_Category | line array loudspeaker for small to medium-scale sound reinforcement applications | - |
| Product_Type | Line array loudspeaker | - |
| Description | 3-way line array loudspeaker; up to 24 cabinets flown per column via XSL Flying frame (compression and/or tension mode), or up to 12 cabinets via XSL Top mounting frame (tension mode only), producing 120 deg constant directivity dispersion in the horizontal plane; supplements other SL-Series systems for fill and/or delay purposes | - |
| Way_Count | 3 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | in conformity with the provisions of the respective directives (specific directive names not enumerated in OM) | - |
| WEEE_Marking | Yes (EU), WEEE-Reg.-Nr. DE: 13421928 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS(Datasheet) v1.3 en; AE v1.2; OM(XSL8/XSL12 Manual v1.4 en) "Manufacturer's declarations" p.12.
**Model_Number**: OM "d&b Z0772 XSL12 loudspeaker".
**나머지 근거**: XSL8_v1.0.md와 동일.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz | 55 - 20000 | Hz |
| Frequency_Response_5dB_Hz | 60 - 18000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Max_SPL_Peak [1] | 140 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m [1] | 152 | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 120 | deg |
| Nominal_Directivity_Vertical | null | - |
| Cardioid_Capability | Built-in (XSL8과 동일 근거) | - |
| DSP_Preset_Name | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter "Technical specifications" p.10(XSL8/XSL12 병기 표).
**[1] Max_SPL — XSL8과 다른 값(120° 확산)**: OM "XSL12 with D90/D80/D40/40D: 140 dB / 4x XSL12: 152 dB" — XSL8(141/153dB)보다 각 1dB 낮음.
**나머지 근거**: XSL8_v1.0.md와 동일.

## signal_processing

XSL8_v1.0.md와 완전 동일.

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | Yes | - |
| CUT_Mode_Frequency_Response_5dB_Hz | 90 - 18000 | Hz |
| CUT_Mode_Frequency_Response_10dB_Hz | 68 - 20000 | Hz |
| HFC_Function_Settings | HFC1: 40 m additional distance compensation; HFC2: 80 m additional distance compensation (reference: 50% RH, 22 deg C) | - |
| Coupling_Function_Range | Low: +5 to -5; Mid: 0 to -8; increments of 0.5 | dB |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: XSL8_v1.0.md와 동일(두 베리언트 공통).

## transducers

XSL8_v1.0.md와 완전 동일.

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

**출처 및 근거**: XSL8_v1.0.md와 동일.

## connectivity

XSL8_v1.0.md와 완전 동일.

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x NLT4 F/M | - |
| Link_Connector | null | - |
| NLT4_Pinout_Pin1 | Front LF+ / Front LF- | - |
| NLT4_Pinout_Pin2 | Side LF/MF/HF+ / Side LF/MF/HF- | - |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: XSL8_v1.0.md와 동일.

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | D90/D80/D40/40D | - |
| Max_Enclosures_Per_Controller_Output | 2 (Line/Arc mode); 1 (AP mode) | count |
| Max_Enclosures_Per_Controller_Total | null | - |
| Crossover_Type | Hybrid — active (front LF channel) + passive (side LF/MF/HF channel) | - |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: XSL8_v1.0.md와 동일.

## rigging_handling

XSL8_v1.0.md와 완전 동일(캐비닛 외형/중량 공통).

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | three point rigging system (front rigging strands + splay/rear link mechanism with dual hole grid for Compression/Tension mode); Z5771 XSL Flying frame (24 cabinets, compression and/or tension) or Z5772-equipped XSL Top mounting frame (12 cabinets, tension only) | - |
| Inter_Enclosure_Angles_deg | 0 - 14 (1° increments) | deg |
| Handles | 4 (1 per side panel x2, 2 at rear) | count |
| Weight_Net | 39 | kg |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: XSL8_v1.0.md와 동일 — XSL Rigging manual "Z0770/Z0772 XSL8/XSL12 cabinets ... 39 kg (86 lb)"로 두 모델 공용 중량 명시.

## physical

XSL8_v1.0.md와 완전 동일(캐비닛 치수 공통).

| Key | Value | Unit |
|---|---|---|
| Width_mm | 700 | mm |
| Height_mm | 283 | mm |
| Depth_mm | 507 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | injection molded ABS Polycarbonate | - |
| Front_Material | rigid metal grill backed by acoustically transparent and water repellent fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | null | - |
| Finish_Type | 2K finish, impact and weather protected | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS/AE "The dimensions (W x H x D) shall not exceed 700 x 283 x 507 mm."
**나머지 근거**: XSL8_v1.0.md와 동일.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: XSL8과 동일.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: XSL8과 동일.

## mechanical_safety

XSL8_v1.0.md와 완전 동일(리깅 액세서리 두 모델 공용).

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown, compression and/or tension mode | Z5771 XSL Flying frame + Z5772 XSL Load beam + Z5707 SL Aiming plate | null | 24 cabinets (1000 kg SWL total system weight incl. rigging) |
| flown, tension mode only | XSL Top mounting frame | null | 12 cabinets |
| SUB column (XSL-SUB, mixed) | Z5783 XSL-SUB Adapter frame | null | 1000 kg SWL total system weight incl. rigging (혼합 배열, XSL-TOP 아래 XSL-SUB) |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | null | - |
| Max_Wind_Load | 6 Beaufort(비행 비권장 상한); 8 Beaufort 초과 시 반드시 하강·고정 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처 및 근거**: XSL8_v1.0.md와 동일(XSL Rigging manual, 두 모델 공용 하중 정격).

## Null Report

**미확인(정보 부족)**: Nominal_Directivity_Vertical, Max_SPL_Single_Module, AES75_Max_Linear_SPL, LF_Nominal_Impedance, HF_Nominal_Impedance, Max_Enclosures_Per_Controller_Total, Rigging_Components_Material, Finish_Color, IP_Rating, mechanical_safety(Safe_Limit 3건), Safety_Factor — 13건.
**비적용(XSL12 아키텍처상 개념 자체 불성립)**: DSP_Preset_Name, LF_Transducer, LF_Nominal_Impedance, MF_Nominal_Impedance, HF_Nominal_Impedance, Link_Connector, preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 8건.

**총계**: null 21건 (미확인 13건 + 비적용 8건). 확정적 비존재(0/No)로 명시한 항목은 0건. XSL8과 총계까지 일치.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — XSL8과 동시 투입, XSL8_v1.0.md를 스켈레톤으로 사용(형제 파일). 베리언트 종속 3개 Key(Nominal_Directivity_Horizontal_deg=120°, Max_SPL_Peak=140dB, Max_SPL_4x_Array_Far_Field_Scaled_1m=152dB)만 XSL12 자신의 원문값으로 대입, 나머지 전 섹션은 XSL8과 완전 동일. Null Report 21건(미확인 13건+비적용 8건), XSL8과 총계까지 일치. |
