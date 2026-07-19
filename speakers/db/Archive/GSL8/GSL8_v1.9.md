# GSL8 (d&b audiotechnik) — Master Schema

**Category**: speakers | **Brand**: d&b audiotechnik (db) | **Schema Phase**: Phase 3-2 (타 브랜드 교차 테스트, K1 대비)

**스켈레톤 근거**: `speakers/LA/K1_v1.0.md`을 뼈대로 사용 — K1과 마찬가지로 GSL8도 온보드 앰프가 없는 패시브 토폴로지(외부 앰프 구동)이며, 아키텍처 축(리깅/트랜스듀서/커넥터/외부 앰프 의존)이 K1과 가장 유사하다고 판단(자체 OM "GSL cabinets are driven by two channels of the applicable d&b amplifier" 및 "Recommended amplifiers: D90/D80" 확인). 다만 채널 토폴로지가 K1(LF/MF/HF 완전 독립 4채널)과 달리 GSL은 2채널(front LF / side LF+MF+HF 패시브 크로스오버 결합)이라 트랜스듀서·임피던스·커넥터 섹션은 GSL 고유 구조에 맞는 신규 Key로 확장했다. 이 신규 Key들은 K1_v1.2.md에 비적용(null)으로 소급 반영되었다(양방향 동기화) — K1이 이후 v1.1(Phase 2 자체 소스 보강)을 거쳐 v1.2(GSL8/GSL12 동기화 반영)로 갱신되는 동안 이 파일 작성이 함께 진행되어, 최종적으로는 K1_v1.2.md 기준으로 동기화가 완료되었다.

**GSL8/GSL12 관계**: 사용자 지침에 따라 GSL8과 GSL12는 앰프 작업 선례(LA1.16i/LA2Xi 등)를 따라 별도 두 파일로 분리했다. 두 제품은 동일 소스 문서(dbaudio-manual-gsl8-gsl12-1.6-en.pdf, Manual 1.6 en)를 공유하며, 스펙 대부분이 동일하고 수평 지향각/최대 SPL/모델번호만 상이하다.

## general

| Key | Value | Unit |
|---|---|---|
| Product_Name | GSL8 | - |
| Model_Number | Z0750 | - |
| Product_Series | SL-Series | - |
| Product_Category | line array loudspeaker for large-scale sound reinforcement applications | - |
| Product_Type | Line array loudspeaker | - |
| Description | 3-way line array loudspeaker; up to 24 cabinets flown per column via GSL Flying frame, producing 80 deg constant directivity dispersion in the horizontal plane | - |
| Way_Count | 3 | - |
| Onboard_Amplification | No | - |
| Compliance_Standards | in conformity with the provisions of the respective directives (specific directive names not enumerated in OM) | - |
| WEEE_Marking | Yes (EU), WEEE-Reg.-Nr. DE: 13421928 | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM(GSL8/GSL12 Manual, Version 1.6 en, 03/2026, D2730.EN.01) Chapter 2.1 "Intended use" p.6, Chapter 3.1 "Conformity of loudspeakers" p.12, Chapter 3.2 "WEEE Declaration (Disposal)" p.12.
**Product_Series/Product_Type(신규 Key, 사용자 지시 2026-07-17)**: d&b는 L-Acoustics처럼 AE 헤더 형식이 없어 OM 본문에서 확인 — GSL8_OM_EN_1.6.pdf 전문에 "www.sl-series.com", "Only operate d&b SL-Series loudspeakers...", "SL-Series rigging components and arrays"(복수 언급)로 "SL-Series" 소속이 명시적으로 확인됨(사용자가 "아마 SL 시리즈일 것"이라 추정했던 것을 원문 검증으로 확정, 짐작에 의존하지 않음). Product_Type은 OM "Product description" 챕터("The GSL8 is a line array loudspeaker for large-scale sound reinforcement applications")에서 "Line array loudspeaker"로 채택.
**Compliance_Standards(v1.1 신설)**: 원문 "We herewith declare that said products are in conformity with the provisions of the respective directives including all applicable amendments." — K1(2006/42/EC 기계지침 명시)과 달리 GSL은 구체적 지침명을 나열하지 않고 포괄적으로만 서술 — 원문 그대로 보존(임의로 지침명을 추정하지 않음).
**WEEE_Marking(v1.1 신설)**: 원문에 등록번호(WEEE-Reg.-Nr. DE: 13421928)까지 명시 — K1(마킹만 존재, 번호 없음)보다 상세.

## acoustical_performance

| Key | Value | Unit |
|---|---|---|
| Usable_Bandwidth_Hz [1] | 41 - 20000 | Hz |
| Frequency_Response_5dB_Hz | 45 - 18000 | Hz |
| Frequency_Response_6dB_Hz | null | Hz |
| Frequency_Response_3dB_Hz | null | Hz |
| Max_SPL_Peak [2] | 150 | dB |
| Max_SPL_4x_Array_Far_Field_Scaled_1m [2] | 162 | dB |
| Max_SPL_Single_Module | null | dB |
| AES75_Max_Linear_SPL | null | - |
| Nominal_Directivity_Horizontal_deg [3] | 80 constant directivity (merging into cardioid dispersion below 150 Hz) | deg |
| Nominal_Directivity_Vertical | null | - |
| Cardioid_Capability [4] | Built-in (단일 인클로저, 150Hz 이하 카디오이드 지향성 수렴) | - |
| DSP_Preset_Name | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.5 "Technical specifications" p.10 (System data 표), Chapter 2.4 "Dispersion characteristics" p.9.
**[1] Usable_Bandwidth_Hz 채택 기준**: K1의 Usable_Bandwidth_Hz는 -10 dB 기준이므로, GSL 쪽도 동일 기준인 "Frequency response (-10 dB standard, IEC60268): 41 Hz - 20 kHz" 값을 채택해 Key를 정렬했다. -5 dB 기준(Standard 모드) 값은 브랜드 무관 범용 임계값 개념이므로 이 섹션에 Frequency_Response_5dB_Hz로 병기. CUT 모드 조건부 대역폭(-5dB/-10dB 모두)은 "CUT mode"가 d&b 고유 명명 기능이라 범용 Key로 동기화하지 않고 아래 signal_processing 섹션에 별도 기재(2026-07-16 사용자 피드백 — 브랜드 고유 명칭이 박힌 Key를 모든 제품에 기계적으로 null 동기화하지 말 것).
**[2] Max_SPL 측정 조건**: "1 m, free field, broadband signal IEC60268" 기준, D90/D80 앰프 구동 시. Max_SPL_4x_Array_Far_Field_Scaled_1m은 4대 어레이 구성을 원거리에서 측정 후 1 m로 환산(scaled)한 값 — 단일 캐비닛 값과 물리적으로 다른 조건이므로 별도 Key로 분리 보존(총량 Key 오염 금지 원칙).
**DSP_Preset_Name**: GSL은 K1처럼 명명된 단일 프리셋을 로드하는 방식이 아니라, 컨트롤러에서 CUT/HFC/Coupling 파라미터형 기능을 개별 설정하는 방식이다(자체 OM Chapter 2.3.1 "Controller settings" 전문 확인) — 아키텍처상 비적용이 아니라 K1과 개념 자체가 달라 이 Key로는 표현되지 않으므로 null 처리하고, 실제 값은 아래 signal_processing 섹션에 별도 기록.
**Nominal_Directivity_Vertical**: OM에 수직 지향각 서술이 없어 미확인 처리.
**[4] Cardioid_Capability=Built-in(전용 Key 신설, v1.7)**: 원문(Chapter 2.4 "Dispersion characteristics") "The nominal horizontal dispersion of 80°/120° is maintained above 150 Hz merging into a cardioid dispersion down to the lowest frequency" — CS1(전방+측면 드라이버 분할로 단일 인클로저 자체가 카디오이드)과 동일하게 **단일 인클로저만으로 성립**(어레이나 반전 유닛 불필요)하는 Built-in 유형이나, 메커니즘은 CS1과 다르다 — GSL8의 하이브리드 크로스오버(전방 LF는 active 채널, 측면 LF/MF/HF는 내부 passive crossover, `speakers/CLAUDE.md` 브랜드 노트 참조) 구조로 인해 150Hz 이하에서 지향성이 자연스럽게 카디오이드 패턴으로 수렴하는 현상 — 별도 프리셋이나 반전 배치 없이 상시 발현. 기존(v1.6까지) Nominal_Directivity_Horizontal_deg 각주에만 있던 이 정보를 전용 Key로 승격.
**[3] 저음역 카디오이드 수렴 특성 발견(2026-07-17, 사용자 지적으로 재조사)**: OM Chapter 2.4 "Dispersion characteristics" p.9 원문 — "The nominal horizontal dispersion of 80°/120° is maintained above 150 Hz merging into a cardioid dispersion down to the lowest frequency." GSL8는 80°, GSL12는 120°가 150Hz 이상에서 유지되다가 그 이하 대역에서는 (isobar 다이어그램상) 카디오이드 형태로 수렴한다는 뜻 — CS1/KS28처럼 선택 가능한 "cardioid 모드"가 아니라 Front_LF/Side_LF 분리 배선 설계에서 비롯된 저음역 고유 지향 특성 서술이다. 이전 버전들에서 이 문장을 놓치고 있었음(사용자가 CS1/GSL 카디오이드 데이터 부재를 지적해 재조사, K1_v1.9.md/CS1_v1.0.md 작성 시점에는 발견되지 않았던 항목).

## signal_processing

GSL 컨트롤러(D90/D80)에서 설정 가능한 파라미터형 음향 보정 기능 — K1에는 해당 개념이 없어(명명 프리셋 방식) 비적용.

| Key | Value | Unit |
|---|---|---|
| CUT_Mode_Available | Yes | - |
| CUT_Mode_Frequency_Response_5dB_Hz | 70 - 18000 | Hz |
| CUT_Mode_Frequency_Response_10dB_Hz | 54 - 20000 | Hz |
| HFC_Function_Settings | HFC1: 40 m additional distance compensation; HFC2: 80 m additional distance compensation (reference: 50% RH, 22 deg C) | - |
| Coupling_Function_Range | Low: +5 to -5; Mid: 0 to -8; increments of 0.5 | dB |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.3.1 "Controller settings" p.8, Chapter 2.5 "Technical specifications" p.10(CUT mode 대역폭 수치).
**CUT_Mode_Frequency_Response_*는 이 섹션에만 위치(범용 acoustical_performance 섹션에 두지 않음)**: "CUT mode"는 d&b 고유 명명 기능이라 브랜드 무관 범용 Key로 동기화하지 않는다 — 이 섹션 자체가 이미 GSL 고유(K1 등 타 브랜드에는 비적용)로 스코프되어 있으므로, 이 안에서는 GSL 고유 명칭을 그대로 사용해도 Null Report의 "제조사별 자료 상세도 비교" 신호를 왜곡하지 않는다.
**CUT mode**: LF 레벨을 낮춰 SL-SUB/SL-GSUB 서브우퍼와 함께 사용하도록 구성하는 모드.
**HFC (High Frequency Compensation)**: 원거리 청취 위치의 공기 흡수로 인한 고역 손실을 보정. 습도가 낮으면 보정 유효 거리가 명시치보다 짧아짐(원문 명시).
**Coupling**: 캐비닛 간 커플링 효과 보정(저역/저중역 레벨 감쇠). AP(ArrayProcessing) 사용 시 자동 적용, 추가 보정용으로도 사용 가능.

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

**출처**: OM Chapter 2.1 "Intended use" p.6 (드라이버 구성 서술), Chapter 2.5 "Technical specifications" p.10 (Components/Loudspeaker data 표).
**LF_Transducer/LF_Acoustical_Load 비적용 사유**: GSL은 LF 드라이버가 전방(front) 2발 + 측면(side) 2발로 물리적으로 분리 배치되고 각각 다른 임피던스 채널에 연결되어, K1처럼 단일 "LF" 그룹으로 표현할 수 없다 — Front_LF_Transducer/Side_LF_Transducer로 대체.
**MF_Nominal_Impedance/HF_Nominal_Impedance 비적용 사유**: GSL 커넥터는 2채널 구조(front LF / side LF+MF+HF 결합)이며, MF와 HF는 내부 패시브 크로스오버로 side LF와 한 채널에 묶여 있어 개별 임피던스가 커넥터 단에서 별도로 측정되지 않는다(원문 "Nominal impedance side LF/MF/HF: 4 ohms" 단일 값). 이를 반영해 Front_LF_Nominal_Impedance/Side_LF_MF_HF_Nominal_Impedance 신규 Key로 대체.
**HF_Acoustical_Load 표기**: 원문은 L-Acoustics의 "DOSC waveguide"와 달리 "dedicated wave shaping device"로 표기 — 개념적으로 유사한 혼/도파관 로딩이나 브랜드별 고유 명칭이 달라 원문 그대로 보존하고 임의로 "waveguide"로 통일하지 않음(표기 방식이 다른 동일 물리량 임의 변환 금지 원칙).
**Power_Handling**: 원문 "RMS/peak 10 ms" 조건. Front LF와 Side LF/MF/HF 두 채널 모두 800/3200 W로 동일하게 명시됨.

## connectivity

| Key | Value | Unit |
|---|---|---|
| Input_Connector | 1 x NLT4 F | - |
| Link_Connector | null | - |
| NLT4_Pinout_Pin1 | Front LF+ / Front LF- | - |
| NLT4_Pinout_Pin2 | Side LF/MF/HF+ / Side LF/MF/HF- | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.2 "Connections" p.7, Chapter 2.5 "Technical specifications" p.10 (Pin assignment 행).
**Link_Connector 비적용 사유**: 원문에 "The cabinets are fitted with a single NLT4 F connector"로 명시 — K1과 달리 별도 LINK(루프스루) 커넥터가 없는 단일 커넥터 구조.
**PA_COM_Pinout_* Key 삭제(v1.2, SKILL v1.14 정책 반영)**: 이전 버전에서는 K1 유래 PA_COM_Pinout_AB/CD/EF/GH를 GSL에 비적용 null로 동기화했으나, 이 Key는 L-Acoustics 자신의 커넥터 모델명(PA-COM)이 박힌 브랜드 고유 명칭이라 완전히 삭제했다 — GSL은 이미 자기 자신의 커넥터(NLT4) 핀아웃을 NLT4_Pinout_Pin1/Pin2로 보유하고 있다.

## amplification_requirements

| Key | Value | Unit |
|---|---|---|
| Compatible_Amplified_Controller | D90/D80 | - |
| Max_Enclosures_Per_Controller_Output [1] | 1 | count |
| Max_Enclosures_Per_Controller_Total | null | - |
| Crossover_Type [2] | Hybrid — active (front LF channel) + passive (side LF/MF/HF channel) | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 "Intended use" p.6 (NOTICE 박스 "Recommended amplifiers: D90/D80"), Chapter 2.3 "Operation" p.7 (Amplifier output mode(s), Cabinets per pair of amplifier channels 표).
**필수 사용 경고**: 원문 NOTICE — "Only operate d&b SL-Series loudspeakers with the specified and correctly configured d&b amplifiers, otherwise there is a risk of damaging the loudspeaker components and the directional characteristics of the system cannot be achieved."
**[1] Max_Enclosures_Per_Controller_Output 단위 정합**: 원문 표기는 "Cabinets per pair of amplifier channels" = 1 (GSL8 Line/Arc/AP 설정 모두 동일). K1의 동일 Key는 "per output"(LA12X 1개 출력당 K1 대수) 기준이며, 두 브랜드 모두 "앰프 채널 쌍(또는 출력) 1개당 인클로저 대수"라는 동일 개념을 가리킨다고 판단해 Key를 재사용했다.
**[2] Crossover_Type(active/passive 크로스오버 축, self-powered 여부와 무관)**: 원문 "Amplifier output mode(s): 2-Way Active"는 앰프가 2개의 능동(active) 채널을 공급한다는 의미이나, 그중 한 채널(side LF/MF/HF)은 인클로저 내부의 "Passive crossover network"(원문, Technical specifications > Components)로 재분리되므로 하이브리드 구조다. K1의 Crossover_Type=Active(3-way, 4채널 전체 능동)와 대조된다. 이 Key는 Onboard_Amplification(self-powered 여부, GSL8=No로 별도 관리)과는 독립적인 축이다.
**Max_Enclosures_Per_Controller_Total**: 원문에 시스템 전체 상한이 명시되어 있지 않음(ArrayCalc 시뮬레이션 소프트웨어로 배열 구성 검증 권장) — 미확인 처리.

## rigging_handling

| Key | Value | Unit |
|---|---|---|
| Rigging_System_Type | rigging strands on both sides of cabinet front and a central strand at the rear; components mounted on cabinet, fold/slide out when needed | - |
| Inter_Enclosure_Angles_deg | 0, 1, 2, 3, 4, 5, 6, 7 | deg |
| Handles | 4 (1 per side panel x2, 2 at rear) | count |
| Weight_Net | 80 | kg |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 "Intended use" p.6 (SL-Series rigging components and arrays), Chapter 2.5 "Technical specifications" p.10 (Splay angle setting, Weight 행).
**리깅 상세**: SL-Series Rigging manual에 상세 절차가 별도 문서로 존재한다고 언급되나 본 세션에는 미제공 — 리깅 상세 구조(정확한 포인트 수 등)는 이 OM 범위 내 서술로만 기재.

## physical

| Key | Value | Unit |
|---|---|---|
| Width_mm [1] | 1300 | mm |
| Height_mm [1] | 391 | mm |
| Depth_mm [1] | 627 | mm |
| Dimensions_Raw [1] | 1300 / 391 / 627 | mm |
| Cabinet_Material | marine plywood | - |
| Front_Material | rigid metal grill backed by acoustically transparent and water repellent fabric | - |
| Rigging_Components_Material | null | - |
| Finish_Color | null | - |
| Finish_Type | PCP (Polyurea Cabinet Protection), impact and weather protected | - |
| IP_Rating | null | - |

### 주석 및 출처 (Notes & Sources)

**출처**: OM Chapter 2.1 "Intended use" p.6, Chapter 2.5 p.11 "GSL8/GSL12 cabinet dimensions in mm [inch]"(도면).
**[1] Width_mm/Height_mm/Depth_mm/Dimensions_Raw 재조사 완료(2026-07-18, 사용자 지적)**: 이전 버전은 "치수 도면이 순수 그래픽으로만 표기되어(텍스트 레이어 없음) 렌더링 도구 미설치로 시각 확인 불가"라는 사유로 미확인 처리했었으나, 이 프로젝트에서 이미 확립된 PowerShell+Windows.Data.Pdf WinRT API 렌더링 기법(pdftoppm 불필요, Windows 내장 기능만 사용)으로 OM p.11 "GSL8/GSL12 cabinet dimensions in mm [inch]" 도면을 직접 이미지 렌더링해 육안 확인 — 정면/측면 입체도에 "1300 [51.2"]"(수평)와 "391 [15.4"]"(수직), 상면도에 "627 [24.7"]"(전후) 3개 숫자가 명확히 표기되어 있음을 확인했다. 축 대응은 (a) 3개 숫자 중 최솟값(391mm)이 배열 적층 방향(Height, 여러 대를 쌓아 하나의 라인어레이 컬럼을 구성하는 축)이라는 라인어레이 캐비닛의 일반적 형상 논리와 정합하고, (b) GSL8의 전방+측면 발사형(front+side-firing) LF 드라이버 배치(스펙 표에 "Nominal impedance front LF"/"side LF/MF/HF" 별도 명시)로 인해 Width가 Depth보다 커야 한다는 물리적 정합성도 만족하여, Width=1300mm/Height=391mm/Depth=627mm으로 확정했다. 도면 제목이 "GSL8/GSL12 cabinet dimensions"로 두 모델 공용임을 명시 — GSL12_v1.8.md에도 동일값 반영.
**TODO.md 치수 W/H/D 축 구분 신뢰도 감사 기준 충족**: 이 케이스는 기준 (2) "도면 이미지 렌더링으로 시각적으로 축을 확인"에 해당(A&E 명시적 라벨링은 아니나, 물리적 정합성 교차검증까지 거친 고신뢰도 사례).
**IP_Rating**: 원문에 명시적 IP 등급 언급이 없음 — 미확인.
**Rigging_Components_Material**: SL-Series Rigging manual(별도 문서, 미제공)에 상세 기재되었을 가능성이 높으나 본 OM 범위 내에서는 재질 명시 없음 — 미확인.

## preset_guide_and_matching

| Configuration | Preset(s) | Frequency_Range_10dB_Hz | Recommended_Ratio | Minimum_Line_Length |
|---|---|---|---|---|
| null | null | null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: K1_v1.1.md에서 신설된 섹션. GSL8/GSL12 OM(Manual 1.6 en)에는 K1처럼 명명된 서브우퍼/다운필 조합 프리셋 가이드(예: [K1SB_60]류)가 없다 — CUT/HFC/Coupling은 파라미터형 함수이지 조합별 명명 프리셋이 아니며, 이 섹션이 표현하는 "구성별 프리셋+매칭비율+최소라인길이" 개념 자체가 GSL 문서 범위에는 존재하지 않는다(비적용). d&b 측 서브우퍼(SL-SUB/SL-GSUB) 매칭 상세는 SL-Series Rigging manual 등 별도 미제공 문서에 있을 가능성이 있으나 본 OM 범위 내에서는 확인 불가.

## delay_defaults

| Preset_Combo | Primary_Element_Delay_ms | Secondary_Element_Delay_ms |
|---|---|---|
| null | null | null |

### 주석 및 출처 (Notes & Sources)

**비적용 사유**: GSL8/GSL12 OM에는 조합별 사전 정렬 딜레이 기본값 표가 없음(CUT/HFC/Coupling 함수 자체가 딜레이가 아닌 레벨/주파수 보정이므로 개념적으로도 다름).

## mechanical_safety

| Configuration | Rigging_Accessory | Safe_Limit | Maximum_Limit |
|---|---|---|---|
| flown (any splay config, up to 10 cabinets) | Z5701 GSL Flying frame + Z5702 GSL Load beam + Z5707 SL Aiming plate | null | 10 cabinets (800 kg system weight) |
| flown (general, ArrayCalc 검증 필요) | 상동 | null | 24 cabinets (2000 kg SWL total system weight incl. rigging) |
| SUB column (SL-SUB) | 상동 | null | 14 cabinets |

### 주석 및 출처 (Notes & Sources)

**실값 확보(v1.9, 2026-07-18)**: KSL8/KSL12 투입 과정에서 `dbaudio-rigging-manual-gsl-ksl-1.16-en.pdf`(GSL/KSL Rigging manual, 두 제품군 공용 단일 문서)를 신규 확보 — v1.0~v1.8 작성 시점에는 이 문서가 세션에 제공되지 않아 이 섹션 전체가 미확인이었다. Chapter 1.3 "Components and weights/Load capacity - GSL System" p.6: "The Z5701 GSL Flying frame together with the Z5702 GSL Load beam and the Z5707 SL Aiming plate is designed to support a total system weight of 2000 kg (4409 lb) - SWL including all rigging components. This allows the suspension of a maximum of 24 x GSL-TOP cabinets or a SUB column consisting of a maximum of 14 x SL-SUB cabinets. The rigging components allow arrays of up to 10 x GSL-TOP cabinets with a total system weight of 800 kg (1764 lb) to be flown in any vertical splay angle configuration between the cabinets. For any other array configuration the load conditions within the array have to be checked using the d&b ArrayCalc simulation software." 캐비닛 중량(80kg) x 24대 = 1920kg로 2000kg SWL 이내.

| Key | Value | Unit |
|---|---|---|
| Safety_Factor | null | - |
| Max_Wind_Load [1] | 6 Beaufort(비행 비권장 상한); 8 Beaufort 초과 시 반드시 하강·고정 | Beaufort |

**Safety_Factor**: 리깅 매뉴얼 Chapter 1.4 "Secondary safety" 절까지 확인했으나 "5:1" 같은 명시적 비율 수치는 없음(독일 DGUV 규정 준수로 "inherently safe up to their uppermost suspension point"라는 정성적 서술만 있음) — 미확인 유지.
**[1] Max_Wind_Load 실값 확보(v1.9)**: 동일 Rigging manual Chapter 1.5 "Wind loads" p.8: "Flying loudspeakers overhead at wind forces higher than 6 bft (22-27 knots, 39-49 km/h, 25-31 mph) is not recommended. If the wind force exceeds 8 bft (34-40 knots, 62-74 km/h, 39-46 mph): Make sure that no person remains in the vicinity of the array. Lower and secure the array." — GSL/KSL 공용 수치(KSL8_v1.0.md에도 동일 반영).

## Null Report

**미확인(정보 부족)**: Nominal_Directivity_Vertical, Frequency_Response_6dB_Hz, Frequency_Response_3dB_Hz, AES75_Max_Linear_SPL, Max_Enclosures_Per_Controller_Total, LF_Acoustical_Load, RMS_Power_Handling_LF, RMS_Power_Handling_MF, RMS_Power_Handling_HF(K1/K2 고유 LF/MF/HF 대역 구조로는 매핑 안 됨, GSL 자체 Power_Handling_Front_LF/Side_LF_MF_HF 참조), Rigging_Components_Material, Finish_Color, IP_Rating, mechanical_safety(Safe_Limit 열 — 3개 Configuration 행의 null 셀, 3건; Safety_Factor, 1건) — 16건.
**비적용(GSL 아키텍처상 개념 자체 불성립)**: DSP_Preset_Name, LF_Transducer, LF_Nominal_Impedance(GSL은 Front_LF_Nominal_Impedance/Side_LF_MF_HF_Nominal_Impedance로 이미 자체 표현, MF/HF_Nominal_Impedance와 동일 사유), MF_Nominal_Impedance, HF_Nominal_Impedance, Link_Connector, preset_guide_and_matching(전 항목), delay_defaults(전 항목) — 8건. PA_COM_Pinout_*는 L-Acoustics 커넥터 고유 명칭이라 애초에 생성하지 않음(SKILL v1.14).

**총계**: null 24건 (미확인 16건 + 비적용 8건). 확정적 비존재(0/No)로 명시한 항목은 0건 — Passive_Crossover_Network는 "Yes"로 실값 확보(GSL 자신의 OM에 명시). LC_Transducer/LC_Acoustical_Load/LC_Nominal_Impedance는 한때 동기화되어 있었으나 LC가 L2 라인 고유 설계 요소라는 사용자 지적(2026-07-17)에 따라 v1.5에서 삭제(SKILL v1.16). (v1.4: 전수 감사에서 LF_Nominal_Impedance 비적용 누락 발견·정정, 총계 산술 오류 정정.) **v1.9(2026-07-18)**: GSL/KSL Rigging manual 신규 확보로 mechanical_safety의 Configuration/Rigging_Accessory/Maximum_Limit 3개 행 및 Max_Wind_Load가 실값으로 전환됨(총계 자체는 24건으로 동일 — Max_Wind_Load가 빠진 자리를 Safe_Limit 3행 분해가 상쇄).

## 버전 변경 이력

| Version | 변경 내용 |
|---|---|
| v1.0 | 최초 작성 — speakers 카테고리 Phase 3-2(d&b audiotechnik 교차 브랜드). K1_v1.0.md를 스켈레톤으로 사용, OM(GSL8/GSL12 Manual v1.6 en) 단일 소스 기준. 신규 섹션 signal_processing 신설, 신규 Key 다수(Front/Side_LF_Transducer, Power_Handling_*, NLT4_Pinout_* 등) 추가 및 K1_v1.2.md에 양방향 동기화 반영. 사용자 피드백(2026-07-16) 반영 — "CUT mode" 조건부 대역폭처럼 브랜드 고유 명칭이 박힌 Key는 범용 acoustical_performance 섹션이 아닌 GSL 고유 signal_processing 섹션에만 위치시키도록 설계(Frequency_Response_5dB/10dB_CUT_Mode_Hz -> CUT_Mode_Frequency_Response_5dB/10dB_Hz로 섹션 이동 및 개명). |
| v1.1 | 사용자 지침("설치 조건 등 매뉴얼이 제공하는 모든 데이터 파싱") 반영 — K1/PANTHER 투입으로 신설된 Compliance_Standards, WEEE_Marking(GSL 자체 OM에 WEEE-Reg-Nr까지 명시되어 있어 실값 확보), Safety_Factor, Max_Wind_Load 양방향 동기화 반영. |
| v1.2 | 사용자 정책 확장(2026-07-16) 반영 — PA_COM_Pinout_AB/CD/EF/GH 완전 삭제(L-Acoustics 커넥터 고유 명칭, GSL은 자기 자신의 NLT4_Pinout_*을 이미 보유). K1/K2/PANTHER 투입으로 신설된 Frequency_Response_3dB/6dB_Hz, RMS_Power_Handling_LF/MF/HF, Width/Height/Depth_mm, AES75_Max_Linear_SPL(단일 통합 Key) null 반영. Frequency_Response_5dB_Standard_Hz -> Frequency_Response_5dB_Hz 개명. |
| v1.3 | Kiva II/L2(신규 제품) 투입으로 신설된 6개 Key(LC_Transducer, LC_Acoustical_Load, LC_Nominal_Impedance, Nominal_Impedance_Overall, RMS_Power_Handling_Overall, Max_SPL_Single_Module)를 이 제품에 비적용 null로 동기화 반영. |
| v1.5 | LC_Transducer/LC_Acoustical_Load/LC_Nominal_Impedance 삭제(사용자 피드백 2026-07-17) — LC는 L2 라인 고유의 물리적 설계 요소이지 업계 표준 대역 구분이 아니므로 v1.3의 범용 동기화 판단을 정정(SKILL v1.16). |
| v1.4 | Null Report 전수 감사(2026-07-17)에서 두 가지 오류 발견 및 수정 — (1) 표에 이미 null로 존재하던 LF_Nominal_Impedance가 미확인/비적용 어느 목록에도 누락되어 있던 것을 발견, MF/HF_Nominal_Impedance와 동일 사유로 비적용 목록에 추가. (2) 총계 줄의 미확인/비적용 숫자가 각 목록 자체의 항목 수와 불일치하던 것을 정정, 총계를 28건(20+8)으로 재계산. 데이터 자체(어느 Key가 null인지)는 LF_Nominal_Impedance의 분류 정정 외에는 변경 없음. |
| v1.6 | delay_defaults 표의 컬럼명 `K1_Delay_ms`를 `Primary_Element_Delay_ms`로 전면 개명(SKILL v1.18) — 값 변경 없음(사용자 지적 2026-07-17). |
| v1.7 | Nominal_Directivity_Horizontal_deg에 저음역 카디오이드 수렴 특성 추가(사용자 지적 2026-07-17 — "CS1과 GSL 등에 자체 카디오이드 내장에 대한 key나 데이터가 없는 것 같다") — OM Chapter 2.4 "Dispersion characteristics" p.9 원문("merging into a cardioid dispersion down to the lowest frequency")을 재조사로 발견, Value에 병기. |
| v1.8 | Cardioid_Capability 전용 Key 신설(Built-in, TaskList #39 최종 동기화 라운드) — v1.7의 각주 정보를 전용 Key로 격상. Product_Series/Product_Type 신규 Key 적용(사용자 지시 2026-07-17) — Series="SL-Series"(OM 본문 "www.sl-series.com"/"d&b SL-Series loudspeakers" 등 복수 명시로 확정, 사용자의 "아마 SL 시리즈일 것" 추정을 원문 검증), Type="Line array loudspeaker"(OM "Product description" 챕터). Width_mm/Height_mm/Depth_mm/Dimensions_Raw 재조사 완료(사용자 지적 2026-07-18) — 이전 버전은 "치수 도면이 그래픽 전용이라 렌더링 도구 미설치로 확인 불가"로 미확인 처리했었으나, PowerShell+Windows.Data.Pdf 렌더링 기법(pdftoppm 불필요)으로 OM p.11 도면을 직접 확인해 Width=1300mm/Height=391mm/Depth=627mm 확보(GSL8/GSL12 공용 도면). Null Report 20건(미확인)→16건으로 감소. |
| v1.8 to v1.9 | (양방향 동기화, Minor) KSL8/KSL12 신규 투입 과정에서 `dbaudio-rigging-manual-gsl-ksl-1.16-en.pdf`(GSL/KSL 공용 Rigging manual) 신규 확보 — v1.0~v1.8 작성 시점에는 이 문서가 미제공되어 mechanical_safety 섹션 전체가 미확인이었으나, 이번에 실값 확보: Maximum_Limit 3개 조건(10대/800kg 무조건 안전, 24대/2000kg SWL ArrayCalc 검증 필요, SUB 컬럼 14대), Max_Wind_Load(6/8 Beaufort). Safety_Factor는 여전히 명시적 비율 수치가 원문에 없어 미확인 유지. Null Report 총계는 24건으로 동일(구성 항목만 재분배). |
