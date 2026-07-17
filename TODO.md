# TODO — 진행 중/예정 작업

이 파일은 **현재 진행 중이거나 예정된 작업만** 담는다. 완료/취소된 항목은 여기서 바로 지우고 `TODO_Archive.md`에 한 줄 기록으로 옮긴다. 세션 시작 시 이 파일과 `Session_Transfer_v*.md`의 "긴급 인계" 섹션을 함께 확인할 것.

**운영 규칙(사용자 지시, 2026-07-17)**: 세션 토큰이 소진되어 강제 종료되기 전에 이 파일을 항상 최우선으로 최신 상태로 갱신해둘 것. **신규 제품 파싱은 서브에이전트 병렬 실행 없이 제품 1개씩 순차 진행**(작업 속도보다 토큰 효율이 제1원칙). 가능하면 서브에이전트 위임보다 메인 세션에서 직접 처리(이미 SKILL.md/CLAUDE.md 컨텍스트 보유).

마지막 갱신: 2026-07-18

## 진행 중

- [ ] **버전 변경 이력(버전 이력 표) 보강 필요** — 오늘(2026-07-18) 대규모로 버전 승격된 파일들 중 일부(특히 새로 Product_Type/Series curvature 재정의를 적용한 K/A/L2 계열)에 아직 해당 버전의 "버전 변경 이력" 표 행이 없음 — 다음 세션에서 전체 점검 후 일괄 보강 필요(데이터 자체는 정확하나 changelog 기록이 누락된 상태).

## 완료 — PANTHER(Meyer Sound) L/M/W 개별 파일 분리 (사용자 지시 2026-07-17/18)

통합 파일(`PANTHER_v1.0.md`~`v1.9.md`, 전체 이력 `speakers/MY/Archive/PANTHER/`에 보존)에서 `PANTHER_L_v1.0.md`/`PANTHER_M_v1.0.md`/`PANTHER_W_v1.0.md` 3개 파일로 분리 완료 — 베리언트 간 차이는 3개 Key뿐(Max_SPL_Peak: 150.5/150.5/149.5dB, AES75_Max_Linear_SPL, Nominal_Directivity_Horizontal_deg: 80/95/110°), 나머지 전 섹션(트랜스듀서/커넥터/전원/보호회로/네트워크/앰프요구사항/리깅/치수/기계안전)은 3개 파일 완전 동일값(원본 자체가 이 3개 값 외엔 베리언트를 구분하지 않음). Original_PDFs도 L2/L2D·Syva 전례에 따라 공용 OM/AE/SPS를 3개 폴더 각각에 복제 보존. `speakers/CLAUDE.md`의 "제품 구성 판단" 절에 이 사례가 기존 파트넘버 기준 원칙의 예외임을 명시(향후 유사 사례에서 자동 일반화하지 않도록 경고 포함).

## 완료 — signal_processing 섹션(d&b 고유 CUT/HFC/Coupling) 전면 삭제 (사용자 지적 2026-07-18)

`speakers/CLAUDE.md` 규칙 2("브랜드 고유 물리 설계·기능명이 Key 이름에 박힌 경우 다른 파일에 null로 끌어오지 않고 아예 생성하지 않는다") 위반 발견 — CUT_Mode_Available/HFC_Function_Settings/Coupling_Function_Range(d&b GSL8/GSL12 전용 기능)가 `speakers/LA` 41개 파일 전부에 null placeholder로 잘못 동기화되어 있었음. 전 41개 파일에서 signal_processing 섹션 완전 삭제, Null Report 비적용 카운트 재계산 완료(모든 총계 라인 재검증). GSL8/GSL12 자신은 실값 유지(영향 없음).

## 완료 — 버전닝 프로토콜 위반 소급 시정 (2026-07-18)

Cardioid_Capability/Product_Series 작업을 34개 기존 버전 파일에 Surgical Versioning Protocol(Duplicate→Archive→Edit) 없이 직접 편집한 위반을 발견·시정 — git 미커밋 상태였던 덕에 원본을 git HEAD에서 복구해 각 파일의 Archive 폴더로 이관, 라이브 파일은 전부 다음 마이너 버전으로 승격(K1 v1.9→v1.10, KS21 v1.2→v1.3 등). 이 과정에서 PowerShell 스크립트의 `$1` 변수보간 버그로 Null Report "비적용" 줄이 여러 차례 손상되었으나(원본 소스 기반 재구성으로) 전부 복구 및 구조 검증 완료.

## 완료 — "시간 배분상/시간 제약상" 전수 재조사 (사용자 지적 2026-07-18)

프로젝트 전체(`speakers/`, `amplifiers/`, 루트) 대상 재스캔 완료. 대부분은 과거 위반을 시정했다는 정상적인 changelog 기록(과거형 서술)이었음을 확인. **실제 라이브 위반 3건 발견 및 원본 재조사로 해소**: (1) KS21 Dimensions_Raw — OM 도면 4개 숫자(764/602/569/571mm) 확보. (2) L2 mechanical_safety — OM p.49 페이지 이미지 렌더링으로 누락된 5개 리깅 구성(L2-ROLL/L2-RIGBAR 풀백/L2-CHARIOT+K2-JACK 스택 등) 전부 확보, 표 완성. (3) X8i rigging_handling 각주 — 이미 정당한 사유(스키마 구조상 한계)가 각주 [1]에 있었으나 문구 자체에 남아있던 금지 표현만 정리.

## 완료 — Product_Type/Product_Series 신규 Key 2종 전면 투입 (사용자 지시 2026-07-17/18)

`speakers/LA`(41개) + `speakers/db`(GSL8/GSL12) + `speakers/MY`(PANTHER) 전체 44개 파일에 100% 적용 완료(검증 스크립트로 재확인). 소스는 대부분 제품 자신의 AE docx 최상단 헤더(L-Acoustics 표준 형식: "제품명 - Type" / "Series" / throw 거리 / 배치방식 / 곡률방식), AE 미제공 제품(CS1/Sokar/SB6r/SB10r/X4r 등)은 install/recessed 상속 정책 또는 OM 본문 서술로 확보(짐작 없음). d&b(GSL8/GSL12)는 OM 본문에서 "SL-Series" 명시적 확인(사용자의 "아마 SL 시리즈" 추정을 원문으로 검증), Meyer Sound(PANTHER)는 3개 문서 전량 스캔 결과 시리즈명 자체가 없음을 확인(null).
**중요한 사용자 정정(2026-07-18)**: Product_Type을 처음엔 AE 헤더 1번째 줄("Medium/Long throw line source" — A/K 시리즈 공통이라 구분력 없음)로 채웠으나, 사용자가 A 시리즈는 "Constant Curvature Line"이어야 하지 않냐고 지적 — 재검토 결과 AE 헤더 5번째 줄("Incremental coverage with fixed/variable inter-element angles")이 실제 구분축임을 확인하고 전면 재정의: A 시리즈(8개 파일)="Constant Curvature Line Source"(fixed 각도), K 시리즈(K1/K2/K3/K3i/Kara_II/Kara_IIi/Kiva_II, 7개 파일)="Variable Curvature Line Source"(variable 각도), L2/L2D="Progressive Curvature Line Source"(원문 자체가 "PROGRESSIVE" 명시). X 시리즈(점음원)는 "Short throw point source" 유지, 서브우퍼류는 "Subwoofer" 유지, Soka/Sokar/Syva 계열(colinear)은 "Ultra-shallow colinear source"/"Medium throw colinear source" 유지 — 이 카테고리들은 사용자 지적이 curvature 축에 한정되어 재검토 대상 아니었음.
발견된 원문 비일관성(임의 통일하지 않고 그대로 보존): X6i/X8i는 "Xi Series"인데 X4i는 동일 install 계열임에도 "X Series"(i 없음); Soka는 시리즈명이 없는데 Syva(동일 colinear 계열)는 "S Series" 있음.

## 완료 — install/recessed 버전 주파수응답·파워핸들링 상속 정책 적용 (사용자 지시 2026-07-18)

정책: "설치형/매입형 버전이 표준형과 치수·무게·리깅 외 특이사항이 없다면 드라이버·인클로저 구성이 동일 스펙이므로 Frequency_Response_6dB/3dB_Hz·RMS_Power_Handling(LF/Overall)은 상속 가능(WEEE_Marking 등 규제/물리 마킹은 제외)". 4개 파일 모두 적용 완료(전부 스켈레톤 근거 각주에서 스펙 완전 동일성이 이미 독립 확인된 상태였음을 재확인 후 진행) — Sokar_v1.1.md(Soka 값: Frequency_Response_6dB/3dB_Hz, RMS_Power_Handling_Overall=133W), X4r_v1.3.md(X4i 값: 상동 + RMS_Power_Handling_Overall=42W), SB6r_v1.3.md(SB6i 값: Frequency_Response_6dB/3dB_Hz + RMS_Power_Handling_LF=85W; RMS_Power_Handling_Overall은 SB6i 자신도 구조적 비적용이라 상속 대상 없음), SB10r_v1.1.md(SB10i 값: 상동 + RMS_Power_Handling_LF=146W). 전부 Surgical Versioning Protocol 준수(git 미커밋 신규 버전 파일이라 직접 편집 가능했음). Null Report 재계산 완료.

## 완료된 신규 제품 (2026-07-17): CS1, SB10i, SB10r, SB15m, SB18, SB18_IIi, Soka, Sokar, Syva, Syva_Low, Syva_Sub, X15 HiQ, 5XT

13개 제품 모두 파싱 완료, 소스 원본은 각 `speakers/LA/Original_PDFs/{제품명}/`에 파일링, `upload/`는 이제 완전히 비어있음(정리 완료). 상세는 `TODO_Archive.md` 참조.

## 완료 — 최종 동기화 라운드(TaskList #39, 2026-07-17)

`Cardioid_Capability` 신규 Key를 `speakers/LA`(35개 파일) + `speakers/db`(GSL8/GSL12) + `speakers/MY`(PANTHER) 전 제품에 전면 동기화 완료 — 각 제품 자신의 OM/AE 전량을 "cardioid" 키워드로 직접 스캔해 확정(짐작 없음). 4가지 유형으로 분류: (1) Built-in — CS1(전방+측면 드라이버 분할), GSL8/GSL12(하이브리드 크로스오버 기반 150Hz 이하 자연 수렴); (2) Array-based only — KS28/KS21/KS21i/SB15m/SB18/SB18_IIi(4대 어레이 중 1대 물리적 반전 배치 필요, 전용 [xxxx_xx_C]/[xxxx_xx_Cx] 프리셋); (3) Array-based, 전용 드라이버군+프리셋 — L2/L2D(LC 드라이버군 내장 + standard array + 프리셋 선택, 반전 불필요); (4) Array-based, automatic — PANTHER(4대 이상 표준 배치 기하학적 설계만으로 자동 발현, 반전·프리셋 모두 불필요). 나머지 전 제품(K1/K2/K3/K3i/Kara_II/Kara_IIi/Kiva_II/X 시리즈 전체/SB6i/SB6r/SB10i/SB10r/A 시리즈 전체)은 No(원문 전량 스캔 0건 확정, 검출된 언급은 전부 컴패니언 서브우퍼 참조였음을 각주로 명시). 사용자 질문에 따라 "array of 4" 요건이 전 소스에서 예외 없이 일관됨을 재확인(2유닛 전후 배치 등 대체 구성 언급 없음 — 짐작하지 않고 원문 그대로 유지). SB15m의 `[SB15_100_Cx]` 프리셋 불일치(X8/X12는 자체 OM에 존재, SB15m 자신의 UM엔 부재)는 양쪽 파일 모두에 상호 참조 각주 추가로 재검토 완료(값 변경 없음, 각자 자기 소스 근거 보존). `speakers/LA`(41개 파일) + db/MY 전체에 걸친 자동화된 Key 목록 파리티 점검도 완료 — HF/MF 관련 Key 격차는 전부 아키텍처상 정당한 부재(순수 서브우퍼는 HF 없음, 2-way 제품은 MF 없음)로 확인, 커넥터 핀아웃 Key(SpeakON/Terminal_Block/PA_COM/AutoConnect/Screw_Terminal)는 설계대로 제품별 고유 유지, 그 외 범용 Key는 전부 100% 커버리지 확인. GSL8/GSL12 Key 목록 완전 동일 확인.

## 신규 발견 — 치수(Dimensions) W/H/D 축 구분 신뢰도 문제 (사용자 지적 2026-07-17)

**문제**: 다수 제품의 치수 도면(dimensions drawing)은 정면도/측면도 등 여러 뷰가 한 페이지에 있고, 뷰마다 숫자가 여러 개 찍혀 있어(예: Syva dimensions 도면은 209mm/144mm/1304mm/1301mm/170mm 5개 숫자가 한 페이지에 존재) pdftotext로 추출한 순서만으로는 어느 숫자가 W/H/D 중 무엇인지 신뢰성 있게 구분하기 어렵다. 지금까지는 A&E 시방서가 명시적으로 "Dimensions (W, H, D): X, Y, Z"로 축을 라벨링해준 경우에만 축을 확정하고, 나머지 도면 숫자는 "부가 치수로 추정"이라는 각주로 얼버무려 왔다(예: A10_Focus의 Dimensions_Raw 각주 "5개 숫자 중 581/339는 AE와 일치, 354는 근사, 나머지는 부가 치수로 추정"). A&E가 없는 제품(예: Sokar, SB6r, SB10r 등 recessed 계열)은 도면 숫자만으로 W/H/D를 판정해야 하는데, 이 판정이 실제로 도면을 시각적으로 재확인하지 않고 이전 제품과의 수치 유사성만으로 이루어진 경우가 있었을 가능성 있음.
**할 일**: 전체 제품 파일을 대상으로 Width_mm/Height_mm/Depth_mm 값이 (1) A&E의 명시적 축 라벨링으로 확정된 것인지, (2) 도면 이미지 렌더링으로 시각적으로 축을 확인한 것인지, (3) 단순히 다른 제품과의 수치 유사성/추정으로 채워진 것인지 감사 필요. (3)에 해당하는 경우 도면을 이미지로 직접 렌더링해 치수선이 어느 변에 걸쳐 있는지 육안 확인 후 정정.
**추가 검증축(사용자 지적 2026-07-17, 2차)**: "(W, H, D)"라는 축 표기 **순서 자체가 브랜드/문서마다 다를 수 있음**을 짐작하지 말고 검증할 것 — 지금까지 L-Acoustics 제품들은 A&E가 "Dimensions (W, H, D): X, Y, Z" 형식으로 일관되게 표기해왔다는 전제로 W=X/H=Y/D=Z를 기계적으로 매핑해왔으나, (a) L-Acoustics 내에서도 문서마다 실제로 항상 이 순서인지 재확인 필요, (b) d&b audiotechnik(GSL8/GSL12)·Meyer Sound(PANTHER) 등 **타 브랜드 문서는 축 표기 순서/라벨링 관례 자체가 다를 수 있음** — 각 브랜드 문서에서 실제로 어떤 순서로 축을 라벨링하는지 원문 문구를 직접 확인(예: "(W, H, D)"가 아니라 "(H, W, D)"나 별도 도면 라벨링 방식일 가능성)한 후 매핑할 것, 임의로 L-Acoustics 관례를 다른 브랜드에 적용하지 않는다.
이 작업은 별도 감사 라운드로 분리 — 최종 동기화 라운드(TaskList #39)와는 성격이 다르므로 함께 묶지 않고 독립 항목으로 추적.

## 참고

- TaskList 도구(#13~#39)에도 동일 항목이 있음 — 이 파일과 병행 사용.
- **Null Report 항목 수 재계산 시 특히 주의** — "콤바인된 불릿"(예: `RMS_Power_Handling_LF/MF/HF`) 패턴에서 반복적으로 오카운트가 발생했다. 항상 실제 콤마-구분 항목을 직접 세어 "— N건" 표기와 대조할 것.
- **서브에이전트 병렬 실행 시 세션 사용량 한도 주의** — 8개 동시 실행 시 전부 세션 한도 초과로 실패한 전례 있음. 신규 제품 파싱은 1개씩 순차 진행(위 운영 규칙 참조).
- git: origin/main에 6b972b7까지 푸시됨(2026-07-17, 5XT 추가 커밋). 이후 오늘(2026-07-18)의 모든 작업(signal_processing 삭제/버전닝 소급 시정/시간 배분상 재조사/install-recessed 상속/Product_Type·Series 전면 투입)은 전부 미커밋 상태(git status 약 134개 변경 파일) — 사용자가 명시적으로 요청하기 전까지 커밋하지 않는다. **주의**: 과거 세션에 커밋 메시지 전체를 빈 문자열로 덮어쓴 이력 있음(사용자 명시적 지시로 진행, force-push 완료) — 커밋 메시지는 향후에도 신경 써서 정확하게 작성할 것.
