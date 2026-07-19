# L-Acoustics Preset Guide — owner's manual v.29.0

원본: `Preset_Guide_OM_EN_29.0.pdf`(`speakers/LA/References/`), 배포일 May 2026, 124페이지+. 이 문서는 개별 제품 마스터 스키마가 아니라 **브랜드 공용 참고자료**를 마크다운으로 옮긴 것 — 여러 제품의 `preset_guide_and_matching`/`delay_defaults`/`amplification_requirements` 섹션 값을 채울 때 1차 근거 문서로 사용한다. 원문 레이아웃(표 포함)을 그대로 마크다운 표로 옮기며, 개별 제품 스키마의 표 순수성 규칙은 이 문서에 적용하지 않는다.

**진행 상태(2026-07-19)**: p.1-124 전체 완료. 원문 표는 압축 텍스트가 아니라 실제 마크다운 표로, 원문이 제품군별로 표를 분리한 경우 마크다운도 동일하게 분리해 옮겼다(둘 다 초안 작성 중 사용자 지적으로 정정된 규칙).

## 1. Introduction (p.5)

L-Acoustics 앰프 컨트롤러는 온보드 펌웨어+프리셋 라이브러리와 함께 출고된다. 온보드 라이브러리 프리셋은 컨트롤러 전면 패널 또는 LA Network Manager(원격 제어/모니터링 소프트웨어)에서 로드 가능. 펌웨어 업데이트는 LA Network Manager로만 수행하며, 최신 프리셋 라이브러리는 펌웨어와 함께 자동 설치됨.

이 버전(v29.0)은 LA2Xi/LA4/LA4X/LA8/LA12X 프리셋 라이브러리 v7.17, LA7.16(i) 인클로저 라이브러리를 서술.

## 2. Revision history (p.6-7, 전체)

이 프로젝트가 이미 파싱한 제품과 관련된 항목만 발췌(전체 이력은 원문 참조):

| Version | 날짜 | 주요 변경 |
|---|---|---|
| 1.0 | Mar 2013 | 최초 버전 |
| 4.0 | Dec 2013 | K2 시스템 추가, LA4X 추가 |
| 6.0 | Oct 2015 | X 시리즈 추가 |
| 7.0 | Feb 2016 | KS28 추가 |
| 7.1 | May 2016 | LA12X 추가 |
| 8.0/8.1 | Oct 2016 | Kiva II 시스템 추가, SB15m 프리셋 출력게인 조정(헤드룸 개선) |
| 9.0 | Jun 2017 | Syva 시스템 추가 |
| 10.0 | Aug 2018 | [KARADOWNK2] 정보 추가 |
| 11.0 | Feb 2019 | X4i 추가 |
| 12.0 | Jun 2019 | A15 Wide/Focus 시스템 추가 |
| 13.0 | Oct 2019 | A15i Wide/Focus, A10(i) Wide/Focus 추가, Cardioid eXtended 프리셋 정보 추가 |
| 14.0 | Apr 2020 | Kara II 시스템 추가 |
| 15.0 | Oct 2020 | LA2Xi 추가, K3 시스템 추가 |
| 16.0 | Mar 2021 | Kara IIi 시스템 추가 |
| 17.0 | Jul 2021 | K3i 시스템 추가 |
| 18.0 | Feb 2022 | X시리즈+서브우퍼 카디오이드 구성 사전정렬딜레이 추가, [A10_MO]/[A15_MO]/[5XT_MO]/[X4_MO] 프리셋 추가, SB10i 추가 |
| 19.0 | Jun 2022 | LA7.16i 인클로저 드라이브 용량 추가, [X4_MO]+Syva Sub/SB10i 딜레이 업데이트 |
| 20.0 | Nov 2022 | SB6i 추가, [X4_60]/[KARA II_MO] 프리셋 추가 |
| 21.0 | Mar 2023 | Soka 추가, [SB10_60] 추가, LA7.16i layout library 추가 |
| 22.0 | Jun 2023 | LA7.16 layout library+드라이브용량 추가, L2/L2D 시스템 추가, [KARAIIDOWNxx 70]/[KARAIIDOWNxx 90] 프리셋 추가 |
| 23.0 | Feb 2024 | X8i/X6i 추가, [K3r1 xxx] 프리셋 추가(K3), LA12X 라이브러리에 [KS28 L2_C]/[KS28 L2_Cx] 추가, X8+SB10i/Syva Sub 딜레이 추가, Kara II 모니터+SB18 딜레이 추가, L2/L2D 딜레이값 갱신 |
| 24.0 | May 2024 | [SYVA SUB SYVA] 프리셋 추가, [SYVA]+[SYVA SUB_100] 사전정렬딜레이 추가 |
| 25.0 | Oct 2024 | [K3r1 xxx]→[K3 xxx]로 개명, 구버전 [K3 xxx] 제거, [SYVA SUB_60] 프리셋 추가(Soka/X6i/X8i 호환) |
| 26.0 | Mar 2025 | Enclosure maximum SPL per amplified controller(p.124) 추가 |
| 27.0 | Jun 2025 | LA1.16i 인클로저 드라이브 용량+최대SPL 추가, L2/L2D+KS28 사전정렬딜레이 업데이트 |
| 28.0 | Jan 2026 | Preset design(p.8)에 K1-SB Noise Control(NC) 구성 추가, [K1SB_100_NC] 프리셋 추가(K1/K2 참조), 사전정렬딜레이 추가, K1-SB [K1SB_100_NC] 사용시 최대SPL 추가 |
| 29.0 | May 2026 | CS1 추가 |

## 3. Preset design (p.8-10)

### 3.1 Gain structure

L-Acoustics 팩토리 프리셋 게인은 기준 핑크노이즈 신호로 캘리브레이션됨. 기준 입력 레벨: **0 dBu**(아날로그) 또는 **-22 dBFS**(디지털). 이 레벨로 구동 시 대부분의 L-Acoustics 인클로저는 8dB 헤드룸을 가지나, 소형 포맷(MTD108A, X4i, 5XT, X8, Kiva, Kilo, SB10i, SB6i, Soka)은 4dB 헤드룸. 동일 프로그램 레벨에서 서로 다른 포맷을 병용할 때는 소형 포맷에 -4dB 게인 조정을 적용해 균형을 맞춘다.

**SB15m 헤드룸**: [SB15_100]/[SB15_100_C]는 프리셋 라이브러리 v5.6(.5)부터 8dB 헤드룸. [SB15_100_Cx]는 8dB 헤드룸. 구버전 프리셋 및 [KIVA_SB15]는 4dB 헤드룸.

**K1-SB/KS28/SB28/SB18/SB218/SB118 헤드룸**: 프리셋 라이브러리 6.0에서 이들 서브우퍼 프리셋 출력게인이 조정되어 8dB 헤드룸을 확보(서브우퍼-풀레인지 간 L-DRIVE 활동 정렬 목적). 6.0 이전 버전 프리셋을 쓰는 세션 파일 게인 조정값: [SB28_60], [SB218_60]: +4dB / [KS28_60], [SB_28_100], [SB18_60], [SB18_100], [SB218_100], [SB118_60], [SB118_100]: +3dB / [KS28_100]: +2dB / [K1SB_60]: +1dB.

### 3.2 Electro-acoustic coupling

L-Acoustics 팩토리 프리셋은 특정 배치 패턴과 결합해 코히어런트한 음원을 보장한다 — 액티브 인클로저 내부 결합, 또는 여러 인클로저 결합 시 외부 결합. 채널 세트(channel set)는 여러 출력채널의 라우팅/게인/딜레이 설정을 하나로 묶어 결합을 유지하는 개념(예: `[LF HF]`=2-way 인클로저용, `[SR SB SB SB]`=카디오이드 서브우퍼용).

### 3.3 Frequency response contour

- **X Series(코액시얼)**: standard 프리셋(대부분 용도) + `_MO` 프리셋(스테이지 모니터 전용)
- **레거시 코액시얼(XT/MTD Series)**: `_FR`(대부분 FOH), `_FI`(스포큰워드/클래식/재즈/필 시스템), `_MO`(하프스페이스, 모니터)
- **A Series/Kara II(WST)**: main 프리셋(FOH), `_FI`(필 시스템), `_MO`(스테이지 모니터)
- **기타 WST 시스템**: main(FOH) + `_FI`(일부 시스템만, 필용)
- **최구형 WST 시스템**: `_HI`/`_LO` 프리셋 구조 계승, Array Morphing 도구(zoom factor, LF contour)로 음색 조정 가능

### 3.4 LF polar pattern (L2/L2D, CS1)

L2/L2D는 측면 4개의 LC(Low frequency Cardioid) 드라이버로 표준 카디오이드(`[L2 xxx]`/`[L2D xxx]`) 또는 슈퍼카디오이드(`[L2 xxx_S]`/`[L2D xxx_S]`) 패턴 선택 가능 — 시스템 전체에 동일 LF 극성 패턴 적용 필요.

CS1은 측면 2개의 SC(Cardioid Subwoofer) 드라이버로 표준(`[CS1_xx]`) 또는 슈퍼카디오이드(`[CS1_xx_S]`) 패턴 선택 가능 — 동일 원칙.

### 3.5 Standard/Cardioid C/Cardioid Cx 서브우퍼 구성

- **Standard**: 전 서브우퍼가 전방을 향한 준-무지향성 클러스터, `[xxxx_60]` 프리셋. 전면 SPL/시간축 정합 최우선, 후방 감쇠 불필요 용도.
- **Cardioid C**: 2/3/4대 그룹당 1대를 반전 배치, `[xxxx_60_C]` 프리셋. 후방 감쇠와 전면 SPL/시간정합을 절충.
- **Cardioid Cx(eXtended)**: 2/3/4대 그룹당 1대를 반전 배치, `[xxxx_60_Cx]` 프리셋. 광대역 후방 감쇠 우선, 전면 SPL/시간정합은 제한적 절충.

### 3.6 K1-SB Noise Control(NC) 구성

K1 또는 K2 어레이 뒤에 K1-SB 어레이를 배치하고 `[xxxx_100_NC]` 프리셋을 사용하는 카디오이드 구성 — 광대역 후방 감쇠, 전면 SPL/시간정합은 제한적 절충 용도.

## 4. Onboard preset libraries (p.11-45)

### 4.1 Amplified controllers maximum output power (p.11)

CEA-2006/490A 1kHz 테스트, 전 채널 구동 기준.

| Type | 16Ω load | 8Ω load | 4Ω load | 2.7Ω load |
|---|---|---|---|---|
| LA12X | 4x700 W | 4x1400 W | 4x2600 W | 4x3300 W |
| LA8 | 4x550 W | 4x1100 W | 4x1800 W | 4x1800 W |
| LA7.16(i) | 16x580 W | 16x920 W | 16x1000 W | — |
| LA4X | 4x500 W | 4x1000 W | 4x1000 W | — |
| LA4 | 4x400 W | 4x800 W | 4x1000 W | — |
| LA2Xi SE | 4x190 W | 4x360 W | 4x640 W | — |
| LA2Xi BTL | 2x710 W | 2x1260 W | — | — |
| LA2Xi PBTL | — | — | 1x2550 W | — |
| LA1.16i SE | 16x40 W | 16x80 W | 16x120 W | — |
| LA1.16i BTL | 8x160 W | 8x230 W | — | — |

### 4.2 LA2Xi preset library v7.17 (p.11-14)

메모리 위치 011-093(001-010은 사용자 저장용).

**KARA_II**

| # | Preset | Description |
|---|---|---|
| 011 | [KARA II 70] | Kara II(i), full range, 70° adjustable fins settings |
| 012 | [KARA II 90] | Kara II(i), full range, 90° adjustable fins settings |
| 013 | [KARA II 110] | Kara II(i), full range, 110° adjustable fins settings |
| 014 | [KARA II_FI] | Kara II(i), HPF=100 Hz, fill |
| 015 | [KARA II_MO] | Kara II(i), full range, monitor, low latency |
| 016 | [KARAIIDOWNK3] | Kara II(i), optimized delay for K3(i) downfill |

**KARA**

| # | Preset | Description |
|---|---|---|
| 017 | [KARA] | Kara(i), full range, FOH |
| 018 | [KARA_FI] | Kara(i), HPF=100 Hz, fill |
| 019 | [KARADOWNK3] | Kara, HPF=100 Hz, optimized delay for K3 downfill |

**KIVA_II**

| # | Preset | Description |
|---|---|---|
| 020 | [KIVA II] | Kiva II, full range, FOH |
| 021 | [KIVA II_FI] | Kiva II, full range, fill |

**A15**

| # | Preset | Description |
|---|---|---|
| 022 | [A15] | A15(i) Wide or A15(i) Focus, full range |
| 023 | [A15_FI] | A15(i) Wide or A15(i) Focus, full range, fill |
| 024 | [A15_MO] | A15(i) Wide or A15(i) Focus, full range, monitor, low latency |

**A10**

| # | Preset | Description |
|---|---|---|
| 025 | [A10] | A10(i) Wide or A10(i) Focus, full range |
| 026 | [A10_FI] | A10(i) Wide or A10(i) Focus, full range, fill |
| 027 | [A10_MO] | A10(i) Wide or A10(i) Focus, full range, monitor, low latency |

**ARCS_WF**

| # | Preset | Description |
|---|---|---|
| 028 | [ARCS_WIFO] | ARCS Wide or ARCS Focus, full range, FOH |
| 029 | [ARCS_WIFO_FI] | ARCS Wide or ARCS Focus, full range, fill |

**KS28**

| # | Preset | Description |
|---|---|---|
| 030 | [KS28_60] | KS28, LPF=60 Hz |
| 031 | [KS28_100] | KS28, LPF=100 Hz |
| 032 | [KS28_60_C] | KS28, LPF=60 Hz, cardioid pattern |
| 033 | [KS28_100_C] | KS28, LPF=100 Hz, cardioid pattern |
| 034 | [KS28_60_Cx] | KS28, LPF=60 Hz, extended cardioid pattern |
| 035 | [KS28_100_Cx] | KS28, LPF=100 Hz, extended cardioid pattern |
| 036 | [KS28 L2] | KS28, optimized for L2(D) |
| 037 | [KS28 L2_C] | KS28, cardioid pattern, optimized for L2(D) |
| 038 | [KS28 L2_Cx] | KS28, extended cardioid pattern, optimized for L2(D) |

**SB28**

| # | Preset | Description |
|---|---|---|
| 039 | [SB28_60] | SB28, LPF=60 Hz |
| 040 | [SB28_100] | SB28, LPF=100 Hz |
| 041 | [SB28_60_C] | SB28, LPF=60 Hz, cardioid pattern |
| 042 | [SB28_100_C] | SB28, LPF=100 Hz, cardioid pattern |
| 043 | [SB28_60_Cx] | SB28, LPF=60 Hz, extended cardioid pattern |
| 044 | [SB28_100_Cx] | SB28, LPF=100 Hz, extended cardioid pattern |

**KS21**

| # | Preset | Description |
|---|---|---|
| 045 | [KS21_60] | KS21(i), LPF=60 Hz |
| 046 | [KS21_100] | KS21(i), LPF=100 Hz |
| 047 | [KS21_60_C] | KS21(i), LPF=60 Hz, cardioid pattern |
| 048 | [KS21_100_C] | KS21(i), LPF=100 Hz, cardioid pattern |
| 049 | [KS21_60_Cx] | KS21(i), LPF=60 Hz, extended cardioid pattern |
| 050 | [KS21_100_Cx] | KS21(i), LPF=100 Hz, extended cardioid pattern |

**SB18**

| # | Preset | Description |
|---|---|---|
| 051 | [SB18_60] | SB18, LPF=60 Hz |
| 052 | [SB18_100] | SB18, LPF=100 Hz |
| 053 | [SB18_60_C] | SB18, LPF=60 Hz, cardioid pattern |
| 054 | [SB18_100_C] | SB18, LPF=100 Hz, cardioid pattern |
| 055 | [SB18_60_Cx] | SB18, LPF=60 Hz, extended cardioid pattern |
| 056 | [SB18_100_Cx] | SB18, LPF=100 Hz, extended cardioid pattern |

**SB15**

| # | Preset | Description |
|---|---|---|
| 057 | [SB15_100] | SB15m, LPF=100 Hz |
| 058 | [SB15_100_C] | SB15m, LPF=100 Hz, cardioid pattern |
| 059 | [SB15_100_Cx] | SB15m, LPF=100 Hz, extended cardioid pattern |

**SB10**

| # | Preset | Description |
|---|---|---|
| 060 | [SB10_60] | SB10i(r), LPF=60 Hz |
| 061 | [SB10_100] | SB10i(r), LPF=100 Hz |
| 062 | [SB10_200] | SB10i(r), LPF=200 Hz |

**SB6**

| # | Preset | Description |
|---|---|---|
| 063 | [SB6_60] | SB6i(r), LPF=60 Hz |
| 064 | [SB6_100] | SB6i(r), LPF=100 Hz |
| 065 | [SB6_200] | SB6i(r), LPF=200 Hz |

**SYVA / SYVA_LOW / SYVA+LOW / SYVA+SUB / SYVA_SUB**

| # | Preset | Description |
|---|---|---|
| 066 | [SYVA] | Syva, full range |
| 067 | [SYVA LOW_100] | Syva Low (separated), LPF=100 Hz |
| 068 | [SYVA LOW SYVA] | Syva & Syva Low (coupled) |
| 069 | [SYVA SUB SYVA] | Syva & Syva Sub (coupled) |
| 070 | [SYVA SUB_60] | Syva Sub, LPF=60 Hz |
| 071 | [SYVA SUB_100] | Syva Sub, LPF=100 Hz |
| 072 | [SYVA SUB_200] | Syva Sub, LPF=200 Hz, optimized for [X4] preset |

**SOKA**

| # | Preset | Description |
|---|---|---|
| 073 | [SOKA] | Soka(r), full range |
| 074 | [SOKA_60] | Soka(r), lower LF limit, max SPL reduced by 6 dB, for on-wall configuration with separated sub |
| 075 | [SOKA_200] | Soka(r) for on-wall configuration with closely coupled sub |

**X15HiQ / X12 / X8 / X8i / X6i / 5XT / X4 / FLAT**

| # | Preset | Description |
|---|---|---|
| 076 | [X15] | X15 HiQ, full range |
| 077 | [X15_MO] | X15 HiQ, full range, monitor, low latency |
| 078 | [X12] | X12, full range |
| 079 | [X12_MO] | X12, full range, monitor, low latency |
| 080 | [X8] | X8, full range |
| 081 | [X8_MO] | X8, full range, monitor, low latency |
| 082 | [X8i] | X8i, full range |
| 083 | [X8i_40] | X8i, lower LF limit, max SPL reduced by 6 dB |
| 084 | [X8i_MO] | X8i, full range, monitor, low latency |
| 085 | [X6i] | X6i, full range |
| 086 | [X6i_50] | X6i, lower LF limit, max SPL reduced by 6 dB |
| 087 | [X6i_MO] | X6i, full range, monitor, low latency |
| 088 | [5XT] | 5XT, full range |
| 089 | [5XT_MO] | 5XT, full range, monitor, low latency |
| 090 | [X4] | X4i(r), full range |
| 091 | [X4_60] | X4i(r), lower LF limit, max SPL reduced by 6 dB, for on-wall configuration with separated sub |
| 092 | [X4_MO] | X4i(r), full range, monitor, low latency |
| 093 | [FLAT_LA2X] | Flat EQ, protection minimizing clipping risks |

### 4.3 LA4 preset library v7.17 (p.15-18)

메모리 위치 011-096(001-010은 사용자 저장용).

**KIVA**

| # | Preset | Description |
|---|---|---|
| 011 | [KIVA] | Kiva, full range, FOH |
| 012 | [KIVA_FI] | Kiva, full range, fill |

**SB15KIVA**

| # | Preset | Description |
|---|---|---|
| 013 | [KIVA_SB15] | Kiva & SB15m, X-OVER=100 Hz, full range, FOH |

**KILOKIVA**

| # | Preset | Description |
|---|---|---|
| 014 | [KIVA_KILO] | Kiva & Kilo, full range, X-OVER=100 Hz, FOH |

**ARCS**

| # | Preset | Description |
|---|---|---|
| 015 | [ARCS_LO] | ARCS, full range, LO contour |
| 016 | [ARCS_LO_60] | ARCS, HPF=60 Hz, LO contour |
| 017 | [ARCS_LO_100] | ARCS, HPF=100 Hz, LO contour |
| 018 | [ARCS_HI] | ARCS, full range, HI contour |
| 019 | [ARCS_HI_60] | ARCS, HPF=60 Hz, HI contour |
| 020 | [ARCS_HI_100] | ARCS, HPF=100 Hz, HI contour |

**ARCS_WF**

| # | Preset | Description |
|---|---|---|
| 021 | [ARCS_WIFO] | ARCS Wide or ARCS Focus, full range, FOH |
| 022 | [ARCS_WIFO_FI] | ARCS Wide or ARCS Focus, full range, fill |

**SB18**

| # | Preset | Description |
|---|---|---|
| 023 | [SB18_60] | SB18, LPF=60 Hz |
| 024 | [SB18_100] | SB18, LPF=100 Hz |
| 025 | [SB18_60_C] | SB18, LPF=60 Hz, cardioid pattern |
| 026 | [SB18_100_C] | SB18, LPF=100 Hz, cardioid pattern |
| 027 | [SB18_60_Cx] | SB18, LPF=60 Hz, extended cardioid pattern |
| 028 | [SB18_100_Cx] | SB18, LPF=100 Hz, extended cardioid pattern |

**SB118**

| # | Preset | Description |
|---|---|---|
| 029 | [SB118_60] | SB118, LPF=60 Hz |
| 030 | [SB118_100] | SB118, LPF=100 Hz |
| 031 | [SB118_60_C] | SB118, LPF=60 Hz, cardioid pattern |
| 032 | [SB118_100_C] | SB118, LPF=100 Hz, cardioid pattern |

**SB15**

| # | Preset | Description |
|---|---|---|
| 033 | [SB15_100] | SB15m, LPF=100 Hz |
| 034 | [SB15_100_C] | SB15m, LPF=100 Hz, cardioid pattern |
| 035 | [SB15_100_Cx] | SB15m, LPF=100 Hz, extended cardioid pattern |

**KILO**

| # | Preset | Description |
|---|---|---|
| 036 | [KILO] | Kilo, LPF=100 Hz |

**12XTA**

| # | Preset | Description |
|---|---|---|
| 037 | [12XTA_FI] | 12XT active, full range, fill |
| 038 | [12XTA_FI_100] | 12XT active, HPF=100 Hz, fill |
| 039 | [12XTA_FR] | 12XT active, full range, FOH |
| 040 | [12XTA_FR_100] | 12XT active, HPF=100 Hz, FOH |
| 041 | [12XTA_MO] | 12XT active, full range, monitor |
| 042 | [12XTA_MO_100] | 12XT active, HPF=100 Hz, monitor |

**12XTP**

| # | Preset | Description |
|---|---|---|
| 043 | [12XTP_FI] | 12XT passive, full range, fill |
| 044 | [12XTP_FI_100] | 12XT passive, HPF=100 Hz, fill |
| 045 | [12XTP_FR] | 12XT passive, full range, FOH |
| 046 | [12XTP_FR_100] | 12XT passive, HPF=100 Hz, FOH |
| 047 | [12XTP_MO] | 12XT passive, full range, monitor |
| 048 | [12XTP_MO_100] | 12XT passive, HPF=100 Hz, monitor |

**8XT**

| # | Preset | Description |
|---|---|---|
| 049 | [8XT_FI] | 8XT, full range, fill |
| 050 | [8XT_FI_100] | 8XT, HPF=100 Hz, fill |
| 051 | [8XT_FR] | 8XT, full range, FOH |
| 052 | [8XT_FR_100] | 8XT, HPF=100 Hz, FOH |
| 053 | [8XT_MO] | 8XT, full range, monitor |
| 054 | [8XT_MO_100] | 8XT, HPF=100 Hz, monitor |

**5XT**

| # | Preset | Description |
|---|---|---|
| 055 | [5XT] | 5XT, full range |
| 056 | [5XT_MO] | 5XT, full range, monitor, low latency |

**X4**

| # | Preset | Description |
|---|---|---|
| 057 | [X4] | X4i(r), full range |
| 058 | [X4_60] | X4i(r), lower LF limit, max SPL reduced by 6 dB, for on-wall configuration with separated sub |
| 059 | [X4_MO] | X4i(r), full range, monitor, low latency |

**115XT**

| # | Preset | Description |
|---|---|---|
| 060 | [115XT_FI] | 115XT, full range, fill |
| 061 | [115XT_FI_100] | 115XT, HPF=100 Hz, fill |
| 062 | [115XT_FR] | 115XT, full range, FOH |
| 063 | [115XT_FR_100] | 115XT, HPF=100 Hz, FOH |
| 064 | [115XT_MO] | 115XT, full range, monitor |
| 065 | [115XT_MO_100] | 115XT, HPF=100 Hz, monitor |

**MTD115bA**

| # | Preset | Description |
|---|---|---|
| 066 | [115bA_FI] | MTD115b active, full range, fill |
| 067 | [115bA_FI_100] | MTD115b active, HPF=100 Hz, fill |
| 068 | [115bA_FR] | MTD115b active, full range, FOH |
| 069 | [115bA_FR_100] | MTD115b active, HPF=100 Hz, FOH |
| 070 | [115bA_MO] | MTD115b active, full range, monitor |
| 071 | [115bA_MO_100] | MTD115b active, HPF=100 Hz, monitor |

**MTD115bP**

| # | Preset | Description |
|---|---|---|
| 072 | [115bP_FI] | MTD115b passive, full range, fill |
| 073 | [115bP_FI_100] | MTD115b passive, HPF=100 Hz, fill |
| 074 | [115bP_FR] | MTD115b passive, full range, FOH |
| 075 | [115bP_FR_100] | MTD115b passive, HPF=100 Hz, FOH |
| 076 | [115bP_MO] | MTD115b passive, full range, monitor |
| 077 | [115bP_MO_100] | MTD115b passive, HPF=100 Hz, monitor |

**112XT**

| # | Preset | Description |
|---|---|---|
| 078 | [112XT_FI] | 112XT, full range, fill |
| 079 | [112XT_FI_100] | 112XT, HPF=100 Hz, fill |
| 080 | [112XT_FR] | 112XT, full range, FOH |
| 081 | [112XT_FR_100] | 112XT, HPF=100 Hz, FOH |
| 082 | [112XT_MO] | 112XT, full range, monitor |
| 083 | [112XT_MO_100] | 112XT, HPF=100 Hz, monitor |

**MTD112b**

| # | Preset | Description |
|---|---|---|
| 084 | [112b_FI] | MTD112b, full range, fill |
| 085 | [112b_FI_100] | MTD112b, HPF=100 Hz, fill |
| 086 | [112b_FR] | MTD112b, full range, FOH |
| 087 | [112b_FR_100] | MTD112b, HPF=100 Hz, FOH |
| 088 | [112b_MO] | MTD112b, full range, monitor |
| 089 | [112b_MO_100] | MTD112b, HPF=100 Hz, monitor |

**MTD108a**

| # | Preset | Description |
|---|---|---|
| 090 | [108a_FI] | MTD108a, full range, fill |
| 091 | [108a_FI_100] | MTD108a, HPF=100 Hz, fill |
| 092 | [108a_FR] | MTD108a, full range, FOH |
| 093 | [108a_FR_100] | MTD108a, HPF=100 Hz, FOH |
| 094 | [108a_MO] | MTD108a, full range, monitor |
| 095 | [108a_MO_100] | MTD108a, HPF=100 Hz, monitor |

**FLAT**

| # | Preset | Description |
|---|---|---|
| 096 | [FLAT_LA4] | Flat EQ, protection minimizing clipping risks |

### 4.4 LA4X preset library v7.17 (p.19-23)

메모리 위치 011-127(001-010 사용자 저장용).

**K2**

| # | Preset | Description |
|---|---|---|
| 011 | [K2 70] | K2, full range, 70° adjustable fins settings |
| 012 | [K2 90] | K2, full range, 90° adjustable fins settings |
| 013 | [K2 110] | K2, full range, 110° adjustable fins settings |

**K3**

| # | Preset | Description |
|---|---|---|
| 014 | [K3 70] | K3(i), full range, 70° adjustable fins settings |
| 015 | [K3 90] | K3(i), full range, 90° adjustable fins settings |
| 016 | [K3 110] | K3(i), full range, 110° adjustable fins settings |

**KUDO**

| # | Preset | Description |
|---|---|---|
| 017 | [KUDO50_25] | Kudo, HPF=25 Hz, 50° K-Louver settings |
| 018 | [KUDO50_40] | Kudo, HPF=40 Hz, 50° K-Louver settings |
| 019 | [KUDO50_60] | Kudo, HPF=60 Hz, 50° K-Louver settings |
| 020 | [KUDO80_25] | Kudo, HPF=25 Hz, 80° K-Louver settings |
| 021 | [KUDO80_40] | Kudo, HPF=40 Hz, 80° K-Louver settings |
| 022 | [KUDO80_60] | Kudo, HPF=60 Hz, 80° K-Louver settings |
| 023 | [KUDO110_25] | Kudo, HPF=25 Hz, 110° K-Louver settings |
| 024 | [KUDO110_40] | Kudo, HPF=40 Hz, 110° K-Louver settings |
| 025 | [KUDO110_60] | Kudo, HPF=60 Hz, 110° K-Louver settings |

**KARA_II**

| # | Preset | Description |
|---|---|---|
| 026 | [KARA II 70] | Kara II(i), full range, 70° adjustable fins settings |
| 027 | [KARA II 90] | Kara II(i), full range, 90° adjustable fins settings |
| 028 | [KARA II 110] | Kara II(i), full range, 110° adjustable fins settings |
| 029 | [KARA II_FI] | Kara II(i), HPF=100 Hz, fill |
| 030 | [KARA II_MO] | Kara II(i), full range, monitor, low latency |
| 031 | [KARAIIDOWNK1] | Kara II, optimized delay for K1 downfill |
| 032 | [KARAIIDOWNK2] | Kara II, optimized delay for K2 downfill |
| 033 | [KARAIIDOWNK3] | Kara II(i), optimized delay for K3(i) downfill |

**KARA**

| # | Preset | Description |
|---|---|---|
| 034 | [KARA] | Kara(i), full range, FOH |
| 035 | [KARA_FI] | Kara(i), HPF=100 Hz, fill |
| 036 | [KARADOWNK1] | Kara, HPF=100 Hz, optimized delay for K1 downfill |
| 037 | [KARADOWNK2] | Kara, HPF=100 Hz, optimized delay for K2 downfill |
| 038 | [KARADOWNK3] | Kara, HPF=100 Hz, optimized delay for K3 downfill |

**KIVA_II**

| # | Preset | Description |
|---|---|---|
| 039 | [KIVA II] | Kiva II, full range, FOH |
| 040 | [KIVA II_FI] | Kiva II, full range, fill |

**KIVA**

| # | Preset | Description |
|---|---|---|
| 041 | [KIVA] | Kiva, full range, FOH |
| 042 | [KIVA_FI] | Kiva, full range, fill |

**SB15KIVA**

| # | Preset | Description |
|---|---|---|
| 043 | [KIVA_SB15] | Kiva & SB15m, X-OVER=100 Hz, full range, FOH |

**KILOKIVA**

| # | Preset | Description |
|---|---|---|
| 044 | [KIVA_KILO] | Kiva & Kilo, full range, X-OVER=100 Hz, FOH |

**ARCS_II**

| # | Preset | Description |
|---|---|---|
| 045 | [ARCS II] | ARCS II, full range |

**A15**

| # | Preset | Description |
|---|---|---|
| 046 | [A15] | A15(i) Wide or A15(i) Focus, full range |
| 047 | [A15_FI] | A15(i) Wide or A15(i) Focus, full range, fill |
| 048 | [A15_MO] | A15(i) Wide or A15(i) Focus, full range, monitor, low latency |

**A10**

| # | Preset | Description |
|---|---|---|
| 049 | [A10] | A10(i) Wide or A10(i) Focus, full range |
| 050 | [A10_FI] | A10(i) Wide or A10(i) Focus, full range, fill |
| 051 | [A10_MO] | A10(i) Wide or A10(i) Focus, full range, monitor, low latency |

**ARCS_WF**

| # | Preset | Description |
|---|---|---|
| 052 | [ARCS_WIFO] | ARCS Wide or ARCS Focus, full range, FOH |
| 053 | [ARCS_WIFO_FI] | ARCS Wide or ARCS Focus, full range, fill |

**KS21**

| # | Preset | Description |
|---|---|---|
| 054 | [KS21_60] | KS21(i), LPF=60 Hz |
| 055 | [KS21_100] | KS21(i), LPF=100 Hz |
| 056 | [KS21_60_C] | KS21(i), LPF=60 Hz, cardioid pattern |
| 057 | [KS21_100_C] | KS21(i), LPF=100 Hz, cardioid pattern |
| 058 | [KS21_60_Cx] | KS21(i), LPF=60 Hz, extended cardioid pattern |
| 059 | [KS21_100_Cx] | KS21(i), LPF=100 Hz, extended cardioid pattern |

**SB18**

| # | Preset | Description |
|---|---|---|
| 060 | [SB18_60] | SB18, LPF=60 Hz |
| 061 | [SB18_100] | SB18, LPF=100 Hz |
| 062 | [SB18_60_C] | SB18, LPF=60 Hz, cardioid pattern |
| 063 | [SB18_100_C] | SB18, LPF=100 Hz, cardioid pattern |
| 064 | [SB18_60_Cx] | SB18, LPF=60 Hz, extended cardioid pattern |
| 065 | [SB18_100_Cx] | SB18, LPF=100 Hz, extended cardioid pattern |

**SB15**

| # | Preset | Description |
|---|---|---|
| 066 | [SB15_100] | SB15m, LPF=100 Hz |
| 067 | [SB15_100_C] | SB15m, LPF=100 Hz, cardioid pattern |
| 068 | [SB15_100_Cx] | SB15m, LPF=100 Hz, extended cardioid pattern |

**SB10**

| # | Preset | Description |
|---|---|---|
| 069 | [SB10_60] | SB10i(r), LPF=60 Hz |
| 070 | [SB10_100] | SB10i(r), LPF=100 Hz |
| 071 | [SB10_200] | SB10i(r), LPF=200 Hz |

**SB6**

| # | Preset | Description |
|---|---|---|
| 072 | [SB6_60] | SB6i(r), LPF=60 Hz |
| 073 | [SB6_100] | SB6i(r), LPF=100 Hz |
| 074 | [SB6_200] | SB6i(r), LPF=200 Hz |

**KILO**

| # | Preset | Description |
|---|---|---|
| 075 | [KILO] | Kilo, LPF=100 Hz |

**SYVA / SYVA_LOW / SYVA+LOW / SYVA+SUB / SYVA_SUB**

| # | Preset | Description |
|---|---|---|
| 076 | [SYVA] | Syva, full range |
| 077 | [SYVA LOW_100] | Syva Low (separated), LPF=100 Hz |
| 078 | [SYVA LOW SYVA] | Syva & Syva Low (coupled) |
| 079 | [SYVA SUB SYVA] | Syva & Syva Sub (coupled) |
| 080 | [SYVA SUB_60] | Syva Sub, LPF=60 Hz |
| 081 | [SYVA SUB_100] | Syva Sub, LPF=100 Hz |
| 082 | [SYVA SUB_200] | Syva Sub, LPF=200 Hz, optimized for [X4] preset |

**SOKA**

| # | Preset | Description |
|---|---|---|
| 083 | [SOKA] | Soka(r), full range |
| 084 | [SOKA_60] | Soka(r), lower LF limit, max SPL -6dB, on-wall+separated sub |
| 085 | [SOKA_200] | Soka(r), on-wall+closely coupled sub |

**X15HiQ**

| # | Preset | Description |
|---|---|---|
| 086 | [X15] | X15 HiQ, full range |
| 087 | [X15_MO] | X15 HiQ, full range, monitor, low latency |

**X12**

| # | Preset | Description |
|---|---|---|
| 088 | [X12] | X12, full range |
| 089 | [X12_MO] | X12, full range, monitor, low latency |

**X8**

| # | Preset | Description |
|---|---|---|
| 090 | [X8] | X8, full range |
| 091 | [X8_MO] | X8, full range, monitor, low latency |

**X8i**

| # | Preset | Description |
|---|---|---|
| 092 | [X8i] | X8i, full range |
| 093 | [X8i_40] | X8i, lower LF limit, max SPL reduced by 6 dB |
| 094 | [X8i_MO] | X8i, full range, monitor, low latency |

**X6i**

| # | Preset | Description |
|---|---|---|
| 095 | [X6i] | X6i, full range |
| 096 | [X6i_50] | X6i, lower LF limit, max SPL reduced by 6 dB |
| 097 | [X6i_MO] | X6i, full range, monitor, low latency |

**115XTHiQ**

| # | Preset | Description |
|---|---|---|
| 098 | [HiQ_FI] | 115XT HiQ, full range, fill |
| 099 | [HiQ_FI_100] | 115XT HiQ, HPF=100 Hz, fill |
| 100 | [HiQ_FR] | 115XT HiQ, full range, FOH |
| 101 | [HiQ_FR_100] | 115XT HiQ, HPF=100 Hz, FOH |
| 102 | [HiQ_MO] | 115XT HiQ, full range, monitor |
| 103 | [HiQ_MO_100] | 115XT HiQ, HPF=100 Hz, monitor |

**12XTA**

| # | Preset | Description |
|---|---|---|
| 104 | [12XTA_FI] | 12XT active, full range, fill |
| 105 | [12XTA_FI_100] | 12XT active, HPF=100 Hz, fill |
| 106 | [12XTA_FR] | 12XT active, full range, FOH |
| 107 | [12XTA_FR_100] | 12XT active, HPF=100 Hz, FOH |
| 108 | [12XTA_MO] | 12XT active, full range, monitor |
| 109 | [12XTA_MO_100] | 12XT active, HPF=100 Hz, monitor |

**12XTP**

| # | Preset | Description |
|---|---|---|
| 110 | [12XTP_FI] | 12XT passive, full range, fill |
| 111 | [12XTP_FI_100] | 12XT passive, HPF=100 Hz, fill |
| 112 | [12XTP_FR] | 12XT passive, full range, FOH |
| 113 | [12XTP_FR_100] | 12XT passive, HPF=100 Hz, FOH |
| 114 | [12XTP_MO] | 12XT passive, full range, monitor |
| 115 | [12XTP_MO_100] | 12XT passive, HPF=100 Hz, monitor |

**8XT**

| # | Preset | Description |
|---|---|---|
| 116 | [8XT_FI] | 8XT, full range, fill |
| 117 | [8XT_FI_100] | 8XT, HPF=100 Hz, fill |
| 118 | [8XT_FR] | 8XT, full range, FOH |
| 119 | [8XT_FR_100] | 8XT, HPF=100 Hz, FOH |
| 120 | [8XT_MO] | 8XT, full range, monitor |
| 121 | [8XT_MO_100] | 8XT, HPF=100 Hz, monitor |

**5XT**

| # | Preset | Description |
|---|---|---|
| 122 | [5XT] | 5XT, full range |
| 123 | [5XT_MO] | 5XT, full range, monitor, low latency |

**X4**

| # | Preset | Description |
|---|---|---|
| 124 | [X4] | X4i(r), full range |
| 125 | [X4_60] | X4i(r), lower LF limit, max SPL reduced by 6 dB, on-wall+separated sub |
| 126 | [X4_MO] | X4i(r), full range, monitor, low latency |

**FLAT**

| # | Preset | Description |
|---|---|---|
| 127 | [FLAT_LA4X] | Flat EQ, protection minimizing clipping risks |

### 4.5 LA8 preset library v7.17 (p.24-31)

메모리 위치 011-193(001-010 사용자 저장용).

**K1**

| # | Preset | Description |
|---|---|---|
| 011 | [K1] | K1, full range |

**K2**

| # | Preset | Description |
|---|---|---|
| 012 | [K2 70] | K2, full range, 70° adjustable fins settings |
| 013 | [K2 90] | K2, full range, 90° adjustable fins settings |
| 014 | [K2 110] | K2, full range, 110° adjustable fins settings |

**K3**

| # | Preset | Description |
|---|---|---|
| 015 | [K3 70] | K3(i), full range, 70° adjustable fins settings |
| 016 | [K3 90] | K3(i), full range, 90° adjustable fins settings |
| 017 | [K3 110] | K3(i), full range, 110° adjustable fins settings |

**K1-SB**

| # | Preset | Description |
|---|---|---|
| 018 | [K1SB_60] | K1-SB, LPF=60 Hz, optimized for CONTOUR configuration |
| 019 | [K1SB_100_NC] | K1-SB, LPF=100 Hz, optimized for NOISE CONTROL configuration |
| 020 | [K1SB_X] | K1-SB, LPF=200 Hz, optimized for THROW configuration with K1 |
| 021 | [K1SB_X K2] | K1-SB, LPF=200 Hz, optimized for THROW configuration with K2 |

**V-DOSC**

| # | Preset | Description |
|---|---|---|
| 022 | [V-DOSC_LO] | V-DOSC, full range, LO contour |
| 023 | [V-DOSC_LO_60] | V-DOSC, HPF=60 Hz, LO contour |
| 024 | [V-DOSC_LO_X] | V-DOSC, full range, LO contour, optimized for [SB218_X] & [dV-S_X] presets |
| 025 | [V-DOSC_HI] | V-DOSC, full range, HI contour |
| 026 | [V-DOSC_HI_60] | V-DOSC, HPF=60 Hz, HI contour |
| 027 | [V-DOSC_HI_X] | V-DOSC, full range, HI contour, optimized for [SB218_X] & [dV-S_X] presets |

**KUDO**

| # | Preset | Description |
|---|---|---|
| 028 | [KUDO50_25] | Kudo, HPF=25 Hz, 50° K-Louver settings |
| 029 | [KUDO50_40] | Kudo, HPF=40 Hz, 50° K-Louver settings |
| 030 | [KUDO50_60] | Kudo, HPF=60 Hz, 50° K-Louver settings |
| 031 | [KUDO80_25] | Kudo, HPF=25 Hz, 80° K-Louver settings |
| 032 | [KUDO80_40] | Kudo, HPF=40 Hz, 80° K-Louver settings |
| 033 | [KUDO80_60] | Kudo, HPF=60 Hz, 80° K-Louver settings |
| 034 | [KUDO110_25] | Kudo, HPF=25 Hz, 110° K-Louver settings |
| 035 | [KUDO110_40] | Kudo, HPF=40 Hz, 110° K-Louver settings |
| 036 | [KUDO110_60] | Kudo, HPF=60 Hz, 110° K-Louver settings |

**KARA_II**

| # | Preset | Description |
|---|---|---|
| 037 | [KARA II 70] | Kara II(i), full range, 70° adjustable fins settings |
| 038 | [KARA II 90] | Kara II(i), full range, 90° adjustable fins settings |
| 039 | [KARA II 110] | Kara II(i), full range, 110° adjustable fins settings |
| 040 | [KARA II_FI] | Kara II(i), HPF=100 Hz, fill |
| 041 | [KARA II_MO] | Kara II(i), full range, monitor, low latency |
| 042 | [KARAIIDOWNK1] | Kara II, optimized delay for K1 downfill |
| 043 | [KARAIIDOWNK2] | Kara II, optimized delay for K2 downfill |
| 044 | [KARAIIDOWNK3] | Kara II(i), optimized delay for K3(i) downfill |

**KARA**

| # | Preset | Description |
|---|---|---|
| 045 | [KARA] | Kara(i), full range, FOH |
| 046 | [KARA_FI] | Kara(i), HPF=100 Hz, fill |
| 047 | [KARADOWNK1] | Kara, HPF=100 Hz, optimized delay for K1 downfill |
| 048 | [KARADOWNK2] | Kara, HPF=100 Hz, optimized delay for K2 downfill |
| 049 | [KARADOWNK3] | Kara, HPF=100 Hz, optimized delay for K3 downfill |

**dV-DOSC**

| # | Preset | Description |
|---|---|---|
| 050 | [dV_FI] | dV-DOSC, HPF=100 Hz, fill |
| 051 | [dV_LO] | dV-DOSC, full range, LO contour |
| 052 | [dV_LO_100] | dV-DOSC, HPF=100 Hz, LO contour |
| 053 | [dV_HI] | dV-DOSC, full range, HI contour |
| 054 | [dV_HI_100] | dV-DOSC, HPF=100 Hz, HI contour |

**dV-D_dVS**

| # | Preset | Description |
|---|---|---|
| 055 | [dV_dV-S_LO] | dV-DOSC & dV-SUB, X-OVER=100 Hz, LO contour |
| 056 | [dV_dV-S_HI] | dV-DOSC & dV-SUB, X-OVER=100 Hz, HI contour |
| 057 | [dV_dV-S_LO60] | dV-DOSC & dV-SUB, HPF=60 Hz, X-OVER=100 Hz, LO contour |
| 058 | [dV_dV-S_HI60] | dV-DOSC & dV-SUB, HPF=60 Hz, X-OVER=100 Hz, HI contour |

**dV-SUB**

| # | Preset | Description |
|---|---|---|
| 059 | [dV-S_60_100] | dV-SUB, HPF=60 Hz, LPF=100 Hz |
| 060 | [dV-S_100] | dV-SUB, LPF=100 Hz |
| 061 | [dV-S_60_X] | dV-SUB, HPF=60 Hz, LPF=200 Hz, optimized for [V-DOSC_xx_60] presets |
| 062 | [dV-S_X] | dV-SUB, LPF=200 Hz, optimized for [V-DOSC_xx_X] presets |

**ARCS_II**

| # | Preset | Description |
|---|---|---|
| 063 | [ARCS II] | ARCS II, full range |

**ARCS**

| # | Preset | Description |
|---|---|---|
| 064 | [ARCS_LO] | ARCS, full range, LO contour |
| 065 | [ARCS_LO_60] | ARCS, HPF=60 Hz, LO contour |
| 066 | [ARCS_LO_100] | ARCS, HPF=100 Hz, LO contour |
| 067 | [ARCS_HI] | ARCS, full range, HI contour |
| 068 | [ARCS_HI_60] | ARCS, HPF=60 Hz, HI contour |
| 069 | [ARCS_HI_100] | ARCS, HPF=100 Hz, HI contour |

**A15**

| # | Preset | Description |
|---|---|---|
| 070 | [A15] | A15(i) Wide or A15(i) Focus, full range |
| 071 | [A15_FI] | A15(i) Wide or A15(i) Focus, full range, fill |
| 072 | [A15_MO] | A15(i) Wide or A15(i) Focus, full range, monitor, low latency |

**A10**

| # | Preset | Description |
|---|---|---|
| 073 | [A10] | A10(i) Wide or A10(i) Focus, full range |
| 074 | [A10_FI] | A10(i) Wide or A10(i) Focus, full range, fill |
| 075 | [A10_MO] | A10(i) Wide or A10(i) Focus, full range, monitor, low latency |

**ARCS_WF**

| # | Preset | Description |
|---|---|---|
| 076 | [ARCS_WIFO] | ARCS Wide or ARCS Focus, full range, FOH |
| 077 | [ARCS_WIFO_FI] | ARCS Wide or ARCS Focus, full range, fill |

**SB28**

| # | Preset | Description |
|---|---|---|
| 078 | [SB28_60] | SB28, LPF=60 Hz |
| 079 | [SB28_100] | SB28, LPF=100 Hz |
| 080 | [SB28_60_C] | SB28, LPF=60 Hz, cardioid pattern |
| 081 | [SB28_100_C] | SB28, LPF=100 Hz, cardioid pattern |
| 082 | [SB28_60_Cx] | SB28, LPF=60 Hz, extended cardioid pattern |
| 083 | [SB28_100_Cx] | SB28, LPF=100 Hz, extended cardioid pattern |

**KS21**

| # | Preset | Description |
|---|---|---|
| 084 | [KS21_60] | KS21(i), LPF=60 Hz |
| 085 | [KS21_100] | KS21(i), LPF=100 Hz |
| 086 | [KS21_60_C] | KS21(i), LPF=60 Hz, cardioid pattern |
| 087 | [KS21_100_C] | KS21(i), LPF=100 Hz, cardioid pattern |
| 088 | [KS21_60_Cx] | KS21(i), LPF=60 Hz, extended cardioid pattern |
| 089 | [KS21_100_Cx] | KS21(i), LPF=100 Hz, extended cardioid pattern |

**SB218**

| # | Preset | Description |
|---|---|---|
| 090 | [SB218_60] | SB218, LPF=60 Hz |
| 091 | [SB218_100] | SB218, LPF=100 Hz |
| 092 | [SB218_X] | SB218, LPF=200 Hz, optimized for [V-DOSC_xx_X] presets |

**SB18**

| # | Preset | Description |
|---|---|---|
| 093 | [SB18_60] | SB18, LPF=60 Hz |
| 094 | [SB18_100] | SB18, LPF=100 Hz |
| 095 | [SB18_60_C] | SB18, LPF=60 Hz, cardioid pattern |
| 096 | [SB18_100_C] | SB18, LPF=100 Hz, cardioid pattern |
| 097 | [SB18_60_Cx] | SB18, LPF=60 Hz, extended cardioid pattern |
| 098 | [SB18_100_Cx] | SB18, LPF=100 Hz, extended cardioid pattern |

**SB118**

| # | Preset | Description |
|---|---|---|
| 099 | [SB118_60] | SB118, LPF=60 Hz |
| 100 | [SB118_100] | SB118, LPF=100 Hz |
| 101 | [SB118_60_C] | SB118, LPF=60 Hz, cardioid pattern |
| 102 | [SB118_100_C] | SB118, LPF=100 Hz, cardioid pattern |

**SB15**

| # | Preset | Description |
|---|---|---|
| 103 | [SB15_100] | SB15m, LPF=100 Hz |
| 104 | [SB15_100_C] | SB15m, LPF=100 Hz, cardioid pattern |
| 105 | [SB15_100_Cx] | SB15m, LPF=100 Hz, extended cardioid pattern |

**SB10**

| # | Preset | Description |
|---|---|---|
| 106 | [SB10_60] | SB10i(r), LPF=60 Hz |
| 107 | [SB10_100] | SB10i(r), LPF=100 Hz |
| 108 | [SB10_200] | SB10i(r), LPF=200 Hz |

**KILO**

| # | Preset | Description |
|---|---|---|
| 109 | [KILO] | Kilo, LPF=100 Hz |

**KIVA_II**

| # | Preset | Description |
|---|---|---|
| 110 | [KIVA II] | Kiva II, full range, FOH |
| 111 | [KIVA II_FI] | Kiva II, full range, fill |

**KIVA**

| # | Preset | Description |
|---|---|---|
| 112 | [KIVA] | Kiva, full range, FOH |
| 113 | [KIVA_FI] | Kiva, full range, fill |

**SB15KIVA**

| # | Preset | Description |
|---|---|---|
| 114 | [KIVA_SB15] | Kiva & SB15m, X-OVER=100 Hz, full range, FOH |

**KILOKIVA**

| # | Preset | Description |
|---|---|---|
| 115 | [KIVA_KILO] | Kiva & Kilo, full range, X-OVER=100 Hz, FOH |

**SYVA / SYVA_LOW / SYVA+LOW / SYVA_SUB**

| # | Preset | Description |
|---|---|---|
| 116 | [SYVA] | Syva, full range |
| 117 | [SYVA LOW_100] | Syva Low (separated), LPF=100 Hz |
| 118 | [SYVA LOW SYVA] | Syva & Syva Low (coupled) |
| 119 | [SYVA SUB_60] | Syva Sub, LPF=60 Hz |
| 120 | [SYVA SUB_100] | Syva Sub, LPF=100 Hz |
| 121 | [SYVA SUB_200] | Syva Sub, LPF=200 Hz, optimized for [X4] preset |

**X15HiQ**

| # | Preset | Description |
|---|---|---|
| 122 | [X15] | X15 HiQ, full range |
| 123 | [X15_MO] | X15 HiQ, full range, monitor, low latency |

**X12**

| # | Preset | Description |
|---|---|---|
| 124 | [X12] | X12, full range |
| 125 | [X12_MO] | X12, full range, monitor, low latency |

**X8**

| # | Preset | Description |
|---|---|---|
| 126 | [X8] | X8, full range |
| 127 | [X8_MO] | X8, full range, monitor, low latency |

**115XTHiQ**

| # | Preset | Description |
|---|---|---|
| 128 | [HiQ_FI] | 115XT HiQ, full range, fill |
| 129 | [HiQ_FI_100] | 115XT HiQ, HPF=100 Hz, fill |
| 130 | [HiQ_FR] | 115XT HiQ, full range, FOH |
| 131 | [HiQ_FR_100] | 115XT HiQ, HPF=100 Hz, FOH |
| 132 | [HiQ_MO] | 115XT HiQ, full range, monitor |
| 133 | [HiQ_MO_100] | 115XT HiQ, HPF=100 Hz, monitor |

**12XTA**

| # | Preset | Description |
|---|---|---|
| 134 | [12XTA_FI] | 12XT active, full range, fill |
| 135 | [12XTA_FI_100] | 12XT active, HPF=100 Hz, fill |
| 136 | [12XTA_FR] | 12XT active, full range, FOH |
| 137 | [12XTA_FR_100] | 12XT active, HPF=100 Hz, FOH |
| 138 | [12XTA_MO] | 12XT active, full range, monitor |
| 139 | [12XTA_MO_100] | 12XT active, HPF=100 Hz, monitor |

**12XTP**

| # | Preset | Description |
|---|---|---|
| 140 | [12XTP_FI] | 12XT passive, full range, fill |
| 141 | [12XTP_FI_100] | 12XT passive, HPF=100 Hz, fill |
| 142 | [12XTP_FR] | 12XT passive, full range, FOH |
| 143 | [12XTP_FR_100] | 12XT passive, HPF=100 Hz, FOH |
| 144 | [12XTP_MO] | 12XT passive, full range, monitor |
| 145 | [12XTP_MO_100] | 12XT passive, HPF=100 Hz, monitor |

**8XT**

| # | Preset | Description |
|---|---|---|
| 146 | [8XT_FI] | 8XT, full range, fill |
| 147 | [8XT_FI_100] | 8XT, HPF=100 Hz, fill |
| 148 | [8XT_FR] | 8XT, full range, FOH |
| 149 | [8XT_FR_100] | 8XT, HPF=100 Hz, FOH |
| 150 | [8XT_MO] | 8XT, full range, monitor |
| 151 | [8XT_MO_100] | 8XT, HPF=100 Hz, monitor |

**5XT**

| # | Preset | Description |
|---|---|---|
| 152 | [5XT] | 5XT, full range |
| 153 | [5XT_MO] | 5XT, full range, monitor, low latency |

**X4**

| # | Preset | Description |
|---|---|---|
| 154 | [X4] | X4i(r), full range |
| 155 | [X4_60] | X4i(r), lower LF limit, max SPL reduced by 6 dB, on-wall+separated sub |
| 156 | [X4_MO] | X4i(r), full range, monitor, low latency |

**115XT**

| # | Preset | Description |
|---|---|---|
| 157 | [115XT_FI] | 115XT, full range, fill |
| 158 | [115XT_FI_100] | 115XT, HPF=100 Hz, fill |
| 159 | [115XT_FR] | 115XT, full range, FOH |
| 160 | [115XT_FR_100] | 115XT, HPF=100 Hz, FOH |
| 161 | [115XT_MO] | 115XT, full range, monitor |
| 162 | [115XT_MO_100] | 115XT, HPF=100 Hz, monitor |

**MTD115bA**

| # | Preset | Description |
|---|---|---|
| 163 | [115bA_FI] | MTD115b active, full range, fill |
| 164 | [115bA_FI_100] | MTD115b active, HPF=100 Hz, fill |
| 165 | [115bA_FR] | MTD115b active, full range, FOH |
| 166 | [115bA_FR_100] | MTD115b active, HPF=100 Hz, FOH |
| 167 | [115bA_MO] | MTD115b active, full range, monitor |
| 168 | [115bA_MO_100] | MTD115b active, HPF=100 Hz, monitor |

**MTD115bP**

| # | Preset | Description |
|---|---|---|
| 169 | [115bP_FI] | MTD115b passive, full range, fill |
| 170 | [115bP_FI_100] | MTD115b passive, HPF=100 Hz, fill |
| 171 | [115bP_FR] | MTD115b passive, full range, FOH |
| 172 | [115bP_FR_100] | MTD115b passive, HPF=100 Hz, FOH |
| 173 | [115bP_MO] | MTD115b passive, full range, monitor |
| 174 | [115bP_MO_100] | MTD115b passive, HPF=100 Hz, monitor |

**112XT**

| # | Preset | Description |
|---|---|---|
| 175 | [112XT_FI] | 112XT, full range, fill |
| 176 | [112XT_FI_100] | 112XT, HPF=100 Hz, fill |
| 177 | [112XT_FR] | 112XT, full range, FOH |
| 178 | [112XT_FR_100] | 112XT, HPF=100 Hz, FOH |
| 179 | [112XT_MO] | 112XT, full range, monitor |
| 180 | [112XT_MO_100] | 112XT, HPF=100 Hz, monitor |

**MTD112b**

| # | Preset | Description |
|---|---|---|
| 181 | [112b_FI] | MTD112b, full range, fill |
| 182 | [112b_FI_100] | MTD112b, HPF=100 Hz, fill |
| 183 | [112b_FR] | MTD112b, full range, FOH |
| 184 | [112b_FR_100] | MTD112b, HPF=100 Hz, FOH |
| 185 | [112b_MO] | MTD112b, full range, monitor |
| 186 | [112b_MO_100] | MTD112b, HPF=100 Hz, monitor |

**MTD108a**

| # | Preset | Description |
|---|---|---|
| 187 | [108a_FI] | MTD108a, full range, fill |
| 188 | [108a_FI_100] | MTD108a, HPF=100 Hz, fill |
| 189 | [108a_FR] | MTD108a, full range, FOH |
| 190 | [108a_FR_100] | MTD108a, HPF=100 Hz, FOH |
| 191 | [108a_MO] | MTD108a, full range, monitor |
| 192 | [108a_MO_100] | MTD108a, HPF=100 Hz, monitor |

**FLAT**

| # | Preset | Description |
|---|---|---|
| 193 | [FLAT_LA8] | Flat EQ, protection minimizing clipping risks |

*참고: LA8은 SB6/Soka/X8i/X6i 패밀리가 라이브러리에 없음(LA4X/LA2Xi에는 있음) — 원문 그대로.*

### 4.6 LA12X preset library v7.17 (p.32-37)

메모리 위치 011-138(001-010 사용자 저장용).

**K1**

| # | Preset | Description |
|---|---|---|
| 011 | [K1] | K1, full range |

**K2**

| # | Preset | Description |
|---|---|---|
| 012 | [K2 70] | K2, full range, 70° adjustable fins settings |
| 013 | [K2 90] | K2, full range, 90° adjustable fins settings |
| 014 | [K2 110] | K2, full range, 110° adjustable fins settings |

**K3**

| # | Preset | Description |
|---|---|---|
| 015 | [K3 70] | K3(i), full range, 70° adjustable fins settings |
| 016 | [K3 90] | K3(i), full range, 90° adjustable fins settings |
| 017 | [K3 110] | K3(i), full range, 110° adjustable fins settings |

**K1-SB**

| # | Preset | Description |
|---|---|---|
| 018 | [K1SB_60] | K1-SB, LPF=60 Hz, optimized for CONTOUR configuration |
| 019 | [K1SB_100_NC] | K1-SB, LPF=100 Hz, optimized for NOISE CONTROL configuration |
| 020 | [K1SB_X] | K1-SB, LPF=200 Hz, optimized for THROW configuration with K1 |
| 021 | [K1SB_X K2] | K1-SB, LPF=200 Hz, optimized for THROW configuration with K2 |

**KARA_II**

| # | Preset | Description |
|---|---|---|
| 022 | [KARA II 70] | Kara II(i), full range, 70° adjustable fins settings |
| 023 | [KARA II 90] | Kara II(i), full range, 90° adjustable fins settings |
| 024 | [KARA II 110] | Kara II(i), full range, 110° adjustable fins settings |
| 025 | [KARA II_FI] | Kara II(i), HPF=100 Hz, fill |
| 026 | [KARA II_MO] | Kara II(i), full range, monitor, low latency |
| 027 | [KARAIIDOWNK1] | Kara II, optimized delay for K1 downfill |
| 028 | [KARAIIDOWNK2] | Kara II, optimized delay for K2 downfill |
| 029 | [KARAIIDOWNK3] | Kara II(i), optimized delay for K3(i) downfill |

**KARA**

| # | Preset | Description |
|---|---|---|
| 030 | [KARA] | Kara(i), full range, FOH |
| 031 | [KARA_FI] | Kara(i), HPF=100 Hz, fill |
| 032 | [KARADOWNK1] | Kara, HPF=100 Hz, optimized delay for K1 downfill |
| 033 | [KARADOWNK2] | Kara, HPF=100 Hz, optimized delay for K2 downfill |
| 034 | [KARADOWNK3] | Kara, HPF=100 Hz, optimized delay for K3 downfill |

**ARCS_II**

| # | Preset | Description |
|---|---|---|
| 035 | [ARCS II] | ARCS II, full range |

**A15**

| # | Preset | Description |
|---|---|---|
| 036 | [A15] | A15(i) Wide or A15(i) Focus, full range |
| 037 | [A15_FI] | A15(i) Wide or A15(i) Focus, full range, fill |
| 038 | [A15_MO] | A15(i) Wide or A15(i) Focus, full range, monitor, low latency |

**A10**

| # | Preset | Description |
|---|---|---|
| 039 | [A10] | A10(i) Wide or A10(i) Focus, full range |
| 040 | [A10_FI] | A10(i) Wide or A10(i) Focus, full range, fill |
| 041 | [A10_MO] | A10(i) Wide or A10(i) Focus, full range, monitor, low latency |

**ARCS_WF**

| # | Preset | Description |
|---|---|---|
| 042 | [ARCS_WIFO] | ARCS Wide or ARCS Focus, full range, FOH |
| 043 | [ARCS_WIFO_FI] | ARCS Wide or ARCS Focus, full range, fill |

**CS1**

| # | Preset | Description |
|---|---|---|
| 044 | [CS1_60] | CS1, LPF=60 Hz, cardioid pattern |
| 045 | [CS1_60_S] | CS1, LPF=60 Hz, supercardioid pattern |

**KS28**

| # | Preset | Description |
|---|---|---|
| 046 | [KS28_60] | KS28, LPF=60 Hz |
| 047 | [KS28_100] | KS28, LPF=100 Hz |
| 048 | [KS28_60_C] | KS28, LPF=60 Hz, cardioid pattern |
| 049 | [KS28_100_C] | KS28, LPF=100 Hz, cardioid pattern |
| 050 | [KS28_60_Cx] | KS28, LPF=60 Hz, extended cardioid pattern |
| 051 | [KS28_100_Cx] | KS28, LPF=100 Hz, extended cardioid pattern |
| 052 | [KS28 L2] | KS28, optimized for L2(D) |
| 053 | [KS28 L2_C] | KS28, cardioid pattern, optimized for L2(D) |
| 054 | [KS28 L2_Cx] | KS28, extended cardioid pattern, optimized for L2(D) |

**SB28**

| # | Preset | Description |
|---|---|---|
| 055 | [SB28_60] | SB28, LPF=60 Hz |
| 056 | [SB28_100] | SB28, LPF=100 Hz |
| 057 | [SB28_60_C] | SB28, LPF=60 Hz, cardioid pattern |
| 058 | [SB28_100_C] | SB28, LPF=100 Hz, cardioid pattern |
| 059 | [SB28_60_Cx] | SB28, LPF=60 Hz, extended cardioid pattern |
| 060 | [SB28_100_Cx] | SB28, LPF=100 Hz, extended cardioid pattern |

**KS21**

| # | Preset | Description |
|---|---|---|
| 061 | [KS21_60] | KS21(i), LPF=60 Hz |
| 062 | [KS21_100] | KS21(i), LPF=100 Hz |
| 063 | [KS21_60_C] | KS21(i), LPF=60 Hz, cardioid pattern |
| 064 | [KS21_100_C] | KS21(i), LPF=100 Hz, cardioid pattern |
| 065 | [KS21_60_Cx] | KS21(i), LPF=60 Hz, extended cardioid pattern |
| 066 | [KS21_100_Cx] | KS21(i), LPF=100 Hz, extended cardioid pattern |

**SB18**

| # | Preset | Description |
|---|---|---|
| 067 | [SB18_60] | SB18, LPF=60 Hz |
| 068 | [SB18_100] | SB18, LPF=100 Hz |
| 069 | [SB18_60_C] | SB18, LPF=60 Hz, cardioid pattern |
| 070 | [SB18_100_C] | SB18, LPF=100 Hz, cardioid pattern |
| 071 | [SB18_60_Cx] | SB18, LPF=60 Hz, extended cardioid pattern |
| 072 | [SB18_100_Cx] | SB18, LPF=100 Hz, extended cardioid pattern |

**SB15**

| # | Preset | Description |
|---|---|---|
| 073 | [SB15_100] | SB15m, LPF=100 Hz |
| 074 | [SB15_100_C] | SB15m, LPF=100 Hz, cardioid pattern |
| 075 | [SB15_100_Cx] | SB15m, LPF=100 Hz, extended cardioid pattern |

**SB10**

| # | Preset | Description |
|---|---|---|
| 076 | [SB10_60] | SB10i(r), LPF=60 Hz |
| 077 | [SB10_100] | SB10i(r), LPF=100 Hz |
| 078 | [SB10_200] | SB10i(r), LPF=200 Hz |

**SB6**

| # | Preset | Description |
|---|---|---|
| 079 | [SB6_60] | SB6i(r), LPF=60 Hz |
| 080 | [SB6_100] | SB6i(r), LPF=100 Hz |
| 081 | [SB6_200] | SB6i(r), LPF=200 Hz |

**KIVA_II**

| # | Preset | Description |
|---|---|---|
| 082 | [KIVA II] | Kiva II, full range, FOH |
| 083 | [KIVA II_FI] | Kiva II, full range, fill |

**KIVA**

| # | Preset | Description |
|---|---|---|
| 084 | [KIVA] | Kiva, full range, FOH |
| 085 | [KIVA_FI] | Kiva, full range, fill |

**SB15KIVA**

| # | Preset | Description |
|---|---|---|
| 086 | [KIVA_SB15] | Kiva & SB15m, X-OVER=100 Hz, full range, FOH |

**SYVA / SYVA_LOW / SYVA+LOW / SYVA+SUB / SYVA_SUB**

| # | Preset | Description |
|---|---|---|
| 087 | [SYVA] | Syva, full range |
| 088 | [SYVA LOW_100] | Syva Low (separated), LPF=100 Hz |
| 089 | [SYVA LOW SYVA] | Syva & Syva Low (coupled) |
| 090 | [SYVA SUB SYVA] | Syva & Syva Sub (coupled) |
| 091 | [SYVA SUB_60] | Syva Sub, LPF=60 Hz |
| 092 | [SYVA SUB_100] | Syva Sub, LPF=100 Hz |
| 093 | [SYVA SUB_200] | Syva Sub, LPF=200 Hz, optimized for [X4] preset |

**SOKA**

| # | Preset | Description |
|---|---|---|
| 094 | [SOKA] | Soka(r), full range |
| 095 | [SOKA_60] | Soka(r), lower LF limit, max SPL -6dB, on-wall+separated sub |
| 096 | [SOKA_200] | Soka(r), on-wall+closely coupled sub |

**X15HiQ**

| # | Preset | Description |
|---|---|---|
| 097 | [X15] | X15 HiQ, full range |
| 098 | [X15_MO] | X15 HiQ, full range, monitor, low latency |

**X12**

| # | Preset | Description |
|---|---|---|
| 099 | [X12] | X12, full range |
| 100 | [X12_MO] | X12, full range, monitor, low latency |

**X8**

| # | Preset | Description |
|---|---|---|
| 101 | [X8] | X8, full range |
| 102 | [X8_MO] | X8, full range, monitor, low latency |

**X8i**

| # | Preset | Description |
|---|---|---|
| 103 | [X8i] | X8i, full range |
| 104 | [X8i_40] | X8i, lower LF limit, max SPL reduced by 6 dB |
| 105 | [X8i_MO] | X8i, full range, monitor, low latency |

**X6i**

| # | Preset | Description |
|---|---|---|
| 106 | [X6i] | X6i, full range |
| 107 | [X6i_50] | X6i, lower LF limit, max SPL reduced by 6 dB |
| 108 | [X6i_MO] | X6i, full range, monitor, low latency |

**115XTHiQ**

| # | Preset | Description |
|---|---|---|
| 109 | [HiQ_FI] | 115XT HiQ, full range, fill |
| 110 | [HiQ_FI_100] | 115XT HiQ, HPF=100 Hz, fill |
| 111 | [HiQ_FR] | 115XT HiQ, full range, FOH |
| 112 | [HiQ_FR_100] | 115XT HiQ, HPF=100 Hz, FOH |
| 113 | [HiQ_MO] | 115XT HiQ, full range, monitor |
| 114 | [HiQ_MO_100] | 115XT HiQ, HPF=100 Hz, monitor |

**12XTA**

| # | Preset | Description |
|---|---|---|
| 115 | [12XTA_FI] | 12XT active, full range, fill |
| 116 | [12XTA_FI_100] | 12XT active, HPF=100 Hz, fill |
| 117 | [12XTA_FR] | 12XT active, full range, FOH |
| 118 | [12XTA_FR_100] | 12XT active, HPF=100 Hz, FOH |
| 119 | [12XTA_MO] | 12XT active, full range, monitor |
| 120 | [12XTA_MO_100] | 12XT active, HPF=100 Hz, monitor |

**12XTP**

| # | Preset | Description |
|---|---|---|
| 121 | [12XTP_FI] | 12XT passive, full range, fill |
| 122 | [12XTP_FI_100] | 12XT passive, HPF=100 Hz, fill |
| 123 | [12XTP_FR] | 12XT passive, full range, FOH |
| 124 | [12XTP_FR_100] | 12XT passive, HPF=100 Hz, FOH |
| 125 | [12XTP_MO] | 12XT passive, full range, monitor |
| 126 | [12XTP_MO_100] | 12XT passive, HPF=100 Hz, monitor |

**8XT**

| # | Preset | Description |
|---|---|---|
| 127 | [8XT_FI] | 8XT, full range, fill |
| 128 | [8XT_FI_100] | 8XT, HPF=100 Hz, fill |
| 129 | [8XT_FR] | 8XT, full range, FOH |
| 130 | [8XT_FR_100] | 8XT, HPF=100 Hz, FOH |
| 131 | [8XT_MO] | 8XT, full range, monitor |
| 132 | [8XT_MO_100] | 8XT, HPF=100 Hz, monitor |

**5XT**

| # | Preset | Description |
|---|---|---|
| 133 | [5XT] | 5XT, full range |
| 134 | [5XT_MO] | 5XT, full range, monitor, low latency |

**X4**

| # | Preset | Description |
|---|---|---|
| 135 | [X4] | X4i(r), full range |
| 136 | [X4_60] | X4i(r), lower LF limit, max SPL reduced by 6 dB, on-wall+separated sub |
| 137 | [X4_MO] | X4i(r), full range, monitor, low latency |

**FLAT**

| # | Preset | Description |
|---|---|---|
| 138 | [FLAT_LA12X] | Flat EQ, protection minimizing clipping risks |

*참고: LA12X는 MTD/115XT/112XT 레거시 코액시얼 패밀리와 KILO/KIVA_KILO가 라이브러리에 없음(LA4X/LA8/LA2Xi와 대조적) — 원문 그대로.*

### 4.7 LA7.16i layout library v7.17 (p.38-41)

메모리 위치 01-076(2자리 번호). **L2/L2D가 01번(최상단)에 배치**되는 점이 다른 라이브러리와의 차이.

**L2**

| # | Preset | Description |
|---|---|---|
| 01 | [L2 110] | L2, full range, 110° adjustable fins settings |

**L2D**

| # | Preset | Description |
|---|---|---|
| 02 | [L2D 110] | L2D, full range, 110° adjustable fins settings |

**K2**

| # | Preset | Description |
|---|---|---|
| 03 | [K2 70] | K2, full range, 70° adjustable fins settings |
| 04 | [K2 90] | K2, full range, 90° adjustable fins settings |
| 05 | [K2 110] | K2, full range, 110° adjustable fins settings |

**K3**

| # | Preset | Description |
|---|---|---|
| 06 | [K3 70] | K3(i), full range, 70° adjustable fins settings |
| 07 | [K3 90] | K3(i), full range, 90° adjustable fins settings |
| 08 | [K3 110] | K3(i), full range, 110° adjustable fins settings |

**KARA_II**

| # | Preset | Description |
|---|---|---|
| 09 | [KARA II 70] | Kara II(i), full range, 70° adjustable fins settings |
| 010 | [KARA II 90] | Kara II(i), full range, 90° adjustable fins settings |
| 011 | [KARA II 110] | Kara II(i), full range, 110° adjustable fins settings |
| 012 | [KARA II_FI] | Kara II(i), HPF=100 Hz, fill |
| 013 | [KARA II_MO] | Kara II(i), full range, monitor, low latency |
| 014 | [KARAIIDOWNK1] | Kara II, optimized delay for K1 downfill |
| 015 | [KARAIIDOWNK2] | Kara II, optimized delay for K2 downfill |
| 016 | [KARAIIDOWNK3] | Kara II(i), optimized delay for K3(i) downfill |

**A15**

| # | Preset | Description |
|---|---|---|
| 017 | [A15] | A15(i) Wide or A15(i) Focus, full range |
| 018 | [A15_FI] | A15(i) Wide or A15(i) Focus, full range, fill |
| 019 | [A15_MO] | A15(i) Wide or A15(i) Focus, full range, monitor, low latency |

**A10**

| # | Preset | Description |
|---|---|---|
| 020 | [A10] | A10(i) Wide or A10(i) Focus, full range |
| 021 | [A10_FI] | A10(i) Wide or A10(i) Focus, full range, fill |
| 022 | [A10_MO] | A10(i) Wide or A10(i) Focus, full range, monitor, low latency |

**CS1**

| # | Preset | Description |
|---|---|---|
| 023 | [CS1_60] | CS1, LPF=60 Hz, cardioid pattern |
| 024 | [CS1_60_S] | CS1, LPF=60 Hz, supercardioid pattern |

**KS21**

| # | Preset | Description |
|---|---|---|
| 025 | [KS21_60] | KS21(i), LPF=60 Hz |
| 026 | [KS21_100] | KS21(i), LPF=100 Hz |
| 027 | [KS21_60_C] | KS21(i), LPF=60 Hz, cardioid pattern |
| 028 | [KS21_100_C] | KS21(i), LPF=100 Hz, cardioid pattern |
| 029 | [KS21_60_Cx] | KS21(i), LPF=60 Hz, extended cardioid pattern |
| 030 | [KS21_100_Cx] | KS21(i), LPF=100 Hz, extended cardioid pattern |

**SB18**

| # | Preset | Description |
|---|---|---|
| 031 | [SB18_60] | SB18, LPF=60 Hz |
| 032 | [SB18_100] | SB18, LPF=100 Hz |
| 033 | [SB18_60_C] | SB18, LPF=60 Hz, cardioid pattern |
| 034 | [SB18_100_C] | SB18, LPF=100 Hz, cardioid pattern |
| 035 | [SB18_60_Cx] | SB18, LPF=60 Hz, extended cardioid pattern |
| 036 | [SB18_100_Cx] | SB18, LPF=100 Hz, extended cardioid pattern |

**SB15**

| # | Preset | Description |
|---|---|---|
| 037 | [SB15_100] | SB15m, LPF=100 Hz |
| 038 | [SB15_100_C] | SB15m, LPF=100 Hz, cardioid pattern |
| 039 | [SB15_100_Cx] | SB15m, LPF=100 Hz, extended cardioid pattern |

**SB10**

| # | Preset | Description |
|---|---|---|
| 040 | [SB10_60] | SB10i(r), LPF=60 Hz |
| 041 | [SB10_100] | SB10i(r), LPF=100 Hz |
| 042 | [SB10_200] | SB10i(r), LPF=200 Hz |

**SB6**

| # | Preset | Description |
|---|---|---|
| 043 | [SB6_60] | SB6i(r), LPF=60 Hz |
| 044 | [SB6_100] | SB6i(r), LPF=100 Hz |
| 045 | [SB6_200] | SB6i(r), LPF=200 Hz |

**KIVA_II**

| # | Preset | Description |
|---|---|---|
| 046 | [KIVA II] | Kiva II, full range, FOH |
| 047 | [KIVA II_FI] | Kiva II, full range, fill |

**SYVA / SYVA_LOW / SYVA+LOW / SYVA+SUB / SYVA_SUB**

| # | Preset | Description |
|---|---|---|
| 048 | [SYVA] | Syva, full range |
| 049 | [SYVA LOW_100] | Syva Low (separated), LPF=100 Hz |
| 050 | [SYVA LOW SYVA] | Syva & Syva Low (coupled) |
| 051 | [SYVA SUB SYVA] | Syva & Syva Sub (coupled) |
| 052 | [SYVA SUB_60] | Syva Sub, LPF=60 Hz |
| 053 | [SYVA SUB_100] | Syva Sub, LPF=100 Hz |
| 054 | [SYVA SUB_200] | Syva Sub, LPF=200 Hz, optimized for [X4] preset |

**SOKA**

| # | Preset | Description |
|---|---|---|
| 055 | [SOKA] | Soka(r), full range |
| 056 | [SOKA_60] | Soka(r), lower LF limit, max SPL -6dB, on-wall+separated sub |
| 057 | [SOKA_200] | Soka(r), on-wall+closely coupled sub |

**X15HiQ**

| # | Preset | Description |
|---|---|---|
| 058 | [X15] | X15 HiQ, full range |
| 059 | [X15_MO] | X15 HiQ, full range, monitor, low latency |

**X12**

| # | Preset | Description |
|---|---|---|
| 060 | [X12] | X12, full range |
| 061 | [X12_MO] | X12, full range, monitor, low latency |

**X8**

| # | Preset | Description |
|---|---|---|
| 062 | [X8] | X8, full range |
| 063 | [X8_MO] | X8, full range, monitor, low latency |

**X8i**

| # | Preset | Description |
|---|---|---|
| 064 | [X8i] | X8i, full range |
| 065 | [X8i_40] | X8i, lower LF limit, max SPL reduced by 6 dB |
| 066 | [X8i_MO] | X8i, full range, monitor, low latency |

**X6i**

| # | Preset | Description |
|---|---|---|
| 067 | [X6i] | X6i, full range |
| 068 | [X6i_50] | X6i, lower LF limit, max SPL reduced by 6 dB |
| 069 | [X6i_MO] | X6i, full range, monitor, low latency |

**5XT**

| # | Preset | Description |
|---|---|---|
| 070 | [5XT] | 5XT, full range |
| 071 | [5XT_MO] | 5XT, full range, monitor, low latency |

**X4**

| # | Preset | Description |
|---|---|---|
| 072 | [X4] | X4i(r), full range |
| 073 | [X4_60] | X4i(r), lower LF limit, max SPL reduced by 6 dB, on-wall+separated sub |
| 074 | [X4_MO] | X4i(r), full range, monitor, low latency |

**FLAT**

| # | Preset | Description |
|---|---|---|
| 075 | [FLAT_LA7.16_8R] | Flat EQ, protection minimizing clipping risks. Use for loads of 8 Ω and more. |
| 076 | [FLAT_LA7.16_4R] | Flat EQ, protection minimizing clipping and overcurrent risks. Use for loads comprised between 4 Ω and 8 Ω. |

*참고: LA7.16i는 KIVA/KILO/SB15KIVA/ARCS/ARCS_II/ARCS_WF/레거시 코액시얼(115XT/MTD계열/112XT/8XT/12XT)/K1/K1-SB/KS28/SB28 패밀리가 없음 — L2/L2D/K2/K3(i)/KARA II(i)/A15(i)/A10(i)/CS1/일부 서브우퍼(KS21/SB18/SB15/SB10/SB6)/Kiva II/Syva/Soka/X 시리즈(신형 코액시얼)만 수록. FLAT이 로드 임피던스별 2종(8Ω/4-8Ω)인 것도 다른 preset library와 다른 점.*

### 4.8 LA7.16 layout library v7.17 (p.42-45)

메모리 위치 01-076 — **LA7.16i layout library와 완전히 동일**(같은 제품군 목록, 같은 번호, 같은 프리셋명/설명, FLAT 2종도 `[FLAT_LA7.16_8R]`/`[FLAT_LA7.16_4R]` 그대로 동일). "i" 없는 구형 LA7.16 컨트롤러도 신형 LA7.16i와 동일한 레이아웃 라이브러리를 공유하는 것으로 원문에서 확인됨(4.7절 표 참조, 별도 표 생략).

## 5. FLAT presets (p.46)

FLAT 프리셋으로 구동되는 출력 채널의 트랜스듀서는 L-DRIVE로 보호되지 않는다 — 앰프 컨트롤러 보호를 위한 클리핑 방지 리미팅만 작동. 따라서 서드파티 인클로저 구동 시, 앰프 컨트롤러 앞단에 해당 모델 전용으로 설계된 외장 DSP 장치 연결을 권장.

FLAT 프리셋에서는 입력 신호가 주파수 응답 수정 없이 출력으로 직결(Mute/Gain/Delay/Polarity/Routing만 조정 가능).

**헤드룸**: [FLAT_LA2X](LA2Xi SE) 0dB / [FLAT_xxxx](LA2Xi BTL/PBTL, LA4, LA4X) 6dB / [FLAT_LA8](LA8) 8dB / [FLAT_LA12X](LA12X) 9.5dB / [FLAT_LA7.16_4R]·[FLAT_LA7.16_8R](LA7.16(i)) 8dB / [FLAT_LA1.16](LA1.16i) -2dB / [FLAT_LA1.16 BTL](LA1.16i) 0dB.

**[FLAT_xxxx]**

| outputs | channels | routing | gain | delay | polarity | mute |
|---|---|---|---|---|---|---|
| OUT 1 | PA | IN A | 0 dB | 0 ms | + | ON |
| OUT 2 | PA | IN A | 0 dB | 0 ms | + | ON |
| OUT 3 | PA | IN B | 0 dB | 0 ms | + | ON |
| OUT 4 | PA | IN B | 0 dB | 0 ms | + | ON |

**[FLAT_LA7.16_4R] / [FLAT_LA7.16_8R] / [FLAT_LA1.16] / [FLAT_LA1.16 BTL]**

16채널 전부 동일 패턴 — `OUT n | PA | IN n | 0 dB | 0 ms | + | ON` (n=1~16). 라우팅/게인/딜레이/극성/뮤트는 사용자 수정 가능.

## 6. Progressive ultra-dense line source presets — L2/L2D (p.47-48)

장거리 투사 용도 최적화. 아래는 L2/L2D 스피커 구성별 프리셋 매핑표(원문 표 그대로):

| 인클로저 구성 | L2 프리셋 | L2D 프리셋 | KS28 프리셋 | CS1 프리셋 | 음향 특성 |
|---|---|---|---|---|---|
| L2/L2D 라인소스 | [L2 70]/[L2 90]/[L2 110] | [L2D 70]/[L2D 90]/[L2D 110] | — | — | 45Hz-20kHz, LF rejection(rear cardioid) |
| L2/L2D 라인소스(슈퍼카디오이드) | [L2_S 70]/[L2_S 90]/[L2_S 110] | [L2D_S 70]/[L2D_S 90]/[L2D_S 110] | — | — | 45Hz-20kHz, supercardioid pattern |
| L2/L2D 라인소스+서브우퍼 | [L2 70]/[L2 90]/[L2 110] | [L2D 70]/[L2D 90]/[L2D 110] | [KS28 L2] | — | down to 25Hz, reinforced LF contour |
| L2/L2D 라인소스+서브우퍼(슈퍼카디오이드) | [L2_S 70]/[L2_S 90]/[L2_S 110] | [L2D_S 70]/[L2D_S 90]/[L2D_S 110] | [KS28 L2] | — | 동일 |
| L2/L2D 라인소스+CS1 결합서브(베사이드/비하인드) | [L2 70]/[L2 90]/[L2 110] | [L2D 70]/[L2D 90]/[L2D 110] | — | [CS1_60] | down to 25Hz, reinforced LF contour, LF rejection(rear cardioid) |
| L2/L2D 라인소스+CS1 결합서브(슈퍼카디오이드) | [L2_S 70]/[L2_S 90]/[L2_S 110] | [L2D_S 70]/[L2D_S 90]/[L2D_S 110] | — | [CS1_60_S] | down to 25Hz, reinforced LF contour, supercardioid pattern |

*서브우퍼를 카디오이드 어레이로 쓰려면 [KS28 L2_C] 또는 [KS28 L2_Cx] 사용.*

**L2/L2D 조절식 핀 설정**: L2 [L2 70]/[L2_S 70]=70°, [L2 90]/[L2_S 90]=90°, [L2 110]/[L2_S 110]=110°. L2D도 동일 대응(하단 2개 모듈은 110° 고정).

**LC(Low Cardioid)**: L2/L2D는 측면 4개 LC 드라이버로 광대역 카디오이드 패턴(후방 SPL 최소화) 구현.

**[L2 70][L2 90][L2 110][L2_S 70][L2_S 90][L2_S 110][L2D 70][L2D 90][L2D 110][L2D_S 70][L2D_S 90][L2D_S 110]**(16채널 공통 라우팅, gain 0dB/delay 0ms/polarity +/mute ON):

| outputs | channels | routing |
|---|---|---|
| OUT 1, 5, 9, 13 | LC | IN 1 |
| OUT 2, 6, 10, 14 | LF | IN 1 |
| OUT 3, 4, 7, 8, 11, 12, 15, 16 | HF | IN 1 |

**[KS28 L2]**

| outputs | channels | routing | gain | delay | polarity | mute |
|---|---|---|---|---|---|---|
| OUT 1-4 | SB | IN A | 0 dB | 0 ms | + | ON |

**[KS28 L2_C] [KS28 L2_Cx]**

| loudspeaker elements | outputs | channels | routing | gain | delay | polarity | mute |
|---|---|---|---|---|---|---|---|
| SR | OUT 1 | SR | IN A | 0 dB | 0 ms | + | ON |
| SB | OUT 2 | SB | IN A | 0 dB | 0 ms | + | ON |
| SB | OUT 3 | SB | IN A | 0 dB | 0 ms | + | ON |
| SB | OUT 4 | SB | IN A | 0 dB | 0 ms | + | ON |

## 7. Variable Curvature WST systems presets — K1 (p.49-50)

**호환성 주의**: 프리셋 라이브러리 4.x 이후의 [K1]/[KARADOWNK1]/[K2 xxx]는 4.0 이전 버전의 [K1]/[KARADOWNK1]과 호환되지 않는다 — 같은 라인소스 내 전 유닛은 동일 버전 프리셋 라이브러리 사용 필요.

| 인클로저 구성 | K1 | K1-SB | KS28/SB28 | CS1 | 음향 특성 |
|---|---|---|---|---|---|
| K1 라인소스 | [K1] | — | — | — | 35Hz-20kHz |
| K1/K1-SB 라인소스(K1-SB 상단) | [K1] | [K1SB_X] | — | — | enhanced LF throw |
| K1 라인소스+K1-SB 결합서브(베사이드/비하인드) | [K1] | [K1SB_60] | — | — | down to 30Hz, reinforced LF contour, LF rejection(side polarized or rear cardioid) |
| K1 라인소스+K1-SB 결합서브(비하인드) | [K1] | [K1SB_100_NC] | — | — | down to 33Hz, reinforced LF contour, LF rejection(rear cardioid) |
| K1 라인소스+서브우퍼 | [K1] | — | [xx28_60] | — | down to 25Hz, reinforced LF contour |
| K1 라인소스+CS1 결합서브(베사이드/비하인드) | [K1] | — | — | [CS1_60] | down to 25Hz, reinforced LF contour, LF rejection(rear cardioid) |
| K1 라인소스+CS1 결합서브(슈퍼카디오이드) | [K1] | — | — | [CS1_60_S] | down to 25Hz, reinforced LF contour, supercardioid pattern |

*카디오이드 서브우퍼 어레이는 [xx28_60_C] 또는 [xx28_60_Cx] 사용.*

**다운필 옵션**: K2 인클로저는 [K2 110]/[K2 90]/[K2 70]로 구동. Kara는 [KARADOWNK1]로, Kara II는 [KARAIIDOWNK1](110°)/[KARAIIDOWNK1 70]/[KARAIIDOWNK1 90]로 구동.

**[K1] and [K2 xxx]**

| loudspeaker elements | outputs | channels | routing | gain | delay | polarity | mute |
|---|---|---|---|---|---|---|---|
| left LF | OUT 1 | LF | IN A | 0 dB | 0 ms | + | ON |
| right LF | OUT 2 | LF | IN A | 0 dB | 0 ms | + | ON |
| MF | OUT 3 | MF | IN A | 0 dB | 0 ms | + | ON |
| HF | OUT 4 | HF | IN A | 0 dB | 0 ms | + | ON |

*left/right는 인클로저 전면 기준.*

**[K1SB_X] / [K1SB_60] / [K1SB_100_NC]**

| outputs | channels | routing | gain | delay | polarity | mute |
|---|---|---|---|---|---|---|
| OUT 1-4 | SB | IN A | 0 dB | 0 ms | + | ON |

**[KARADOWNK1] / [KARAIIDOWNK1] / [KARAIIDOWNK1 70] / [KARAIIDOWNK1 90]**

| loudspeaker elements | outputs | channels | routing | gain | delay | polarity | mute |
|---|---|---|---|---|---|---|---|
| LF | OUT 1 | LF | IN A | 0 dB | 0 ms | + | ON |
| HF | OUT 2 | HF | IN A | 0 dB | 0 ms | + | ON |
| LF | OUT 3 | LF | IN A | 0 dB | 0 ms | + | ON |
| HF | OUT 4 | HF | IN A | 0 dB | 0 ms | + | ON |

*[KARAIIDOWNK1]은 Kara II 110° 핀 설정 최적화. 팩토리 파라미터에 K1 라인소스+Kara/Kara II 다운필 커플링 최적 딜레이값 이미 포함.*

## 8. Variable Curvature WST systems presets — K2 (p.51-52)

| 인클로저 구성 | K2 | K1-SB | KS28/SB28 | CS1 | 음향 특성 |
|---|---|---|---|---|---|
| K2 라인소스 | [K2 xxx] | — | — | — | 35Hz-20kHz, adjustable horizontal directivity |
| K2/K1-SB 라인소스(K1-SB 상단) | [K2 xxx] | [K1SB_X K2] | — | — | enhanced LF throw |
| K2 라인소스+K1-SB 결합서브(상단/베사이드/비하인드) | [K2 xxx] | [K1SB_60] | — | — | down to 30Hz, reinforced LF contour, LF rejection(side polarized or rear cardioid) |
| K2 라인소스+K1-SB 결합서브(비하인드) | [K2 xxx] | [K1SB_100_NC] | — | — | down to 33Hz, reinforced LF contour, LF rejection(rear cardioid) |
| K2 라인소스+서브우퍼 | [K2 xxx] | — | [xx28_60] | — | down to 25Hz, reinforced LF contour |
| K2 라인소스+CS1 결합서브(베사이드/비하인드) | [K2 xxx] | — | — | [CS1_60] | down to 25Hz, reinforced LF contour, LF rejection(rear cardioid) |
| K2 라인소스+CS1 결합서브(슈퍼카디오이드) | [K2 xxx] | — | — | [CS1_60_S] | down to 25Hz, reinforced LF contour, supercardioid pattern |

*카디오이드 서브우퍼 어레이는 [xx28_60_C] 또는 [xx28_60_Cx] 사용.*

**조절식 핀**: [K2 70]=70°, [K2 90]=90°, [K2 110]=110°. **다운필**: Kara는 [KARADOWNK2], Kara II는 [KARAIIDOWNK2](110°)/[KARAIIDOWNK2 70]/[KARAIIDOWNK2 90].

**[K2 xxx]** — K1과 동일 구조(left LF/right LF/MF/HF → OUT1-4, IN A, 0dB/0ms/+/ON).

**[K1SB_X K2] / [K1SB_60] / [K1SB_100_NC]** — K1-SB와 동일 구조(4채널 SB, IN A). *[K1SB_X K2]는 10dB 헤드룸 제공.*

**[KARADOWNK2] / [KARAIIDOWNK2] / [KARAIIDOWNK2 70] / [KARAIIDOWNK2 90]** — K1과 동일 구조(LF/HF/LF/HF → OUT1-4). *[KARAIIDOWNK2]는 Kara II 110° 최적화, 4종 모두 11dB 헤드룸 제공.*

## 9. Variable Curvature WST systems presets — K3 (p.53-54)

**참고**: K3와 K3i는 동일 인클로저의 다른 버전 — 팩토리 프리셋/권장 구성 공유(K3i는 K3와 동일 표 적용). KS21/KS21i, Kara II/Kara IIi도 각각 동일 관계.

| 인클로저 구성 | K3 | KS28/KS21 | CS1 | 음향 특성 |
|---|---|---|---|---|
| K3 라인소스 | [K3 xxx] | — | — | 42Hz-20kHz, adjustable horizontal directivity |
| K3 라인소스+서브우퍼 | [K3 xxx] | [KSxx_60] | — | down to 29Hz(KS21) or 25Hz(KS28), reinforced LF contour |
| K3 라인소스+CS1 결합서브(베사이드/비하인드) | [K3 xxx] | — | [CS1_60] | down to 25Hz, reinforced LF contour, LF rejection(rear cardioid) |
| K3 라인소스+CS1 결합서브(슈퍼카디오이드) | [K3 xxx] | — | [CS1_60_S] | down to 25Hz, reinforced LF contour, supercardioid pattern |

*카디오이드 서브우퍼 어레이는 [KSxx_xx_C] 또는 [KSxx_xx_Cx] 사용.*

**조절식 핀**: [K3 70]=70°, [K3 90]=90°, [K3 110]=110°. **다운필**: K3는 Kara([KARADOWNK3]) 또는 Kara II([KARAIIDOWNK3] 110°/[KARAIIDOWNK3 70]/[KARAIIDOWNK3 90]) 사용, K3i는 Kara IIi([KARAIIDOWNK3] 110°/70°/90°)만 사용.

**[K3 xxx]** — K1/K2와 동일 구조(LF/HF/LF/HF → OUT1-4, IN A, 0dB/0ms/+/ON, LF+HF 2채널 구조).

**[KARADOWNK3] / [KARAIIDOWNK3] / [KARAIIDOWNK3 70] / [KARAIIDOWNK3 90]** — K1/K2 다운필과 동일 구조(LF/HF/LF/HF → OUT1-4). *[KARAIIDOWNK3]는 Kara II(i) 110° 최적화, 4종 모두 15dB 헤드룸 제공.*

## 10. Variable Curvature WST systems presets — Kara II (p.55-56)

**참고**: Kara II/Kara IIi, SB18/SB18 IIi, KS21/KS21i 각각 동일 인클로저 버전 관계(프리셋/권장구성 공유).

| 인클로저 구성 | Kara II | SB18/KS21 | KS28/SB28 | 음향 특성 |
|---|---|---|---|---|
| 라인소스 | [KARA II xxx] | — | — | 55Hz-20kHz |
| 라인소스+결합서브 | [KARA II xxx] | [xxxx_100] | — | down to 32Hz(SB18)/31Hz(KS21)/25Hz(KS28/SB28), reinforced LF contour |
| 라인소스+분리서브 | [KARA II xxx] | [xxxx_60] | — | 동일 |
| 라인소스+결합서브+KS28/SB28 | [KARA II xxx] | [xxxx_100] | [xxxx_60] | 동일 |
| 단일/2대 인클로저 | [KARA II_FI] | — | — | high-pass 100Hz, flat response |
| 단일/2대 인클로저+결합서브 | [KARA II_FI] | [xxxx_100] | — | down to 32Hz(SB18)/31Hz(KS21), flat response, reinforced LF contour |
| 최대 3대 인클로저 | [KARA II_MO] | — | — | 55Hz-20kHz, low latency |
| 최대 3대+결합서브 | [KARA II_MO] | [xxxx_60] | — | down to 32Hz(SB18)/29Hz(KS21), reinforced LF contour, low latency |

*카디오이드 서브우퍼는 [xxxx_xx_C]/[xxxx_xx_Cx] 사용.*

**조절식 핀**: [KARA II 70]=70°, [KARA II 90]=90°, [KARA II 110]=110°.

**[xx_MO] 프리셋 주의(레거시 XT/MTD 제외)**: 컨트롤러 저지연 모드 사용 — 서브우퍼 병용 시 서브우퍼도 저지연 모드 권장. 4-출력 컨트롤러는 저지연 채널세트+서브우퍼 채널세트를 커스텀 조합해야 함. 서브우퍼가 별도 4-출력 컨트롤러의 일반(저지연 아닌) 프리셋으로 구동되면, [xx_MO] 저지연 채널에 추가 딜레이 필요(정렬용): LA4/LA8=2.66ms, LA2Xi/LA4X/LA12X=3.00ms. 16출력 컨트롤러는 서브우퍼 동반 채널도 [xx_MO] 프리셋 선택 시 저지연 혜택.

**Kara와 Kara II 동일 라인소스 병용 비권장**: 음향 결합이 최적이 아님.

**[KARA II 70]/[KARA II 90]/[KARA II 110]** — LF/HF/LF/HF → OUT1-4, IN A, 0dB/0ms/+/ON.
**[KARA II_FI]/[KARA II_MO]** — LF/HF(IN A)/LF/HF(IN B) → OUT1-4, 0dB/0ms/+/ON. *110° 핀 설정 최적화.*

## 11. Variable Curvature WST systems presets — Kara (p.57)

**참고**: Kara/Karai 동일 인클로저 버전 관계.

| 인클로저 구성 | Kara | KS28/SB28/SB18/KS21 | 음향 특성 |
|---|---|---|---|
| 라인소스 | [KARA] | — | 55Hz-20kHz |
| 라인소스+결합서브 | [KARA] | [xxxx_100] | down to 32Hz(SB18)/31Hz(KS21)/25Hz(KS28/SB28), reinforced LF contour |
| 라인소스+분리서브 | [KARA] | [xxxx_60] | 동일 |
| 단일/2대 인클로저 | [KARA_FI] | — | high-pass 100Hz, flat response |

*카디오이드 서브우퍼는 [xxxx_xx_C]/[xxxx_xx_Cx] 사용.*

**[KARA]** — LF/HF/LF/HF → OUT1-4, IN A, 0dB/0ms/+/ON.
**[KARA_FI]** — LF/HF(IN A)/LF/HF(IN B) → OUT1-4, 0dB/0ms/+/ON.

## 12. Variable Curvature WST systems presets — Kiva II (p.58)

| 인클로저 구성 | Kiva II | SB15m | SB18 | 음향 특성 |
|---|---|---|---|---|
| 라인소스 | [KIVA II] | — | — | 70Hz-20kHz |
| 라인소스+결합서브 | [KIVA II] | [SB15_100] | [SB18_60] | down to 32Hz(SB18)/40Hz(SB15m), reinforced LF contour |
| 최대 3대 인클로저 | [KIVA II_FI] | — | — | 70Hz-20kHz, flat response |
| 최대 3대+결합서브 | [KIVA II_FI] | [SB15_100] | — | down to 40Hz, reinforced LF contour |

*카디오이드 서브우퍼는 [SB1x_xx_C]/[SB1x_xx_Cx] 사용.*

**[KIVA II]** — 4채널 PA, IN A, 0dB/0ms/+/ON.
**[KIVA II_FI]** — OUT1-2 PA(IN A), OUT3-4 PA(IN B), 0dB/0ms/+/ON.

## 13. Variable Curvature WST systems presets — Kiva/SB15m (p.59)

| 인클로저 구성 | Kiva | SB15m | 음향 특성 |
|---|---|---|---|
| 라인소스 | [KIVA] | — | 80Hz-20kHz |
| 라인소스+결합서브 | [KIVA_SB15](hybrid) 또는 [KIVA]+[SB15_100] | — | down to 40Hz, reinforced LF contour |
| 단일/2대 인클로저 | [KIVA_FI] | — | 80Hz-20kHz, flat response |
| 2대 인클로저+결합서브 | [KIVA_FI] | [SB15_100] | down to 40Hz, reinforced LF contour |

*카디오이드 서브우퍼는 [SB15_100_C]/[SB15_100_Cx] 사용.*

**[KIVA]/[KIVA_FI]** — K1-SB류와 동일 4채널 PA 구조(FI는 IN A/IN B 분리).
**[KIVA_SB15]** — SB15m(OUT1, LF, IN A)+Kiva(OUT2-4, PA, IN A) 결합, 0dB/0ms/+/ON. *[KIVA]+[SB15_100] 결합 하이브리드 프리셋, 사전정렬딜레이 내장.*

## 14. Variable Curvature WST systems presets — Kiva Kilo (p.60-61)

| 인클로저 구성 | Kiva | Kilo | SB18 | 음향 특성 |
|---|---|---|---|---|
| 라인소스 | [KIVA] | — | — | 80Hz-20kHz |
| 라인소스+결합Kilo | [KIVA_KILO](hybrid) | 포함 | — | down to 50Hz |
| 라인소스+결합Kilo+SB18 | [KIVA_KILO](hybrid) | 포함 | [SB18_100] | down to 32Hz, reinforced LF contour |
| 단일/2대 인클로저 | [KIVA_FI] | — | — | 80Hz-20kHz, flat response |

*카디오이드 서브우퍼는 [SB18_100_C]/[SB18_100_Cx] 사용.*

**[KIVA]/[KIVA_FI]** — Kiva II와 동일 구조(4채널 PA, FI는 IN A/IN B 분리).
**[KIVA_KILO]** — KILO(OUT1, LF, IN A)+KIVA(OUT2-4, PA, IN A) 결합, 0dB/0ms/+/ON. *[KIVA]+[KILO] 결합 하이브리드, 사전정렬딜레이 내장.*
**[KILO]** — 4채널 SB, IN A, 0dB/0ms/+/ON.

## 15. Variable Curvature WST systems presets — Kudo (p.62)

| 인클로저 구성 | Kudo | KS28/SB28/SB18 | 음향 특성 |
|---|---|---|---|
| 라인소스 | [KUDOxx_25] | — | 35Hz-20kHz |
| 라인소스 | [KUDOxx_40] | — | 40Hz-20kHz |
| 라인소스 | [KUDOxx_60] | — | 60Hz-20kHz |
| 라인소스+서브우퍼 | [KUDOxx_40] | [xxx8_60] | down to 25Hz(KS28/SB28)/32Hz(SB18), reinforced LF contour |

*카디오이드 서브우퍼는 [xxx8_60_C]/[xxx8_60_Cx] 사용.*

**K-LOUVER**: [KUDO50_xx]=50°, [KUDO80_xx]=80°, [KUDO110_xx]=110°(K-LOUVER 패널 각도와 프리셋 일치 필수).

**[KUDOxx_xx]** — left LF/right LF/MF/HF → OUT1-4, IN A, 0dB/0ms/+/ON(K1/K2류와 동일 3-way 구조, left/right는 전면 기준).

## 16. Variable Curvature WST systems presets — V-DOSC (p.63-64)

| 인클로저 구성 | V-DOSC | dV-SUB | KS28/SB28/SB218 | 음향 특성 |
|---|---|---|---|---|
| 라인소스 | [V-DOSC_LO] 또는 [V-DOSC_HI] | — | — | 40Hz-20kHz |
| 라인소스+결합dV-SUB | [V-DOSC_xx_X] | [dV-S_X] | — | down to 35Hz, reinforced LF contour |
| 라인소스+KS28/SB28 | [V-DOSC_xx_60] | — | [xx28_60] | down to 25Hz, reinforced LF contour |
| 라인소스+결합SB218 | [V-DOSC_xx_X] | — | [SB218_X] | down to 25Hz, reinforced LF contour |
| 라인소스+dV-SUB+KS28/SB28 | [V-DOSC_xx_60] | [dV-S_60_X] | [xx28_60] | down to 25Hz, reinforced LF contour+additional LF resources |

*[xx_LO]=표준 HF contour, [xx_HI]=증강 HF contour. 카디오이드 서브우퍼(KS28/SB28)는 [xxxx_xx_C]/[xx28_xx_Cx] 사용.*

**다운필**: dV-DOSC는 [dV_xx_100]로 구동.

**[V-DOSC_LO], [V-DOSC_HI], [V-DOSC_xx_60], [V-DOSC_xx_X]** — left LF/right LF/MF/HF → OUT1-4, IN A, 0dB/0ms/+/ON(전면 기준).
**[dV-S_X], [dV-S_60_X], [SB218_X]** — 4채널 SB, IN A, 0dB/0ms/+/ON.

## 17. Variable Curvature WST systems presets — dV-DOSC (p.65-66)

| 인클로저 구성 | dV-DOSC | dV-SUB | KS28/SB218/SB28/SB18/SB118 | 음향 특성 |
|---|---|---|---|---|
| 라인소스 | [dV_LO] 또는 [dV_HI] | — | — | 65Hz-20kHz |
| 라인소스+결합dV-SUB | [dV_dV-S_xx] | 포함 | — | down to 35Hz, reinforced LF contour |
| 라인소스+결합dV-SUB(대체표기) | [dV_xx_100] | [dV-S_100] | — | 동일 |
| 라인소스+서브우퍼 | [dV_xx_100] | — | [xxxx_100] | down to 32Hz(SB18/SB118)/25Hz(KS28/SB28/SB218), reinforced LF contour |
| 라인소스+dV-SUB+서브우퍼 | [dV_dV-S_xx60] | 포함 | [xxxx_60] | down to 32Hz/25Hz, reinforced LF contour |
| 라인소스+dV-SUB+서브우퍼(대체표기) | [dV_xx_100] | [dV-S_60_100] | [xxxx_60] | 동일 |
| 단일/2대 인클로저 | [dV_FI] | — | — | high-pass 100Hz, flat response |

*[xx_LO]=표준 HF contour, [xx_HI]=증강 HF contour. 카디오이드 서브우퍼(KS28/SB28/SB18)는 [xxxx_xx_C]/[xxxx_xx_Cx] 사용.*

**[dV_LO], [dV_HI], [dV_xx_60], [dV_xx_100]** — LF/HF/LF/HF → OUT1-4, IN A, 0dB/0ms/+/ON.
**[dV_FI]** — LF/HF(IN A)/LF/HF(IN B) → OUT1-4, 0dB/0ms/+/ON.
**[dV-S_100], [dV-S_60_100]** — 4채널 SB, IN A, 0dB/0ms/+/ON.
**[dV_dV-S_HI], [dV_dV-S_HI60], [dV_dV-S_LO], [dV_dV-S_LO60]** — dV-SUB(OUT1-2, SB, IN A)+dV-DOSC LF(OUT3, IN A)+dV-DOSC HF(OUT4, IN A) 결합, 0dB/0ms/+/ON. *[dV_dV-S_xx]는 [dV_LO_100]/[dV_HI_100]+[dV-S_100] 결합 하이브리드, [dV_dV-S_xx60]은 [dV_LO_100]/[dV_HI_100]+[dV-S_60_100] 결합 하이브리드, 둘 다 사전정렬딜레이 내장.*

**Variable Curvature WST systems presets 섹션(p.49-66) 완료.**

## 18. Constant Curvature WST systems presets — ARCS Wide/Focus (p.67)

중거리 투사 최적화 상수곡률 WST 시스템.

| 인클로저 구성 | ARCS Wide/Focus | SB18 | 음향 특성 |
|---|---|---|---|
| 라인소스 | [ARCS_WIFO] | — | 55Hz-20kHz |
| 라인소스+SB18 | [ARCS_WIFO] | [SB18_60] | down to 32Hz, reinforced LF contour |
| 단일 인클로저 | [ARCS_WIFO_FI] | — | 55Hz-20kHz, flat response |
| 단일 인클로저+SB18m | [ARCS_WIFO_FI] | [SB18_60] | down to 32Hz, reinforced LF contour |

*카디오이드 서브우퍼는 [SB18_60_C]/[SB18_60_Cx] 사용.*

**[ARCS_WIFO]** — 4채널 PA, IN A, 0dB/0ms/+/ON.
**[ARCS_WIFO_FI]** — OUT1-2 PA(IN A), OUT3-4 PA(IN B), 0dB/0ms/+/ON.

## 19. Constant Curvature WST systems presets — A10 Wide/Focus (p.68-69)

**참고**: A10/A10i, KS21/KS21i 각각 동일 인클로저 버전 관계.

| 인클로저 구성 | A10 Wide/Focus | KS21 | 음향 특성 |
|---|---|---|---|
| 라인소스 | [A10] | — | 66Hz-20kHz(Focus)/67Hz-20kHz(Wide) |
| 라인소스+KS21 | [A10] | [KS21_100] | down to 31Hz, reinforced LF contour |
| 단일 인클로저 | [A10_FI] | — | 66/67Hz-20kHz, flat response |
| 단일 인클로저 | [A10_MO] | — | 66/67Hz-20kHz, flat response, low latency |
| 단일 인클로저+KS21 | [A10_FI] | [KS21_100] | down to 31Hz, reinforced LF contour |
| 단일 인클로저+KS21 | [A10_MO] | [KS21_100] | down to 31Hz, reinforced LF contour, low latency |

*카디오이드 서브우퍼는 [KS21_100_C]/[KS21_100_Cx] 사용. [xx_MO] 저지연 정렬 규칙은 10절(Kara II) 참조.*

**[A10]** — 4채널 PA, IN A, 0dB/0ms/+/ON.
**[A10_FI]/[A10_MO]** — OUT1-2 PA(IN A), OUT3-4 PA(IN B), 0dB/0ms/+/ON.

## 20. Constant Curvature WST systems presets — A15 Wide/Focus (p.70-71)

| 인클로저 구성 | A15 Wide/Focus | KS21 | 음향 특성 |
|---|---|---|---|
| 라인소스 | [A15] | — | 41Hz-20kHz(Focus)/42Hz-20kHz(Wide) |
| 라인소스+KS21 | [A15] | [KS21_60] | down to 29Hz, reinforced LF contour |
| 단일 인클로저 | [A15_FI] | — | 42/43Hz-20kHz, flat response |
| 단일 인클로저 | [A15_MO] | — | 42/43Hz-20kHz, flat response, low latency |
| 단일 인클로저+KS21 | [A15_FI] | [KS21_60] | down to 29Hz, reinforced LF contour |
| 단일 인클로저+KS21 | [A15_MO] | [KS21_60] | down to 29Hz, reinforced LF contour, low latency |

*카디오이드 서브우퍼는 [KS21_60_C]/[KS21_60_Cx] 사용.*

**[A15]** — 4채널 PA, IN A, 0dB/0ms/+/ON.
**[A15_FI]/[A15_MO]** — OUT1-2 PA(IN A), OUT3-4 PA(IN B), 0dB/0ms/+/ON.

## 21. Constant Curvature WST systems presets — ARCS II (p.72)

| 인클로저 구성 | ARCS II | KS28/SB28 | 음향 특성 |
|---|---|---|---|
| 라인소스 | [ARCS II] | — | 50Hz-20kHz |
| 라인소스+서브우퍼 | [ARCS II] | [xx28_60] | down to 25Hz, reinforced LF contour |

*카디오이드 서브우퍼는 [xx28_60_C]/[xx28_60_Cx] 사용.*

**[ARCS II]** — LF/HF/LF/HF → OUT1-4, IN A, 0dB/0ms/+/ON.

## 22. Constant Curvature WST systems presets — ARCS (p.73)

| 인클로저 구성 | ARCS | SB18/SB118/KS28/SB28/SB218 | 음향 특성 |
|---|---|---|---|
| 라인소스 | [ARCS_LO] 또는 [ARCS_HI] | — | 50Hz-20kHz |
| 라인소스+서브우퍼 | [ARCS_xx_60] | [xxxx_60] | down to 32Hz(SB18/SB118)/25Hz(KS28/SB28/SB218), reinforced LF contour |
| 라인소스+결합서브 | [ARCS_xx_100] | [xxxx_100] | 동일 |

*[xx_LO]=표준 HF contour, [xx_HI]=증강 HF contour. 카디오이드 서브우퍼(SB18/KS28/SB28)는 [xxxx_xx_C]/[xxxx_xx_Cx] 사용.*

**[ARCS_LO], [ARCS_HI], [ARCS_xx_60], [ARCS_xx_100]** — LF/HF/LF/HF → OUT1-4, IN A, 0dB/0ms/+/ON.

**Constant Curvature WST systems presets 섹션(p.67-73) 완료.**

## 23. Colinear systems presets — Syva (p.74-75)

콜리니어 소스(동축 미드/하이 위에 LF 결합) 중거리 투사 최적화.

| 인클로저 구성 | Syva | Syva Low | Syva Sub | 음향 특성 |
|---|---|---|---|---|
| 콜리니어 소스 | [SYVA] | — | — | 87Hz-20kHz |
| 콜리니어 소스+밀착결합 Syva Low | [SYVA LOW SYVA] | 포함 | — | down to 42Hz, reinforced LF contour |
| 콜리니어 소스+결합 Syva Low | [SYVA] | [SYVA LOW_100] | — | down to 40Hz, reinforced LF contour |
| 콜리니어 소스+밀착결합 Syva Sub | [SYVA SUB SYVA] | — | 포함 | down to 28Hz |
| 콜리니어 소스+결합 Syva Sub | [SYVA] | — | [SYVA SUB_100] | down to 27Hz |
| 콜리니어 소스+밀착결합 Syva Low+Syva Sub | [SYVA LOW SYVA] | 포함 | [SYVA SUB_100] | down to 27Hz, reinforced LF contour |
| 콜리니어 소스+분리 Syva Low+Syva Sub | [SYVA] | [SYVA LOW_100] | [SYVA SUB_100] | down to 27Hz, reinforced LF contour |

**[SYVA] 사용 시 주의**: [SYVA SUB_100]와 병용할 때 Syva 게인을 5dB 낮춰야 flat response 확보.

**[SYVA]** — 4채널 PA, IN A, 0dB/0ms/+/ON.
**[SYVA LOW SYVA]** — Syva Low(OUT1, LF, IN A)+Syva(OUT2, PA, IN A)+Syva Low(OUT3, LF, IN B)+Syva(OUT4, PA, IN B), 0dB/0ms/+/ON. *AutoConnect로 Syva Low가 Syva 바로 위/아래 밀착 배치일 때만 사용, 이격 시 [SYVA]+[SYVA LOW_100] 커스텀 조합 권장.*
**[SYVA SUB SYVA]** — Syva Sub(OUT1, LF, IN A)+Syva(OUT2, PA, IN A)+Syva Sub(OUT3, LF, IN B)+Syva(OUT4, PA, IN B), 0dB/0ms/+/ON. *동일 원칙(AutoConnect 밀착배치 전용).* **[SYVA SUB_200]는 Syva와 병용 금지**(X4 프리셋 전용 최적화).

## 24. Colinear systems presets — Soka (p.76)

| 인클로저 구성 | Soka | SB6i/SB10i/Syva Sub | 음향 특성 |
|---|---|---|---|
| 콜리니어 소스 | [SOKA] | — | 100Hz-20kHz |
| 콜리니어 소스+밀착결합 서브 | [SOKA_200] | [SBxx_200] | down to 32Hz(SB6i)/29Hz(SB10i), reinforced LF contour |
| 콜리니어 소스+결합 서브 | [SOKA] | [SBxx_100] | down to 29Hz(SB6i)/27Hz(SB10i), reinforced LF contour |
| 콜리니어 소스+분리 서브 | [SOKA_60] | [xxx_60] | down to 29Hz(SB6i)/25Hz(SB10i)/26Hz(Syva Sub), reinforced LF contour |

**[SOKA]** — 4채널 PA, IN A, 0dB/0ms/+/ON.

**Colinear systems presets 섹션(p.74-76) 완료. Constant Curvature+Colinear WST systems presets 섹션(p.67-76) 전체 완료.**

## 25. Coaxial loudspeaker enclosures presets — X4i (p.77-78)

단거리 투사 최적화, 패시브 코액시얼 인클로저.

| 인클로저 구성 | X4i | SB6i/SB10i | Syva Sub | 음향 특성 |
|---|---|---|---|---|
| 단일 인클로저 | [X4] | — | — | 120Hz-20kHz |
| 단일 인클로저 | [X4_MO] | — | — | 120Hz-20kHz, low latency |
| 단일/2대+밀착결합 서브 | [X4] | [SBxx_200] | [SYVA SUB_200] | down to 32Hz(SB6i)/29Hz(SB10i/Syva Sub), reinforced LF contour |
| 단일/2대+밀착결합 서브 | [X4_MO] | [SBxx_200] | [SYVA SUB_200] | 동일, low latency |
| 단일/2대+결합 서브 | [X4] | [SBxx_100] | — | down to 29Hz(SB6i)/27Hz(SB10i), reinforced LF contour |
| 단일/2대+결합 서브 | [X4_MO] | [SBxx_100] | — | 동일, low latency |
| 단일/2대+분리 서브 | [X4_60] | [SBxx_60] | — | down to 29Hz(SB6i)/25Hz(SB10i), reinforced LF contour |

**[X4], [X4_60], [X4_MO]** — 4채널 PA(IN A/IN A/IN B/IN B), 0dB/0ms/+/ON.

## 26. Coaxial loudspeaker enclosures presets — 5XT (p.79)

패시브 코액시얼.

| 인클로저 구성 | 5XT | SB15m/SB10i | 음향 특성 |
|---|---|---|---|
| 단일 인클로저 | [5XT] | — | 95Hz-20kHz |
| 단일 인클로저 | [5XT_MO] | — | 95Hz-20kHz, low latency |
| 단일+서브 | [5XT] | [xxxx_100] | down to 40Hz(SB15m)/27Hz(SB10i), reinforced LF contour |
| 단일+서브 | [5XT_MO] | [xxxx_100] | 동일, low latency |

**[5XT], [5XT_MO]** — 4채널 PA(IN A/IN A/IN B/IN B), 0dB/0ms/+/ON.

## 27. Coaxial loudspeaker enclosures presets — X6i (p.80)

패시브 코액시얼.

| 인클로저 구성 | X6i | SB6i/SB10i/Syva Sub | 음향 특성 |
|---|---|---|---|
| 단일 인클로저 | [X6i] | — | 69Hz-20kHz |
| 단일 인클로저 | [X6i_50] | — | 54Hz-20kHz |
| 단일 인클로저 | [X6i_MO] | — | 65Hz-20kHz, low latency |
| 단일+밀착결합 서브 | [X6i]/[X6i_50] | [SBxx_200] | down to 32Hz(SB6i)/29Hz(SB10i), reinforced LF contour |
| 단일+결합 서브 | [X6i]/[X6i_50] | [SBxx_100] | down to 29Hz(SB6i)/27Hz(SB10i), reinforced LF contour |
| 단일+분리 서브 | [X6i_50] | [SYVA SUB_60] | down to 26Hz |

**[X6i], [X6i_50], [X6i_MO]** — 4채널 PA(IN A/IN A/IN B/IN B), 0dB/0ms/+/ON.

## 28. Coaxial loudspeaker enclosures presets — X8 (p.81)

패시브 코액시얼.

| 인클로저 구성 | X8 | SB15m | 음향 특성 |
|---|---|---|---|
| 단일 인클로저 | [X8] | — | 60Hz-20kHz |
| 단일 인클로저 | [X8_MO] | — | 55Hz-20kHz, low latency |
| 단일+SB15m | [X8] | [SB15_100] | down to 40Hz, reinforced LF contour |
| 단일+SB15m | [X8_MO] | [SB15_100] | 동일, low latency |

**[X8], [X8_MO]** — 4채널 PA(IN A/IN A/IN B/IN B), 0dB/0ms/+/ON.

## 29. Coaxial loudspeaker enclosures presets — X8i (p.82)

패시브 코액시얼. **참고**: KS21/KS21i 동일 인클로저 버전 관계.

| 인클로저 구성 | X8i | SB10i/KS21/Syva Sub | 음향 특성 |
|---|---|---|---|
| 단일 인클로저 | [X8i] | — | 67Hz-20kHz |
| 단일 인클로저 | [X8i_40] | — | 43Hz-20kHz |
| 단일 인클로저 | [X8i_MO] | — | 59Hz-20kHz, low latency |
| 단일+결합 서브 | [X8i]/[X8i_40] | [xxx_100] | down to 27Hz(SB10i/Syva Sub)/31Hz(KS21), reinforced LF contour |
| 단일+분리 서브 | [X8i]/[X8i_40] | [xxx_60] | down to 25Hz(SB10i/KS21)/26Hz(Syva Sub), reinforced LF contour |

**[X8i], [X8i_40], [X8i_MO]** — 4채널 PA(IN A/IN A/IN B/IN B), 0dB/0ms/+/ON.

## 30. Coaxial loudspeaker enclosures presets — X12 (p.83)

패시브 코액시얼.

| 인클로저 구성 | X12 | SB15m/SB18/KS21 | 음향 특성 |
|---|---|---|---|
| 단일 인클로저 | [X12] | — | 59Hz-20kHz |
| 단일 인클로저 | [X12_MO] | — | 57Hz-20kHz, low latency |
| 단일+서브 | [X12] | [xxxx_100] | down to 40Hz(SB15m)/32Hz(SB18) reinforced LF contour |
| 단일+서브 | [X12_MO] | [xxxx_100] | 동일, low latency |

**[X12], [X12_MO]** — 4채널 PA(IN A/IN A/IN B/IN B), 0dB/0ms/+/ON.

## 31. Coaxial loudspeaker enclosures presets — X15 HiQ (p.84)

**액티브** 코액시얼 인클로저(다른 X 시리즈는 패시브).

| 인클로저 구성 | X15 HiQ | SB18/KS21 | 음향 특성 |
|---|---|---|---|
| 단일 인클로저 | [X15] | — | 55Hz-20kHz |
| 단일 인클로저 | [X15_MO] | — | 52Hz-20kHz, low latency |
| 단일+서브 | [X15] | [xxxx_100] | down to 32Hz, reinforced LF contour |
| 단일+서브 | [X15_MO] | [xxxx_100] | 동일, low latency |

**[X15], [X15_MO]** — LF/HF/LF/HF → OUT1-4(IN A/IN A/IN B/IN B), 0dB/0ms/+/ON. *다른 X 시리즈(4채널 PA)와 달리 LF/HF 분리 채널 구조 — 액티브 아키텍처 차이 반영.*

*[xx_MO] 저지연 정렬 규칙(4-출력 컨트롤러 커스텀 조합, 서브우퍼 정렬 딜레이 2.66/3.00ms 등)은 10절(Kara II) 참조, X4i~X15 HiQ 전체에 동일 적용.*

## 32. Coaxial loudspeaker enclosures presets — 8XT, 12XTP, MTD108a, MTD112b, MTD115bP (p.85)

**레거시 패시브** 코액시얼 인클로저 5종 공용 프리셋 구조.

**프리셋명**: 8XT=`[8XT_xx]` / 12XTP(패시브 모드)=`[12XTP_xx]` / MTD108a=`[108a_xx]` / MTD112b=`[112b_xx]` / MTD115b(패시브 모드)=`[115bP_xx]`.

| 인클로저 구성 | 패시브 xxx | SB15m/SB18/SB118 | 음향 특성 |
|---|---|---|---|
| 코액시얼 | [xxx_FR]/[xxx_FI]/[xxx_MO] | — | nominal bandwidth |
| 코액시얼+결합 서브 | [xxx_xx_100] | [SBxx_100] | down to 40Hz(SB15m)/32Hz(SB18/SB118), reinforced LF contour |

*[xxx_FR]=FOH, [xxx_FI]=스포큰워드/클래식/필, [xxx_MO]=하프스페이스(바닥/벽/천장) flat. 카디오이드 서브우퍼는 [SBxx_xx_C]/[SBxx_xx_Cx] 사용. 3개 컨투어(FR/FI/MO) 중 택1하는 구조.*

**[xxx_FR], [xxx_FI], [xxx_MO], [xxx_xx_100]** — 4채널 PA(IN A/IN A/IN B/IN B), 0dB/0ms/+/ON.

## 33. Coaxial loudspeaker enclosures presets — 12XTA, 115XT, 115XT HiQ, MTD115bA (p.86)

**레거시 액티브** 코액시얼 인클로저 4종 공용 프리셋 구조.

**프리셋명**: 12XT(액티브 모드)=`[12XTA_xx]` / 115XT HiQ=`[HiQ_xx]` / MTD115b(액티브 모드)=`[115bA_xx]` / 115XT=`[115XT_xx]`.

| 인클로저 구성 | 액티브 xxx | SB18/SB118 | 음향 특성 |
|---|---|---|---|
| 코액시얼 | [xxx_FR]/[xxx_FI]/[xxx_MO] | — | nominal bandwidth |
| 코액시얼+결합 서브 | [xxx_xx_100] | [SBxx_100] | down to 32Hz, reinforced LF contour |

*카디오이드 서브우퍼는 [SBxx_xx_C]/[SB18_100_Cx] 사용.*

**[xxx_FR], [xxx_FI], [xxx_MO], [xxx_xx_100]** — LF/HF/LF/HF → OUT1-4(IN A/IN A/IN B/IN B), 0dB/0ms/+/ON. *레거시 액티브 계열은 LF/HF 분리 채널 구조(X15 HiQ와 동일 패턴).*

**Coaxial loudspeaker enclosures presets 섹션(p.77-86) 완료.**

## 34. Subwoofer loudspeaker enclosures presets (p.87-90)

L-Acoustics 범용 서브우퍼 전체를 다루는 섹션. 카디오이드 구성 일반 원칙은 3.5절(Preset design) 참조.

**헤드룸**: SB15m [SB15_100]/[SB15_100_C]는 프리셋 라이브러리 v5.6(.5)부터 8dB, [SB15_100_Cx]도 8dB. 구버전 프리셋+[KIVA_SB15]는 4dB. K1-SB/KS28/SB28/SB18/SB218/SB118은 v6.0에서 8dB로 게인 조정 — 구버전(v6.0 이전) 프리셋 게인 보정값: [SB28_60]/[SB218_60] +4dB, [KS28_60]/[SB_28_100]/[SB18_60]/[SB18_100]/[SB218_100]/[SB118_60]/[SB118_100] +3dB, [KS28_100] +2dB, [K1SB_60] +1dB.

### 34.1 Optimal subwoofer compatibilities (p.87-88)

| 서브우퍼 인클로저 | 프리셋 | 최적 호환 대상 |
|---|---|---|
| CS1 | [CS1_60] / [CS1_60_S] | K1, K2, K3(i), L2, L2D |
| KS28 | [KS28_60]/[KS28_60_C]/[KS28_60_Cx] | K1, K2, K3(i), V-DOSC, Kudo, dV-DOSC/dV-SUB, Kara/SB18, Kara II(i), ARCS, ARCS II |
| KS28 | [KS28_100]/[KS28_100_C]/[KS28_100_Cx] | dV-DOSC, Kara, ARCS(coupled) |
| KS28 | [KS28 L2]/[KS28 L2_C]/[KS28 L2_Cx] | L2, L2D |
| SB28 | [SB28_60]/[SB28_60_C]/[SB28_60_Cx] | K1, K2, V-DOSC, Kudo, dV-DOSC/dV-SUB, Kara/SB18, Kara II(i), ARCS, ARCS II |
| SB28 | [SB28_100]/[SB28_100_C]/[SB28_100_Cx] | dV-DOSC, Kara, ARCS(coupled) |
| KS21(i) | [KS21_60]/[KS21_60_C]/[KS21_60_Cx] | A15(i) Wide/Focus, Kara(i), Kara II(i), K3(i), X8i |
| KS21(i) | [KS21_100]/[KS21_100_C]/[KS21_100_Cx] | A10(i) Wide/Focus, X15 HiQ, X12, XT, Kara(i), Kara II(i), X8i |
| SB18(i/m)/SB18 IIi | [SB18_60]/[SB18_60_C]/[SB18_60_Cx] | Kudo, Kara, Kara II(i), Kiva/Kilo, ARCS, ARCS Wide, ARCS Focus |
| SB18(i/m)/SB18 IIi | [SB18_100]/[SB18_100_C]/[SB18_100_Cx] | Kara, Kara II(i), ARCS, XT, X series, Kiva II |
| SB218 | [SB218_60] | V-DOSC, Kudo, dV-DOSC/dV-SUB, ARCS |
| SB218 | [SB218_100] | dV-DOSC, ARCS(coupled) |
| SB118 | [SB118_60]/[SB118_60_C] | Kudo, dV-DOSC/dV-SUB, Kiva/Kilo, ARCS |
| SB118 | [SB118_100]/[SB118_100_C] | dV-DOSC, ARCS, XT, MTD(coupled) |
| SB15m | [SB15_100]/[SB15_100_C]/[SB15_100_Cx] | Kiva(coupled), Kiva II(coupled), XT, X12, X8 |
| SB10i | [SB10_60] | X8i, X6i |
| SB10i | [SB10_100] | X4i(coupled), 5XT, X8i, X6i |
| SB10i | [SB10_200] | X6i(closely coupled) |
| SB6i | [SB6_60] | X4i, X6i |
| SB6i | [SB6_100] | X4i(coupled), X6i(coupled) |
| SB6i | [SB6_200] | X6i(closely coupled) |
| Syva Low | [SYVA LOW SYVA] | Syva(coupled), Syva+Syva Sub(coupled) |
| Syva Low | [SYVA LOW_100] | Syva, Syva+Syva Sub |
| Syva Sub | [SYVA SUB_60] | Soka, X8i, X6i |
| Syva Sub | [SYVA SUB_100] | Syva/Syva Low, Syva/Syva Low(coupled), X8i |
| Syva Sub | [SYVA SUB_200] | X4i |

### 34.2 Acoustic properties of subwoofers (p.89)

| 구성 | 프리셋 | 음향 특성 |
|---|---|---|
| standard | [xxxx_60]/[xxxx_100]/[xxxx_200] | down to 25Hz(KS28/SB28/SB218/SB10i), 26Hz(Syva Sub), 27Hz(Syva Low), 29Hz(KS21/SB6i), 32Hz(SB18/SB118), 40Hz(SB15m/Syva Low) |
| cardioid C | [xxxx_60_C]/[xxxx_100_C] | down to 25Hz(KS28/SB28), 29Hz(KS21), 32Hz(SB18/SB118), 40Hz(SB15m), cardioid directivity pattern |
| cardioid Cx | [xxxx_60_Cx]/[xxxx_100_Cx] | down to 25Hz(KS28/SB28), 29Hz(KS21), 32Hz(SB18), 40Hz(SB15m), extended cardioid directivity pattern |
| cardioid | [CS1_xx] | down to 25Hz(CS1), cardioid directivity pattern |
| supercardioid | [CS1_xx_S] | down to 25Hz(CS1), supercardioid pattern |

*SB28/SB218은 LA8/LA12X 전용 구동. KS28은 LA2Xi/LA12X 전용 구동. CS1은 LA7.16/LA12X 전용 구동.*

**[xxxx_60], [xxxx_100], [xxxx_200]** — 4채널 SB, IN A, 0dB/0ms/+/ON.
**[xxxx_60_C], [xxxx_100_C], [xxxx_60_Cx], [xxxx_100_Cx]** — SR(OUT1)+SB(OUT2-4), IN A, 0dB/0ms/+/ON(6절 [KS28 L2_C]와 동일 카디오이드 구조).
**[CS1_xx], [CS1_xx_S]** — SC(OUT1)+SB(OUT2)+SB(OUT3)+SC(OUT4), IN A, 0dB/0ms/+/ON. *CS1은 측면 2개 SC(cardioid subwoofer) 드라이버로 광대역 카디오이드 패턴 구현.*

**Subwoofer loudspeaker enclosures presets 섹션(p.87-90) 완료. Preset Guide 전체 섹션 5~34(p.67-90) 완료.**

## 35. Pre-alignment delay values (p.91-118)

### 35.1 Time alignment from geometric measurements — 방법론 (p.91-92)

여러 라우드스피커 시스템을 결합할 때 음향적 합산을 위해 딜레이값 조정이 필요하다. 음향 측정 도구가 없을 경우 본 섹션의 사전정렬(pre-alignment) 딜레이값을 사용한다. 이 값들은 동일 기하학적 위치·동일 전면 평면에서 측정됨. 팩토리 프리셋에 이 값을 더한 뒤, 기준 청취점과 각 시스템 중심 간 경로차로 계산한 기하학적 딜레이를 가장 가까운 시스템에 추가하면 시간정렬이 완성된다.

**레이저 거리계**: L-Acoustics Tech Toolcase에 TruPulse 200/Leica DISTO D3 2종 포함.

**절차**: (1) 경로차 PA-PB 측정(P=기준 청취점, A=더 먼 시스템 중심="system a", B=더 가까운 시스템 중심="system b"). (2) 기하학적 딜레이=경로차(m)/음속(340m/s, 20°C 건조공기 기준). (3) 표에서 Pre-alignment delay a/b 조회. (4) system a 정렬딜레이=Pre-alignment delay a(ms), system b 정렬딜레이=Pre-alignment delay b(ms)+기하학적 딜레이(ms). 정규화: 0이 아니면 두 정렬딜레이 값에서 Pre-alignment delay a를 뺀다.

**Autofilter 주의**: Default/Bypassed LF filters 모드의 Autofilter는 메인 시스템 컨트롤러 레이턴시를 6.50ms로 확장 — 서브우퍼가 표준 레이턴시일 때 정렬하려면 서브우퍼 딜레이에 2.66ms를 더하거나(가능하면) 메인 시스템 딜레이에서 2.66ms를 뺀다.

**[xx_MO] 정렬 규칙**(전 섹션 공통, 재확인): 4-출력 컨트롤러는 저지연+서브우퍼 채널세트 커스텀 조합 필요, 별도 컨트롤러 서브우퍼(일반 레이턴시)와 정렬 시 [xx_MO] 채널에 추가 딜레이(LA4/LA8=2.66ms, LA2Xi/LA4X/LA12X=3.00ms), 16출력 컨트롤러는 서브우퍼도 [xx_MO] 선택.

**표기 규칙**: 아래 표는 "프리셋 조합 → 각 요소의 사전정렬 딜레이(ms)+극성(+/-)"을 나타낸다. 극성 `-`는 반전(역상), `+`는 정상.

### 35.2 Progressive ultra-dense line sources — L2/L2D (p.92)

**L2/L2D + KS28**

| Presets | L2/L2D | KS28 |
|---|---|---|
| [L2/L2D 70/90/110]/[L2/L2D_S 70/90/110] + [KS28 L2] | 0 ms + | 5 ms − |
| [L2/L2D 70/90/110]/[L2/L2D_S 70/90/110] + [KS28 L2_C] | 0 ms + | 6 ms + |
| [L2/L2D 70/90/110]/[L2/L2D_S 70/90/110] + [KS28 L2_Cx] | 0 ms + | 3 ms − |

**L2/L2D + CS1**

| Presets | L2/L2D | CS1 |
|---|---|---|
| [L2/L2D 70/90/110]/[L2/L2D_S 70/90/110] + [CS1_60] | 0 ms + | 4.7 ms + |
| [L2/L2D 70/90/110]/[L2/L2D_S 70/90/110] + [CS1_60_S] | 0 ms + | 4.7 ms + |

### 35.3 Variable curvature WST systems — K1 (p.93-94)

**K1 + K1-SB**

| Presets | K1 | K1-SB |
|---|---|---|
| [K1] + [K1SB_X] | 0 ms + | 0 ms + |
| [K1] + [K1SB_60] | 6 ms + | 0 ms + |
| [K1] + [K1SB_100_NC] | 8.3 ms + | 0 ms − |

**K1 + SB28**

| Presets | K1 | SB28 |
|---|---|---|
| [K1] + [SB28_60] | 0.5 ms + | 0 ms − |
| [K1] + [SB28_60_C] | 6 ms + | 0 ms − |
| [K1] + [SB28_60_Cx] | 4 ms + | 0 ms − |

**K1 + KS28**

| Presets | K1 | KS28 |
|---|---|---|
| [K1] + [KS28_60] | 0.5 ms + | 0 ms − |
| [K1] + [KS28_60_C] | 6 ms + | 0 ms − |
| [K1] + [KS28_60_Cx] | 4 ms + | 0 ms − |

**K1 + K1-SB + SB28**

| Presets | K1 | K1-SB | SB28 |
|---|---|---|---|
| [K1]+[K1SB_X]+[SB28_60] | 0 ms + | 0 ms + | 0 ms − |
| [K1]+[K1SB_X]+[SB28_60_C] | 5.5 ms + | 5.5 ms + | 0 ms − |
| [K1]+[K1SB_X]+[SB28_60_Cx] | 3.5 ms + | 3.5 ms + | 0 ms − |
| [K1]+[K1SB_60]+[SB28_60] | 6 ms + | 0 ms + | 6 ms − |
| [K1]+[K1SB_60]+[SB28_60_C] | 6 ms + | 0 ms + | 0.5 ms − |
| [K1]+[K1SB_60]+[SB28_60_Cx] | 6 ms + | 0 ms + | 4 ms − |

**K1 + K1-SB + KS28**

| Presets | K1 | K1-SB | KS28 |
|---|---|---|---|
| [K1]+[K1SB_X]+[KS28_60] | 0 ms + | 0 ms + | 0 ms − |
| [K1]+[K1SB_X]+[KS28_60_C] | 5.5 ms + | 5.5 ms + | 0 ms − |
| [K1]+[K1SB_X]+[KS28_60_Cx] | 3.5 ms + | 3.5 ms + | 0 ms − |
| [K1]+[K1SB_60]+[KS28_60] | 6 ms + | 0 ms + | 6 ms − |
| [K1]+[K1SB_60]+[KS28_60_C] | 6 ms + | 0 ms + | 0.5 ms − |
| [K1]+[K1SB_60]+[KS28_60_Cx] | 6 ms + | 0 ms + | 4 ms − |

**K1 + CS1**

| Presets | K1 | CS1 |
|---|---|---|
| [K1] + [CS1_60] | 7.5 ms + | 0 ms − |
| [K1] + [CS1_60_S] | 7.5 ms + | 0 ms − |

**K1 + K1-SB + CS1**

| Presets | K1 | K1-SB | CS1 |
|---|---|---|---|
| [K1]+[K1SB_X]+[CS1_60] | 7.5 ms + | 7.5 ms + | 0 ms − |
| [K1]+[K1SB_X]+[CS1_60_S] | 7.5 ms + | 7.5 ms + | 0 ms − |

### 35.4 Variable curvature WST systems — K2 (p.95-96)

**K2 + K1-SB**

| Presets | K2 | K1-SB |
|---|---|---|
| [K2 70/90/110] + [K1SB_X K2] | 0 ms + | 0 ms + |
| [K2 70/90/110] + [K1SB_60] | 6 ms + | 0 ms + |
| [K2 70/90/110] + [K1SB_100_NC] | 8.3 ms + | 0 ms − |

**K2 + SB28**

| Presets | K2 | SB28 |
|---|---|---|
| [K2 70/90/110] + [SB28_60] | 0.5 ms + | 0 ms − |
| [K2 70/90/110] + [SB28_60_C] | 6 ms + | 0 ms − |
| [K2 70/90/110] + [SB28_60_Cx] | 4 ms + | 0 ms − |

**K2 + KS28**

| Presets | K2 | KS28 |
|---|---|---|
| [K2 70/90/110] + [KS28_60] | 0.5 ms + | 0 ms − |
| [K2 70/90/110] + [KS28_60_C] | 6 ms + | 0 ms − |
| [K2 70/90/110] + [KS28_60_Cx] | 4 ms + | 0 ms − |

**K2 + K1-SB + SB28**

| Presets | K2 | K1-SB | SB28 |
|---|---|---|---|
| [K2 70/90/110]+[K1SB_X K2]+[SB28_60] | 0 ms + | 0 ms + | 0 ms − |
| [K2 70/90/110]+[K1SB_X K2]+[SB28_60_C] | 5.5 ms + | 5.5 ms + | 0 ms − |
| [K2 70/90/110]+[K1SB_X K2]+[SB28_60_Cx] | 3.5 ms + | 3.5 ms + | 0 ms − |
| [K2 70/90/110]+[K1SB_60]+[SB28_60] | 6 ms + | 0 ms + | 6 ms − |
| [K2 70/90/110]+[K1SB_60]+[SB28_60_C] | 6 ms + | 0 ms + | 0.5 ms − |
| [K2 70/90/110]+[K1SB_60]+[SB28_60_Cx] | 6 ms + | 0 ms + | 4 ms − |

**K2 + K1-SB + KS28**

| Presets | K2 | K1-SB | KS28 |
|---|---|---|---|
| [K2 70/90/110]+[K1SB_X K2]+[KS28_60] | 0 ms + | 0 ms + | 0 ms − |
| [K2 70/90/110]+[K1SB_X K2]+[KS28_60_C] | 5.5 ms + | 5.5 ms + | 0 ms − |
| [K2 70/90/110]+[K1SB_X K2]+[KS28_60_Cx] | 3.5 ms + | 3.5 ms + | 0 ms − |
| [K2 70/90/110]+[K1SB_60]+[KS28_60] | 6 ms + | 0 ms + | 6 ms − |
| [K2 70/90/110]+[K1SB_60]+[KS28_60_C] | 6 ms + | 0 ms + | 0.5 ms − |
| [K2 70/90/110]+[K1SB_60]+[KS28_60_Cx] | 6 ms + | 0 ms + | 4 ms − |

**K2 + CS1**

| Presets | K2 | CS1 |
|---|---|---|
| [K2 70/90/110] + [CS1_60] | 7.5 ms + | 0 ms − |
| [K2 70/90/110] + [CS1_60_S] | 7.5 ms + | 0 ms − |

**K2 + K1-SB + CS1**

| Presets | K2 | K1-SB | CS1 |
|---|---|---|---|
| [K2 70/90/110]+[K1SB_X K2]+[CS1_60] | 7.5 ms + | 7.5 ms + | 0 ms − |
| [K2 70/90/110]+[K1SB_X K2]+[CS1_60_S] | 7.5 ms + | 7.5 ms + | 0 ms − |

### 35.5 Variable curvature WST systems — K3 (p.96-97)

**K3 + KS28**

| Presets | K3 | KS28 |
|---|---|---|
| [K3 70/90/110] + [KS28_60] | 0.5 ms + | 0 ms − |
| [K3 70/90/110] + [KS28_60_C] | 6 ms + | 0 ms − |
| [K3 70/90/110] + [KS28_60_Cx] | 4 ms + | 0 ms − |

**K3 + KS21**

| Presets | K3 | KS21 |
|---|---|---|
| [K3 70/90/110] + [KS21_60] | 0 ms + | 0 ms − |
| [K3 70/90/110] + [KS21_60_C] | 5.5 ms + | 0 ms − |
| [K3 70/90/110] + [KS21_60_Cx] | 5 ms + | 0 ms + |

**K3 + CS1**(p.97)

| Presets | K3 | CS1 |
|---|---|---|
| [K3 70/90/110] + [CS1_60] | 0.4 ms + | 0 ms + |
| [K3 70/90/110] + [CS1_60_S] | 0.4 ms + | 0 ms + |

### 35.6 Variable curvature WST systems — Kudo (p.97)

| Presets | Kudo | Sub |
|---|---|---|
| [KUDOxx_60] + [SB118_60] | 0 ms + | 3.5 ms + |
| [KUDOxx_60] + [SB118_60_C] | 2 ms + | 0 ms + |
| [KUDOxx_60] + [SB18_60] | 0 ms + | 3.9 ms + |
| [KUDOxx_60] + [SB18_60_C] | 1.6 ms + | 0 ms + |
| [KUDOxx_60] + [SB218_60] | 0 ms + | 5 ms + |
| [KUDOxx_60] + [SB28_60] | 0 ms + | 5 ms + |
| [KUDOxx_60] + [SB28_60_C] | 0.5 ms + | 0 ms + |
| [KUDOxx_60] + [KS28_60] | 0 ms + | 5 ms + |
| [KUDOxx_60] + [KS28_60_C] | 0.5 ms + | 0 ms + |

*[KUDOxx_60]는 [KUDO50_60]/[KUDO80_60]/[KUDO110_60] 공통. Sub 열은 각 행의 서브우퍼(SB118/SB18/SB218/SB28/KS28)를 나타냄.*

### 35.7 Variable curvature WST systems — Kara (p.98-100)

**Kara + SB18**

| Presets | Kara | SB18 |
|---|---|---|
| [KARA] + [SB18_100] | 0 ms + | 0 ms + |
| [KARA_FI] + [SB18_100] | 3 ms + | 0 ms + |
| [KARA] + [SB18_100_C] | 5.5 ms + | 0 ms + |
| [KARA] + [SB18_100_Cx] | 4 ms + | 0 ms − |
| [KARA_FI] + [SB18_100_C] | 8.5 ms + | 0 ms + |
| [KARA_FI] + [SB18_100_Cx] | 7 ms + | 0 ms − |
| [KARA] + [SB18_60] | 2.5 ms + | 0 ms + |
| [KARA] + [SB18_60_C] | 8 ms + | 0 ms + |
| [KARA] + [SB18_60_Cx] | 6.5 ms + | 0 ms − |

**Kara + KS21**

| Presets | Kara | KS21 |
|---|---|---|
| [KARA] + [KS21_60] | 0.5 ms + | 0 ms + |
| [KARA] + [KS21_60_C] | 6 ms + | 0 ms + |
| [KARA] + [KS21_60_Cx] | 5.5 ms + | 0 ms − |
| [KARA] + [KS21_100] | 0 ms + | 0.5 ms + |
| [KARA] + [KS21_100_C] | 5 ms + | 0 ms + |
| [KARA] + [KS21_100_Cx] | 4 ms + | 0 ms − |
| [KARA_FI] + [KS21_100] | 0 ms + | 2.5 ms − |
| [KARA_FI] + [KS21_100_C] | 3 ms + | 0 ms − |
| [KARA_FI] + [KS21_100_Cx] | 2 ms + | 0 ms + |

**Kara + SB28**

| Presets | Kara | SB28 |
|---|---|---|
| [KARA] + [SB28_100] | 0 ms + | 1 ms + |
| [KARA] + [SB28_100_C] | 4.5 ms + | 0 ms + |
| [KARA] + [SB28_100_Cx] | 7.5 ms + | 0 ms − |
| [KARA] + [SB28_60] | 0 ms + | 5 ms − |
| [KARA] + [SB28_60_C] | 0.5 ms + | 0 ms − |
| [KARA] + [SB28_60_Cx] | 4.5 ms + | 0 ms + |

**Kara + KS28**

| Presets | Kara | KS28 |
|---|---|---|
| [KARA] + [KS28_100] | 0 ms + | 1 ms + |
| [KARA] + [KS28_100_C] | 4.5 ms + | 0 ms + |
| [KARA] + [KS28_100_Cx] | 7.5 ms + | 0 ms − |
| [KARA] + [KS28_60] | 0 ms + | 5 ms − |
| [KARA] + [KS28_60_C] | 0.5 ms + | 0 ms − |
| [KARA] + [KS28_60_Cx] | 4.5 ms + | 0 ms + |

**Kara + SB18 + SB28**

| Presets | Kara | SB18 | SB28 |
|---|---|---|---|
| [KARA]+[SB18_100]+[SB28_60] | 0 ms + | 0 ms + | 5.5 ms − |
| [KARA]+[SB18_100]+[SB28_60_C] | 0 ms + | 0 ms + | 0 ms − |
| [KARA]+[SB18_100]+[SB28_60_Cx] | 5.5 ms + | 5.5 ms + | 0 ms + |

**Kara + SB18 + KS28**

| Presets | Kara | SB18 | KS28 |
|---|---|---|---|
| [KARA]+[SB18_100]+[KS28_60] | 0 ms + | 0 ms + | 5.5 ms − |
| [KARA]+[SB18_100]+[KS28_60_C] | 0 ms + | 0 ms + | 0 ms − |
| [KARA]+[SB18_100]+[KS28_60_Cx] | 5.5 ms + | 5.5 ms + | 0 ms + |

**Kara + KS21 + SB28**

| Presets | Kara | KS21 | SB28 |
|---|---|---|---|
| [KARA]+[KS21_100]+[SB28_60] | 0 ms + | 0.5 ms + | 5.5 ms − |
| [KARA]+[KS21_100]+[SB28_60_C] | 0 ms + | 0.5 ms + | 0 ms − |
| [KARA]+[KS21_100]+[SB28_60_Cx] | 5.5 ms + | 6 ms + | 0 ms + |

**Kara + KS21 + KS28**

| Presets | Kara | KS21 | KS28 |
|---|---|---|---|
| [KARA]+[KS21_100]+[KS28_60] | 0 ms + | 0 ms + | 5.5 ms − |
| [KARA]+[KS21_100]+[KS28_60_C] | 0 ms + | 0.5 ms + | 0 ms − |
| [KARA]+[KS21_100]+[KS28_60_Cx] | 5.5 ms + | 6 ms + | 0 ms + |

### 35.8 Variable curvature WST systems — Kara II (p.101-103)

**Kara II + SB18**

| Presets | Kara II | SB18 |
|---|---|---|
| [KARA II 70/90/110] + [SB18_100] | 0 ms + | 0 ms + |
| [KARA II_FI] + [SB18_100] | 3 ms + | 0 ms + |
| [KARA II_MO] + [SB18_100] | 0 ms + | 0 ms + |
| [KARA II 70/90/110] + [SB18_100_C] | 5.5 ms + | 0 ms + |
| [KARA II 70/90/110] + [SB18_100_Cx] | 4 ms + | 0 ms − |
| [KARA II_FI] + [SB18_100_C] | 8.5 ms + | 0 ms + |
| [KARA II_FI] + [SB18_100_Cx] | 7 ms + | 0 ms − |
| [KARA II 70/90/110] + [SB18_60] | 2.5 ms + | 0 ms + |
| [KARA II_MO] + [SB18_60] | 2.5 ms + | 0 ms + |
| [KARA II 70/90/110] + [SB18_60_C] | 8 ms + | 0 ms + |
| [KARA II 70/90/110] + [SB18_60_Cx] | 6.5 ms + | 0 ms − |

**Kara II + KS21**

| Presets | Kara II | KS21 |
|---|---|---|
| [KARA II 70/90/110] + [KS21_60] | 0.5 ms + | 0 ms + |
| [KARA II 70/90/110] + [KS21_60_C] | 6 ms + | 0 ms + |
| [KARA II 70/90/110] + [KS21_60_Cx] | 5.5 ms + | 0 ms − |
| [KARA II_MO] + [KS21_60] | 0 ms + | 0 ms + |
| [KARA II 70/90/110] + [KS21_100] | 0 ms + | 0.5 ms + |
| [KARA II 70/90/110] + [KS21_100_C] | 5 ms + | 0 ms + |
| [KARA II 70/90/110] + [KS21_100_Cx] | 4 ms + | 0 ms − |
| [KARA II_FI] + [KS21_100] | 0 ms + | 2.5 ms − |
| [KARA II_FI] + [KS21_100_C] | 3 ms + | 0 ms − |
| [KARA II_FI] + [KS21_100_Cx] | 2 ms + | 0 ms + |

**Kara II + SB18 + KS28**(p.103)

| Presets | Kara II | SB18 | KS28 |
|---|---|---|---|
| [KARA II 70/90/110]+[SB18_100]+[KS28_60] | 0 ms + | 0 ms + | 5.5 ms − |
| [KARA II 70/90/110]+[SB18_100]+[KS28_60_C] | 0 ms + | 0 ms + | 0 ms − |
| [KARA II 70/90/110]+[SB18_100]+[KS28_60_Cx] | 5.5 ms + | 5.5 ms + | 0 ms + |

**Kara II + KS21 + SB28**

| Presets | Kara II | KS21 | SB28 |
|---|---|---|---|
| [KARA II 70/90/110]+[KS21_100]+[SB28_60] | 0 ms + | 0.5 ms + | 5.5 ms − |
| [KARA II 70/90/110]+[KS21_100]+[SB28_60_C] | 0 ms + | 0.5 ms + | 0 ms − |
| [KARA II 70/90/110]+[KS21_100]+[SB28_60_Cx] | 5.5 ms + | 6 ms + | 0 ms + |

**Kara II + KS21 + KS28**

| Presets | Kara II | KS21 | KS28 |
|---|---|---|---|
| [KARA II 70/90/110]+[KS21_100]+[KS28_60] | 0 ms + | 0 ms + | 5.5 ms − |
| [KARA II 70/90/110]+[KS21_100]+[KS28_60_C] | 0 ms + | 0.5 ms + | 0 ms − |
| [KARA II 70/90/110]+[KS21_100]+[KS28_60_Cx] | 5.5 ms + | 6 ms + | 0 ms + |

### 35.9 Variable curvature WST systems — Kiva/Kilo/Kiva II (p.103-104)

**Kiva + Kilo**

| Presets | Kiva | Kilo |
|---|---|---|
| [KIVA] + [KILO] | 0 ms + | 1.5 ms + |

**Kiva/Kilo + SB118**

| Presets | Kiva/Kilo | SB118 |
|---|---|---|
| [KIVA KILO] + [SB118_60] | 0 ms + | 5.9 ms + |
| [KIVA KILO] + [SB118_60_C] | 0 ms + | 0.4 ms + |

**Kiva/Kilo + SB18**

| Presets | Kiva/Kilo | SB18 |
|---|---|---|
| [KIVA KILO] + [SB18_60] | 0 ms + | 6.3 ms + |
| [KIVA KILO] + [SB18_60_C] | 0 ms + | 0.8 ms + |

**Kiva + SB15m**

| Presets | Kiva | SB15m |
|---|---|---|
| [KIVA] + [SB15_100] | 0 ms + | 1.4 ms + |
| [KIVA] + [SB15_100_C] | 2.4 ms + | 0 ms + |
| [KIVA_FI] + [SB15_100] | 0 ms + | 0.6 ms + |

**Kiva/SB15m + SB18**

| Presets | Kiva/SB15m | SB18 |
|---|---|---|
| [KIVA SB15] + [SB18_60] | 0 ms + | 8.5 ms + |
| [KIVA SB15] + [SB18_60_C] | 0 ms + | 3 ms + |

**Kiva II + SB15m**

| Presets | Kiva II | SB15m |
|---|---|---|
| [KIVA II] + [SB15_100] | 0 ms + | 1 ms + |
| [KIVA II] + [SB15_100_C] | 2.5 ms + | 0 ms + |
| [KIVA II] + [SB15_100_Cx] | 4.5 ms + | 0 ms − |
| [KIVA II_FI] + [SB15_100] | 0 ms + | 1 ms + |
| [KIVA II_FI] + [SB15_100_C] | 2.5 ms + | 0 ms + |
| [KIVA II_FI] + [SB15_100_Cx] | 5 ms + | 0 ms − |

**Kiva II + SB15m + SB18**

| Presets | Kiva II | SB15m | SB18 |
|---|---|---|---|
| [KIVA II]+[SB15_100]+[SB18_60] | 0 ms + | 1 ms + | 1 ms − |
| [KIVA II]+[SB15_100]+[SB18_60_C] | 4.5 ms + | 5.5 ms + | 0 ms − |
| [KIVA II]+[SB15_100]+[SB18_60_Cx] | 1 ms + | 2 ms + | 0 ms + |
| [KIVA II]+[SB15_100_C]+[SB18_60] | 2.5 ms + | 0 ms + | 3.5 ms − |
| [KIVA II]+[SB15_100_C]+[SB18_60_C] | 4.5 ms + | 2 ms + | 0 ms − |
| [KIVA II]+[SB15_100_C]+[SB18_60_Cx] | 3 ms + | 0.5 ms + | 0 ms + |

### 35.10 Variable curvature WST systems — V-DOSC (p.105-106)

| Presets | V-DOSC | Sub 1 | Sub 2 |
|---|---|---|---|
| [V-DOSC_HI_X]/[V-DOSC_LO_X] + [SB218_X] | 1.8 ms + | 0 ms + | — |
| [V-DOSC_HI_60]/[V-DOSC_LO_60] + [SB218_60] | 0 ms + | 3.8 ms + | — |
| [V-DOSC_HI_60]/[V-DOSC_LO_60] + [SB28_60] | 0 ms + | 3.8 ms + | — |
| [V-DOSC_HI_60]/[V-DOSC_LO_60] + [SB28_60_C] | 1.7 ms + | 0 ms + | — |
| [V-DOSC_HI_60]/[V-DOSC_LO_60] + [KS28_60] | 0 ms + | 3.8 ms + | — |
| [V-DOSC_HI_60]/[V-DOSC_LO_60] + [KS28_60_C] | 1.7 ms + | 0 ms + | — |
| [V-DOSC_HI_X]/[V-DOSC_LO_X] + [dV-S_X] | 0 ms + | 0.2 ms(dV-SUB) + | — |
| [V-DOSC_HI_60]/[V-DOSC_LO_60]+[dV-S_60_X]+[SB218_60] | 0 ms + | 0.2 ms(dV-SUB) + | 3.7 ms(SB218) + |
| [V-DOSC_HI_60]/[V-DOSC_LO_60]+[dV-S_60_X]+[SB28_60] | 0 ms + | 0.2 ms(dV-SUB) + | 3.7 ms(SB28) + |
| [V-DOSC_HI_60]/[V-DOSC_LO_60]+[dV-S_60_X]+[SB28_60_C] | 1.9 ms + | 2 ms(dV-SUB) + | 0 ms(SB28) + |
| [V-DOSC_HI_60]/[V-DOSC_LO_60]+[dV-S_60_X]+[KS28_60] | 0 ms + | 0.2 ms(dV-SUB) + | 3.7 ms(KS28) + |
| [V-DOSC_HI_60]/[V-DOSC_LO_60]+[dV-S_60_X]+[KS28_60_C] | 1.9 ms + | 2 ms(dV-SUB) + | 0 ms(KS28) + |
| [V-DOSC_HI_60]/[V-DOSC_LO_60]+[dV_HI_100]/[dV_LO_100] | 0 ms + | 0 ms(dV-DOSC) + | — |
| [V-DOSC_HI_60]/[V-DOSC_LO_60]+[dV_HI_100]/[dV_LO_100](downfill) | 0 ms + | 0.04 ms(dV-DOSC) + | — |

### 35.11 Variable curvature WST systems — dV-DOSC (p.106-107)

| Presets | dV-DOSC | Sub 1 | Sub 2 |
|---|---|---|---|
| [dV_HI_100]/[dV_LO_100] + [SB118_100] | 2.7 ms + | 0 ms + | — |
| [dV_HI_100]/[dV_LO_100] + [SB118_100_C] | 8.3 ms + | 0 ms + | — |
| [dV_HI_100]/[dV_LO_100] + [SB218_100] | 0.8 ms + | 0 ms + | — |
| [dV_HI_100]/[dV_LO_100] + [SB18_100] | 2.4 ms + | 0 ms + | — |
| [dV_HI_100]/[dV_LO_100] + [SB18_100_C] | 8 ms + | 0 ms + | — |
| [dV_HI_100]/[dV_LO_100] + [SB28_100] | 0.8 ms + | 0 ms + | — |
| [dV_HI_100]/[dV_LO_100] + [SB28_100_C] | 6.3 ms + | 0 ms + | — |
| [dV_HI_100]/[dV_LO_100] + [KS28_100] | 0.8 ms + | 0 ms + | — |
| [dV_HI_100]/[dV_LO_100] + [KS28_100_C] | 6.3 ms + | 0 ms + | — |
| [dV_HI_100]/[dV_LO_100] + [dV-S_100] | 0 ms + | 0 ms(dV-SUB) + | — |
| [dV_HI_100]/[dV_LO_100]+[dV-S_60_100]+[SB118_60] | 0 ms + | 0.75 ms(dV-SUB) + | 4 ms(SB118) + |
| [dV_HI_100]/[dV_LO_100]+[dV-S_60_100]+[SB118_60_C] | 1.5 ms + | 2.25 ms(dV-SUB) + | 0 ms(SB118) + |
| [dV_HI_100]/[dV_LO_100]+[dV-S_60_100]+[SB218_60] | 0 ms + | 0.75 ms(dV-SUB) + | 4.5 ms(SB218) + |
| [dV_HI_100]/[dV_LO_100]+[dV-S_60_100]+[SB18_60] | 0 ms + | 0.75 ms(dV-SUB) + | 4.4 ms(SB18) + |
| [dV_HI_100]/[dV_LO_100]+[dV-S_60_100]+[SB18_60_C] | 1.1 ms + | 1.85 ms(dV-SUB) + | 0 ms(SB18) + |
| [dV_HI_100]/[dV_LO_100]+[dV-S_60_100]+[SB28_60] | 0 ms + | 0.75 ms(dV-SUB) + | 4.5 ms(SB28) + |
| [dV_HI_100]/[dV_LO_100]+[dV-S_60_100]+[SB28_60_C] | 1 ms + | 1.75 ms(dV-SUB) + | 0 ms(SB28) + |
| [dV_HI_100]/[dV_LO_100]+[dV-S_60_100]+[KS28_60] | 0 ms + | 0.75 ms(dV-SUB) + | 4.5 ms(KS28) + |
| [dV_HI_100]/[dV_LO_100]+[dV-S_60_100]+[KS28_60_C] | 1 ms + | 1.75 ms(dV-SUB) + | 0 ms(KS28) + |

**Variable curvature WST systems presets 딜레이표 섹션(p.93-107) 완료.**

### 35.12 Constant curvature WST systems (p.108-110)

**ARCS + SB118**(p.108)

| Presets | ARCS | SB118 |
|---|---|---|
| [ARCS_HI_60]/[ARCS_LO_60] + [SB118_60] | 0.8 ms + | 0 ms + |
| [ARCS_HI_60]/[ARCS_LO_60] + [SB118_60_C] | 6.3 ms + | 0 ms + |
| [ARCS_HI_100]/[ARCS_LO_100] + [SB118_100] | 1.4 ms + | 0 ms + |
| [ARCS_HI_100]/[ARCS_LO_100] + [SB118_100_C] | 6.9 ms + | 0 ms + |

**ARCS + SB18**

| Presets | ARCS | SB18 |
|---|---|---|
| [ARCS_HI_60]/[ARCS_LO_60] + [SB18_60] | 0.4 ms + | 0 ms + |
| [ARCS_HI_60]/[ARCS_LO_60] + [SB18_60_C] | 5.9 ms + | 0 ms + |
| [ARCS_HI_100]/[ARCS_LO_100] + [SB18_100] | 1.1 ms + | 0 ms + |
| [ARCS_HI_100]/[ARCS_LO_100] + [SB18_100_C] | 6.6 ms + | 0 ms + |

**ARCS + SB218**

| Presets | ARCS | SB218 |
|---|---|---|
| [ARCS_HI_60]/[ARCS_LO_60] + [SB218_60] | 0 ms + | 0.9 ms + |
| [ARCS_HI_100]/[ARCS_LO_100] + [SB218_100] | 0 ms + | 0.3 ms + |

**ARCS + SB28**

| Presets | ARCS | SB28 |
|---|---|---|
| [ARCS_HI_60]/[ARCS_LO_60] + [SB28_60] | 0 ms + | 0.6 ms + |
| [ARCS_HI_60]/[ARCS_LO_60] + [SB28_60_C] | 4.9 ms + | 0 ms + |
| [ARCS_HI_100]/[ARCS_LO_100] + [SB28_100] | 0 ms + | 0.5 ms + |
| [ARCS_HI_100]/[ARCS_LO_100] + [SB28_100_C] | 5.0 ms + | 0 ms + |

**ARCS + KS28**(p.109)

| Presets | ARCS | KS28 |
|---|---|---|
| [ARCS_HI_60]/[ARCS_LO_60] + [KS28_60] | 0 ms + | 0.6 ms + |
| [ARCS_HI_60]/[ARCS_LO_60] + [KS28_60_C] | 4.9 ms + | 0 ms + |
| [ARCS_HI_100]/[ARCS_LO_100] + [KS28_100] | 0 ms + | 0.5 ms + |
| [ARCS_HI_100]/[ARCS_LO_100] + [KS28_100_C] | 5.0 ms + | 0 ms + |

**ARCS II + SB28**

| Presets | ARCS II | SB28 |
|---|---|---|
| [ARCS II] + [SB28_60] | 0 ms + | 2 ms + |
| [ARCS II] + [SB28_60_C] | 3.5 ms + | 0 ms + |
| [ARCS II] + [SB28_60_Cx] | 7.5 ms + | 0 ms − |

**ARCS II + KS28**

| Presets | ARCS II | KS28 |
|---|---|---|
| [ARCS II] + [KS28_60] | 0 ms + | 2 ms + |
| [ARCS II] + [KS28_60_C] | 3.5 ms + | 0 ms + |
| [ARCS II] + [KS28_60_Cx] | 7.5 ms + | 0 ms − |

**ARCS Wide/Focus + SB18m**

| Presets | ARCS Wide/Focus | SB18m |
|---|---|---|
| [ARCS_WIFO]/[ARCS_WIFO_FI] + [SB18_60] | 1.5 ms + | 0 ms + |
| [ARCS_WIFO]/[ARCS_WIFO_FI] + [SB18_60_C] | 7 ms + | 0 ms + |
| [ARCS_WIFO]/[ARCS_WIFO_FI] + [SB18_60_Cx] | 6 ms + | 0 ms − |

**A15 Wide/Focus + KS21**

| Presets | A15 Wide/Focus | KS21 |
|---|---|---|
| [A15]/[A15_FI]/[A15_MO] + [KS21_60] | 0 ms + | 2.3 ms + |
| [A15]/[A15_FI] + [KS21_60_C] | 9 ms + | 0 ms − |
| [A15]/[A15_FI] + [KS21_60_Cx] | 8 ms + | 0 ms + |

**A10 Wide/Focus + KS21**(p.110)

| Presets | A10 Wide/Focus | KS21 |
|---|---|---|
| [A10]/[A10_FI]/[A10_MO] + [KS21_100] | 0 ms + | 0 ms + |
| [A10]/[A10_FI] + [KS21_100_C] | 5.5 ms + | 0 ms + |
| [A10]/[A10_FI] + [KS21_100_Cx] | 0 ms + | 0 ms + |

**Constant curvature WST systems presets 딜레이표 섹션(p.108-110) 완료.**

### 35.13 Colinear systems (p.110)

**Syva + Syva Sub**

| Presets | Syva | Syva Sub |
|---|---|---|
| [SYVA] + [SYVA SUB_100] | 0 ms + | 2.6 ms + |

**Syva + Syva Low + Syva Sub**

| Presets | Syva | Syva Low | Syva Sub |
|---|---|---|---|
| [SYVA]+[SYVA LOW_100]+[SYVA SUB_100] | 0 ms + | 0 ms + | 3.8 ms + |

**Soka + SB6i**

| Presets | Soka | SB6i |
|---|---|---|
| [SOKA] + [SB6_100] | 1.4 ms + | 0 ms + |
| [SOKA_200] + [SB6_200] | 1.9 ms + | 0 ms + |
| [SOKA_60] + [SB6_60] | 3.6 ms + | 0 ms − |

**Soka + SB10i**

| Presets | Soka | SB10i |
|---|---|---|
| [SOKA] + [SB10_100] | 2.6 ms + | 0 ms + |
| [SOKA_200] + [SB10_200] | 3.2 ms + | 0 ms + |
| [SOKA_60] + [SB10_60] | 9 ms + | 0 ms − |

**Soka + Syva Sub**

| Presets | Soka | Syva Sub |
|---|---|---|
| [SOKA_60] + [SYVA SUB_60] | 5.6 ms + | 0 ms − |

**Colinear systems presets 딜레이표 섹션(p.110) 완료.**

### 35.14 Coaxial loudspeaker enclosures (p.111-118)

**X15 HiQ + SB18**(p.111)

| Presets | X15 HiQ | SB18 |
|---|---|---|
| [X15] + [SB18_100] | 4 ms + | 0 ms − |
| [X15_MO] + [SB18_100] | 0 ms + | 1 ms + |
| [X15] + [SB18_100_C] | 9.7 ms + | 0 ms − |
| [X15] + [SB18_100_Cx] | 8.25 ms + | 0 ms + |

**X15 HiQ + KS21**

| Presets | X15 HiQ | KS21 |
|---|---|---|
| [X15] + [KS21_100] | 0 ms + | 1.5 ms + |
| [X15_MO] + [KS21_100] | 0 ms + | 1.5 ms + |
| [X15] + [KS21_100_C] | 3.9 ms + | 0 ms + |
| [X15] + [KS21_100_Cx] | 2.6 ms + | 0 ms − |

**X12 + SB15m**

| Presets | X12 | SB15m |
|---|---|---|
| [X12] + [SB15_100] | 1.5 ms + | 0 ms − |
| [X12_MO] + [SB15_100] | 0 ms + | 2.85 ms + |
| [X12] + [SB15_100_C] | 5.1 ms + | 0 ms − |
| [X12] + [SB15_100_Cx] | 3 ms + | 0 ms − |

**X12 + SB18**(p.112)

| Presets | X12 | SB18 |
|---|---|---|
| [X12] + [SB18_100] | 0 ms + | 0 ms + |
| [X12_MO] + [SB18_100] | 0 ms + | 0 ms + |
| [X12] + [SB18_100_C] | 5.7 ms + | 0 ms + |
| [X12] + [SB18_100_Cx] | 4 ms + | 0 ms − |

**X12 + KS21**

| Presets | X12 | KS21 |
|---|---|---|
| [X12] + [KS21_100] | 0 ms + | 1 ms + |
| [X12_MO] + [KS21_100] | 0 ms + | 0.4 ms + |
| [X12] + [KS21_100_C] | 4.8 ms + | 0 ms + |
| [X12] + [KS21_100_Cx] | 3.4 ms + | 0 ms − |

**X8 + SB10i**

| Presets | X8 | SB10i |
|---|---|---|
| [X8] + [SB10_100] | 0 ms + | 3.2 ms + |

**X8 + SB15m**

| Presets | X8 | SB15m |
|---|---|---|
| [X8] + [SB15_100] | 2 ms + | 0 ms − |
| [X8_MO] + [SB15_100] | 0 ms + | 3 ms + |
| [X8] + [SB15_100_C] | 5.7 ms + | 0 ms − |
| [X8] + [SB15_100_Cx] | 3.8 ms + | 0 ms − |

**X8 + Syva Sub**

| Presets | X8 | Syva Sub |
|---|---|---|
| [X8] + [SYVA SUB_100] | 0 ms + | 0.7 ms − |

**X8i + SB10i**(p.113)

| Presets | X8i | SB10i |
|---|---|---|
| [X8i] + [SB10_100] | 0 ms + | 0.5 ms + |
| [X8i_40] + [SB10_60] | 0 ms + | 3 ms + |

**X8i + Syva Sub**

| Presets | X8i | Syva Sub |
|---|---|---|
| [X8i] + [SYVA SUB_100] | 0 ms + | 0 ms − |
| [X8i_40] + [SYVA SUB_60] | 3.5 ms + | 0 ms − |

**X8i + KS21**

| Presets | X8i | KS21 |
|---|---|---|
| [X8i] + [KS21_100] | 0 ms + | 0 ms + |
| [X8i_40] + [KS21_60] | 4.8 ms + | 0 ms − |

**X6i + SB6i**

| Presets | X6i | SB6i |
|---|---|---|
| [X6i] + [SB6_200] | 0 ms + | 0 ms − |
| [X6i] + [SB6_100] | 0 ms + | 1.2 ms + |
| [X6i_50] + [SB6_60] | 0 ms + | 2 ms + |

**X6i + SB10i**

| Presets | X6i | SB10i |
|---|---|---|
| [X6i] + [SB10_200] | 1.4 ms + | 0 ms − |
| [X6i] + [SB10_100] | 0 ms + | 0 ms + |
| [X6i_50] + [SB10_60] | 0 ms + | 6.8 ms − |

**X6i + Syva Sub**

| Presets | X6i | Syva Sub |
|---|---|---|
| [X6i_50] + [SYVA SUB_60] | 0 ms + | 0.4 ms + |

**5XT + SB15m**(p.114)

| Presets | 5XT | SB15m |
|---|---|---|
| [5XT] + [SB15_100] | 0 ms + | 0 ms + |
| [5XT_MO] + [SB15_100] | 0.2 ms + | 0 ms + |

**5XT + SB10i**

| Presets | 5XT | SB10i |
|---|---|---|
| [5XT]/[5XT_MO] + [SB10_100] | 0 ms + | 1.6 ms − |

**X4i + Syva Sub**

| Presets | X4i | Syva Sub |
|---|---|---|
| [X4]/[X4_MO] + [SYVA SUB_200] | 0 ms + | 0.5 ms + |

**X4i + SB6i**

| Presets | X4i | SB6i |
|---|---|---|
| [X4_60] + [SB6_60] | 1.8 ms + | 0 ms − |
| [X4]/[X4_MO] + [SB6_100] | 0 ms + | 0.4 ms + |
| [X4]/[X4_MO] + [SB6_200] | 0.6 ms + | 0 ms − |

**X4i + SB10i**

| Presets | X4i | SB10i |
|---|---|---|
| [X4_60] + [SB10_60] | 7.2 ms + | 0 ms − |
| [X4]/[X4_MO] + [SB10_100] | 0.8 ms + | 0 ms + |
| [X4] + [SB10_200] | 1.9 ms + | 0 ms − |
| [X4_MO] + [SB10_200] | 0 ms + | 0 ms + |

**115XT HiQ + SB118**

| Presets | 115XT HiQ | SB118 |
|---|---|---|
| [HiQ_FI_100] + [SB118_100] | 2.6 ms + | 0 ms + |
| [HiQ_FR_100] + [SB118_100] | 2.6 ms + | 0 ms + |
| [HiQ_MO_100] + [SB118_100] | 2.5 ms + | 0 ms + |

**115XT HiQ + SB18**(p.115)

| Presets | 115XT HiQ | SB18 |
|---|---|---|
| [HiQ_FI_100] + [SB18_100] | 2.3 ms + | 0 ms + |
| [HiQ_FR_100] + [SB18_100] | 2.3 ms + | 0 ms + |
| [HiQ_MO_100] + [SB18_100] | 2.2 ms + | 0 ms + |

**115XT HiQ + dV-SUB**

| Presets | 115XT HiQ | dV-SUB |
|---|---|---|
| [HiQ_FI_100] + [dV-S_100] | 0.6 ms + | 0 ms + |
| [HiQ_FR_100] + [dV-S_100] | 0.6 ms + | 0 ms + |
| [HiQ_MO_100] + [dV-S_100] | 0.5 ms + | 0 ms + |

**Active 12XT + SB118**

| Presets | 12XTA | SB118 |
|---|---|---|
| [12XTA_FI_100] + [SB118_100] | 2.6 ms + | 0 ms + |
| [12XTA_FR_100] + [SB118_100] | 2.6 ms + | 0 ms + |
| [12XTA_MO_100] + [SB118_100] | 2.5 ms + | 0 ms + |

**Active 12XT + SB18**

| Presets | 12XTA | SB18 |
|---|---|---|
| [12XTA_FI_100] + [SB18_100] | 2.3 ms + | 0 ms + |
| [12XTA_FR_100] + [SB18_100] | 2.3 ms + | 0 ms + |
| [12XTA_MO_100] + [SB18_100] | 2.2 ms + | 0 ms + |

**Passive 12XT + SB118**

| Presets | 12XTP | SB118 |
|---|---|---|
| [12XTP_FI_100] + [SB118_100] | 2.4 ms + | 0 ms + |
| [12XTP_FR_100] + [SB118_100] | 2.4 ms + | 0 ms + |
| [12XTP_MO_100] + [SB118_100] | 2.4 ms + | 0 ms + |

**Passive 12XT + SB18**(p.116)

| Presets | 12XTP | SB18 |
|---|---|---|
| [12XTP_FI_100] + [SB18_100] | 2.1 ms + | 0 ms + |
| [12XTP_FR_100] + [SB18_100] | 2.1 ms + | 0 ms + |
| [12XTP_MO_100] + [SB18_100] | 2.1 ms + | 0 ms + |

**8XT + SB118**

| Presets | 8XT | SB118 |
|---|---|---|
| [8XT_FI_100] + [SB118_100] | 3.1 ms + | 0 ms + |
| [8XT_FR_100] + [SB118_100] | 3.2 ms + | 0 ms + |
| [8XT_MO_100] + [SB118_100] | 3.0 ms + | 0 ms + |

**8XT + SB18**

| Presets | 8XT | SB18 |
|---|---|---|
| [8XT_FI_100] + [SB18_100] | 2.8 ms + | 0 ms + |
| [8XT_FR_100] + [SB18_100] | 2.9 ms + | 0 ms + |
| [8XT_MO_100] + [SB18_100] | 2.7 ms + | 0 ms + |

**115XT + SB118**

| Presets | 115XT | SB118 |
|---|---|---|
| [115XT_FI_100] + [SB118_100] | 2.6 ms + | 0 ms + |
| [115XT_FR_100] + [SB118_100] | 2.5 ms + | 0 ms + |
| [115XT_MO_100] + [SB118_100] | 2.9 ms + | 0 ms + |

**115XT + SB18**

| Presets | 115XT | SB18 |
|---|---|---|
| [115XT_FI_100] + [SB18_100] | 2.3 ms + | 0 ms + |
| [115XT_FR_100] + [SB18_100] | 2.2 ms + | 0 ms + |
| [115XT_MO_100] + [SB18_100] | 2.6 ms + | 0 ms + |

**Active MTD115 + SB118**(p.117)

| Presets | 115bA | SB118 |
|---|---|---|
| [115bA_FI_100] + [SB118_100] | 2.4 ms + | 0 ms + |
| [115bA_FR_100] + [SB118_100] | 2.5 ms + | 0 ms + |
| [115bA_MO_100] + [SB118_100] | 2.7 ms + | 0 ms + |

**Active MTD115 + SB18**

| Presets | 115bA | SB18 |
|---|---|---|
| [115bA_FI_100] + [SB18_100] | 2.1 ms + | 0 ms + |
| [115bA_FR_100] + [SB18_100] | 2 ms + | 0 ms + |
| [115bA_MO_100] + [SB18_100] | 2.4 ms + | 0 ms + |

**Passive MTD115 + SB118**

| Presets | 115bP | SB118 |
|---|---|---|
| [115bP_FI_100] + [SB118_100] | 2.1 ms + | 0 ms + |
| [115bP_FR_100] + [SB118_100] | 2.2 ms + | 0 ms + |
| [115bP_MO_100] + [SB118_100] | 2.8 ms + | 0 ms + |

**Passive MTD115 + SB18**

| Presets | 115bP | SB18 |
|---|---|---|
| [115bP_FI_100] + [SB18_100] | 1.8 ms + | 0 ms + |
| [115bP_FR_100] + [SB18_100] | 1.9 ms + | 0 ms + |
| [115bP_MO_100] + [SB18_100] | 2.5 ms + | 0 ms + |

**112XT + SB118**

| Presets | 112XT | SB118 |
|---|---|---|
| [112XT_FI_100] + [SB118_100] | 2.3 ms + | 0 ms + |
| [112XT_FR_100] + [SB118_100] | 2.3 ms + | 0 ms + |
| [112XT_MO_100] + [SB118_100] | 2.6 ms + | 0 ms + |

**112XT + SB18**(p.118)

| Presets | 112XT | SB18 |
|---|---|---|
| [112XT_FI_100] + [SB18_100] | 2 ms + | 0 ms + |
| [112XT_FR_100] + [SB18_100] | 2 ms + | 0 ms + |
| [112XT_MO_100] + [SB18_100] | 2.3 ms + | 0 ms + |

**MTD112b + SB118**

| Presets | 112b | SB118 |
|---|---|---|
| [112b_FI_100] + [SB118_100] | 2.4 ms + | 0 ms + |
| [112b_FR_100] + [SB118_100] | 2.5 ms + | 0 ms + |
| [112b_MO_100] + [SB118_100] | 3.0 ms + | 0 ms + |

**MTD112b + SB18**

| Presets | 112b | SB18 |
|---|---|---|
| [112b_FI_100] + [SB18_100] | 2.1 ms + | 0 ms + |
| [112b_FR_100] + [SB18_100] | 2.2 ms + | 0 ms + |
| [112b_MO_100] + [SB18_100] | 2.7 ms + | 0 ms + |

**MTD108a + SB118**

| Presets | 108a | SB118 |
|---|---|---|
| [108a_FI_100] + [SB118_100] | 3.5 ms + | 0 ms + |
| [108a_FR_100] + [SB118_100] | 3.6 ms + | 0 ms + |
| [108a_MO_100] + [SB118_100] | 4.0 ms + | 0 ms + |

**MTD108a + SB18**

| Presets | 108a | SB18 |
|---|---|---|
| [108a_FI_100] + [SB18_100] | 3.2 ms + | 0 ms + |
| [108a_FR_100] + [SB18_100] | 3.3 ms + | 0 ms + |
| [108a_MO_100] + [SB18_100] | 3.7 ms + | 0 ms + |

**Coaxial loudspeaker enclosures presets 딜레이표 섹션(p.111-118) 완료. Pre-alignment delay values 섹션(p.91-118) 전체 완료.**

## 36. Impedance load (p.119)

대부분 인클로저는 공칭 임피던스 8Ω. 예외: **16Ω** — K2(HF 섹션), Kiva II, V-DOSC(HF 섹션), 5XT, X4i. **4Ω** — SB28, KS28, Syva Low, K1-SB, SB6i.

**병렬 연결 시 총 임피던스**(Amp Bulletin의 표와 동일 데이터):

| Nominal | 2대 병렬 | 3대 병렬 | 4대 병렬 | 5대 병렬 | 6대 병렬 |
|---|---|---|---|---|---|
| 16 Ω | 8 Ω | 5.3 Ω | 4 Ω | 3.2 Ω | 2.7 Ω |
| 8 Ω | 4 Ω | 2.7 Ω | — | — | — |

**4Ω 인클로저는 병렬 연결 불가**(예외: Syva Low, SB6i).

## 37. Enclosure drive capacity per amplified controller (p.120-123)

**주의**: 채널당/총 연결 인클로저 수 상한을 초과하면 출력 뮤트/전역 감쇠/음질 저하 위험. L-SMART 호환 컨트롤러(LA1.16i, LA7.16(i))는 전 채널 풀파워 구동 기준 공칭값(Power Budget과 무관하게 이 상한 자체를 넘지 않아야 Fuse Protect 알고리즘 미작동). LA7.16(i)는 100V 전원 사용 시 정격의 75%를 넘지 않도록 대수 축소. LA1.16i는 프리셋별 총 대수 상한이 다를 수 있어 Soundvision/LA Network Manager Power Budget 모니터링 참조.

값 형식: **채널당/총 대수**(passive는 출력당 병렬 대수, active는 출력당 병렬 섹션 수).

### 37.1 LA1.16i / LA2Xi / LA4X / LA7.16(i) / LA12X (p.120-121)

**coaxial enclosures**

| Product | LA1.16i SE | LA1.16i BTL | LA2Xi SE | LA2Xi BTL | LA2Xi PBTL | LA4X | LA7.16(i) | LA12X |
|---|---|---|---|---|---|---|---|---|
| X4i | 3/48 | 2/12 | 4/16 | — | — | 4/16 | 4/64 | 6/24 |
| 5XT | 3/48 | 2/14 | 4/16 | — | — | 4/16 | 3/48 | 6/24 |
| X6i | 2/20 | 1/8 | 2/8 | 1/2 | — | 2/8 | 1/16 | 3/12 |
| X8 | 2/32 | 1/8 | 2/8 | 1/2 | — | 2/8 | 1/16 | 3/12 |
| X8i | 2/30 | 1/8 | 2/8 | 1/2 | — | 2/8 | 1/16 | 3/12 |
| X12 | — | 1/4 | 1/4 | 1/2 | — | 1/4 | 1/14 | 3/12 |
| X15 HiQ | — | 1/2 | — | — | — | 1/2 | 1/8 | 3/6 |
| 8XT | — | — | — | — | — | 2/8 | — | 3/12 |
| Active 12XT | — | — | — | — | — | 2/4 | — | 3/6 |
| Passive 12XT | — | — | — | — | — | 1/4 | — | 3/12 |
| 112XT | — | — | — | — | — | 2/4 | — | 3/6 |
| 115XT HiQ | — | — | — | — | — | 1/2 | — | 3/6 |
| 115XT | — | — | — | — | — | 1/2 | — | 3/6 |
| MTD108a | — | — | — | — | — | 2/8 | — | 3/12 |
| MTD112b | — | — | — | — | — | 1/4 | — | 2/8 |
| Active MTD115b | — | — | — | — | — | 1/2 | — | 2/4 |
| Passive MTD115b | — | — | — | — | — | 1/4 | — | 2/8 |

**colinear sources**

| Product | LA1.16i SE | LA1.16i BTL | LA2Xi SE | LA2Xi BTL | LA2Xi PBTL | LA4X | LA7.16(i) | LA12X |
|---|---|---|---|---|---|---|---|---|
| Soka | 2/26 | 1/4 | 1/4 | 1/2 | — | 2/8 | 1/16 | 3/12 |
| Syva | — | 1/4 | 1/2 | — | — | 1/4 | 1/10 | 3/12 |

**constant curvature WST enclosures**

| Product | LA1.16i SE | LA1.16i BTL | LA2Xi SE | LA2Xi BTL | LA2Xi PBTL | LA4X | LA7.16(i) | LA12X |
|---|---|---|---|---|---|---|---|---|
| A10(i) Wide/Focus | — | 1/4 | 2/8 | 1/2 | — | 2/8 | 1/16 | 3/12 |
| A15(i) Wide/Focus | — | 1/4 | 1/4 | 1/2 | — | 1/4 | 1/10 | 3/12 |
| ARCS Wide/Focus | — | 1/4 | 1/4 | 1/2 | — | 1/4 | — | 3/12 |
| ARCS II | — | — | — | — | — | 1/2 | — | 3/6 |
| ARCS | — | — | — | — | — | 1/2 | — | 3/6 |

**variable curvature WST enclosures**

| Product | LA1.16i SE | LA1.16i BTL | LA2Xi SE | LA2Xi BTL | LA2Xi PBTL | LA4X | LA7.16(i) | LA12X |
|---|---|---|---|---|---|---|---|---|
| K1 | — | — | — | — | — | — | — | 2/2 |
| K1-SB | — | — | — | — | — | — | — | 1/4 |
| K2 | — | — | — | — | — | 1/1 | 1/4 | 3/3 |
| K3(i) | — | — | — | — | — | 1/2 | 1/8 | 3/6 |
| Kara(i) | — | — | 2/4 | — | — | 2/4 | — | 3/6 |
| Kara II(i) | — | — | 2/4 | — | — | 2/4 | 1/8 | 3/6 |
| Kiva II | — | 2/10 | 2/8 | 2/4 | — | 2/8 | 2/32 | 6/24 |
| Kiva/Kilo | — | — | — | — | — | 2/8 | — | 3/12 |
| Kudo | — | — | — | — | — | 1/1 | — | 3/3 |
| V-DOSC | — | — | — | — | — | — | — | 2/2 |
| dV-DOSC | — | — | — | — | — | — | — | 3/6 |

**progressive curvature WST enclosures**

| Product | LA1.16i SE | LA1.16i BTL | LA2Xi SE | LA2Xi BTL | LA2Xi PBTL | LA4X | LA7.16(i) | LA12X |
|---|---|---|---|---|---|---|---|---|
| L2 / L2D | — | — | — | — | — | — | 1/1 | — |

**subwoofer enclosures**

| Product | LA1.16i SE | LA1.16i BTL | LA2Xi SE | LA2Xi BTL | LA2Xi PBTL | LA4X | LA7.16(i) | LA12X |
|---|---|---|---|---|---|---|---|---|
| CS1 | — | — | — | — | — | — | 1/2 | 2/2 |
| KS28 | — | — | 1/4 | — | 1/1 | — | — | 1/4 |
| SB28 | — | — | 1/4 | — | 1/1 | — | — | 1/4 |
| KS21(i) | — | — | 1/4 | 1/2 | — | 1/4 | 1/8 | 2/8 |
| SB18(i/m)/SB18 IIi | — | — | 1/4 | 1/2 | — | 1/4 | 1/6 | 3/12 |
| SB218 | — | — | — | — | — | — | — | 1/4 |
| SB118 | — | — | — | — | — | 1/4 | — | 2/8 |
| SB15m | — | — | 1/4 | 1/2 | — | 1/4 | 1/9 | 3/12 |
| Syva Low | — | — | 1/4 | — | — | 1/4 | 1/8 | 2/6[a] |
| Syva Sub | — | 1/4 | 1/4 | 1/2 | — | 1/4 | 1/16 | 3/12 |
| SB10i | 2/20 | 1/4 | 2/8 | 1/2 | — | 2/8 | 2/32 | 3/12 |
| SB6i | 1/12 | — | 1/4 | — | — | 1/4 | 1/16 | 2/8 |
| dV-SUB | — | — | — | — | — | — | — | 1/4 |

*[a] LA12X는 출력당 최대 2대의 Syva Low 구동 가능하나, 고레벨 사용 시 컨트롤러당 총 6대를 넘지 않아야 함.*

### 37.2 LA4 / LA8 (p.122-123)

**coaxial enclosures**

| Product | LA4 | LA8 |
|---|---|---|
| X4i | 4/16 | 6/24 |
| 5XT | 3/12 | 6/24 |
| X8 | — | 3/8[a] |
| X12 | — | 2/8 |
| X15 HiQ | — | 2/4 |
| 8XT | 2/8 | 3/12 |
| Active 12XT | 2/4 | 3/6 |
| Passive 12XT | 1/4 | 2/8 |
| 112XT | 2/4 | 3/6 |
| 115XT HiQ | 1/2 | 2/4 |
| 115XT | 1/2 | 3/6 |
| MTD108a | 2/8 | 3/12 |
| MTD112b | 1/4 | 2/8 |
| Active MTD115b | 1/2 | 2/4 |
| Passive MTD115b | 1/4 | 2/8 |

*[a] LA8은 출력당 최대 3대의 X8 구동 가능하나, 고레벨 사용 시 컨트롤러당 총 8대를 넘지 않아야 함.*

**colinear sources**

| Product | LA4 | LA8 |
|---|---|---|
| Syva | — | 2/8 |

**constant curvature WST enclosures**

| Product | LA4 | LA8 |
|---|---|---|
| ARCS Wide/Focus | 1/4 | 2/8 |
| A10(i) Wide/Focus | — | 2/8 |
| A15(i) Wide/Focus | — | 2/8 |
| ARCS II | — | 2/4 |
| ARCS | 1/2 | 3/6 |

**variable curvature WST enclosures**

| Product | LA4 | LA8 |
|---|---|---|
| K1 | — | 2/2 |
| K1-SB | — | 1/4 |
| K2 | — | 3/3 |
| K3(i) | — | 2/4 |
| Kara(i) | — | 3/6 |
| Kara II(i) | — | 3/6 |
| Kiva II | — | 4/16 |
| Kiva/Kilo | 2/8 | 3/12 |
| Kudo | — | 3/3 |
| V-DOSC | — | 2/2 |
| dV-DOSC | — | 3/6 |

**subwoofer enclosures**

| Product | LA4 | LA8 |
|---|---|---|
| KS28 | — | — |
| SB28 | — | 1/4 |
| KS21(i) | — | 2/6[b] |
| SB18(i/m)/SB18 IIi | 1/4 | 2/6[c] |
| SB218 | — | 1/4 |
| SB118 | 1/4 | 2/8 |
| SB15m | 1/4 | 2/6[d] |
| SB10i | — | 3/12 |
| Syva Low | — | 1/4 |
| Syva Sub | 1/4 | 2/8 |
| dV-SUB | — | 1/4 |

*[b] LA8은 출력당 최대 2대의 KS21/KS21i 구동 가능하나, 고레벨 사용 시 컨트롤러당 총 6대를 넘지 않아야 함. [c] LA8은 출력당 최대 2대의 SB18/SB18i/SB18m/SB18 IIi 구동 가능하나, 고레벨 사용 시 컨트롤러당 총 6대를 넘지 않아야 함. [d] LA8은 출력당 최대 2대의 SB15m 구동 가능하나, 고레벨 사용 시 컨트롤러당 총 6대를 넘지 않아야 함.*

## 38. Enclosure maximum SPL per amplified controller (p.124)

Peak level, 1m, 풀레인지는 free field, 서브우퍼는 half space, pink noise crest factor 4 기준. 이 표는 Amp Bulletin 4절의 동명 표와 동일 데이터셋(제품 구성이 대부분 겹침) — 값은 두 문서 간 상충 없이 일치.

**표기 규칙(Amp Bulletin과 동일 병합 패턴, 사용자 재확인 2026-07-19)**: X4i~A15(i) Focus 구간과 K2/K3(i)/Kara II(i)/Kiva II 행은 원문에서 **LA4X/LA7.16(i)/LA12X 3개 열이 하나의 값으로 병합**되어 있다 — 마크다운은 셀 병합을 표현할 수 없어 세 열 모두에 동일 값을 반복 기재한다. K1/K1-SB/L2/L2D/CS1/KS28은 실제로 특정 컨트롤러 전용(비병합, 원문 그대로).

| Product | Preset | LA1.16i SE | LA1.16i BTL | LA2Xi SE | LA2Xi BTL | LA2Xi PBTL | LA4X | LA7.16(i) | LA12X |
|---|---|---|---|---|---|---|---|---|---|
| X4i | [X4] | 107 dB | 115 dB | 116 dB | — | — | 116 dB | 116 dB | 116 dB |
| X4i | [X4_60] | 104 dB | 110 dB | 110 dB | — | — | 110 dB | 110 dB | 110 dB |
| 5XT | [5XT] | 112 dB | 120 dB | 121 dB | — | — | 121 dB | 121 dB | 121 dB |
| X6i | [X6i_50] | 110 dB | 117 dB | 117 dB | — | — | 117 dB | 117 dB | 117 dB |
| X6i | [X6i] | 115 dB | 122 dB | 122 dB | 123 dB | — | 123 dB | 123 dB | 123 dB |
| X8 | [X8] | 117 dB | 124 dB | 125 dB | 129 dB | — | 129 dB | 129 dB | 129 dB |
| X8i | [X8i_40] | 114 dB | 121 dB | 121 dB | 123 dB | — | 123 dB | 123 dB | 123 dB |
| X8i | [X8i] | 117 dB | 124 dB | 125 dB | 129 dB | — | 129 dB | 129 dB | 129 dB |
| X12 | [X12] | — | 131 dB | 131 dB | 136 dB | — | 136 dB | 136 dB | 136 dB |
| X15 HiQ | [X15] | — | — | 133 dB | — | — | 138 dB | 138 dB | 138 dB |
| Soka | [SOKA] | 119 dB | 127 dB | 128 dB | 130 dB | — | 130 dB | 130 dB | 130 dB |
| Soka | [SOKA_60] | 114 dB | 122 dB | 124 dB | 124 dB | — | 124 dB | 124 dB | 124 dB |
| Soka | [SOKA_200] | 120 dB | 130 dB | 130 dB | 133 dB | — | 133 dB | 133 dB | 133 dB |
| Syva | [SYVA] | — | — | 130 dB | 137 dB | — | 137 dB | 137 dB | 137 dB |
| A10(i) Wide | [A10](70°) | — | 132 dB | 133 dB | 137 dB | — | 137 dB | 137 dB | 137 dB |
| A10(i) Focus | [A10](70°) | — | 135 dB | 136 dB | 140 dB | — | 140 dB | 140 dB | 140 dB |
| A15(i) Wide | [A15](70°) | — | — | 136 dB | 141 dB | — | 141 dB | 141 dB | 141 dB |
| A15(i) Focus | [A15](70°) | — | — | 139 dB | 144 dB | — | 144 dB | 144 dB | 144 dB |
| K1 | [K1] | — | — | — | — | — | — | — | 149 dB |
| K1-SB | [K1SB_60] | — | — | — | — | — | — | — | 141 dB |
| K1-SB | [K1SB_100_NC] | — | — | — | — | — | — | — | 142 dB |
| K1-SB | [K1SB_X] | — | — | — | — | — | — | — | 145 dB |
| K2 | [K2 70] | — | — | — | — | — | 147 dB | 147 dB | 147 dB |
| K3(i) | [K3 70] | — | — | — | — | — | 143 dB | 143 dB | 143 dB |
| Kara II(i) | [KARA II 70] | — | — | 137 dB | — | — | 142 dB | 142 dB | 142 dB |
| Kiva II | [KIVA II] | — | 132 dB | 133 dB | 138 dB | — | 138 dB | 138 dB | 138 dB |
| L2 | [L2 70] | — | — | — | — | — | — | 155 dB(entire enclosure) | — |
| L2D | [L2D 70] | — | — | — | — | — | — | 151 dB(entire enclosure) | — |
| CS1 | [CS1_60] | — | — | — | — | — | — | 147 dB | — |
| CS1 | [CS1_X] | — | — | — | — | — | — | 150 dB | — |
| KS28 | [KS28_100] | — | — | 136 dB | — | 143 dB | — | — | 143 dB |
| KS21(i) | [KS21_100] | — | — | 131 dB | 138 dB | — | 138 dB | 138 dB | 138 dB |
| SB18(IIi) | [SB18_100] | — | — | 133 dB | 138 dB | — | 138 dB | 138 dB | 138 dB |
| SB15m | [SB15_100] | — | — | 131 dB | 137 dB | — | 137 dB | 137 dB | 137 dB |
| Syva Low | [SYVA LOW_100] | — | — | 131 dB | — | — | 137 dB | 137 dB | 137 dB |
| Syva Sub | [SYVA SUB_60] | — | 119 dB | 122 dB | — | — | 122 dB | 122 dB | 122 dB |
| Syva Sub | [SYVA SUB_100] | — | 122 dB | 123 dB | 128 dB | — | 128 dB | 128 dB | 128 dB |
| Syva Sub | [SYVA SUB_200] | — | 123 dB | 125 dB | 130 dB | — | 130 dB | 130 dB | 130 dB |
| SB10i | [SB10_60] | 111 dB | 118 dB | 119 dB | — | — | 119 dB | 119 dB | 119 dB |
| SB10i | [SB10_100] | 112 dB | 120 dB | 120 dB | 122 dB | — | 122 dB | 122 dB | 122 dB |
| SB10i | [SB10_200] | 114 dB | 123 dB | 123 dB | 125 dB | — | 125 dB | 125 dB | 125 dB |
| SB6i | [SB6_60] | 106 dB | — | 110 dB | — | — | 110 dB | 110 dB | 110 dB |
| SB6i | [SB6_100] | 106 dB | — | 111 dB | — | — | 111 dB | 111 dB | 111 dB |
| SB6i | [SB6_200] | 108 dB | — | 115 dB | — | — | 115 dB | 115 dB | 115 dB |

**Enclosure maximum SPL per amplified controller 섹션(p.124) 완료 — 사용자 제공 데이터로 병합 오류 및 누락 행(KS21(i)~SB6i) 정정(2026-07-19).**

**Impedance load/Enclosure drive capacity/Enclosure maximum SPL 섹션(p.119-124) 완료.**

## 문서 전체 완료

**Preset Guide owner's manual v.29.0 마크다운 정리 전체 완료(2026-07-19)** — p.1-124 전체(Introduction/Revision history/Preset design/Onboard preset libraries/FLAT/Progressive/Variable Curvature/Constant Curvature/Colinear/Coaxial/Subwoofer presets/Pre-alignment delay values/Impedance load/Enclosure drive capacity/Enclosure maximum SPL) 반영 완료. 개별 스피커 파일의 null 필드(Max_Enclosures_Per_Controller_Output/Total, preset_guide_and_matching, delay_defaults 등) 백필은 별도 요청 시에만 진행.
