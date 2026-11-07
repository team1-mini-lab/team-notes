# Phase 2 Functional Requirements

> 작성 담당: B
> 작성 범위: SRS 3.1 Functional Requirements
> 문서 상태: Draft

## 1. 작성 범위

Phase 2의 Function Component, State, useState, useEffect, useMemo 기능을 요구사항으로 정의한다.

함수형 컴포넌트 실행, Props 전달, State 관리 및 변경에 따른 화면 갱신을 포함한다.

## 2. 기능 요구사항

| 요구사항 ID | 요구사항명 | 요구사항 내용 | 우선순위 | 적용 Phase | 관련 PR ID |
|---|---|---|---|---|---|
| FR-11 | 함수형 컴포넌트 실행 | 시스템은 Hook 배열을 관리하는 FunctionComponent를 구현하고, mount()와 update()를 실행할 수 있어야 한다. | Must | Phase 2 | PR-08 |
| FR-12 | 컴포넌트 렌더링 | 시스템은 함수형 컴포넌트의 실행 결과를 UI에 렌더링해야 한다. | Must | Phase 2 | PR-08 |
| FR-13 | Props 전달 | 부모 컴포넌트는 자식 컴포넌트에 Props를 전달할 수 있어야 하며, 자식 컴포넌트는 전달받은 Props를 사용할 수 있어야 한다. | Must | Phase 2 | PR-10 |
| FR-14 | 컴포넌트 재렌더링 | 시스템은 State 변경 시 해당 컴포넌트를 다시 실행하고 화면을 갱신해야 한다. | Must | Phase 2 | PR-11 |
| FR-15 | State 관리 | 시스템은 루트 컴포넌트에서 State를 관리하고, 자식 컴포넌트에는 Props를 전달해야 한다. | Must | Phase 2 | PR-10 |
| FR-16 | useState 초기값 | useState는 전달받은 초기값으로 상태를 초기화하고, 상태값과 상태 변경 함수를 반환해야 한다. | Must | Phase 2 | PR-12 |
| FR-17 | State 변경 | 사용자는 useState가 반환하는 상태 변경 함수를 통해 상태를 변경할 수 있어야 한다. 상태 변경 시 화면이 갱신되어야 한다. | Must | Phase 2 | PR-11, PR-12 |
| FR-18 | useEffect 실행 | 시스템은 컴포넌트 렌더링 이후 useEffect에 전달된 Effect 함수를 실행해야 한다. | Must | Phase 2 | PR-13 |
| FR-19 | useEffect 의존성 처리 | 시스템은 useEffect의 의존성 배열을 기준으로 Effect 함수의 실행 여부를 판단해야 한다. | Must | Phase 2 | PR-13 |
| FR-20 | useMemo 계산 결과 재사용 | 시스템은 의존성 배열의 값이 변경되지 않으면 이전 계산 결과를 재사용하고, 의존성 값이 변경되면 계산을 다시 수행해야 한다. | Must | Phase 2 | PR-14 |
| FR-21 | Hook 호출 규칙 | 시스템은 Hook을 루트 함수형 컴포넌트의 최상위에서만 호출하도록 제한해야 한다. | Must | Phase 2 | PR-09 |
| FR-22 | Phase 1 기능 재사용 | 시스템은 Phase 2에서 State 변경에 따른 화면 갱신을 수행할 때 Phase 1에서 구현한 Virtual DOM, Diff, Patch를 사용해야 한다. | Must | Phase 2 | PR-15 |
| FR-23 | Phase 2 테스트 페이지 | 시스템은 Phase 2의 State 변경과 화면 갱신 동작을 확인할 수 있는 테스트 페이지를 제공해야 한다. | Must | Phase 2 | PR-16 |
| FR-24 | Batching | 시스템은 하나의 이벤트 처리 과정에서 발생한 여러 State 변경을 모아 한 번의 렌더링으로 처리할 수 있어야 한다. | Could | Phase 2 | PR-21 |

## 3. 요구사항 작성 시 확인 사항

- 기존 과제 요구사항 R1~R20 중 담당 범위에 해당하는 항목을 연결한다.
- 팀에서 정의한 프로젝트 요구사항 PR-08~PR-16을 기준으로 기능 요구사항을 구체화한다.
- FunctionComponent의 Hook 배열 관리, mount(), update() 실행 방식을 확인한다.
- State는 루트 컴포넌트에서 관리하고 자식 컴포넌트에는 Props를 전달하는 구조를 기준으로 작성한다.
- useState의 초기값, 상태 변경 함수 및 화면 갱신 동작을 구분한다.
- useEffect와 useMemo는 의존성 배열의 초기 실행, 값 유지 및 변경 조건을 구분한다.
- Hook은 함수형 컴포넌트의 최상위에서만 호출하도록 정의한다.
- 우선순위는 과제 필수 여부와 팀 합의에 따라 결정한다.
- Hook은 루트 함수형 컴포넌트의 최상위에서만 호출하도록 정의한다.
- Phase 2의 화면 갱신에는 Phase 1의 Virtual DOM, Diff, Patch를 재사용한다.
- Phase 2 테스트 페이지에서 State 변경과 화면 갱신을 확인할 수 있도록 정의한다.
- Batching은 TBD-05에 대한 팀 결정 이후 구현 여부와 우선순위를 확정한다.
