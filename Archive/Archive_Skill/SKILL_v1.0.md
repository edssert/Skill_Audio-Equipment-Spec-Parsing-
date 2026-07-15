---
name: audio-spec-parsing
description: Parse and unify audio equipment specification data (owner's manuals, spec sheets, A&E specs, website tiers) from any manufacturer into a single master schema markdown file.
---

# Audio Equipment Spec Parsing Skill

Skill_Version: 1.0 (재구성본 — 출력 포맷 규칙 도입 이전 상태)

이 스킬은 음향 기기(앰프, 스피커, 컨트롤러 등) 스펙 데이터를 여러 출처(오너 매뉴얼, 스펙시트 PDF, A&E 시방서, 웹사이트 계층별 텍스트)에서 추출하여 하나의 마스터 스키마 마크다운으로 통합한다. 대상 실행 환경은 Claude Sonnet(주력, 대량 반복 파싱)과 Claude Opus(보조, 복잡한 매뉴얼/충돌 해결)이다.

문서 구조는 마크다운 골격 + XML 국소 삽입 하이브리드를 따른다: 워크플로/규칙 서술은 마크다운 헤더로, 예시 입출력 쌍·용어 매핑 사전·데이터 블록처럼 원문과 경계가 흐려지기 쉬운 부분은 XML 태그로 격리한다. 최종 산출물(파싱 결과)의 포맷은 항상 마크다운(.md)이다.

## 핵심 파싱 원칙

<core_principles>
1. 스키마 동적 발견: 제조사마다 다른 용어(예: "Max Power", "최대 출력")를 공학 표준 스네이크 케이스 영문 키로 통합한다(예: Peak_Power_W).
2. 데이터 정제: 값에서 단위를 분리하고 계산 가능한 숫자로 변환한다.
3. 측정 기준 추출: 오너 매뉴얼 등에 있는 조건(-3dB, RMS, 핑크노이즈 등)을 별도로 추출한다.
4. 무결성 유지: 없는 스펙은 억지로 만들지 않고 null 처리한다.
</core_principles>

## 워크플로 (Phase 테스트)

<phase_workflow>
Phase 1: 단일 제품 기초 파싱 - 마스터 스키마 뼈대 구축.
Phase 2: 복합 데이터 통합 - 동일 제품의 매뉴얼/브로셔/웹 스펙을 교차 검증해 하나의 스키마로 병합.
Phase 3: 타 브랜드 교차 테스트 - 용어 매핑 사전을 확장 통합.
Phase 4: 스키마 진화 및 하위 호환성 - 새 속성 발견 시 기존 제품 .md 파일에도 해당 키를 null 값으로 일괄 추가하여 리팩토링.
</phase_workflow>

## 용어 매핑 사전 (초기)

<term_mapping_dictionary>
| 원문 표현 (예시) | 표준 키 |
|---|---|
| Max Power, Peak Power, 최대 출력 | Peak_Power_W |
</term_mapping_dictionary>

## 참고

이 버전에는 아직 출력 포맷 규칙(섹션 단위 출처 표기, 표 순수성, 데이터 충돌 보존, 브랜드별 출처 우선순위, 이모지 금지), 저항 표기 표준화, 임의 추론 금지 강화 조항이 포함되어 있지 않다. 해당 규칙들은 v1.1 이후 순차적으로 추가되었다.
