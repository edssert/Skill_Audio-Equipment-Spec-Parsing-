# KSL8 (d&b audiotechnik) — Master Schema

**Category**: speakers | **Brand**: d&b audiotechnik (db) | **Schema Phase**: Phase 4 (d&b 4번째 제품군 투입, GSL8/GSL12 대비)

**스켈레톤 근거**: `speakers/db/GSL8_v1.8.md`를 뼈대로 사용 — KSL8은 GSL8과 **동일한 2채널 하이브리드 크로스오버** 구조(전방 LF 채널 능동 + 측면 LF/MF/HF 채널 내부 패시브 크로스오버)이며, 3-way·NLT4 F/M·SL-Series 소속까지 GSL과 완전히 동일한 아키텍처 축을 공유한다. 원문 자체가 "It also serves as partner to the GSL system for fill and/or delay purposes"라고 명시 — 사실상 GSL 시스템의 하위 호환 파트너 제품.

**제품 계열**: SL-Series(GSL과 동일, OM "www.sl-series.com" 링크 재확인). Model_Number는 Manual Chapter 3.1 "d&b Z0780 KSL8 loudspeaker".

**KSL8/KSL12 관계**: GSL8/GSL12 전례와 동일하게 별도 두 파일로 분리. 두 제품은 동일 소스(Manual 1.4 en)를 공유하며 수평 지향각(80°/120°)·모델번호(Z0780/Z0781)·Max_SPL만 상이.

**GSL/KSL 리깅 매뉴얼 신규 확보(중요, GSL8/GSL12 소급 갱신 트리거)**: 이번 라운드에서 `dbaudio-rigging-manual-gsl-ksl-1.16-en.pdf`(GSL/KSL Rigging manual, GSL과 KSL 공용 단일 문서)를 확보했다 — 이전 GSL8/GSL12 파싱 시점에는 이 문서가 세션에 제공되지 않아 mechanical_safety 섹션 전체가 미확인이었으나, 이번에 확보되어 GSL8/GSL12도 함께 소급 갱신 필요(이 라운드 직후 별도 버전업으로 처리 예정, TODO.md 기록). Max_Wind_Load도 이 문서에서 최초로 구체적 수치(6bft/8bft) 확보 — GSL/KSL 공통.

**아키텍처 판단(원본 근거)**: AE "The loudspeaker system shall be 3-way, actively driven between the forward LF drivers and the sideward LF driver with mid/high sections. Passive crossovers shall be used between the sideward LF driver and the mid/high sections." Manual "KSL cabinets are driven by two channels of the applicable d&b amplifier which provides dedicated processing functions for the front LF and passively crossed-over side LF and MF/HF sections." GSL8_v1.8.md와 완전히 동일한 서술 구조.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | KSL8 | - |
| Model_Number | Z0780 | - |
| Product_Series | SL-Series | - |
| Product_Category | line array loudspeaker for medium to large-scale sound reinforcement applications | - |
| Product_Type | Line array loudspeaker | - |
| Description | 3-way line array loudspeaker; up to 24 cabinets flown per column via KSL Flying frame, producing 80 deg constant directivity dispersion in the horizontal plane; serves as partner to the GSL system for fill and/or delay purposes | - |
| Way_Count | 3 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | in conformity with the provisions of the respective directives (specific directive names not enumerated in OM) | - |
| WEEE_Marking | Yes (EU), WEEE-Reg.-Nr. DE: 13421928 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS(Datasheet) v1.2 en p.1-2; AE v1.2; OM(KSL8/KSL12 Manual v1.4 en) Chapter 2.1 "Intended use" p.6, Chapter 3.1/3.2 p.12.
**Description — GSL 파트너 관계**: OM "The KSL8 is a line array loudspeaker for medium to large-scale sound reinforcement applications. It also serves as partner to the GSL system for fill and/or delay purposes." — GSL과의 시스템 결합 사용을 원문이 명시.
**Model_Number**: OM Chapter 3.1 "d&b Z0780 KSL8 loudspeaker".
**WEEE_Marking**: GSL/CCL과 동일 등록번호.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [1] | 48 - 19000 | Hz |
| Frequency_Response_5dB_Hz | 54 - 18000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Frequency_Response_4dB_Hz | null | Hz |
| Max_SPL_Peak [2] | 145 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m [2] | 157 | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg [3] | 80 constant directivity (merging into cardioid dispersion below 150 Hz) | deg |
| Nominal_Directivity_Vertical | null | - |
| Cardioid_Capability [3] | Built-in (단일 인클로저, 150Hz 이하 카디오이드 지향성 수렴 — GSL과 동일 메커니즘) | - |
| DSP_Preset_Name | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.5 "Technical specifications" p.10(KSL8/KSL12 병기 표); Chapter 2.4 "Dispersion characteristics" p.9.
**[1] Usable_Bandwidth_Hz**: -10dB 기준("48 Hz - 19 kHz") 채택 — GSL과 동일 원칙. -5dB 기준은 Frequency_Response_5dB_Hz로 병기.
**[2] Max_SPL**: OM "KSL8 with D90/D80/D40/40D: 145 dB / 4x KSL8(far field, scaled to 1m): 157 dB" — GSL과 달리 D25 계열 앰프에 대한 별도 수치는 제공되지 않음(D90/D80/D40/40D 단일 조건만).
**[3] 카디오이드 수렴 — GSL과 완전히 동일한 원문 문구**: OM "The nominal horizontal dispersion of 80°/120° is maintained above 150 Hz merging into a cardioid dispersion down to the lowest frequency." — GSL8_v1.8.md의 각주와 완전히 동일한 문장, 하이브리드 크로스오버(전방 active/측면 passive) 구조로 인한 저음역 지향성 수렴 현상도 동일 메커니즘으로 판단.

## signal_processing

KSL 컨트롤러(D90/D80/D40/40D)에서 설정 가능한 파라미터형 음향 보정 기능 — GSL과 동일한 d&b 브랜드 표준 체계.

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | Yes | - |
| HFA_Function_Settings | null | - |
| CUT_Mode_Frequency_Response_5dB_Hz | 75 - 18000 | Hz |
| CUT_Mode_Frequency_Response_10dB_Hz | 63 - 19000 | Hz |
| HFC_Function_Settings | HFC1: 40 m additional distance compensation; HFC2: 80 m additional distance compensation (reference: 50% RH, 22 deg C) | - |
| Coupling_Function_Range | Low: +5 to -5; Mid: 0 to -8; increments of 0.5 | dB |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.3.1 "Controller settings" p.8.
**CUT mode — KSL 고유 서브우퍼 파트너**: OM "The KSL8/KSL12 array is now configured for use with the actively driven d&b SL-SUB or SL-GSUB cabinets." — CCL의 CCL-SUB, GSL의 (문서 미언급) 서브우퍼와 각각 다른 파트너 서브우퍼 모델명(SL-SUB/SL-GSUB)이 명시됨.
**HFC/Coupling 수치 — GSL/CCL과 완전 동일**: HFC1=40m/HFC2=80m, Coupling Low ±5/Mid 0~-8(0.5 증분) — 3개 db 제품군(GSL/CCL/KSL) 모두 동일 수치 확인, d&b 브랜드 표준 컨트롤러 기능임이 더 강하게 뒷받침됨(다만 여전히 제품별 재확인 원칙 유지).

## transducers

GSL8_v1.8.md와 동일한 Key 구조(하이브리드 크로스오버 물리 설계 공유).

| Key | Value | Unit |
|---|---|---|
| LF_Transducer | null | - |
| Front_LF_Transducer | 2 x 10" neodymium, forward-firing | - |
| Side_LF_Transducer | 2 x 8" neodymium, side-firing | - |
| MF_Transducer | 1 x 8" driver, horn-loaded | - |
| HF_Transducer | 2 x 1.4" exit compression drivers with 3" coil, mounted to dedicated wave shaping device | - |
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
| Power_Handling_Front_LF_RMS | 450 | W |
| Power_Handling_Front_LF_Peak_10ms | 1800 | W |
| Power_Handling_Side_LF_MF_HF_RMS | 250 | W |
| Power_Handling_Side_LF_MF_HF_Peak_10ms | 1000 | W |
| RMS_Power_Handling_LF | null | W |
| RMS_Power_Handling_MF | null | W |
| RMS_Power_Handling_HF | null | W |
| RMS_Power_Handling_Overall | null | W |
| Peak_Power_Handling_10ms_Overall | null | W |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.5 "Technical specifications" p.10.
**Front_LF_Nominal_Impedance/Side_LF_MF_HF_Nominal_Impedance=8Ω(GSL과 다른 값)**: GSL은 4Ω이었으나 KSL은 8Ω — 각 제품 자신의 원문값 그대로 채택(임의 통일 금지).
**Power_Handling — 전방/측면 채널 비대칭(GSL과 다름)**: GSL은 전방/측면 두 채널 모두 800/3200W로 동일했으나, KSL은 **전방 LF 450/1800W, 측면 LF/MF/HF 250/1000W로 비대칭** — 전방 채널이 측면보다 훨씬 큰 파워 핸들링을 가짐(원문 그대로 반영, 임의로 GSL식 대칭 가정하지 않음).

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x NLT4 F/M | - |
| Link_Connector | null | - |
| NLT4_Pinout_Pin1 | Front LF+ / Front LF- | - |
| NLT4_Pinout_Pin2 | Side LF/MF/HF+ / Side LF/MF/HF- | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.2 "Connections" p.7("NLT4 F/M Connector wiring, Following the driver arrangement within the cabinet"); SPS "Pin assignment" 행.
**Link_Connector=null**: OM "The cabinets are fitted with NLT4 F/M connectors. All four pins of both connectors are wired in parallel using the following pin assignment" — GSL과 마찬가지로 별도 루프스루 커넥터 서술 없이 F/M 한 쌍이 병렬 배선(GSL과 동일 해석 적용).
**핀 배정 — GSL과 완전히 동일한 구조**: Pin1=Front LF±, Pin2=Side LF/MF/HF± — GSL8_v1.8.md의 NLT4_Pinout_Pin1/Pin2와 동일한 논리, KSL 자신의 원문에서 독립 재확인.

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller [1] | D90/D80/D40/40D | - |
| Max_Enclosures_Per_Controller_Output | 2 (Line/Arc mode); 1 (AP mode) | count |
| Max_Enclosures_Per_Controller_Total | null | - |
| Crossover_Type | Hybrid — active (front LF channel) + passive (side LF/MF/HF channel) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 p.6(NOTICE "Recommended amplifiers: D90/D80/D40/40D"), Chapter 2.3 "Operation" p.7(Cabinets per pair of amplifier channels 표).
**[1] Compatible_Amplified_Controller — GSL보다 확장된 세트**: GSL은 D90/D80 2종만 권장되었으나 KSL8은 D90/D80/D40/40D 4종(CCL8과 동일한 4종 세트) — GSL이 최상위 앰프만 요구하는 반면 KSL은 더 폭넓은 앰프 호환성을 가진 것으로 판단.
**Max_Enclosures_Per_Controller_Output**: 원문 "Cabinets per pair of amplifier channels" — GSL과 동일 단위(채널쌍 1개당 대수), 다만 KSL8은 CCL8처럼 Line=2/Arc=2/AP=1로 모드별 값이 달라 병기(GSL은 단일값 1이었음 — GSL 자신의 표를 재확인할 필요가 있으나 이번 라운드에서는 KSL 자신의 값만 확정).

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type [1] | rigging strands on both sides of cabinet front and a central strand at the rear; patented SL-Series rigging hardware enables rapid deployment from touring cart in compression or tension rigging modes; Z5722 KSL Flying frame required for array assembly | - |
| Inter_Enclosure_Angles_deg | 0 - 10 (1° increments) | deg |
| Handles | 4 (1 recessed per side panel x2, 2 at rear) | count |
| Weight_Net | 58 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 p.6("SL-Series rigging components and arrays"); SPS "Loudspeaker data"(Weight 행); GSL/KSL Rigging manual v1.16 en Chapter 1.3 "Components and weights/Load capacity" p.6.
**[1] Z5722 KSL Flying frame 하중 정격(GSL/KSL 공용 리깅 매뉴얼 신규 확보)**: "The Z5722 KSL Flying frame together with the Z5723 KSL Load beam and the Z5707 SL Aiming plate is designed to support a total system weight of 1500 kg (3307 lb) - SWL including all rigging components. This allows the suspension of a maximum of 24 x KSL-TOP cabinets or a SUB column consisting of a maximum of 16 x KSL-SUB cabinets." — 캐비닛 중량(58kg) x 24대 = 1392kg로 1500kg SWL 이내.
**Handles**: OM "Each side panel incorporates a recessed handle, with additional handles provided at the rear." — GSL의 "handle"(non-recessed 표현)과 달리 "recessed handle"로 명시된 차이가 있으나 개수 구조는 동일(4개).

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm | 1000 | mm |
| Height_mm | 330 | mm |
| Depth_mm | 597 | mm |
| Dimensions_Raw | null | mm |
| Cabinet_Material | marine plywood | - |
| Front_Material | rigid metal grill backed by acoustically transparent and water repellent fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | null | - |
| Finish_Type | PCP (Polyurea Cabinet Protection), impact and weather protected | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS/AE "The dimensions (W x H x D) shall not exceed 1000 x 330 x 597 mm" — 축이 AE에 명시적으로 라벨링되어 GSL(도면 렌더링 필요)과 달리 즉시 확정.
**Dimensions_Raw**: 축 확정으로 null.
**IP_Rating/Finish_Color/Rigging_Components_Material**: 전량 스캔 결과 없음 — 미확인(GSL과 동일 사유).

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: GSL과 동일 — CUT/HFC/Coupling 파라미터형 함수, 명명 프리셋 조합 가이드 없음.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: GSL과 동일.

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown (any splay config, up to 10 cabinets) | Z5722 KSL Flying frame + Z5723 KSL Load beam + Z5707 SL Aiming plate | null | 10 cabinets (685 kg system weight) |
| flown (general, ArrayCalc 검증 필요) | 상동 | null | 24 cabinets (1500 kg SWL total system weight incl. rigging) |
| SUB column (KSL-SUB) | 상동 | null | 16 cabinets |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | null | - |
| Max_Wind_Load [1] | 6 Beaufort(비행 비권장 상한); 8 Beaufort 초과 시 반드시 하강·고정 | Beaufort |

### 주석 및 출처 (Notes & Sources)

**출처**: GSL/KSL Rigging manual v1.16 en Chapter 1.3(Load capacity - KSL System) p.6, Chapter 1.5 "Wind loads" p.8.
**GSL/KSL 공용 리깅 매뉴얼 신규 확보(이 라운드에서 최초 확보)**: "The rigging components allow arrays of up to 10 x KSL-TOP cabinets with a total system weight of 685 kg (1510 lb) to be flown in any vertical splay angle configuration between the cabinets. For any other array configuration the load conditions within the array have to be checked using the d&b ArrayCalc simulation software." — 10대 이하는 무조건 안전, 그 이상(최대 24대)은 ArrayCalc 검증 필요.
**[1] Max_Wind_Load(GSL/KSL 공용, 이 브랜드 최초 구체적 수치 확보)**: "Flying loudspeakers overhead at wind forces higher than 6 bft (22-27 knots, 39-49 km/h, 25-31 mph) is not recommended. If the wind force exceeds 8 bft (34-40 knots, 62-74 km/h, 39-46 mph): Make sure that no person remains in the vicinity of the array. Lower and secure the array." — GSL8/GSL12에도 동일하게 적용되는 수치이므로 이 라운드 직후 GSL8/GSL12 파일도 소급 갱신 예정(TODO.md 기록).
**Safety_Factor**: 리깅 매뉴얼 Chapter 1.4 "Secondary safety" 절까지 확인했으나 "5:1" 같은 명시적 비율 수치는 없음(DGUV 규정 준수로 "inherently safe"라는 정성적 서술만 있음, secondary safety device 필요 여부만 조건부 서술) — 미확인 유지.

## Null Report

**미확인(정보 부족)**: Nominal_Directivity_Vertical, Max_SPL_Single_Module, AES75_Max_Linear_SPL, LF_Nominal_Impedance, HF_Nominal_Impedance, Max_Enclosures_Per_Controller_Total, Rigging_Components_Material, Finish_Color, IP_Rating, mechanical_safety(Safe_Limit 3건), Safety_Factor, Frequency_Response_4dB_Hz — 14건.
**비적용(KSL8 아키텍처상 개념 자체 불성립)**: DSP_Preset_Name, LF_Transducer, LF_Nominal_Impedance(Front/Side_LF_MF_HF로 이미 표현), MF_Nominal_Impedance, HF_Nominal_Impedance, Link_Connector, HFA_Function_Settings(point-source setup이 없는 구조), Peak_Power_Handling_10ms_Overall(2채널 하이브리드 구조, front/side 분리 보고), preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 10건.

**총계**: null 24건 (미확인 14건 + 비적용 10건). 확정적 비존재(0/No)로 명시한 항목은 0건 — Passive_Crossover_Network는 "Yes"로 실값 확보. **v1.1(2026-07-19)**: speakers 카테고리 전체 일괄 동기화 라운드 — 신규 Key 3종(Frequency_Response_4dB_Hz=미확인, HFA_Function_Settings=비적용, Peak_Power_Handling_10ms_Overall=비적용) 반영, 총계 21건→24건.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — d&b audiotechnik 4번째 제품군(KSL8) 최초 투입, GSL8_v1.8.md를 스켈레톤으로 사용(동일 아키텍처 — 2채널 하이브리드 크로스오버, 3-way). `upload/` 폴더 제공 Datasheet+AE+Manual(KSL8/KSL12 공용)+**GSL/KSL 공용 Rigging manual**(신규 확보, GSL 파싱 시점에는 미제공) 통합. GSL 대비 차이: Power_Handling 전방/측면 비대칭(GSL은 대칭), Nominal_Impedance 8Ω(GSL은 4Ω), 권장앰프 4종(GSL은 2종), CUT mode 서브우퍼 파트너가 SL-SUB/SL-GSUB(CCL-SUB와 다름). **Max_Wind_Load 실값 최초 확보**(6/8 Beaufort, GSL/KSL 공용 수치) — mechanical_safety Maximum_Limit도 3개 조건(685kg/10대 무조건 안전, 1500kg SWL/24대 ArrayCalc 검증 필요, SUB 컬럼 16대)으로 실값 확보. 이 신규 정보는 GSL8/GSL12에도 소급 반영 필요(TODO.md 기록, 별도 버전업 예정). Null Report 21건(미확인 13건+비적용 8건). |
| v1.1 | speakers 카테고리 전체 일괄 동기화 라운드(2026-07-19) — 신규 Key 3종 반영: `Frequency_Response_4dB_Hz`(미확인), `HFA_Function_Settings`(비적용), `Peak_Power_Handling_10ms_Overall`(비적용). Null Report 21건→24건(미확인 14+비적용 10). |
