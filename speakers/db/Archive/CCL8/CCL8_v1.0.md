# CCL8 (d&b audiotechnik) — Master Schema

**Category**: speakers | **Brand**: d&b audiotechnik (db) | **Schema Phase**: Phase 4 (d&b 2번째 제품군 투입, GSL8/GSL12 대비)

**스켈레톤 근거**: `speakers/db/GSL8_v1.8.md`를 뼈대로 사용(동일 브랜드, 외부 앰프 구동 패시브 토폴로지, 전방+측면 LF 드라이버 분리 배치라는 물리 설계가 유사) — 다만 아키텍처가 근본적으로 다르다: GSL은 **2채널 하이브리드**(전방 LF만 능동 채널, 측면 LF+MF+HF는 내부 패시브 크로스오버로 묶인 별도 채널) 3-way 구조인 반면, CCL8은 **단일 앰프 채널로 구동되는 완전 패시브** 2-way 구조다(원문 "Requires only one amplifier channel", NLT4 커넥터 핀 배정도 1+/1- 단일 세트만 사용). MF 대역 자체가 없어(전방 LF+측면 LF+동축 HF만 존재) GSL의 MF_Transducer류 Key는 이 제품에 생성하지 않는다(SKILL v1.19, 웨이 구조상 존재하지 않는 대역).

**제품 계열**: 이 제품은 "CL-Series"(원문 OM "CL-Series rigging components and arrays") 소속으로 확인 — GSL의 "SL-Series"와는 다른 시리즈명. Model_Number는 OM Chapter 3.1 "Conformity of loudspeakers"에서 "d&b Z0880 CCL8 loudspeaker"로 확인.

**CCL8/CCL12 관계**: GSL8/GSL12 전례와 동일하게 별도 두 파일로 분리한다. 두 제품은 동일 소스 문서(Manual 1.5 en, dbaudio-manual-ccl8-ccl12-1.5-en.pdf)를 공유하며, 스펙 대부분이 동일하고 수평 지향각(80°/120°)·모델번호(Z0880/Z0882)·Max_SPL 수치만 상이하다.

**아키텍처 판단(원본 근거)**: AE "The loudspeaker system shall be a bipolar 2-way design with passive crossover network consisting of two forward 7" LF neodymium drivers in a vented enclosure radiating to the front, two sideward 5" LF neodymium drivers and two coaxially mounted 10.2 x 63 mm exit HF compression drivers with 1.75" voicecoils, coupled to a waveshaping device." Manual "Features and benefits" — "Requires only one amplifier channel." GSL과 달리 "actively driven between X and Y" 같은 능동/패시브 분리 서술이 전혀 없어, 전방 LF+측면 LF+HF 전체가 하나의 채널에서 완전 패시브 크로스오버로 분리되는 구조로 판단.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | CCL8 | - |
| Model_Number | Z0880 | - |
| Product_Series | CL-Series | - |
| Product_Category | compact cardioid line array loudspeaker for small to medium-scale sound reinforcement | - |
| Product_Type | Line array loudspeaker | - |
| Description | 2-way line array loudspeaker; up to 24 cabinets flown per column via CCL Flying frame, producing 80 deg constant directivity dispersion in the horizontal plane; requires only one amplifier channel | - |
| Way_Count | 2 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | in conformity with the provisions of the respective directives (specific directive names not enumerated in OM) | - |
| WEEE_Marking | Yes (EU), WEEE-Reg.-Nr. DE: 13421928 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS(Datasheet) v1.5 en p.1-2; AE(Architectural specifications, Datasheet 내 포함) v1.3; OM(CCL8/CCL12 Manual v1.5 en) Chapter 2.1 "Intended use" p.5, Chapter 3.1/3.2 p.11.
**Product_Series="CL-Series"**: OM Chapter 2.2 "Connections" 절 소제목 "CL-Series rigging components and arrays" — GSL의 "SL-Series"와 마찬가지로 원문에서 명시적으로 확인, 짐작에 의존하지 않음.
**Model_Number**: OM Chapter 3.1 "This declaration applies to: d&b Z0880 CCL8 loudspeaker".
**WEEE_Marking**: GSL8과 동일한 등록번호(WEEE-Reg.-Nr. DE: 13421928) — 브랜드 전체 공통 등록번호로 판단(각 제품 자신의 OM에서 개별 확인됨, 원본성 요건 충족).
**Way_Count=2**: 전방 LF+측면 LF(동일 대역, LF 그룹)와 HF 동축 드라이버로 2-way — GSL(3-way, MF 섹션 포함)과 다름.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [1] | 55 - 20000 | Hz |
| Frequency_Response_5dB_Hz | 60 - 18000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Max_SPL_Peak [2] | 137 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m [2] | 149 | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg | 80 | deg |
| Nominal_Directivity_Vertical | null | - |
| Cardioid_Capability [3] | Built-in (원문 자체가 "compact cardioid line array loudspeaker"로 자기 서술, GSL과 달리 저음역 카디오이드 수렴 대역 조건은 원문에 별도 명시 없음) | - |
| DSP_Preset_Name | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS "System data"/"Loudspeaker data" 표; OM Chapter 2.5 "Technical specifications" p.9.
**[1] Usable_Bandwidth_Hz 채택 기준**: GSL과 동일하게 -10dB 기준("Frequency response (-10 dB standard, IEC60268): 55 Hz - 20 kHz")을 채택해 정렬. -5dB 기준(Standard)은 Frequency_Response_5dB_Hz로 병기. CUT 모드 조건부 대역폭(-5dB: 90-18000Hz, -10dB: 80-20000Hz)은 GSL과 동일 원칙으로 범용 Key로 동기화하지 않고 signal_processing 섹션에 별도 기재.
**[2] Max_SPL 앰프별 소스 충돌 보존**: SPS "Max. SPL(Peak, 1m, free field, broadband signal IEC60268) with D25/D20/25D/30D: 135 dB / with D90/D80/D40/40D: 137 dB" — 앰프 등급에 따라 두 값이 다름, 둘 다 원문 그대로 보존. GSL의 대표 앰프(D90/D80)와 정합되도록 더 높은 137dB(D90/D80/D40/40D 조건)를 Value로 채택, 135dB(D25 계열)는 이 각주로 보존. 4대 어레이 값(149dB)은 D90/D80/D40/40D 조건에서만 제공됨(D25 계열 값 없음).
**[3] Cardioid_Capability — GSL과 다른 근거 수준**: Manual "The CCL8 is a compact cardioid line array loudspeaker for small to medium-scale sound reinforcement in mobile applications."(제품 자체 서술) — 다만 GSL의 OM처럼 "merging into a cardioid dispersion down to the lowest frequency"라는 저음역 수렴 조건부 서술은 CCL8 자신의 3개 문서(SPS/AE/OM) 전량 스캔 결과 없음. 원문 자체가 "cardioid"를 제품명 서술에 명시하므로 Built-in으로 채택하되, 근거 수준의 차이를 명확히 구분.
**Nominal_Directivity_Vertical**: 전량 스캔 결과 없음 — 미확인.

## transducers

| Key | Value | Unit |
|---|---|---|
| Front_LF_Transducer | 2 x 7" neodymium, forward-firing | - |
| Side_LF_Transducer | 2 x 5" neodymium, side-firing | - |
| HF_Transducer | 2 x 10.2 x 63 mm exit compression drivers with 1.75" coil, coupled to dedicated wave shaping device | - |
| LF_Acoustical_Load [1] | vented enclosure (front LF driver only) | - |
| HF_Acoustical_Load | dedicated wave shaping device | - |
| Passive_Crossover_Network | Yes | - |
| Nominal_Impedance_Overall [2] | 10 | Ohm |
| LF_Nominal_Impedance | null | - |
| HF_Nominal_Impedance | null | - |
| RMS_Power_Handling_Overall [3] | 400 | W |
| Peak_Power_Handling_10ms_Overall [3, 신규 Key] | 1200 | W |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS "TRANSDUCERS"/"Loudspeaker data" 표; AE 전문.
**총 등가 전방 LF 드라이버 크기**: AE/SPS "The total equivalent front facing LF driver size shall be 2x 8.7"" — 전방+측면 LF 드라이버의 결맞음(coherent) 합산 계산값(각주 "Calculated equivalent diameter of coherent addition of front and side radiating LF drivers"), 실제 물리적 드라이버 크기(7"/5")와 다른 파생 수치이므로 별도 각주로만 보존.
**[1] LF_Acoustical_Load**: AE "two forward 7" LF neodymium drivers in a vented enclosure radiating to the front, two sideward 5" LF neodymium drivers" — vented enclosure 서술이 전방 LF에만 명시적으로 연결되어 있어 측면 LF 로딩 방식은 미확인.
**[2] Nominal_Impedance_Overall=10Ω(GSL과 다른 임피던스 구조)**: GSL은 2채널(Front_LF_Nominal_Impedance/Side_LF_MF_HF_Nominal_Impedance)로 나뉘어 별도 값이었으나, CCL8은 단일 채널 전체가 하나의 임피던스(SPS "Nominal impedance: 10 ohms")로 측정됨 — 단일 채널 구조를 반영해 Nominal_Impedance_Overall 채택, GSL식 Front/Side 분리 Key는 이 제품에 생성하지 않음(물리 구조 자체가 다름).
**[3] RMS_Power_Handling_Overall/Peak_Power_Handling_10ms_Overall(신규 Key)**: SPS "Power handling capacity (RMS/peak 10 ms): 400/1200 W" — 단일 채널 전체 파워 핸들링. RMS_Power_Handling_Overall은 기존 범용 Key 재사용, `Peak_Power_Handling_10ms_Overall`은 이번에 신설한 신규 범용 Key(10ms 피크 파워 핸들링은 업계 표준 측정 조건으로 브랜드 무관 개념) — 배치 완료 후 speakers 카테고리 전체 동기화 라운드에서 함께 처리 예정(TODO.md 기록).
**MF 관련 Key 전체 미생성**: 2-way 구조로 MF 대역 자체가 없음(SKILL v1.19).

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector [1] | 1 x NLT4 male | - |
| Link_Connector [1] | 1 x NLT4 female | - |
| NLT4_Pinout_Pin1 [2] | Full-range signal (front LF + side LF + HF, combined via internal passive crossover) | - |
| NLT4_Pinout_Pin2 [2] | Not used by CCL8 itself — designated pass-through for downstream subwoofer (e.g., CCL-SUB) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.2 "Connections" p.6("NLT4 F/M Connector wiring" 도해); SPS "Connections"/"Pin assignment" 행.
**[1] Input_Connector/Link_Connector — GSL과 다른 구조**: GSL은 단일 F 커넥터만 있어 Link_Connector가 비적용이었으나, CCL8은 Manual "Using the male connector as the input, the female connector allows for direct connection to a second cabinet."로 명시적 루프스루 구조 확인 — K1식 Input/Link 분리 패턴 채택.
**[2] NLT4_Pinout_Pin1/Pin2**: OM "The cabinets use the pin assignments 1+/1-. Pins 2+/2- are designated to subwoofers." — CCL8 자신의 오디오 신호는 Pin1만 사용, Pin2는 하위 서브우퍼(CCL-SUB 등, 이 배치에는 미포함)로 신호를 통과시키는 병렬 배선용.

## signal_processing

CCL8 컨트롤러(D90/D80/D40/40D 등)에서 설정 가능한 파라미터형 음향 보정 기능 — GSL과 동일한 d&b 브랜드 표준 기능 체계이나 CCL8 자신의 수치로 확인.

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | Yes | - |
| CUT_Mode_Frequency_Response_5dB_Hz | 90 - 18000 | Hz |
| CUT_Mode_Frequency_Response_10dB_Hz | 80 - 20000 | Hz |
| HFC_Function_Settings | HFC1: 40 m additional distance compensation; HFC2: 80 m additional distance compensation (reference: 50% RH, 22 deg C) | - |
| Coupling_Function_Range | Low: +5 to -5; Mid: 0 to -8; increments of 0.5 | dB |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.3.1 "Controller settings" p.7-8.
**CUT mode**: CCL8/CCL12 캐비닛을 CCL-SUB 등 적용 서브우퍼와 함께 구성하도록 LF 레벨을 낮추는 모드 — GSL과 동일 개념이나 주파수 수치는 CCL8 자신의 값(GSL은 70-18000/54-20000Hz)으로 다름.
**HFC/Coupling 수치가 GSL과 동일**: HFC1=40m/HFC2=80m, Coupling Low ±5/Mid 0~-8(0.5 증분) — GSL8과 완전히 동일한 수치 확인, d&b 브랜드 전체에 표준화된 컨트롤러 기능으로 판단(제품별 재확인 필요, 이 판단을 다른 제품에 자동 적용하지 않음).

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | D25/D40/D90/D80 | - |
| Max_Enclosures_Per_Controller_Output [1] | 2 (Line/Arc mode); 1 (AP mode) | count |
| Max_Enclosures_Per_Controller_Total | null | - |
| Crossover_Type [2] | Passive (2-way, single amplifier channel, front LF+side LF+HF combined via internal passive crossover network) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 "Intended use" p.5(NOTICE "Recommended amplifiers: D25/D40/D90/D80"), Chapter 2.3 "Operation" p.6("Amplifier output mode(s): Dual Channel or Mix TOP/SUB", Cabinets per channel 표).
**[1] Max_Enclosures_Per_Controller_Output — 3가지 설정 모드**: OM "Amplifier output mode(s): Dual Channel or Mix TOP/SUB" 표 — CCL8 Line=2대/channel, CCL8 Arc=2대/channel, CCL8 AP(ArrayProcessing)=1대/channel. GSL의 단일값(1)과 달리 CCL8은 설정 모드에 따라 값이 달라져 병기.
**[2] Crossover_Type=Passive(GSL과 대조)**: GSL은 "Hybrid — active+passive"였으나 CCL8은 완전 패시브(단일 채널, active/passive 분리 서술 자체가 원문에 없음) — 파일 서두 아키텍처 판단 참조.
**Max_Enclosures_Per_Controller_Total**: GSL과 동일 사유로 ArrayCalc 시뮬레이션 소프트웨어 검증 권장, 시스템 전체 상한 명시 없음 — 미확인.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type [1] | three point rigging system (strands on both sides of cabinet front + central strand at rear, fold/slide out when needed); Z5820 CCL Flying frame required for array assembly | - |
| Inter_Enclosure_Angles_deg | 0 - 14 (1° increments) | deg |
| Handles | 4 (1 per side panel x2, 2 at rear) | count |
| Weight_Net | 17.6 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 "Intended use" p.5-6("CL-Series rigging components and arrays"); SPS "Loudspeaker data"(Weight 행); CCL Rigging manual v1.3 en Chapter 1.3 "Components and weights/Load capacity" p.5.
**[1] Z5820 CCL Flying frame 하중 정격(별도 리깅 매뉴얼 확보)**: GSL과 달리 이번 라운드에서 CCL Rigging manual(별도 문서)을 확보해 상세 확인 — "The Z5820 CCL Flying frame including Beam extension is designed to support a total system weight of 500 kg (1100 lb) - SWL including all rigging components." 캐비닛 중량(17.6kg) x 24대 = 422.4kg로 500kg SWL 이내(mechanical_safety 섹션 참조).
**Handles**: SPS/OM/Manual 3개 문서 모두 동일 문구("Each side panel incorporates a handle while two additional support handles are provided at the rear") — GSL과 완전히 동일한 서술.

## physical

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
| IP_Rating [1] | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: SPS p.2 "CCL8 cabinet dimensions in mm [inch]"(도면, W/H/D 명시적 라벨링); OM Chapter 2.1 p.5-6.
**W/H/D 축 확정**: SPS/AE 모두 "Dimensions (W x H x D) shall not exceed 593 x 209 x 355 mm"로 축이 명시적으로 라벨링되어 있어 GSL(도면 렌더링 필요)과 달리 즉시 확정.
**Dimensions_Raw**: 축이 명확히 확인되어 상위 호환 Key로 대체 — null.
**[1] IP_Rating — 명시적 비-완전방수 경고(정식 등급 아님)**: OM Chapter 2.1 "NOTICE! Possible risk of water ingress! The passive LF cardioid design of the d&b CL-Series systems requires dedicated rear ports. For acoustic reasons, these ports cannot be fully water sealed... While permanent damage is unlikely under normal conditions, water ingress can require cabinet disassembly for drainage to prevent damage to internal components." — 정식 IP 등급 수치는 없으나(미확인), 완전 방수가 구조적으로 불가능하다는 제조사 명시적 경고가 있어 이 각주로 보존.
**Finish_Color**: 3개 문서 전량 스캔 결과 색상명 명시 없음(이미지상 검정으로 보이나 텍스트 근거 없음) — 미확인.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: GSL과 동일 — CUT/HFC/Coupling은 파라미터형 함수이지 조합별 명명 프리셋이 아니며, 이 섹션이 요구하는 "구성별 프리셋+매칭비율+최소라인길이" 개념 자체가 CCL8 문서 범위에 존재하지 않는다.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: GSL과 동일 — 조합별 사전 정렬 딜레이 기본값 표 없음(CUT/HFC/Coupling은 레벨/주파수 보정 기능이지 딜레이가 아님).

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown | Z5820 CCL Flying frame | null | 24 cabinets (500 kg SWL total system weight incl. rigging components) |

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | null | - |
| Max_Wind_Load | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: AE/SPS "The cabinet shall incorporate a three point rigging system for the assembly of vertical line source arrays of up to 24 cabinets in connection with a dedicated flying frame."; CCL Rigging manual v1.3 en p.5(SWL 500kg).
**GSL 대비 개선 — 실값 확보**: GSL8/GSL12는 SL-Series Rigging manual이 세션에 미제공되어 이 섹션 전체가 미확인이었으나, CCL은 이번 라운드에서 CCL Rigging manual을 확보해 Maximum_Limit 실값을 채웠다.
**Safe_Limit 열 null 사유**: 확보한 리깅 매뉴얼 앞부분(5페이지)에는 "Maximum" 상한(SWL)만 있고 별도 안전 한도 구분이 없음.
**Safety_Factor/Max_Wind_Load**: 리깅 매뉴얼의 "Wind loads"(Chapter 1.5) 절은 이번 라운드에서 재조회하지 않아 미확인 — 향후 필요 시 해당 챕터 확인 필요(원본은 존재하나 이번 세션에서 미열람, 원본 부재와 구분).

## Null Report

**미확인(정보 부족)**: Nominal_Directivity_Vertical, Max_SPL_Single_Module, AES75_Max_Linear_SPL, LF_Nominal_Impedance, HF_Nominal_Impedance(단일 채널이라 개별 측정 불가, 아래 비적용과 성격 다름 — 원문에 채널 자체가 분리되지 않아 물리적으로 미확인), Max_Enclosures_Per_Controller_Total, Rigging_Components_Material, Finish_Color, IP_Rating, mechanical_safety(Safe_Limit 1건, Safety_Factor, Max_Wind_Load) — 12건.
**비적용(CCL8 아키텍처상 개념 자체 불성립)**: DSP_Preset_Name, preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 3건. **참고(GSL과의 차이 명시)**: GSL은 Link_Connector가 비적용(단일 F 커넥터 구조)이었으나, CCL8은 루프스루 구조라 Link_Connector가 실값("1 x NLT4 female")으로 존재해 이 null 목록 어디에도 해당하지 않는다. MF_Transducer/MF_Acoustical_Load/MF_Nominal_Impedance 등은 2-way 구조상 애초에 생성하지 않음(SKILL v1.19, null 목록 대상 아님). Front_LF_Nominal_Impedance/Side_LF_MF_HF_Nominal_Impedance(GSL 고유 Key)도 이 제품의 물리 구조(단일 채널)에 맞지 않아 애초에 생성하지 않음.

**총계**: null 15건 (미확인 12건 + 비적용 3건). 확정적 비존재(0/No)로 명시한 항목은 0건 — Passive_Crossover_Network는 "Yes"로 실값 확보.

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — d&b audiotechnik 2번째 제품군(CCL8) 최초 투입, GSL8_v1.8.md를 스켈레톤으로 사용(같은 브랜드이나 아키텍처는 상이 — GSL의 2채널 하이브리드와 달리 CCL8은 단일 채널 완전 패시브). `upload/` 폴더 제공 Datasheet(SPS, AE 절 포함)+Manual(CCL8/CCL12 공용)+CCL Rigging manual 통합. GSL과 달리 Link_Connector 실값 확보(루프스루 구조), 리깅 매뉴얼 확보로 mechanical_safety Maximum_Limit(24대/500kg SWL) 실값 확보. 신규 범용 Key `Peak_Power_Handling_10ms_Overall` 신설(배치 종료 후 일괄 동기화 예정). Product_Series="CL-Series"(GSL의 "SL-Series"와 다름) 확인. CUT/HFC/Coupling 파라미터가 GSL과 값이 유사(HFC/Coupling 완전 동일, CUT 주파수만 다름)해 d&b 브랜드 표준 기능 체계일 가능성 확인(제품별 재검증 원칙 유지). Null Report 15건(미확인 12건+비적용 3건). |
