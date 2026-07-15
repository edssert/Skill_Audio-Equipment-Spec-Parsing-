# LA12X — Master Spec Schema

> Schema_Version: 1.0 (Phase 1 baseline)
> Generated: 2026-07-15 | Parsing engine: Ultimate Audio Data Parsing Skill (draft)

## _meta

| Key | Value |
|---|---|
| Manufacturer | L-Acoustics |
| Model | LA12X |
| Product_Category | Amplified_Controller (4-ch Class D amplifier + DSP) |
| Form_Factor | 19" rack, 2U |

### Source Registry

| Source_ID | Document | Version / Date |
|---|---|---|
| OM | Owner's Manual (EN) | v10.1 / 2023-08-31 |
| SPS | Spec Sheet PDF (EN) | 2.5 / 2025-08 |
| AE | Architects & Engineers Spec (docx) | undated |
| WEB-L | Website — List View | current |
| WEB-O | Website — Overview | current |
| WEB-F | Website — Full Spec | current |

**Status legend** — `verified`: 2개 이상 소스 일치 · `single`: 단일 소스 · `CONFLICT`: 소스 간 값 불일치(→ 하단 Conflict Log 참조)

---

## amplification

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| Channel_Count_In | 4 | ch | — | OM, SPS, AE, WEB-L/O/F | verified |
| Channel_Count_Out | 4 | ch | — | OM, SPS, AE, WEB-L/O/F | verified |
| Amplification_Class | Class D (high efficiency) | — | — | OM, SPS, AE, WEB-F | verified |
| Rated_Power_Per_Ch_2R7_W | 3300 | W (RMS) | CEA-2006/490A, sine burst 1 kHz, 20 ms, THD < 1%, all ch driven, 2.7 Ω | OM, SPS, AE, WEB-L/O/F | verified¹ |
| Rated_Power_Per_Ch_4R_W | 2600 | W (RMS) | 동일 조건, 4 Ω | OM, SPS, AE, WEB-O/F | verified¹ |
| Rated_Power_Per_Ch_8R_W | 1400 | W (RMS) | 동일 조건, 8 Ω | OM, SPS, AE, WEB-O/F | verified¹ |
| Total_Power_Capability_W | 12000 | W | SMPS 총 공급 능력 (마케팅 표기, "record hold times") | OM, SPS | verified |
| Max_Output_Voltage_Peak_V | 157 | V (peak) | — | AE | single |
| Amplification_Gain_dB | 32 | dB | — | OM, AE | verified |
| Output_Delay_Range_ms | 0 – 1000 | ms | 채널별, 총 딜레이(그룹 포함) 1000 ms 상한 | OM, SPS, AE, WEB-F | verified |

¹ 측정 버스트 길이 충돌 있음 → Conflict Log C-1

## power_supply

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| PSU_Type | Universal SMPS + DSP-controlled PFC | — | — | OM, SPS, AE, WEB-L/O/F | verified |
| Mains_Voltage_Range_V | 100 – 240 (±10%) | V AC | — | OM, SPS, AE, WEB-F | verified |
| Mains_Frequency_Range_Hz | 50 – 60 | Hz | — | OM, SPS, AE | verified |
| Nominal_Current_100_120V_A | 30 | A | — | OM, SPS | verified |
| Nominal_Current_200_240V_A | 16 | A | OM 안전 섹션은 220–240 V, 스펙 섹션은 200–240 V로 표기 | OM, SPS | verified² |
| Power_Factor | > 0.9 | — | Standby(전 전압) 및 230 V Idle 제외 | OM | single |
| Power_Consumption_Idle_W | 141 | W | 230/120/100 V 공통 | OM | single |
| Power_Consumption_Standby_W | 10 | W | 230/120/100 V 공통 | OM | single |
| Current_Draw_1_3_Power_4R_A | 19 | A | 230 V, 4 Ω, 전 채널, 1/3 출력(-5 dB, 압축 음원/핑크노이즈 클립 구동 가정) | OM | single |
| Current_Draw_1_8_Power_4R_A | 8.1 | A | 230 V, 4 Ω, 전 채널, 1/8 출력(-9 dB, IEC 표준 정격, 9 dB 헤드룸) | OM | single |
| Mains_Connector | powerCON 32 A | — | — | OM, SPS | verified |
| Required_Breaker_100_120V | 30 A (Schneider Square D 30A QO / Mitsubishi CP30-BA-M 동급) | — | 상별 독립 동작 필수(기계적 연동 금지) | OM | single |
| Required_Breaker_220_240V | 16 A, Type C | — | 상동 | OM | single |

² 전압 대역 표기 불일치 → Conflict Log C-2

## audio_performance

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| Frequency_Response_Hz | 20 – 20000 | Hz | ±0.1 dB @ 8 Ω 60 W 및 @ 4 Ω 120 W | OM, SPS, AE | verified |
| THD_N_8R_pct | < 0.05 | % | 20 Hz – 10 kHz, 8 Ω, 60 W | OM, SPS, AE | verified |
| THD_N_4R_pct | < 0.1 | % | 20 Hz – 10 kHz, 4 Ω, 120 W | OM | single |
| Output_Dynamic_Range_dB | > 114 | dB | 20 Hz – 20 kHz, 8 Ω, A-weighted (SPS: digital input) | OM, SPS, AE | verified |
| Noise_Level_dBV | < -75 | dBV | 20 Hz – 20 kHz, 8 Ω, A-weighted | OM, SPS | CONFLICT → C-3 |
| Channel_Separation_dB | > 85 | dB | 1 kHz, 3 × 120 W, 4 Ω | OM, AE | verified |
| Damping_Factor | > 400 | — | ≤ 1 kHz, 8 Ω | OM | single |

## dsp

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| DSP_Processor | 2 × SHARC 32-bit floating point | — | — | OM, SPS, AE, WEB-F | verified |
| DSP_Sampling_Rate_kHz | 96 | kHz | 내부 고정 클럭(외부 동기 모드 없음) | OM, SPS, AE, WEB-F | verified |
| Routing_Matrix | 4 × 4 routing + summation | — | 입력 선택: A, B, A+B, A-B, C, D, C+D, C-D, A+B+C+D | OM, SPS, AE, WEB-F | verified |
| EQ_Filters_Per_Output | 8 IIR + 4 FIR (linear phase) | — | Array Morphing, Air Absorption Compensation 포함 | SPS, WEB-F | verified |
| Speaker_Protection | L-DRIVE (excursion + temperature + over-voltage) | — | 실시간+RMS 이중 감시, 파워 레귤레이터로 동작 | OM, SPS, AE, WEB-F | verified |
| Preset_Memory_User | 10 | slots | 메모리 001–010 (read/write) | OM, AE | verified |
| Preset_Memory_Factory | 189 | slots | 메모리 011–199 (read only), 펌웨어 업데이트 시 자동 설치 | OM | single |

## latency

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| Latency_Standard_ms | 3.84 | ms | Analog/AES-EBU 입력, 입력 Fs 무관 | OM, SPS(웹반영), AE, WEB-F | verified |
| Latency_Low_Mode_ms | 0.84 | ms | Analog/AES-EBU 입력, 입력 Fs 무관 | OM, WEB-F | CONFLICT → C-4 |
| AVB_Max_Network_Latency_ms | 2 | ms | Class A 스트림 | OM, AE | verified |

## input_analog

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| Analog_Input_Channels | 4 | ch | XLR3F, balanced, ESD protected | OM, SPS, AE, WEB-F | verified |
| Input_Impedance_kR | 22 | kΩ | balanced, 병렬 다중 연결 허용 | OM, AE | verified |
| Max_Input_Level_dBu | 22 | dBu | balanced, THD 1% (0 dBFS = +22 dBu) | OM, AE | verified |
| ADC_Architecture | 4 cascaded 24-bit @ 96 kHz | — | encoding dynamic range 130 dB | SPS, AE, OM(스펙 섹션) | verified³ |
| Analog_Link_Type | passive parallel (XLR3M × 4) | — | — | OM, AE | verified |

³ OM 본문(기술 설명)은 "two cascaded"로 기재 — 내부 불일치 → Conflict Log C-5

## input_digital

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| Digital_Input_Channels | 4 | ch | 2 × AES/EBU(AES3) 포트, 페어 전송 | OM, SPS, AE, WEB-F | verified |
| Digital_Standard | AES/EBU (AES3) | — | AE 문서만 "or S/PDIF" 추가 표기 | OM, SPS, WEB-F | CONFLICT → C-6 |
| Supported_Fs_kHz | 44.1 / 48 / 88.2 / 96 / 176.4 / 192 | kHz | SRC 입력 허용 범위 | OM, SPS, AE, WEB-F | verified |
| Supported_Word_Length_bit | 16 / 18 / 20 / 24 | bit | AE는 "16 to 24"로 축약 표기 | OM, AE | verified |
| SRC_Output_Format | 24-bit / 96 kHz | — | 내부 클럭 기준 리샘플, 전파 지연 일정 | OM, AE | verified |
| SRC_Dynamic_Range_dB | 140 | dB | — | OM, AE | verified |
| SRC_THD_N_dBFS | < -120 | dBFS | 강한 입력 지터 감쇠 | OM, AE | verified |
| Digital_Input_Gain_Range_dB | -12 – +12 | dB | 0.1 dB step (AES/EBU & AVB 공용 게인) | OM, AE, WEB-F(SRC 언급) | verified |
| Digital_Link_Type | electronically buffered + failsafe relay (XLR3M × 2) | — | 전원 상실 시 릴레이로 IN–LINK 패시브 연결 유지 | OM, AE | verified |
| Max_AES_Cable_Length_m | 300 | m | 단일 케이블, Fs 48 kHz, Belden 1696A / Klotz OT234H 기준 | OM | single |

## input_avb

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| AVB_Certification | MILAN™ / Avnu™ certified (Bridge + Listener) | — | — | OM, SPS, AE, WEB-L/O | verified |
| AVB_Channels | 4 | ch | 최대 8ch 스트림 1개에서 추출, 스트림 매핑 가능 | OM, SPS, AE, WEB-F | verified |
| AVB_Stream_Count | 1 (redundancy 모드 시 2) | streams | Class A | OM, AE | verified |
| AVB_Formats | AAF PCM32, IEC 61883-6 AM824 | — | 48 kHz 또는 96 kHz (48k 입력 시 96k 업샘플) | OM, AE | verified |
| AVB_Standards | IEEE 802.1BA-2011 / 1722-2016 / 1722.1-2013 | — | — | OM, AE(802.1BA) | verified |
| AVB_Bridge_Forwarded_Streams | ≤ 150 | streams | normal 모드 | OM | single |
| Redundancy_Type | Milan-AVB seamless (Primary/Secondary 자동 절체·복귀) | — | redundancy 모드: star topology 필수, 포트 1=Primary/포트 2=Secondary | OM, SPS, WEB-O | verified |
| Fallback_Modes | AVB→XLR, AES(AB)→XLR(CD) | — | 절체 조건: no clock, loss of lock, CRC error, bipolar encoding error, data slip / 복귀는 수동 | OM, SPS, AE | verified |
| Fallback_Behavior | constant delay + constant level | — | 입력 Fs 무관, AES/EBU & AVB 게인으로 레벨 정렬 | OM, SPS | verified |

## connectivity

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| Input_Connectors | 4 × XLR3F (2쌍 analog/AES3 전환) + 4 × XLR3M link | — | IEC 60268-12 결선 | OM, SPS, AE, WEB-F | verified |
| XLR_Pin_Polarity | pin 1 = shield, pin 2 = + (hot), pin 3 = − (cold) | — | 텍스트 표로 확인(이미지 분석 불필요) | OM | single |
| Speaker_Connectors | 2 × speakON 4P + 1 × CA-COM 8P | — | — | OM, SPS, AE, WEB-F | verified |
| SpeakON_Left_Pinout | 1+/1− = Out1 ± , 2+/2− = Out2 ± | — | 극성 텍스트 표 확인 | OM | single |
| SpeakON_Right_Pinout | 1+/1− = Out3 ± , 2+/2− = Out4 ± | — | 상동 | OM | single |
| CACOM_Pinout | A/B = Out1 ± , C/D = Out2 ± , E/F = Out3 ± , G/H = Out4 ± | — | 상동 | OM | single |
| Network_Connectors | 2 × etherCON RJ45, 1 Gb/s | — | AVB-capable, normal 모드 시 내부 AVB 스위치로 데이지체인 | OM, SPS, AE, WEB-F | verified |

## control_monitoring

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| Remote_Software | LA Network Manager (Win/Mac) | — | L-NET(L-COM PROTOCOL, TCP/IPv4), 최대 253대 | OM, SPS, AE, WEB-F | verified |
| Network_Topologies | daisy-chain / star / hybrid | — | redundancy 모드에서는 star만 | OM, SPS, AE | verified |
| Third_Party_Control | Q-SYS, Crestron, Extron, SNMP, Control4, Savant, HTTP API | — | 소스별 목록 상이 — 합집합 기재(→ C-7 참고) | OM, SPS, AE, WEB-O/F | verified |
| Front_Panel | 2×24자 LCD, 로터리 엔코더, power/mute 키, 상태·미터 LED | — | — | OM, SPS, AE, WEB-F | verified |
| Settings_Protection | PIN(4자리) / lock, LA NWM에서 설정 | — | — | OM | single |

## operating_conditions

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| Operating_Temp_Range_C | 0 – 50 (채택) / OM: -5 – 50 | °C | → Conflict Log C-8 | OM vs SPS·AE·WEB-F | CONFLICT |
| Cooling | temperature-controlled fans, front→rear airflow | — | AE: 팬 3개 | OM, SPS, AE | verified |
| Fan_Count | 3 | ea | — | AE | single |
| Fan_Noise_Min_dBA | < 34 | dBA | free field, 1 m, 최저 속도 | OM | single |
| Fan_Noise_Max_dBA | < 62 | dBA | free field, 1 m, 최고 속도 | OM | single |
| EMC_Class | residential (Class B) | — | — | OM | single |

## physical

| Key | Value | Unit | Measurement_Conditions | Sources | Status |
|---|---|---|---|---|---|
| Width_mm | 483 | mm | 19 in | OM, SPS, AE | verified |
| Height_mm | 88 | mm | 2U / 3.5 in | OM, SPS, AE | verified |
| Depth_mm | 419.1 (섀시) / 454.7 (핸들 포함) / 534.3 (리어 브래킷 포함 최대) | mm | AE는 455로 반올림 표기 | OM, SPS, AE | verified |
| Weight_kg | 14.5 | kg | 32 lb (net) | OM, SPS, AE, WEB-F | verified |
| Protection_Rating | IP20 | — | OM/AE는 IP2x로 표기(IP20이 더 구체적, 모순 아님) | OM, AE, WEB-F | verified |
| Finish | black | — | — | OM, AE | verified |

## protection_summary

| Key | Value | Sources | Status |
|---|---|---|---|
| Protection_Mains_PSU | over/under voltage, over temperature, overcurrent, inrush current, fuse protect | OM, SPS, WEB-F | verified |
| Protection_Outputs | over current, DC, short circuit, rail over/under voltage, over temperature, HF energy(>25 kHz) 감지 | OM, WEB-F | verified |
| Protection_Transducer | L-DRIVE: excursion, temperature, over-voltage | OM, SPS, WEB-F | verified |

---

## Conflict Log

| ID | Key | 소스별 값 | 채택 값 / 근거 |
|---|---|---|---|
| C-1 | 출력 측정 버스트 길이 | OM·SPS: sine burst **20 ms** (CEA-2006/490A) / AE: **200 ms** ("no limiter") | **20 ms** 채택. CEA-2006/490A 표준 명시 소스 2개 우선. AE의 200 ms는 오기 또는 별도 조건(무리미터 롱버스트) 가능성 — 제조사 확인 권장 |
| C-2 | 16 A 적용 전압 대역 | OM 안전: 220–240 V / OM 스펙·SPS: 200–240 V | **200–240 V** 채택(스펙 섹션 + SPS 일치). 안전 섹션은 지역 규격 서술로 판단 |
| C-3 | Noise_Level_dBV | OM(v10.0에서 갱신)·SPS: **< -75** / AE: **< -72** | **< -75 dBV** 채택. OM 개정 이력에 "noise level 갱신" 명시 → AE는 구버전 수치로 판단 |
| C-4 | Latency_Low_Mode_ms | OM·WEB-F: **0.84** / AE: **0.76** | **0.84 ms** 채택(최신 OM + 웹 일치, 2:1). AE는 구버전 수치 추정 |
| C-5 | ADC 캐스케이드 수 | OM 본문: two cascaded / OM 스펙·SPS·AE: **4 cascaded** | **4** 채택(3개 소스 + OM 스펙 섹션). OM 본문은 채널 페어 기준 서술로 추정되는 내부 불일치 |
| C-6 | 디지털 입력 규격 | OM·SPS·WEB-F: AES/EBU(AES3)만 / AE: "AES3 **or S/PDIF**" | **AES3만** 공식 채택. S/PDIF는 AE 단독 표기(전기적 호환 가능성 서술로 추정) — 스키마에 `SPDIF_Support: unconfirmed` 로 별도 유지하지 않고 Conflict Log에만 기록 |
| C-7 | 서드파티 제어 목록 | OM: Q-SYS·Crestron·Extron·SNMP / SPS·WEB: +Control4·Savant·HTTP API | **합집합** 채택(누락이 아닌 문서 세대 차이). 최신 소스(SPS 2.5, 웹)가 상위 집합 |
| C-8 | 동작 온도 하한 | OM: **-5 °C** / SPS·AE·WEB-F: **0 °C** | **0 °C** 채택(3:1 다수결 + 최신 SPS 2.5). 단, OM이 최심층 문서이므로 보수적 운용 시 0 °C 하한 권장이라는 점에서도 0 °C가 안전 |

## Null Report

이번 소스 집합에서 정의되지 않아 `null` 처리된 항목: 없음(모든 스키마 키가 최소 1개 소스에서 확인됨).
Phase 3–4에서 타 브랜드/카테고리 키 추가 시 본 파일에 `null` 값으로 소급 반영 예정.
