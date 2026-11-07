

# Quality, Interface, Constraints and Verification

> 작성 담당: C  
> 작성 범위: SRS 3.2, 3.3, 3.4, 4, 5.1  
> 문서 상태: Draft

## 1. Non-functional Requirements (SRS 3.2)

시스템의 성능, 안정성, 유지보수성 등 품질 요구사항을 작성한다.

| 요구사항 ID | 품질 특성 | 요구사항 내용 | 측정 및 검증 기준 | 관련 PR ID |
|---|---|---|---|---|
| NFR-01 | Performance | 시스템은 DOM 변경 시 변경되지 않은 영역에 대한 불필요한 업데이트를 최소화해야 한다. | 변경된 노드와 변경되지 않은 노드의 업데이트 여부 비교 | PR-02, PR-06, PR-15 |
| NFR-02 | Reliability | 각 모듈은 정의된 입력 조건에서 정상적으로 동작해야 하며, 예외 입력과 경계 조건을 처리해야 한다. | 정상 입력, 빈 값, 잘못된 입력 및 경계 조건 테스트 | PR-18, PR-19, PR-20 |
| NFR-03 | Maintainability | 시스템은 Virtual DOM, Diff, Patch, Component, Hooks 기능을 역할에 따라 구분하여 관리해야 한다. | 모듈별 책임 및 함수 인터페이스 검토 | PR-18 |

### 추가 확인 사항

| 항목 | 결정할 내용 |
|---|---|
| 성능 목표 | 렌더링 및 Diff 처리 시간의 측정 여부와 목표값 |
| 안정성 | 빈 값, 잘못된 입력, 경계 조건의 처리 범위 |
| 유지보수성 | 모듈 분리 및 함수별 책임 범위 |
| 테스트 환경 | 브라우저 DOM API를 사용하는 테스트를 위한 jsdom 등 테스트 환경 구성 |

## 2. Interface Requirements (SRS 3.3)

사용자 인터페이스와 모듈 간 인터페이스 요구사항을 작성한다.

| 인터페이스 ID | 인터페이스 대상 | 요구사항 내용 | 입력 | 출력 |
|---|---|---|---|---|
| IR-01 | 테스트 영역 | 사용자는 테스트를 위한 HTML 내용을 입력하거나 수정할 수 있어야 한다. | HTML 입력값 | 입력된 테스트 내용 |
| IR-02 | Patch 버튼 | 사용자는 Patch 기능을 실행할 수 있어야 한다. | 버튼 클릭 | 변경 사항 적용 |
| IR-03 | Undo/Redo 버튼 | 사용자는 변경 이력을 되돌리거나 다시 적용할 수 있어야 한다. | 버튼 클릭 | 이전 또는 이후 상태 |
| IR-04 | DOM 변환 모듈 | 모듈은 DOM 노드를 전달받아 Virtual DOM 객체를 반환해야 한다. | DOM 노드 | Virtual DOM 객체 |
| IR-05 | Diff 모듈 | 모듈은 이전·새로운 Virtual DOM을 전달받아 변경 사항을 반환해야 한다. | 두 Virtual DOM | Diff 결과 |
| IR-06 | Patch 모듈 | 모듈은 Diff 결과를 전달받아 실제 DOM에 변경 사항을 적용해야 한다. | Diff 결과 및 실제 DOM | 변경된 DOM |
| IR-07 | Phase 2 테스트 페이지 | 사용자는 입력 및 클릭을 통해 State 변경과 화면 갱신을 확인할 수 있어야 한다. | 사용자 입력 및 클릭 | 변경된 State와 UI |
| IR-08 | State 변경 인터페이스 | 컴포넌트는 setter를 통해 State 변경을 요청할 수 있어야 한다. | State 변경값 | 변경된 State 및 화면 갱신 |

> 내부 모듈의 함수명, 매개변수 및 반환 형식은 설계 문서에서 확정한다.

## 3. Constraints (SRS 3.4)

프로젝트 구현에 적용되는 기술적 제약사항과 전제조건을 작성한다.

| 제약사항 ID | 구분 | 제약 조건 | 사유 | 관련 PR ID |
|---|---|---|---|---|
| CON-01 | 기술적 제약 | React, Vue 등 외부 UI 프레임워크를 사용하지 않고 Virtual DOM, Diff, Patch, Component, Hooks의 핵심 기능을 직접 구현한다. | React의 핵심 동작 원리 구현 | PR-17 |
| CON-02 | 개발 환경 | HTML, CSS, Vanilla JavaScript 또는 TypeScript를 사용한다. | 과제에서 허용한 개발 환경 | PR-17 |
| CON-03 | 구현 범위 | Phase 1의 Virtual DOM, Diff, Patch와 Phase 2의 Function Component, State, Hooks를 구현한다. | 프로젝트 구현 범위 | PR-01~PR-16, PR-21 |
| CON-04 | 전제조건 및 의존성 | 브라우저 DOM API를 사용할 수 있는 환경에서 실행한다. | 실제 DOM 조작 및 화면 갱신 | PR-01, PR-04 |
| CON-05 | 테스트 환경 | DOM API를 사용하는 모듈의 테스트는 DOM 테스트 환경을 구성하여 수행한다. | 브라우저 DOM API에 의존하는 코드의 테스트 | PR-18, PR-19, PR-20 |

## 4. Verification (SRS 4)

요구사항별 구현 여부를 확인하기 위한 검증 방법과 통과 기준을 작성한다.

### 4.1 검증 방법

| 검증 방법 | 설명 |
|---|---|
| Unit Test | 개별 함수 또는 모듈의 입력과 출력 검증 |
| Integration Test | 여러 모듈 간 연동 검증 |
| Functional Test | 사용자의 조작에 따른 전체 기능 동작 검증 |
| Boundary Test | 빈 값, 잘못된 입력, 경계 조건에서의 동작 검증 |
| Code Review | 기술적 제약사항과 모듈별 책임 분리 여부 검토 |

### 4.2 Phase 1 검증

A가 작성한 Phase 1 FR 목록을 기준으로 검증한다.

| 검증 ID | 요구사항 ID | 검증 방법 | 테스트 조건 | 예상 결과 | 합격 기준 |
|---|---|---|---|---|---|
| VT-01 | FR-01 | Unit Test | 브라우저 DOM 요소를 Virtual DOM으로 변환 | Virtual DOM 객체 생성 | 원본 DOM의 노드 정보가 대응되는 객체로 변환됨 |
| VT-02 | FR-02 | Unit Test | Element, Text 등 서로 다른 노드 변환 | 노드 유형, 속성, 자식 노드 표현 | 각 노드 정보가 정의한 Virtual DOM 구조에 저장됨 |
| VT-03 | FR-03 | Unit Test | 이전·새로운 Virtual DOM 비교 | 두 객체의 차이 확인 | 비교 결과가 예상한 결과와 일치함 |
| VT-04 | FR-04 | Unit Test | 노드 추가, 삭제, 교체 및 속성 변경 | 변경 유형 탐지 | 각 변경 유형을 구분하여 탐지함 |
| VT-05 | FR-05 | Unit Test | 탐지한 변경 사항 기록 | Patch에서 처리할 수 있는 변경 정보 생성 | 변경 유형과 대상 정보가 정확하게 기록됨 |
| VT-06 | FR-06, FR-07 | Integration Test | Diff 결과를 Patch에 전달 | 실제 DOM의 변경된 영역 업데이트 | 변경된 영역에만 변경 사항이 반영됨 |
| VT-07 | FR-08 | Integration Test | Patch 실행 후 변경 이력 확인 | 변경된 상태 저장 | 변경된 Virtual DOM이 History에 기록됨 |
| VT-08 | FR-09 | Functional Test | 변경 이후 Undo 실행 | 이전 상태 복원 | 실제 영역과 테스트 영역이 이전 상태와 일치함 |
| VT-09 | FR-10 | Functional Test | Undo 이후 Redo 실행 | 변경 상태 재적용 | 실제 영역과 테스트 영역이 변경 이후 상태와 일치함 |

### 4.3 Phase 2 검증

B가 작성한 Phase 2 FR 목록을 기준으로 검증한다.

| 검증 ID | 요구사항 ID | 검증 방법 | 테스트 조건 | 예상 결과 | 합격 기준 |
|---|---|---|---|---|---|
| VT-10 | FR-11, FR-12 | Unit Test | FunctionComponent 생성 및 mount(), update() 실행 | 컴포넌트 생성 및 렌더링 | 정의한 컴포넌트 생명주기 함수가 정상 실행됨 |
| VT-11 | FR-13, FR-15 | Unit Test | 부모 컴포넌트에서 자식 컴포넌트로 Props 전달 | 자식 컴포넌트에서 Props 사용 | 전달한 Props 값과 실제 사용 값이 일치함 |
| VT-12 | FR-16 | Unit Test | useState 초기값 전달 | State와 setter 반환 | 초기값이 State에 설정되고 setter가 반환됨 |
| VT-13 | FR-14, FR-17 | Integration Test | setter를 이용한 State 변경 | 컴포넌트 재렌더링 및 화면 갱신 | 변경된 State가 UI에 반영됨 |
| VT-14 | FR-18, FR-19 | Unit Test | useEffect 실행 및 의존성 변경 | Effect 실행 여부 판단 | 의존성 조건에 따라 Effect가 실행됨 |
| VT-15 | FR-20 | Unit Test | 동일한 의존성 값과 변경된 의존성 값 전달 | 계산 결과 재사용 또는 재계산 | 의존성이 같으면 이전 결과를 재사용하고, 변경되면 다시 계산함 |
| VT-16 | FR-21 | Unit Test | 컴포넌트 내부가 아닌 위치에서 Hook 호출 시도 | Hook 호출 제한 | 정의한 Hook 호출 규칙을 위반한 호출을 제한함 |
| VT-17 | FR-22 | Integration Test | Phase 2에서 State 변경 후 화면 갱신 | Phase 1의 VDOM, Diff, Patch 실행 | Phase 1 기능을 통해 변경된 화면이 반영됨 |
| VT-18 | FR-23 | Functional Test | Phase 2 테스트 페이지에서 입력 및 클릭 | State 변경 및 UI 갱신 | 사용자 조작에 따라 화면이 정상적으로 갱신됨 |
| VT-19 | FR-24 | Functional Test | 하나의 이벤트 핸들러에서 여러 State 변경 | 한 번의 렌더링으로 업데이트 처리 | 렌더링 횟수가 1회이며 모든 State 변경 결과가 UI에 반영됨 |

### 4.4 품질 및 제약사항 검증

R17~R20과 Batching 관련 요구사항을 검증한다.

| 검증 ID | 요구사항 ID | 검증 방법 | 테스트 조건 | 예상 결과 | 합격 기준 |
|---|---|---|---|---|---|
| VT-20 | NFR-01 | Integration Test | 일부 DOM 노드만 변경하는 Patch 실행 | 변경된 영역만 업데이트 | 변경되지 않은 영역은 불필요하게 업데이트되지 않음 |
| VT-21 | NFR-02 | Boundary Test | 빈 값, 잘못된 입력, 존재하지 않는 노드 전달 | 예외 상황 처리 | 정의한 예외 처리 결과와 일치하며 프로그램이 비정상 종료되지 않음 |
| VT-22 | NFR-03 | Code Review | Virtual DOM, Diff, Patch, Component, Hooks 코드 검토 | 모듈별 책임 분리 | 각 모듈의 역할과 인터페이스가 구분되어 있음 |
| VT-23 | CON-01, CON-02 | Code Review | 프로젝트의 기술 스택 및 의존성 확인 | Vanilla JS 또는 TS 기반 구현 | React, Vue 등 외부 UI 프레임워크 없이 핵심 기능이 구현됨 |
| VT-24 | CON-04, CON-05 | Functional Test | 브라우저 및 DOM 테스트 환경에서 애플리케이션 실행 | DOM API 정상 동작 | 실제 DOM 조작과 화면 갱신이 정상적으로 수행됨 |

### 4.5 엣지 케이스 검증

R20의 예외 및 경계 조건을 구체적인 테스트 항목으로 작성한다.

| 검증 ID | 관련 기능 | 테스트 조건 | 예상 결과 | 합격 기준 |
|---|---|---|---|---|
| VT-25 | DOM 변환 | 자식 노드가 없는 요소 변환 | 빈 자식 노드 목록 생성 | 오류 없이 Virtual DOM으로 변환됨 |
| VT-26 | DOM 변환 | 속성이 없는 요소 변환 | 빈 속성 정보 생성 | 오류 없이 Virtual DOM으로 변환됨 |
| VT-27 | Diff | 기존 속성 삭제 | 속성 삭제 변경 사항 탐지 | 삭제 대상 속성이 Diff 결과에 기록됨 |
| VT-28 | Diff | 변경되지 않은 Virtual DOM 비교 | 변경 사항 없음 | 빈 Diff 결과 반환 |
| VT-29 | Patch | 동일한 값 입력 후 Patch 실행 | 실제 DOM 유지 | 불필요한 DOM 변경이 발생하지 않음 |
| VT-30 | History | History가 없는 상태에서 Undo 또는 Redo 실행 | 상태 변경 없음 | 오류 없이 기존 상태 유지 |
| VT-31 | Patch | 존재하지 않는 노드에 대한 수정 및 삭제 요청 | 정의된 예외 처리 수행 | 비정상 종료 없이 예외 상황 처리 |

> VT-25~VT-31은 R20의 엣지 케이스를 구체화한 테스트 항목이다. 실제 구현 방식에 따라 예상 결과와 예외 처리 기준을 설계 단계에서 확정한다.

## 5. Requirements Traceability (SRS 5.1)

### 5.1 프로젝트 요구사항과 SRS 추적 관계

팀에서 정의한 PR과 SRS 요구사항, 검증 항목 간의 관계를 정리한다.

| 프로젝트 요구사항 ID | SRS 요구사항 ID | 검증 ID | 비고 |
|---|---|---|---|
| PR-01 | FR-01, FR-02, IR-04 | VT-01, VT-02 | DOM 변환 |
| PR-02 | FR-03, FR-04, FR-05 | VT-03~VT-05 | Diff |
| PR-03 | IR-01, IR-02, IR-03 | VT-18 | 검증 페이지 |
| PR-04 | FR-01, FR-02 | VT-01, VT-02 | 초기 렌더링 관련 추가 검증 필요 |
| PR-05 | IR-01 | VT-18 | 테스트 영역 직접 수정 |
| PR-06 | FR-06, FR-07, FR-08, IR-06 | VT-06, VT-07 | Patch 및 History 저장 |
| PR-07 | FR-09, FR-10, IR-03 | VT-08, VT-09 | History 이동 |
| PR-08 | FR-11, FR-12 | VT-10 | Function Component |
| PR-09 | FR-21 | VT-16 | Hook 호출 규칙 |
| PR-10 | FR-13, FR-15 | VT-11 | Props 및 State 관리 |
| PR-11 | FR-14, FR-17 | VT-13 | State 변경에 따른 렌더링 |
| PR-12 | FR-16, FR-17, IR-08 | VT-12, VT-13 | useState |
| PR-13 | FR-18, FR-19 | VT-14 | useEffect |
| PR-14 | FR-20 | VT-15 | useMemo |
| PR-15 | FR-22 | VT-17 | Phase 1 기능 재사용 |
| PR-16 | FR-23, IR-07 | VT-18 | Phase 2 테스트 페이지 |
| PR-17 | CON-01, CON-02 | VT-23 | 기술 스택 및 프레임워크 제약 |
| PR-18 | NFR-02, NFR-03 | VT-01~VT-05, VT-10~VT-16, VT-21, VT-22 | 모듈별 단위 테스트 |
| PR-19 | NFR-02 | VT-06~VT-09, VT-13, VT-17~VT-19, VT-24 | 기능 테스트 |
| PR-20 | NFR-02 | VT-25~VT-31 | 엣지 케이스 |
| PR-21 | FR-24 | VT-19 | Batching |

### 5.2 원본 과제 요구사항과 SRS 추적 관계

원본 과제 요구사항과 SRS 요구사항, 검증 항목 간의 추적 관계를 정리한다.

| 원본 요구사항 ID | SRS 요구사항 ID | 검증 ID | 비고 |
|---|---|---|---|
| R17 | CON-01, CON-02 | VT-23 | Vanilla JS/TS 사용 및 외부 UI 프레임워크 금지 |
| R18 | NFR-02, NFR-03 | VT-01~VT-05, VT-10~VT-16, VT-21, VT-22 | 모듈별 단위 테스트 |
| R19 | NFR-02, IR-01~IR-03, IR-07, IR-08 | VT-06~VT-09, VT-13, VT-17~VT-19, VT-24 | 사용자 입력부터 화면 갱신까지 기능 테스트 |
| R20 | NFR-02 | VT-25~VT-31 | 엣지 케이스 |

> R1~R16의 매핑은 원본 과제 요구사항 내용을 확인한 뒤 추가한다.

## 6. 최종 검토 항목

- [ ] 기능 요구사항에 고유 ID가 부여되었는가?
- [ ] 기능 요구사항과 비기능 요구사항이 구분되었는가?
- [ ] 프로젝트 요구사항 PR과 SRS 요구사항의 연결이 정확한가?
- [ ] 원본 과제 요구사항 R과 프로젝트 요구사항 PR을 구분했는가?
- [ ] 인터페이스의 입력과 출력이 명확한가?
- [ ] 제약사항이 과제 조건과 일치하는가?
- [ ] 각 요구사항에 검증 방법과 합격 기준이 연결되었는가?
- [ ] Phase 1과 Phase 2의 검증 항목이 구분되었는가?
- [ ] 엣지 케이스가 테스트 항목에 반영되었는가?
- [ ] 최종 SRS.md의 항목과 내용이 일치하는가?

