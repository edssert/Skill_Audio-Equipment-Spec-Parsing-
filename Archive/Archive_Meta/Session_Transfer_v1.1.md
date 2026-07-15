# Session Transfer — 음향 기기 데이터 파싱 스킬 프로젝트 (v1.1)

## 프로젝트 개요

L-Acoustics(추후 타 브랜드로 확장) 음향 기기 스펙 데이터를 오너 매뉴얼/스펙시트/A&E 시방서/웹 3계층에서 교차 검증해 단일 마스터 스키마 마크다운으로 통합하는 스킬 크리에이터 프로젝트. 상세 파싱 규칙 전문은 항상 루트의 최신 `SKILL_vX.X.md` 1개를 참조할 것 — 본 파일에는 규칙을 반복하지 않는다.

## 현재 상태: Phase 3-1 완료, Phase 3-2 시작 대기

- Phase 1-2: LA12X(4채널) 6개 소스 교차 검증, 마스터 스키마 최초 구축 완료.
- Phase 3-1: LA7.16(16채널) 신규 파싱 + LA12X와 완벽한 양방향 스키마 동기화(Key 목록 100% 일치) 완료. 사용자 검토를 거쳐 Total_Power_Capability 오기재 정정, 12-point terminal block 핀맵 보강까지 반영됨.
- 작업공간 정리: `_latest` 태그 전면 제거, 시맨틱 버저닝(`v[Major].[Minor]`) 확립, 루트에는 카테고리별 최신 파일만 유지하고 구버전은 `Archive/Archive_Skill`, `Archive/Archive_Data`, `Archive/Archive_Meta`로 분리 보관.

**현재 루트 최신 파일** (다음 세션은 이 3개 + 아래 폴더만 확인하면 됨):
- `SKILL_v1.8.md` — 파싱 규칙 전문(양방향 동기화, PDF 분석 규칙, 원본 보존 규칙, 버전 체계화 규칙 등 전부 포함)
- `LA7.16_v1.3.md`, `LA12X_v2.5.md` — 두 제품 마스터 스키마(Key 목록 100% 동일, 104개)
- `Original_PDFs/` — 두 제품 원본 매뉴얼/스펙시트/A&E 문서 보존
- `Raw_Web_Data/` — 두 제품 웹 텍스트(리스트뷰/오버뷰/Full Spec) 원문 무수정 보존
- `Archive/` — 모든 구버전(과거 판단 근거 확인용, 평소엔 참조 불필요)

## 다음 세션에서 즉시 진행할 작업: Phase 3-2

**목표**: 완전히 다른 브랜드(예: d&b audiotechnik) 제품 1개를 투입해 용어 매핑 사전을 확장하고 브랜드 고유 표기법을 스키마에 통합한다.

**필수 요건** (SKILL_v1.8.md 참조):
1. 신규 브랜드 제품에서 발견되는 신규 Key는 LA12X/LA7.16 양쪽에 `null`로 소급 반영(양방향 동기화 — 반대로 LA12X/LA7.16 전용 Key도 신규 제품에 `null`로 반영).
2. 결과물은 총 3개 파일 동시 출력: 신규 브랜드 제품 1개 + LA12X 갱신본 1개 + LA7.16 갱신본 1개. 세 파일의 Key 목록이 100% 동일함을 스크립트로 검증할 것.
3. 원본 문서는 `Original_PDFs/`에, 웹 원문은 `Raw_Web_Data/`에 동일 컨벤션으로 보존.
4. 새 파일 생성만 허용, 기존 파일 직접 수정 금지 — 버전을 올려 새로 만들고 구버전은 `Archive/Archive_Data`로 이동.
5. L-Acoustics 브랜드 우선순위 규칙(OM 최우선)은 L-Acoustics 제품에만 적용됨 — 타 브랜드는 "가장 상세하고 개정 이력 있는 문서 우선" 기본값 적용, 필요시 브랜드별 출처 우선순위 규칙을 SKILL.md에 신규 절로 추가.

## 참고: 과거 이력 요약 (상세 근거는 Archive 참조)

- SKILL.md는 v1.0부터 v1.8까지 8회 개정(각주 체계, 이모지 금지, 저항 표기 표준화, Phase 3 세분화, PDF 분석 규칙, 원본 보존 규칙, 양방향 동기화, 버전 체계화 순으로 누적). 전문은 `Archive/Archive_Skill/`.
- LA12X는 원래 v1.0~v5.1로 발행되었으나 시맨틱 버저닝 소급 적용으로 v1.0/v2.0/v2.1/v2.2/v2.3/v2.4/v2.5로 재분류됨(v2.0만 Major, 이후 전부 Minor). 재분류 근거는 `Archive/Archive_Data/`의 각 파일 상단 "버전 재분류 안내" 참조.
- LA7.16은 v1.0(최초 파싱, Total_Power_Capability 오기재 있었음) → v1.1(양방향 동기화 + 오기재 정정) → v1.2(LA12X 파일명 참조 갱신) → v1.3(12-point terminal block 핀맵 보강) 순으로 발행. 전문은 `Archive/Archive_Data/`.
- 이 파일(Session_Transfer.md) 자체도 v1.0(Phase 1-2 시점 원본, 상세 이력 포함)을 `Archive/Archive_Meta/`에 보존하고 있다.
