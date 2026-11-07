
# Phase 2 Functional Requirements

> 작성 담당: B  
> 작성 범위: SRS 3.1 Functional Requirements  
> 문서 상태: Draft (아래는 예시일 뿐, 내용은 각자 채워야 합니다.)

## 1. 작성 범위

Phase 2의 Function Component, State, useState, useEffect, useMemo 기능을 요구사항으로 정의한다.

## 2. 기능 요구사항

| 요구사항 ID | 요구사항명 | 요구사항 내용 | 우선순위 | 적용 Phase | 관련 R ID |
|---|---|---|---|---|---|
| FR-11 | - | - | Must | Phase 2 | 확인 필요 |
| FR-12 | - | - | Must | Phase 2 | 확인 필요 |
| FR-13 | - | - | Must | Phase 2 | 확인 필요 |
| FR-14 | - |  - | Must | Phase 2 | 확인 필요 |
| FR-15 | - |  - | Must | Phase 2 | 확인 필요 |
| FR-16 | - |  - | Must | Phase 2 | 확인 필요 |
| FR-17 | - |  - | Must | Phase 2 | 확인 필요 |
| FR-18 | - |  - | Must | Phase 2 | 확인 필요 |
| FR-19 | - |  - | Must | Phase 2 | 확인 필요 |
| FR-20 | - |  - | Must | Phase 2 | 확인 필요 |

## 3. 요구사항 작성 시 확인 사항

- 기존 과제 요구사항 R1~R20 중 담당 범위에 해당하는 항목을 연결한다.
- Hooks별 초기 실행, 업데이트, 의존성 처리 조건을 구체화한다.
- 우선순위는 과제 필수 여부와 팀 합의에 따라 결정한다.

## 4. 검증 항목 초안

검증 방법과 합격 기준은 담당 기능을 기준으로 작성한다. 최종 검증표는 `quality-and-verification.md`에서 통합한다.

| 검증 ID | 요구사항 ID | 검증 방법 | 테스트 조건 | 예상 결과 | 합격 기준 |
|---|---|---|---|---|---|
| VT-06 | FR-11 | Unit Test | -| 컴포넌트 실행 결과 반환 | 예상 결과와 일치 |
| VT-07 | FR-13 | Functional Test |  - | 자식 컴포넌트에서 값 사용 | 전달한 값과 일치 |
| VT-08 | FR-16 | Unit Test |  - | 초기 상태 반환 | 초기값과 일치 |
| VT-09 | FR-17 | Functional Test |  -| 상태 변경 및 재렌더링 | 변경된 상태가 UI에 반영 |
| VT-10 | FR-19 | Unit Test |  - | Effect 실행 여부 판단 | 정의한 실행 조건과 일치 |
| VT-11 | FR-20 | Unit Test |  - | 계산 결과 재사용 또는 재계산 | 정의한 의존성 조건과 일치 |

> 위 내용은 작성 예시이며 실제 과제 요구사항 및 팀 설계에 따라 수정한다.
