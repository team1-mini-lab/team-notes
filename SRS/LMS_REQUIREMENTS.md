# LMS Original Requirements

## 1. 작성 목적

LMS에서 제공한 미니 React 프로젝트의 원본 요구사항을 보관한다.

원본 요구사항을 Phase 1, Phase 2, 제약·품질, 선택 항목으로 구분하고, SRS 작성 과정에서 요구사항이 어떻게 반영되었는지 추적하기 위한 기준 자료로 사용한다.

※ R1~R20은 제공된 요구사항을 추적하기 위해 부여한 식별자다. 원본에 공식 식별자가 별도로 존재하는 경우 원본 번호를 우선한다.

## 2. 원본 요구사항

### 2.1 Phase 1 — Virtual DOM, Diff, Patch, History

| 요구사항 ID | 원본 요구사항 |
|---|---|
| R1 | 브라우저 DOM을 읽어 Virtual DOM으로 변환 |
| R2 | 두 Virtual DOM을 비교해 변경점을 찾는 Diff |
| R3 | 실제 영역, 테스트 영역, Patch·뒤로가기·앞으로가기 버튼 |
| R4 | 로드 시 실제 영역 HTML을 Virtual DOM으로 만들고, 그걸로 테스트 영역 렌더링 |
| R5 | 사용자가 테스트 영역 HTML을 자유롭게 수정 |
| R6 | Patch: 테스트 영역 → Virtual DOM → Diff → 바뀐 부분만 실제 영역에 반영 → History 저장 |
| R7 | 뒤로가기·앞으로가기로 History 이동, 두 영역이 함께 바뀜 |

### 2.2 Phase 2 — Function Component, State, Hooks

| 요구사항 ID | 원본 요구사항 |
|---|---|
| R8 | 함수형 컴포넌트 + FunctionComponent 클래스 (hooks 배열, mount(), update()) |
| R9 | Hook은 최상위 컴포넌트에서만 사용 |
| R10 | State는 루트에서만 관리, 자식은 props만 사용 (Lifting State Up) |
| R11 | State가 바뀌면 화면이 자동으로 다시 그려짐 |
| R12 | useState |
| R13 | useEffect |
| R14 | useMemo |
| R15 | 다시 렌더링할 때 Phase 1의 Virtual DOM, Diff, Patch를 그대로 사용 |
| R16 | 테스트 페이지: 입력이나 클릭에 따라 화면이 바뀜 (주제 자유) |

### 2.3 제약 및 품질

| 요구사항 ID | 원본 요구사항 |
|---|---|
| R17 | HTML, CSS, JS(또는 TS) Vanilla. 외부 프레임워크 금지 |
| R18 | 모듈별 단위 테스트 (변환, Diff, Patch, 각 Hook) |
| R19 | 기능 테스트로 화면 동작 확인 |
| R20 | 엣지 케이스 고려 |

### 2.4 선택 사항

| 식별자 | 원본 요구사항 | 구분 |
|---|---|---|
| OPT-01 | Batching (여러 상태 변경을 한 번에 처리) | 선택 기능 |

Batching은 필수 구현 요구사항과 구분한다. 실제 구현 대상으로 선정한 경우에만 SRS 및 검증 항목에 추가한다.

## 3. SRS 요구사항으로의 변환 기준

LMS 원본 요구사항은 성격에 따라 SRS의 요구사항 유형으로 구분한다.

| LMS 요구사항 | 요구사항 성격 | SRS 반영 항목 | 반영 방법 |
|---|---|---|---|
| R1~R2 | Virtual DOM 변환 및 비교 | FR | 변환 및 Diff 동작을 구체적인 기능 요구사항으로 작성 |
| R3~R5 | 화면 구성 및 사용자 입력 | FR, IR | 화면 동작은 FR, 사용자 인터페이스 특성은 IR로 구분 |
| R6~R7 | Patch 및 History | FR | 변경 사항 반영과 History 이동 동작을 명세 |
| R8~R16 | Function Component 및 Hooks | FR, 필요한 경우 IR | 컴포넌트, State, Hooks의 동작과 관련 인터페이스 명세 |
| R17 | 기술 및 구현 제약 | CON | 사용 기술과 외부 프레임워크 제한 명세 |
| R18 | 모듈별 단위 테스트 | VT | 모듈별 단위 테스트 기준 정의 |
| R19 | 기능 테스트 | VT | 사용자 관점의 화면 동작 검증 기준 정의 |
| R20 | 엣지 케이스 | VT | 입력, 변경, 상태 및 History 경계 조건별 검증 항목 정의 |
| OPT-01 | 선택 기능 | 구현 결정에 따라 FR, VT | Batching을 구현 범위에 포함한 경우 추가 |

NFR은 LMS 원본에서 직접 식별되는 요구사항과 구분한다. 프로젝트 전체에 적용할 품질 기준이 별도로 합의된 경우 SRS에 추가한다.

## 4. 관련 문서

| 구분 | 자료 | 활용 목적 |
|---|---|---|
| 원본 요구사항 | [LMS Requirements](https://github.com/team1-mini-lab/team-notes/blob/main/SRS/LMS_REQUIREMENTS.md) | LMS에서 제공한 원본 요구사항 확인 |
| SRS 문서 | [Software Requirements Specification](https://github.com/team1-mini-lab/team-notes/blob/main/SRS/SRS.md) | 프로젝트 요구사항의 구체적인 명세 확인 |
| SRS 템플릿 | [SRS Template](https://github.com/team1-mini-lab/team-notes/blob/main/SRS/SRS_TEMPLATE.md) | SRS 문서 작성 구조 및 형식 확인 |
