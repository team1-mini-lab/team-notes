# Phase 1 Functional Requirements

> 작성 담당: A  
> 작성 범위: SRS 3.1 Functional Requirements  
> 문서 상태: Draft  

## 1. 작성 범위

Phase 1의 Virtual DOM, DOM 변환, Diff, Patch, History 기능을 요구사항으로 정의한다.

## 2. 기능 요구사항

| 요구사항 ID | 요구사항명 | 요구사항 내용 | 우선순위 | 적용 Phase | 관련 R ID |
|---|---|---|---|---|---|
| FR-01 | DOM 변환 | 시스템은 브라우저 DOM 요소를 Virtual DOM 객체 구조로 변환해야 한다. | Must | Phase 1 | 확인 필요 |
| FR-02 | Virtual DOM 구조 표현 | Virtual DOM 객체는 노드 종류, 속성, 자식 노드 정보를 표현해야 한다. | Must | Phase 1 | 확인 필요 |
| FR-03 | Virtual DOM 비교 | 시스템은 이전 Virtual DOM과 새로운 Virtual DOM을 비교해야 한다. | Must | Phase 1 | 확인 필요 |
| FR-04 | 변경 사항 탐지 | 시스템은 두 Virtual DOM 사이의 노드 추가, 삭제, 교체 및 속성 변경을 탐지해야 한다. | Must | Phase 1 | 확인 필요 |
| FR-05 | 변경 사항 기록 | 시스템은 탐지한 변경 사항을 Patch에서 처리할 수 있는 형태로 기록해야 한다. | Must | Phase 1 | 확인 필요 |
| FR-06 | DOM 업데이트 | 시스템은 Diff 결과를 실제 DOM에 적용해야 한다. | Must | Phase 1 | 확인 필요 |
| FR-07 | 변경 영역 업데이트 | 시스템은 변경 사항이 발생한 DOM 영역을 업데이트해야 한다. | Must | Phase 1 | 확인 필요 |
| FR-08 | 변경 이력 기록 | 시스템은 DOM 변경 이력을 기록해야 한다. | Must | Phase 1 | 확인 필요 |
| FR-09 | Undo | 사용자는 이전 변경 상태로 되돌릴 수 있어야 한다. | Must | Phase 1 | 확인 필요 |
| FR-10 | Redo | 사용자는 Undo로 되돌린 변경 사항을 다시 적용할 수 있어야 한다. | Must | Phase 1 | 확인 필요 |

## 3. 요구사항 작성 시 확인 사항

- 기존 과제 요구사항 R1~R20 중 담당 범위에 해당하는 항목을 연결한다.
- 하나의 요구사항에는 하나의 기능 조건을 작성한다.
- 구현 및 테스트가 가능한 수준으로 요구사항을 구체화한다.
- 우선순위는 과제 필수 여부와 팀 합의에 따라 결정한다.
- 기능 범위가 변경되면 요구사항 내용과 관련 R ID를 함께 수정한다.

## 4. 검증 항목 초안

검증 방법과 합격 기준은 담당 기능을 기준으로 작성한다. 최종 검증표는 `quality-and-verification.md`에서 통합한다.

| 검증 ID | 요구사항 ID | 검증 방법 | 테스트 조건 | 예상 결과 | 합격 기준 |
|---|---|---|---|---|---|
| VT-01 | FR-01 | Unit Test | DOM 요소를 Virtual DOM으로 변환 | Virtual DOM 객체 생성 | 원본 DOM의 노드 구조와 대응 |
| VT-02 | FR-03 | Unit Test | 서로 다른 두 Virtual DOM 비교 | 변경 사항 탐지 | 예상한 차이와 일치 |
| VT-03 | FR-06 | Functional Test | Diff 결과를 Patch에 전달 | 실제 DOM 업데이트 | 화면에 변경 사항 반영 |
| VT-04 | FR-09 | Functional Test | DOM 변경 후 Undo 실행 | 이전 상태 복원 | 변경 전 상태와 일치 |
| VT-05 | FR-10 | Functional Test | Undo 후 Redo 실행 | 변경 상태 재적용 | 변경 후 상태와 일치 |

> 위 내용은 작성 예시이며 실제 과제 요구사항 및 팀 설계에 따라 수정한다.
