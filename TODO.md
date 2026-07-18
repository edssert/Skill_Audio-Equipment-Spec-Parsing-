# TODO — 진행 중/예정 작업

이 파일은 **현재 진행 중이거나 예정된 작업만** 담는다. 완료/취소된 항목은 여기서 바로 지우고 `TODO_Archive.md`에 한 줄 기록으로 옮긴다. 세션 시작 시 이 파일과 `Session_Transfer_v*.md`의 "긴급 인계" 섹션을 함께 확인할 것.

**운영 규칙(사용자 지시, 2026-07-17)**: 세션 토큰이 소진되어 강제 종료되기 전에 이 파일을 항상 최우선으로 최신 상태로 갱신해둘 것. **신규 제품 파싱은 서브에이전트 병렬 실행 없이 제품 1개씩 순차 진행**(작업 속도보다 토큰 효율이 제1원칙). 가능하면 서브에이전트 위임보다 메인 세션에서 직접 처리(이미 SKILL.md/CLAUDE.md 컨텍스트 보유).

**운영 규칙 2(사용자 지시, 2026-07-18)**: 완료된 항목은 상세 서술을 이 파일에 남기지 말고 즉시 `TODO_Archive.md`로 옮겨 한 줄 요약만 남긴다. 완료 로그에도 제품 나열 등 헤비한 상세는 넣지 말고 간결하게 유지한다(사용자 지시 2026-07-18).

**운영 규칙 3(사용자 지시, 2026-07-18 심야)**: 사용자가 자리비움 — 질문하지 말고 계속 작업 진행(판단 필요 지점은 합리적으로 스스로 결정, 각주로 근거 남김). TODO.md 갱신을 항상 최우선으로 유지.

마지막 갱신: 2026-07-18 14:05

## 진행 중

- [ ] **`upload/` 폴더에 Meyer Sound 신규 제품 대량 투입됨(2026-07-18 오후) — 파싱 시작 대기**. 컨텍스트 클리어 직후 시작할 다음 작업. speakers/MY 스켈레톤(PANTHER/TIGRA/LEOPARD/LINA)을 그대로 재사용 가능 — self-powered 아키텍처, Linear_Peak_SPL/전류 기반 소비전력 등 기존에 확립된 Key 체계와 호환될 가능성 높음(단, 서브우퍼 제품군이라 LF-only 구조일 것 — Way_Count/transducers 섹션은 자체 판단 필요, "이름으로 구조 짐작 금지" 원칙 준수).
  - **원본 3종(AE+SPS+OM) 완비**: 2100-LFC.
  - **OM+SPS만(AE 없음)**: 750-LFC, 900-LFC, MM-10, USW-112P, USW-112XP, USW-210P.
  - **AE+SPS만(OM 없음)**: USW-121P.
  - **SPS만(OM/AE 둘 다 없음)**: VLFC, X-400C.
  - **극히 제한적 — "Preliminary Product Information"만 존재(정식 Datasheet/OM 아님, 프리릴리즈 추정)**: 1800-LFC — 파싱 가능 여부 자체를 먼저 판단할 것, 정식 스펙 문서가 아니므로 무결성 원칙상 데이터가 부족할 수 있음.
  - **제품 전용 문서 아님, 브랜드 공용 참고자료로 추정(References/ 폴더 후보, speakers/LA/References/ 전례 참조)**: "Installation Instructions — IntelligentDC Products Wiring Verification.pdf", "Wiring_ 48 V IntelligentDC loudspeakers.pdf" — IntelligentDC는 Meyer의 데이지체인 배선/전원분배 시스템으로 추정, 여러 제품에 걸쳐 참조될 수 있음. speakers/MY/References/ 폴더가 아직 없으므로 신설 필요.
  - **권장 진행 순서**: 원본이 가장 풍부한 2100-LFC부터 시작(TIGRA 전례와 동일 이유) → OM+SPS 완비 제품 6개 순차 진행 → AE+SPS만 있는 USW-121P → SPS만 있는 VLFC/X-400C → 1800-LFC는 별도 판단. **제품 1개씩 순차 처리, 서브에이전트 병렬 금지**(운영 규칙 1 참조).

## 참고

- **완료 — Null Report 결합형 불릿 오카운트 감사, speakers 전체 40개 파일(2026-07-18)**: speakers/LA 32개(preset_guide_and_matching 다중 행 부분-null 26개 + 기타 결합형 불릿 6개) + speakers/MY 8개(mechanical_safety Safe_Limit 다중 행, PANTHER x3/TIGRA x2/LEOPARD x2/LINA 전부) 정정. 데이터(Key/Value/Unit)는 건드리지 않고 Null Report 요약 통계만 정정. 상세는 `TODO_Archive.md` 참조.
- **완료 — Meyer Sound 신규 제품 3종(TIGRA/LEOPARD/LINA) 투입(2026-07-18)**: 5개 파일 신규 작성, 신규 Key 9종 발견 및 PANTHER/TIGRA 전체에 양방향 동기화 완료. 상세는 `TODO_Archive.md` 참조.
- **완료 — Session_Transfer_v1.10.md 갱신**: v1.9가 크게 낡아 있어 전면 재작성.
- **TaskList 도구는 파일이 아닌 하네스 자체 기능(세션/도구 상태)이라 영구 보존되지 않는다** — 과거 세션에서 병행 사용했던 흔적(#13~#39)이 있었으나 2026-07-18 확인 결과 비어있음(초기화됨). TODO.md/TODO_Archive.md(커밋되는 파일)만 신뢰할 것 — TaskList는 현재 세션 내 임시 작업 분해용으로만 필요시 보조 사용.
- **Null Report 항목 수 재계산 시 특히 주의** — Key-Value 단순 리스트의 "콤바인된 불릿"뿐 아니라 **다중 행 테이블(preset_guide_and_matching/mechanical_safety 등)의 부분-null 컬럼도 행×컬럼 단위로 정확히 세어야 한다**(2026-07-18에 반복 확인된 패턴).
- **서브에이전트 병렬 실행 시 세션 사용량 한도 주의** — 8개 동시는 실패 전례 있음, 4개 배치 병렬까지는 안정적 확인.
- **changelog 기록 정확성 주의** — 완료 항목을 "완료"로 기록하기 전 실제로 파일을 grep/diff로 재확인할 것.
- **버저닝 프로토콜 "변경 없음" 판명 시** — Duplicate+Archive까지 했더라도 실질 변경이 없다면 버전을 새로 만들지 않고 원상복구할 것.
- **커밋된 파일 편집 전 항상 git status 먼저 확인** — 여러 파일을 순회 편집할 때 이미 커밋된 파일과 미커밋 파일이 섞여 있을 수 있다.
- git: origin/main에 4131d21까지 커밋+푸시 완료(2026-07-18, 사용자 명시적 지시). 작업 트리 클린, 미커밋 변경 없음. 다음 변경분도 사용자 명시적 요청 시에만 커밋.
