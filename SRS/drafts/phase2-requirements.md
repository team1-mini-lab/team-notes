
# Phase 2 Functional Requirements

> 작성 담당: B  
> 작성 범위: SRS 3.1 Functional Requirements  
> 문서 상태: Draft (아래는 예시일 뿐, 내용은 각자 채워야 합니다.)

## 1. 작성 범위

Phase 2의 Function Component, State, useState, useEffect, useMemo 기능을 요구사항으로 정의한다.

## 2. 기능 요구사항

| 요구사항 ID | 요구사항명 | 요구사항 내용 | 우선순위 | 적용 Phase | 관련 R ID |
|---|---|---|---|---|---|
| FR-11 | 함수형 컴포넌트 실행 | 시스템은 함수형 컴포넌트를 정의하고 실행할 수 있어야 한다. | Must | Phase 2 | 확인 필요 |
| FR-12 | 컴포넌트 렌더링 | 시스템은 함수형 컴포넌트의 실행 결과를 UI에 렌더링해야 한다. | Must | Phase 2 | 확인 필요 |
| FR-13 | Props 전달 | 부모 컴포넌트는 자식 컴포넌트에 Props를 전달할 수 있어야 한다. | Must | Phase 2 | 확인 필요 |
| FR-14 | 컴포넌트 재렌더링 | 시스템은 컴포넌트의 상태 변경에 따라 컴포넌트를 다시 렌더링해야 한다. | Must | Phase 2 | 확인 필요 |
| FR-15 | State 관리 | 시스템은 컴포넌트별 상태를 관리할 수 있어야 한다. | Must | Phase 2 | 확인 필요 |
| FR-16 | useState 초기값 | useState는 전달받은 초기값으로 상태를 초기화해야 한다. | Must | Phase 2 | 확인 필요 |
| FR-17 | State 변경 | 사용자는 useState가 반환하는 상태 변경 함수를 통해 상태를 변경할 수 있어야 한다. | Must | Phase 2 | 확인 필요 |
| FR-18 | useEffect 실행 | 시스템은 useEffect에 전달된 Effect 함수를 실행해야 한다. | Must | Phase 2 | 확인 필요 |
| FR-19 | useEffect 의존성 처리 | 시스템은 useEffect의 의존성 배열을 기준으로 Effect 실행 여부를 판단해야 한다. | Must | Phase 2 | 확인 필요 |
| FR-20 | useMemo 계산 결과 재사용 | 시스템은 의존성이 변경되지 않으면 useMemo의 이전 계산 결과를 재사용해야 한다. | Must | Phase 2 | 확인 필요 |

## 3. 요구사항 작성 시 확인 사항

- 기존 과제 요구사항 R1~R20 중 담당 범위에 해당하는 항목을 연결한다.
- Hooks별 초기 실행, 업데이트, 의존성 처리 조건을 구체화한다.
- Cleanup 함수 지원 여부 등 과제에서 요구하지 않은 기능은 팀 합의 후 추가한다.
- 우선순위는 과제 필수 여부와 팀 합의에 따라 결정한다.

## 4. 검증 항목 초안

검증 방법과 합격 기준은 담당 기능을 기준으로 작성한다. 최종 검증표는 `quality-and-verification.md`에서 통합한다.

| 검증 ID | 요구사항 ID | 검증 방법 | 테스트 조건 | 예상 결과 | 합격 기준 |
|---|---|---|---|---|---|
| VT-06 | FR-11 | Unit Test | 함수형 컴포넌트 실행 | 컴포넌트 실행 결과 반환 | 예상 결과와 일치 |
| VT-07 | FR-13 | Functional Test | 부모에서 자식으로 Props 전달 | 자식 컴포넌트에서 값 사용 | 전달한 값과 일치 |
| VT-08 | FR-16 | Unit Test | useState 초기값 전달 | 초기 상태 반환 | 초기값과 일치 |
| VT-09 | FR-17 | Functional Test | 상태 변경 함수 호출 | 상태 변경 및 재렌더링 | 변경된 상태가 UI에 반영 |
| VT-10 | FR-19 | Unit Test | 의존성 배열 값 변경 및 유지 | Effect 실행 여부 판단 | 정의한 실행 조건과 일치 |
| VT-11 | FR-20 | Unit Test | 의존성 배열 값 유지 및 변경 | 계산 결과 재사용 또는 재계산 | 정의한 의존성 조건과 일치 |

> 위 내용은 작성 예시이며 실제 과제 요구사항 및 팀 설계에 따라 수정한다.
