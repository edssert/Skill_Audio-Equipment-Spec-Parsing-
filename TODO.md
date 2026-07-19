# TODO — 진행 중/예정 작업

이 파일은 **현재 진행 중이거나 예정된 작업만** 담는다. 완료/취소된 항목은 여기서 바로 지우고 `TODO_Archive.md`에 한 줄 기록으로 옮긴다. 세션 시작 시 이 파일과 `Session_Transfer_v*.md`의 "긴급 인계" 섹션을 함께 확인할 것.

**운영 규칙(사용자 지시, 2026-07-17)**: 세션 토큰이 소진되어 강제 종료되기 전에 이 파일을 항상 최우선으로 최신 상태로 갱신해둘 것. **신규 제품 파싱은 서브에이전트 병렬 실행 없이 제품 1개씩 순차 진행**(작업 속도보다 토큰 효율이 제1원칙). 가능하면 서브에이전트 위임보다 메인 세션에서 직접 처리(이미 SKILL.md/CLAUDE.md 컨텍스트 보유).

**운영 규칙 2(사용자 지시, 2026-07-18)**: 완료된 항목은 상세 서술을 이 파일에 남기지 말고 즉시 `TODO_Archive.md`로 옮겨 한 줄 요약만 남긴다. 완료 로그에도 제품 나열 등 헤비한 상세는 넣지 말고 간결하게 유지한다(사용자 지시 2026-07-18).

**운영 규칙 3(사용자 지시, 2026-07-18)**: 사용자가 자리비움 — 질문하지 말고 계속 작업 진행(판단 필요 지점은 합리적으로 스스로 결정, 각주로 근거 남김). TODO.md 갱신을 항상 최우선으로 유지.

마지막 갱신: 2026-07-19 (Preset Guide 마크다운 정리 전체 완료)

## 진행 중

(현재 없음 — Preset Guide 마크다운 정리 완료. 다음 세션은 사용자 지시 대기. 남은 후속 작업은 아래 "참고" 항목의 백필 미착수 메모 참조.)

## 참고

- **완료 — Preset_Guide_OM_EN_29.0.md 전체 작성(2026-07-19)**: `speakers/LA/References/`에 원본 PDF(124페이지) 전체를 표 형식으로 마크다운 정리(Introduction/Revision history/Preset design/Onboard preset libraries/FLAT/Progressive/Variable·Constant Curvature/Colinear/Coaxial/Subwoofer presets/Pre-alignment delay values/Impedance load/Enclosure drive capacity/Enclosure maximum SPL). 작업 중 두 차례 사용자 지적으로 형식 정정: (1) 압축 텍스트 대신 실제 마크다운 표로, (2) 원문이 제품군별 표를 분리하면 마크다운도 동일하게 분리, (3) 섹션 번호 체계(Pre-alignment delay values는 최상위 "35"이고 그 안의 Constant Curvature/Colinear/Coaxial은 "35.12/35.13/35.14" 하위번호여야 하는데 실수로 최상위 36/37/38로 올렸던 것을 재정정). Amplification_Reference_Technical_Bulletin_EN_16.0.md와 함께 speakers/LA/References/에 2개 참고자료 완비. **개별 스피커 파일의 Max_Enclosures_Per_Controller_Output/Total, preset_guide_and_matching, delay_defaults 등 null 필드 백필은 아직 착수 안 함 — 별도 요청 시에만 진행.**
- **완료 — Amplification_Reference_Technical_Bulletin_EN_16.0.md 작성 및 병합 셀 오류 정정(2026-07-19)**: `speakers/LA/References/`에 신규 마크다운 작성(임피던스/출력, 컨트롤러별 최대 연결대수, 컨트롤러별 최대 SPL, 배선 요약, 케이블 규격). 최초 작성 시 "Enclosure maximum SPL" 표에서 LA4X/LA7.16(i)/LA12X 3열이 원문에서 병합된 걸 놓치고 개별 값처럼 잘못 옮긴 오류를 사용자가 지적 — X4i~A15(i) Focus 전 구간 + K2/K3(i)/Kara II(i)/Kiva II/KS21(i)/SB18(IIi)/SB15m/Syva Low/Syva Sub(3)/SB10i(3)/SB6i(3) 총 21개 행 정정 완료.
- **완료 — Null Report 결합형 불릿 오카운트 감사, speakers 전체 40개 파일(2026-07-18)**: speakers/LA 32개(preset_guide_and_matching 다중 행 부분-null 26개 + 기타 결합형 불릿 6개) + speakers/MY 8개(mechanical_safety Safe_Limit 다중 행, PANTHER x3/TIGRA x2/LEOPARD x2/LINA 전부) 정정. 데이터(Key/Value/Unit)는 건드리지 않고 Null Report 요약 통계만 정정. 상세는 `TODO_Archive.md` 참조.
- **완료 — Meyer Sound 신규 제품 3종(TIGRA/LEOPARD/LINA) 투입(2026-07-18)**: 5개 파일 신규 작성, 신규 Key 9종 발견 및 PANTHER/TIGRA 전체에 양방향 동기화 완료. 상세는 `TODO_Archive.md` 참조.
- **완료 — Session_Transfer_v1.10.md 갱신**: v1.9가 크게 낡아 있어 전면 재작성.
- **TaskList 도구는 파일이 아닌 하네스 자체 기능(세션/도구 상태)이라 영구 보존되지 않는다** — 과거 세션에서 병행 사용했던 흔적(#13~#39)이 있었으나 2026-07-18 확인 결과 비어있음(초기화됨). TODO.md/TODO_Archive.md(커밋되는 파일)만 신뢰할 것 — TaskList는 현재 세션 내 임시 작업 분해용으로만 필요시 보조 사용.
- **Null Report 항목 수 재계산 시 특히 주의** — Key-Value 단순 리스트의 "콤바인된 불릿"뿐 아니라 **다중 행 테이블(preset_guide_and_matching/mechanical_safety 등)의 부분-null 컬럼도 행×컬럼 단위로 정확히 세어야 한다**(2026-07-18에 반복 확인된 패턴).
- **서브에이전트 병렬 실행 시 세션 사용량 한도 주의** — 8개 동시는 실패 전례 있음, 4개 배치 병렬까지는 안정적 확인.
- **changelog 기록 정확성 주의** — 완료 항목을 "완료"로 기록하기 전 실제로 파일을 grep/diff로 재확인할 것.
- **버저닝 프로토콜 "변경 없음" 판명 시** — Duplicate+Archive까지 했더라도 실질 변경이 없다면 버전을 새로 만들지 않고 원상복구할 것.
- **커밋된 파일 편집 전 항상 git status 먼저 확인** — 여러 파일을 순회 편집할 때 이미 커밋된 파일과 미커밋 파일이 섞여 있을 수 있다.
- git: origin/main에 4131d21까지 커밋+푸시 완료(2026-07-18, 사용자 명시적 지시). 그 이후 Meyer Sound 배치 전체 + d&b audiotechnik 대량 배치 21개 제품이 전부 미커밋 상태로 누적됨(2026-07-18 기준 변경 파일 약 98개). 다음 변경분도 사용자 명시적 요청 시에만 커밋 — 세션 시작 시 이 커밋 대기 상태를 먼저 사용자에게 확인할 것.
