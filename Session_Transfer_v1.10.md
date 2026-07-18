# Session Transfer — 음향 기기 데이터 파싱 스킬 프로젝트 (v1.10)

## ⚠️ 긴급 인계 (2026-07-18, 최신 갱신) — 다음 세션은 이 섹션부터 읽을 것

v1.9는 2026-07-17 시점 서술이라 낡았다(제품 수 28개로 기재되어 있으나 실제로는 대규모 감사 라운드 + Meyer Sound 신규 3개 제품군 투입으로 67개). `TODO.md`/`TODO_Archive.md`를 항상 함께 확인할 것 — 진행 중/예정 작업은 `TODO.md`, 완료 로그는 `TODO_Archive.md`.

### 현재 상태: 전체 제품 수 67개, 대규모 프로젝트 전면 감사 완료, 미커밋 변경 다수

**제품 수**: amplifiers 16개(LA 6 + db 10) + speakers 51개(LA 41 + db 2 + MY 8) = **67개**.

**가장 중요한 미해결 사항 — git 커밋 대기 중**: origin/main에는 `91c62c3`까지 푸시됨. 로컬 커밋은 `fab4b05`까지. `fab4b05` 이후 상당한 변경이 미커밋 상태로 누적되어 있다(치수 W/H/D 축 감사로 4개 파일 버전 상향, Meyer Sound TIGRA/LEOPARD/LINA 신규 투입 5개 파일 + PANTHER 동기화 3개 파일). **사용자가 "커밋하지 말고 계속 작업"을 명시적으로 지시한 상태**이므로 다음 세션은 이 지시가 여전히 유효한지 먼저 확인할 것 — 유효하지 않다면(즉 사용자가 커밋을 원하면) 위 변경사항을 검토 후 커밋한다.

### 이번 라운드(2026-07-18)에 있었던 일 — 세 갈래 대규모 작업

**1. amplifiers "핑계성 미확인" 전수 재조사**: "원본 문서를 재조회하지 않고 기존 파싱 결과 텍스트만으로 판단"이라는 각주가 스스로 남아있던 5개 파일(LA12X/LA7.16i/LA7.16/D80/D90)을 전부 각자의 원본 OM/SPS/AE로 재검증. Bridging_Support/AES67_Support/Service_Port_Type 등 다수 Key가 실값(No 확정 또는 실제 스펙값)으로 전환됨 — 예: D80/D90 둘 다 실제로는 Web Remote Interface 챕터를 갖고 있었으나 이전 버전에서 재조회 없이 null 처리되어 있었음. 5개 파일 모두 버전 상향 완료.

**2. speakers 버전 변경 이력(changelog) 전수 백필**: 파일명 버전과 "버전 변경 이력" 절 마지막 행 버전이 어긋나 있던 29개 `speakers/LA` 파일 전체를 Archive의 직전 문서화 버전과 diff해 실제 변경 내용을 changelog로 복원. 서브에이전트 4개 배치로 병렬 처리 후 grep 전수 검증으로 0건 누락 확인.

**3. 치수(Dimensions) W/H/D 축 구분 신뢰도 전수 감사**: speakers 51개 파일 전체를 (1) A&E 명시적 축 라벨링 확정, (2) 도면 이미지 렌더링 확인, (3) 미확인/유사값 추정 3그룹으로 분류. A&E가 없어 근거가 약했던 CS1/SB10r/SB6r/Sokar/X4r 5개 제품을 PowerShell+Windows.Data.Pdf로 도면을 직접 렌더링해 육안 재확인 — 전부 기존 값이 정확했음을 확인(CS1은 이미 v1.0 당시 검증돼 있어 버전 변경 불필요, 나머지 4개는 각주 보강 목적으로 버전 상향).

**4. `[신규]` 각주 태그 프로젝트 전체 제거**: 시점이 지나 더 이상 "신규"가 아닌 Key에 계속 붙어있던 `[신규]` 텍스트를 amplifiers 14개 파일 전체에서 제거(각주 번호는 유지).

**5. Meyer Sound 신규 제품 3종(TIGRA/LEOPARD/LINA) 투입**: `upload/` 폴더로 제공된 원본을 파싱해 5개 파일 작성 — TIGRA-L/TIGRA-W, LEOPARD/LEOPARD-M80(둘 다 PANTHER-L/M/W와 동일하게 파트넘버 없는 지향각 베리언트 패턴으로 판단해 개별 파일 분리, 사용자 확인 완료), LINA(베리언트 없는 단일 모델). 이 과정에서 LEOPARD/LINA가 PANTHER/TIGRA와 다른 측정 표준(AES75 대신 Meyer 자체 "Linear Peak SPL")과 다른 전력 스펙 단위(W 대신 A)를 쓴다는 것을 발견 — 신규 Key 9종을 PANTHER x3 + TIGRA x2에 양방향 동기화, 전 8개 MY 파일 Key-list parity 검증 완료.

**6. README.md/TODO.md 재작성**: README.md는 한국어로 "최신 버전 제품별 .md 파일만 보면 된다"는 사용법 중심으로 재작성(폴더구조 세부는 부록). TODO.md는 완료 항목을 즉시 TODO_Archive.md로 이관하는 방식으로 재구조화(사용자 지시) — 완료 항목이 쌓여 "지금 뭘 해야 하는가" 파악을 방해하던 문제 해소.

**자체 발견·시정한 실수 2건(교훈으로 기록)**:
- PANTHER_L/M/W 양방향 동기화 편집 중, 이미 git 커밋된 v1.0 파일을 Duplicate→Archive 없이 직접 편집한 Surgical Versioning Protocol 위반을 스스로 발견 — git HEAD에서 원본을 Archive로 복구하고 편집분을 v1.1로 이전해 시정. **교훈**: 여러 파일을 순회 편집할 때 파일마다 개별적으로 `git status`를 먼저 확인할 것(일부는 커밋됨/일부는 미커밋 상태로 섞여 있을 수 있음).
- 위 시정 작업 중 git checkout으로 복원된 구버전 파일을 Archive로 옮기지 않고 라이브 폴더에 그대로 방치해뒀던 것을 이번 세션 후반(v1.10 작성 준비 중)에 재발견 — PANTHER_L/M/W v1.0 파일 3개를 최종적으로 라이브 폴더에서 제거(Archive 사본과 content-diff로 동일함을 확인 후).

### 다음에 할 일

1. **git 커밋/푸시 여부 확인**: 위 "가장 중요한 미해결 사항" 참조.
2. **미착수 항목 없음**: `TODO.md`의 "진행 중" 섹션이 비어있는 상태로 인계됨 — 다음 세션은 새로 감사할 항목을 찾는 것부터 시작(예: LEOPARD/LINA도 changelog 백필이 필요한지, 각주 버전 참조 최신성 등 아직 다루지 않은 감사 축이 있는지 검토).
3. **LEOPARD/LEOPARD-M80 분리 결정은 사용자 확인 완료**(2026-07-18) — 재검토 불필요.

## 프로젝트 개요

L-Acoustics, d&b audiotechnik, Meyer Sound 등 여러 브랜드의 음향 기기 스펙 데이터를 오너 매뉴얼/스펙시트/A&E 시방서/웹 3계층에서 교차 검증해 단일 마스터 스키마 마크다운으로 통합하는 스킬 크리에이터 프로젝트. 상세 파싱 규칙 전문은 항상 루트의 최신 `SKILL_vX.X.md` 1개를 참조할 것 — 본 파일에는 규칙을 반복하지 않는다.

## 현재 파일 위치

- `amplifiers/LA/`(6개): LA1.16i, LA2Xi, LA4X, LA7.16, LA7.16i, LA12X
- `amplifiers/db/`(10개): D25, D40, D80, D90, 5D, 5DM, 10D, 30D, 25D, 40D
- `speakers/LA/`(41개): K/A/X/S/L 시리즈 및 서브우퍼 전반
- `speakers/db/`(2개): GSL8, GSL12
- `speakers/MY/`(8개): PANTHER-L/M/W, TIGRA-L/W, LEOPARD/LEOPARD-M80, LINA
- 각 카테고리/브랜드 폴더 내부 구조(`Original_PDFs/{제품}/`, `Raw_Web_Data/`, `Archive/{제품}/`)는 `amplifiers/CLAUDE.md`, `speakers/CLAUDE.md` 참조.

## 핵심 교훈 — 이름과 아키텍처는 무관하다 (v1.9에서 이어짐, 계속 유효)

d&b의 "X" vs "XD" 이름 규칙이나 브랜드명만으로 아키텍처(네트워크 프로토콜, 커넥터, GPIO, 크로스오버, 냉각 방식 등)를 예측할 수 없다는 원칙은 Meyer Sound 3개 신규 제품군 투입에서도 재확인되었다 — PANTHER/TIGRA는 AES75+Neutrik TOP 커넥터+W단위 전력스펙이지만, LEOPARD/LINA는 Meyer 자체 Linear Peak SPL+표준 XLR 커넥터(IP등급 없음, 옵션 Weather Protection 시에만)+A단위 전류스펙을 쓴다. **신규 제품 파싱 시 스켈레톤을 고를 때는 반드시 그 제품 자신의 원본에서 아키텍처 축을 확인할 것** — 상세는 `speakers/CLAUDE.md`의 Meyer Sound 브랜드 참고사항 절, `amplifiers/`는 이전 세션의 d&b 5가지 아키텍처 축 확인 원칙(v1.9 Archive 버전 참조).

## 참고: 과거 이력 요약

- SKILL.md는 v1.0부터 현재 최신 버전까지 개정 이력 보유, 전문은 `Archive/Archive_Skill/`, 변경 로그는 `SKILL_Changelog.md`.
- 이 파일(Session_Transfer.md) 자체는 v1.0~v1.9까지를 `Archive/Archive_Meta/`에 보존.
- 각 제품 파일의 상세 버전 이력은 파일 자체 하단 "버전 변경 이력" 절 참조(본 파일에서 반복하지 않음). 완료된 작업의 상세 서술은 `TODO_Archive.md` 참조(본 파일은 요약만 유지).
