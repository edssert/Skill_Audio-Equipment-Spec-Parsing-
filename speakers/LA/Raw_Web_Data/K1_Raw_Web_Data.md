# K1 보조 참고 자료 (출처 미검증)

**중요 — 이 파일은 SKILL.md가 정의하는 "Raw_Web_Data"(웹사이트에서 직접 복사한 원문)가 아니다.** 사용자가 대화 중 붙여넣은 이 텍스트는 실제로는 "다른 세션에서 필요에 의해 파싱한 결과물"이며(사용자 확인, 2026-07-16), L-Acoustics 공식 웹사이트나 실물 문서에서 직접 복사한 것이 아니다. 텍스트 자체가 인용하는 "preset_guide_EN.pdf(owner's manual EN v29.0)"·"manualslib.com 게재본(K1 User Manual v6.0)"은 이 프로젝트의 `upload/`나 `Original_PDFs/`에 실물로 존재하지 않는다 — 즉 이 텍스트에 담긴 수치들은 검증 가능한 1차 출처가 없는 상태다.

**처리 원칙**: 이 파일은 폐기하지 않고 참고용으로 원문 그대로 보존하되(사용자가 실제로 제공한 텍스트이므로), 마스터 스키마(K1_v1.1.md 등)에는 오직 이 프로젝트가 실제 보유한 원본 문서(K1_OM_EN_4.0.pdf)로 **직접 재검증에 성공한 항목만** 반영한다. K1_OM_EN.pdf(v4.0) 페이지를 인용하는 항목은 실제 그 페이지를 재조회해 일치 여부를 확인했고, preset_guide_EN.pdf(v29.0)나 manualslib.com(v6.0)만을 근거로 하는 항목(예: 대역별 RMS 파워 핸들링, -3dB/-6dB 대역폭, 정확한 W×H×D 치수, 프리셋별 상세 서술)은 미검증 상태로 마스터 스키마에 반영하지 않았다 — "판단 근거의 원본성 요건"(SKILL v1.13) 위반을 피하기 위함이다.

## 원문 (사용자 제공, 2026-07-16, 출처 불명확)

```
L-Acoustics · Long Throw · K Series
K1
Line Array
active
3-way

K1 Horizontal
Horizontal
Vertical
Array
8x + K1-BUMP
System Elements
▸
Rigging
Protections & Transportations
Cables
Acoustical

Max SPL
149 dB
RMS Power Handling (Total)
1118 W
Transducers
LF
2 × 15″
MF
4 × 6.5″
HF
3 × 3″
By Band
LF
422 W
MF
497 W
HF
199 W
Horizontal
90°
Inter-element Splay · 선택 각도
0.25° · 1° · 2° · 3° · 4° · 5°
Frequency Response
-3 dB
42 Hz – 19 kHz
-6 dB
38 Hz – 19 kHz
-10 dB
35 Hz – 20 kHz
General

Dimensions (W×H×D)
mm
in
1342 x 438 x 520 mm
Weight
kg
lb
106 kg
IP Rating
IP43
Connectors
8-point PA-COM x2 (IN 1 + LINK 1)
Amplifier Matching

Amplifier
Mode
Preset
Links/ch
Max/amp
Max SPL
LA12X
—
[K1]
2
2
149 dB
Preset Guide
▸
Loudspeaker Configuration
Preset
Acoustic Properties
K1 line source
[K1]
35 Hz - 20 kHz
K1​+​K1-SB​(on top)
[K1]​+​[K1SB_X]
enhanced throw, down to 30 Hz
K1​+​coupled K1-SB​(beside/behind)
[K1]​+​[K1SB_60]
side/rear cardioid, down to 33 Hz
K1​+​coupled K1-SB​(behind, NC)
[K1]​+​[K1SB_100_NC]
rear cardioid, down to 25 Hz
K1​+​subwoofers​(KS28/SB28)
[K1]​+​[xx28_60]
reinforced contour, down to 25 Hz
K1​+​coupled CS1​(beside/behind)
[K1]​+​[CS1_60]
rear cardioid, down to 25 Hz
K1​+​coupled CS1​(supercardioid)
[K1]​+​[CS1_60_S]
supercardioid, down to 25 Hz
K1​+​Kara II​(downfill)
[K1]​+​[KARAIIDOWNK1]
35 Hz - 20 kHz, downfill
K1​+​K2​(downfill)
[K1]​+​[K2 110]
35 Hz - 20 kHz, downfill
참고 사항
▸
Acoustic Properties 열의 주파수 대역(예: "35 Hz - 20 kHz", "down to 25 Hz")은 원문 서문(p.49)에 명시된 대로 -10 dB 기준 대역폭/저역 한계다.
카디오이드 배열(측면·후면으로 향하는 저역을 상쇄해 무대 뒤나 옆으로 새는 저음을 줄이는 배치)로 세울 때는 [xx28_60_C] 또는 [xx28_60_Cx] 프리셋을 쓴다.
호환성 주의: 프리셋 라이브러리 4.0 버전을 기점으로 [K1] · [KARADOWNK1] · [K2 xxx] 프리셋의 내부 구성이 바뀌어, 4.0 이후 버전과 4.0 이전 버전은 서로 호환되지 않는다. 같은 라인 소스(어레이) 안의 모든 유닛은 반드시 동일한 라이브러리 버전을 써야 한다(일부만 다른 버전이면 유닛 간 특성이 어긋난다).
출력 라우팅(공식 매뉴얼 Preset Description, p.50/p.16 기준)은 프리셋 그룹에 따라 다음 두 가지로 나뉜다. 게인·딜레이·극성 등 나머지 파라미터 기본값은 Delay Defaults 표 참고.
[K1] / [K2 xxx] 계열: OUT1=좌측 LF, OUT2=우측 LF, OUT3=MF, OUT4=HF.
[K1SB_X] / [K1SB_60] / [K1SB_100_NC] 등 K1-SB 서브우퍼 계열: OUT1~4 네 채널 전부 SB(서브우퍼) 채널로 통일.
출처: preset_guide_EN.pdf p.49-50 (owner's manual EN v29.0); 교차검증: L-Acoustics K1 User Manual "Preset description" p.23 (manualslib.com 게재본, v6.0); K1_OM_EN.pdf(owner's manual EN v4.0) p.34-45(매칭 비율/최소 라인 길이/딜레이), p.16(라우팅 재검증)
Matching Ratio & Minimum Line Length
▸
Loudspeaker Configuration
Recommended Ratio
Minimum Line Length
K1​+​K1-SB​(on top)
2 K1 : 1 K1-SB
8 K1 + 4 K1-SB
K1​+​coupled K1-SB​(beside/behind)
1 K1 : 1 subwoofer
—
K1​+​coupled K1-SB​(behind, NC)
1 K1 : 1 subwoofer
—
K1​+​subwoofers​(KS28/SB28)
1 K1 : 1 subwoofer
—
K1​+​coupled CS1​(beside/behind)
2 K1 : 1 CS1
—
K1​+​coupled CS1​(supercardioid)
2 K1 : 1 CS1
—
K1​+​Kara II​(downfill)
up to 6 Kara II
—
참고 사항
▸
Downfill(무대 바로 앞 관객 등 어레이 아래쪽 사각지대를 보완하는 추가 수직 커버리지) 프리셋은 라인마다 다르다. 위 표의 K1(신형) 라인 외에 구형 라인은 다음 프리셋을 쓴다.
K2 라인: [K2 110] / [K2 90] / [K2 70]
Kara: [KARADOWNK1]
Kara II: [KARAIIDOWNK1](110°) / [KARAIIDOWNK1 70] / [KARAIIDOWNK1 90](이 중 [KARAIIDOWNK1]은 Kara II를 110° 핀 설정으로 조립했을 때 맞춰 최적화된 프리셋).
출처: K1_OM_EN.pdf (K1 owner's manual EN version 4.0) p.35-45; 구형 라인 Downfill 프리셋명은 preset_guide_EN.pdf p.49-50 (owner's manual EN v29.0)
Delay Defaults
▸
Preset combo
Pre-alignment delay & Polarity
[K1] + [K1SB_X]
K1 = 0 ms
K1-SB = 0 ms
[K1] + [K1SB_60]
K1 = 6 ms
K1-SB = 0 ms
[K1] + [K1SB_100_NC]
K1 = 8.3 ms
K1-SB = 0 ms (−)
[K1] + [KS28_60]
K1 = 0.5 ms
KS28 = 0 ms (−)
[K1] + [KS28_60_C]
K1 = 6 ms
KS28 = 0 ms (−)
[K1] + [KS28_60_Cx]
K1 = 4 ms
KS28 = 0 ms (−)
[K1] + [K1SB_X] + [KS28_60]
K1 = 0 ms
K1-SB = 0 ms
KS28 = 0 ms (−)
[K1] + [K1SB_X] + [KS28_60_C]
K1 = 5.5 ms
K1-SB = 5.5 ms
KS28 = 0 ms (−)
[K1] + [K1SB_X] + [KS28_60_Cx]
K1 = 3.5 ms
K1-SB = 3.5 ms
KS28 = 0 ms (−)
[K1] + [CS1_60] / [CS1_60_S]
K1 = 7.5 ms
CS1 = 0 ms (−)
[K1] + [K1SB_X] + [CS1_60] / [CS1_60_S]
K1 = 7.5 ms
K1-SB = 7.5 ms
CS1 = 0 ms (−)
참고 사항
▸
위 표의 값은 pre-alignment(사전 정렬) 딜레이와 극성 기본값을 함께 표기한 것이며, 실제 현장에서는 여기에 배치 간격에 따른 geometric(기하학적) 딜레이를 추가로 더해야 한다(극성은 geometric 딜레이와 무관하게 표에 적힌 그대로 유지).
별도 표기가 없으면 극성은 반전 없는 정상(+). 빨간색 (−) 표시가 있는 엘리먼트만 반전이다. K1은 모든 조합에서 항상 정상(+). K1-SB는 [K1SB_X]/[K1SB_60] 조합에서는 정상, [K1SB_100_NC](노이즈 컨트롤) 조합에서는 반전. KS28과 CS1은 K1과 병용하는 모든 조합에서 항상 반전(카디오이드/서브우퍼 위상 상쇄를 위한 의도된 설정).
geometric 딜레이(K1-SB를 서브우퍼로 배치 시): 간격 1.5 m(5 ft)면 4.5 ms, 2 m(7 ft)면 6 ms 추가.
[K1]과 [K1SB_X]([K1-SB]를 K1과 같은 라인소스 안에 편입할 때)는 서로 딜레이를 추가하지 않는다(동일 라인소스 내 엘리먼트이기 때문). K1-Kara II, K1-K2(다운필) 조합도 마찬가지로 딜레이 추가 금지.
출처: K1_OM_EN.pdf (K1 owner's manual EN version 4.0) p.37-38, 40, 42, 딜레이/극성 기본값 표
Mechanical Safety
▸
Flown
Configuration
Rigging accessory
Safe limit
Maximum limit
flown
K1-BUMP
16
24
flown
K1-BUMP
14 K1 + 3 LA-RAK II AVB
23 K1 + 4 LA-RAK II AVB
flown with a downfill
KARA-DOWNK1
6 Kara II
6 Kara II
Stacked / Other configurations
Configuration
Rigging accessory
Safe limit
Maximum limit
stacked
K1-CHARIOT
4
4
항상 혼합 어레이(mixed array)의 안전계수는 Soundvision을 참조할 것. K1 어레이를 Kara II 다운필과 함께 플라잉할 때는 시스템 전체 엘리먼트의 기계적 안전을 고려해야 하며, 위 표의 maximum limit은 K1에만 적용된다.
LA-RAK II AVB를 위에 얹은 K1 어레이에는 풀백(pullback)을 적용하지 말 것.
Kara II 다운필이 있는 K1 어레이에는 풀백을 적용하지 말 것.
참고 사항
▸
Safe limit: 이 매뉴얼에 정의된 용도 내에서, 사이트 각도·인터엘리먼트 각도 등 다른 배치 변수와 무관하게 2006/42/EC 기계지침 기준을 항상 만족하는 최대 엘리먼트 수.
Maximum limit: 다른 배치 변수가 최선의 기계적 조건을 제공할 때 2006/42/EC 기준을 만족할 수 있는 최대 엘리먼트 수.
K1 리깅 시스템은 2006/42/EC 기계지침을 준수하며 BGV-C1 가이드라인에 따라 설계됐다. 이 지침은 파단에 대해 안전계수 4를 요구하며, 이 매뉴얼에 기술된 플라잉 배치는 안전계수 4 이상을 달성한다. 특정 배치의 정확한 안전계수는 Soundvision을 참조.
안전성 평가 원칙(Assessing mechanical safety, p.33): 정격 WLL만으로는 복합 기계 시스템의 안전성을 판단할 수 없다.
각 연결점의 작업 하중과 안전계수는 어레이 구성(인클로저 종류·수량·스플레이 각도)과 플라잉/스태킹 구조(플라잉 포인트 수·위치, 사이트 각도)에 좌우되며 Soundvision의 복합 기계 모델링 없이는 판단 불가.
전체 안전계수는 항상 모든 연결점 중 가장 낮은 값을 따른다. Soundvision Mechanics view에서 가장 약한 연결점을 확인할 것.
그라운드 스택 어레이는 Soundvision에서 별도 전도 위험(tipping hazard) 경고가 표시된다(어레이 고정 및 경고 무시 여부는 사용자 책임).
플라잉 시 사용 가능한 홀을 활용해 2차 안전장치(secondary safety)를 구현할 것.
극한 고온/저온, 강풍, 장기간 염수 노출 등 특수 환경에서는 더 높은 안전계수가 권장되며, 리깅 전문가와 상담할 것.
출처: K1_OM_EN.pdf (K1 owner's manual EN version 4.0) p.31-33, K1 관련 부분만 발췌
```

**참고**: 이 텍스트 자체에 포함된 출처 각주(예: "preset_guide_EN.pdf p.49-50 owner's manual EN v29.0", "manualslib.com 게재본 v6.0")는 웹 페이지가 자체적으로 표기한 출처이며, 작성 당시(K1_v1.1 갱신 시점)에는 이 프로젝트의 `upload/`에 K1_OM_EN.pdf(version 4.0)만 제공되어 있어 검증할 수 없었다.

**갱신(2026-07-16, K1_v1.2 시점)**: 사용자가 이후 `preset-guide-en.pdf`(실제로 "Preset Guide owner's manual (EN) version 29.0" — 이 텍스트가 인용한 버전과 정확히 일치)와 `amplification-reference-tb-en.pdf`(Amplification reference technical bulletin v16.0)를 실물로 제공, `speakers/LA/References/`에 보존했다. 이 두 실물 문서로 재검증한 결과: (1) K1 Max SPL 149dB, 앰프 매칭 LA12X 2/2 — 완전 일치 확인. (2) K1+K1-SB 프리셋별 대역폭("down to 30 Hz"/"down to 33 Hz" 등) — 이 텍스트가 "on top"(K1SB_X) 행에 잘못 붙인 "down to 30 Hz"를 제외하면 나머지는 preset-guide-en.pdf v29.0 원문과 일치. 즉 이 텍스트는 완전히 근거 없는 창작이 아니라, 실제 문서(v29.0) 정보를 요약하는 과정에서 행이 밀리는 오류가 발생한 것으로 추정된다. (3) 다만 RMS 파워 핸들링 대역별 수치(LF 422W/MF 497W/HF 199W)와 -3dB/-6dB 대역폭은 이 두 실물 문서 어디에도 없어 여전히 미검증 — manualslib.com v6.0처럼 이 프로젝트가 보유하지 않은 제3의 문서에서 나왔을 가능성이 있으며, 마스터 스키마에는 반영하지 않는다.
