# GSL12 (d&b audiotechnik) — Master Schema

**Category**: speakers | **Brand**: d&b audiotechnik (db) | **Schema Phase**: Phase 3-2 (타 브랜드 교차 테스트, K1 대비)

**스켈레톤 근거**: `speakers/db/GSL8_v1.0.md`을 뼈대로 사용 — GSL8과 GSL12는 동일 OM(dbaudio-manual-gsl8-gsl12-1.6-en.pdf)에서 나온 폭(coverage) 베리언트로, 물리·전기적 구조가 수평 지향각과 그에 따른 Max SPL 외에는 동일하다("The GSL12 line array loudspeaker is acoustically and mechanically compatible with the GSL8", 원문). GSL8_v1.0.md의 섹션 구조와 Key 목록을 그대로 계승했다.

**GSL8/GSL12 관계**: 사용자 지침에 따라 GSL8과 GSL12는 앰프 작업 선례(LA1.16i/LA2Xi 등)를 따라 별도 두 파일로 분리했다. 두 제품은 동일 소스 문서를 공유하며, 스펙 대부분이 동일하고 수평 지향각/최대 SPL/모델번호만 상이하다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | GSL12 | - |
| Model_Number | Z0751 | - |
| Product_Category | line array loudspeaker for large-scale sound reinforcement applications | - |
| Description | 3-way line array loudspeaker; acoustically and mechanically compatible with GSL8, providing 120 deg horizontal dispersion | - |
| Way_Count | 3 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | in conformity with the provisions of the respective directives (specific directive names not enumerated in OM) | - |
| WEEE_Marking | Yes (EU), WEEE-Reg.-Nr. DE: 13421928 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM(GSL8/GSL12 Manual, Version 1.6 en, 03/2026, D2730.EN.01) Chapter 2.1 "Intended use" p.6, Chapter 3.1 "Conformity of loudspeakers" p.12, Chapter 3.2 "WEEE Declaration (Disposal)" p.12 — GSL8과 완전 동일(공용 선언, 두 모델 모두 나열).

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [1] | 41 - 20000 | Hz |
| Frequency_Response_5dB_Hz | 45 - 18000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Max_SPL_Peak [2] | 149 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m [2] | 161 | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 120 constant directivity | deg |
| Nominal_Directivity_Vertical | null | - |
| DSP_Preset_Name | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.5 "Technical specifications" p.10 (System data 표, GSL8/GSL12 공용), Chapter 2.4 "Dispersion characteristics" p.9.
**[1] Usable_Bandwidth_Hz**: 주파수 응답 표는 GSL8/GSL12 공용 수치(-10 dB standard: 41-20000 Hz)이며 두 모델 간 차이가 없음. CUT mode 조건부 대역폭은 signal_processing 섹션 참조(브랜드 고유 명칭 Key는 범용 섹션에 두지 않음 — GSL8_v1.1.md 참조).
**[2] Max_SPL 측정 조건**: GSL8과 동일 조건("1 m, free field, broadband signal IEC60268", D90/D80 구동). GSL12 값은 149 dB(단일)/161 dB(4대 어레이)로 GSL8(150/162 dB)보다 낮음 — 광각 지향(120°)에 따른 지향지수 차이로 판단되나 원문에 명시적 설명은 없어 수치만 채택.
**DSP_Preset_Name/Nominal_Directivity_Vertical**: GSL8과 동일 사유(비적용/미확인) — 상세는 GSL8_v1.1.md 참조.

## signal_processing

GSL8과 동일(공용 컨트롤러 기능, GSL8/GSL12 간 차이 없음).

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | Yes | - |
| CUT_Mode_Frequency_Response_5dB_Hz | 70 - 18000 | Hz |
| CUT_Mode_Frequency_Response_10dB_Hz | 54 - 20000 | Hz |
| HFC_Function_Settings | HFC1: 40 m additional distance compensation; HFC2: 80 m additional distance compensation (reference: 50% RH, 22 deg C) | - |
| Coupling_Function_Range | Low: +5 to -5; Mid: 0 to -8; increments of 0.5 | dB |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.3.1 "Controller settings" p.8, Chapter 2.5 p.10. GSL8과 완전 동일한 컨트롤러 기능 세트/대역폭 — 상세 설명은 GSL8_v1.1.md 참조.

## transducers

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | null | - |
| Front_LF_Transducer | 2 x 14" neodymium, forward-firing | - |
| Side_LF_Transducer | 2 x 10" neodymium, side-firing | - |
| MF_Transducer | 1 x 10" driver, high sensitivity, horn-loaded | - |
| HF_Transducer | 3 x 1.4" exit compression drivers with 3.4" coil, mounted to dedicated wave shaping device | - |
| LF_Acoustical_Load | null | - |
| MF_Acoustical_Load | horn-loaded | - |
| HF_Acoustical_Load | dedicated wave shaping device | - |
| Passive_Crossover_Network | Yes | - |
| LF_Nominal_Impedance | null | - |
| Nominal_Impedance_Overall | null | Ohm |
| MF_Nominal_Impedance | null | - |
| HF_Nominal_Impedance | null | - |
| Front_LF_Nominal_Impedance | 4 | Ohm |
| Side_LF_MF_HF_Nominal_Impedance | 4 | Ohm |
| Power_Handling_Front_LF_RMS | 800 | W |
| Power_Handling_Front_LF_Peak_10ms | 3200 | W |
| Power_Handling_Side_LF_MF_HF_RMS | 800 | W |
| Power_Handling_Side_LF_MF_HF_Peak_10ms | 3200 | W |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 "Intended use" p.6, Chapter 2.5 "Technical specifications" p.10 — Components/Loudspeaker data 표는 GSL8/GSL12 공용(트랜스듀서 구성과 임피던스/파워 핸들링에 모델 간 차이 없음). 상세 판단 근거는 GSL8_v1.1.md 참조.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x NLT4 F | - |
| Link_Connector | null | - |
| NLT4_Pinout_Pin1 | Front LF+ / Front LF- | - |
| NLT4_Pinout_Pin2 | Side LF/MF/HF+ / Side LF/MF/HF- | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.2 "Connections" p.7, Chapter 2.5 "Technical specifications" p.10 — GSL8과 동일 커넥터 구조. 상세 판단 근거는 GSL8_v1.1.md 참조.

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | D90/D80 | - |
| Max_Enclosures_Per_Controller_Output [1] | 1 | count |
| Max_Enclosures_Per_Controller_Total | null | - |
| Crossover_Type | Hybrid — active (front LF channel) + passive (side LF/MF/HF channel) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 "Intended use" p.6, Chapter 2.3 "Operation" p.7 — "GSL12 Line/Arc/AP" 행도 GSL8과 동일하게 "Cabinets per pair of amplifier channels = 1". 상세 판단 근거는 GSL8_v1.1.md 참조.
**[1] Max_Enclosures_Per_Controller_Output**: GSL8과 동일 개념·값.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | rigging strands on both sides of cabinet front and a central strand at the rear; components mounted on cabinet, fold/slide out when needed | - |
| Inter_Enclosure_Angles_deg | 0, 1, 2, 3, 4, 5, 6, 7 | deg |
| Handles | 4 (1 per side panel x2, 2 at rear) | count |
| Weight_Net | 80 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 p.6, Chapter 2.5 p.10 — GSL8과 리깅/중량 동일(원문에 모델 간 구분 없음).

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | null | mm |
| Height_mm | null | mm |
| Depth_mm | null | mm |
| Dimensions_Raw [1] | null | mm |
| Cabinet_Material | marine plywood | - |
| Front_Material | rigid metal grill backed by acoustically transparent and water repellent fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | null | - |
| Finish_Type | PCP (Polyurea Cabinet Protection), impact and weather protected | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 p.6, Chapter 2.5 p.11 "GSL8/GSL12 cabinet dimensions in mm [inch]"(GSL8/GSL12 공용 도면, 두 모델이 함께 표기됨 — 캐비닛 외형 치수 자체가 동일한 것으로 판단되나 도면이 그래픽 전용이라 GSL8과 동일하게 미확인).
**[1] Dimensions_Raw/IP_Rating/Rigging_Components_Material/Finish_Color 미확인 사유**: GSL8과 동일 — 상세는 GSL8_v1.1.md 참조.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: GSL8과 동일 — 상세는 GSL8_v1.1.md 참조.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: GSL8과 동일 — 상세는 GSL8_v1.1.md 참조.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| null | null | null | null |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | null | - |
| Max_Wind_Load | null | - |

### 주석 및 출처 (Notes & Sources)

**미확인 사유**: GSL8과 동일 — 상세는 GSL8_v1.1.md 참조.

## Null Report

**미확인(정보 부족)**: Nominal_Directivity_Vertical, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, AES75_Max_Linear_SPL, Max_Enclosures_Per_Controller_Total, LF_Acoustical_Load, RMS_Power_Handling_LF, RMS_Power_Handling_MF, RMS_Power_Handling_HF, Width_mm, Height_mm, Depth_mm, Dimensions_Raw, Rigging_Components_Material, Finish_Color, IP_Rating, mechanical_safety(Configuration/Rigging_Accessory/Safe_Limit/Maximum_Limit, Safety_Factor, Max_Wind_Load) — 20건.
**비적용(GSL 아키텍처상 개념 자체 불성립)**: DSP_Preset_Name, LF_Transducer, LF_Nominal_Impedance(GSL은 Front_LF_Nominal_Impedance/Side_LF_MF_HF_Nominal_Impedance로 이미 자체 표현, MF/HF_Nominal_Impedance와 동일 사유), MF_Nominal_Impedance, HF_Nominal_Impedance, Link_Connector, preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 8건. PA_COM_Pinout_*는 L-Acoustics 커넥터 고유 명칭이라 애초에 생성하지 않음.

**총계**: null 28건 (미확인 20건 + 비적용 8건) — 이 수치는 Kiva II/L2 투입 이전 기준. Kiva II/L2 투입으로 신설된 Key 중 Nominal_Impedance_Overall/RMS_Power_Handling_Overall/Max_SPL_Single_Module(3개)이 이 파일에 비적용 null로 추가 반영되어 실제 총계는 위 수치+3건이다. LC_Transducer/LC_Acoustical_Load/LC_Nominal_Impedance는 한때 동기화되어 있었으나 LC가 L2 라인 고유 설계 요소라는 사용자 지적(2026-07-17)에 따라 v1.5에서 삭제(SKILL v1.16). 확정적 비존재(0/No)로 명시한 항목은 0건 — Passive_Crossover_Network는 "Yes"로 실값 확보. (v1.4: GSL8_v1.4.md와 동일 사유 — LF_Nominal_Impedance 누락 추가, 총계 산술 정정.)

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리 Phase 3-2(d&b audiotechnik). GSL8_v1.0.md를 스켈레톤으로 사용, 동일 OM(GSL8/GSL12 Manual v1.6 en) 소스 기준. GSL8과 Key 목록 100% 동일, 값은 수평 지향각/Max SPL/모델번호만 상이. |
| v1.1 | GSL8_v1.1.md와 동일 사유로 Compliance_Standards, WEEE_Marking(실값), Safety_Factor, Max_Wind_Load(미확인) 반영. |
| v1.2 | GSL8_v1.2.md와 동일 — PA_COM_Pinout_* 삭제, Frequency_Response_3dB/6dB_Hz·RMS_Power_Handling_LF/MF/HF·Width/Height/Depth_mm·AES75_Max_Linear_SPL null 반영, Frequency_Response_5dB_Hz 개명. |
| v1.3 | Kiva II/L2(신규 제품) 투입으로 신설된 6개 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)를 이 제품에 비적용 null로 동기화 반영. |
| v1.5 | LC_Transducer/LC_Acoustical_Load/LC_Nominal_Impedance 삭제(사용자 피드백 2026-07-17) — LC는 L2 라인 고유의 물리적 설계 요소이지 업계 표준 대역 구분이 아니므로 v1.3의 범용 동기화 판단을 정정(SKILL v1.16). |
| v1.4 | GSL8_v1.4.md와 동일 — Null Report 전수 감사(2026-07-17)에서 표에 이미 null로 존재하던 LF_Nominal_Impedance가 미확인/비적용 목록에서 누락되어 있던 것을 발견하고 비적용에 추가, 총계 산술 오류를 정정해 28건(20+8)으로 재계산. 데이터 자체는 LF_Nominal_Impedance의 분류 정정 외 변경 없음. |
| v1.6 | delay_defaults 표의 컬럼명 `K1_Delay_ms`를 `Primary_Element_Delay_ms`로 전면 개명(SKILL v1.18) — 값 변경 없음(사용자 지적 2026-07-17). |
