# SRS Template Selection Rationale

## 1. 작성 목적

ISO/IEC/IEEE 29148:2018을 참고한 SRS 템플릿을 선정하고, 미니 React 프로젝트에 적용하기 위해 검토한 기준과 판단 근거를 기록한다.

## 2. 참고 자료

| 구분 | 자료 | 활용 목적 |
|---|---|---|
| 표준 | ISO/IEC/IEEE 29148:2018 | SRS 구성 및 요구사항 작성 원칙 확인 |
| 공개 템플릿 | [DIN-DKE SRS Template](https://github.com/DIN-DKE/ISO_IEC_IEEE_29148__SRS-Template/blob/master/template.md) | SRS 세부 항목 및 문서 구조 비교 |
| 프로젝트 요구사항 | LMS R1~R20 | 템플릿 항목의 도입 필요성 판단 |

## 3. 템플릿 선정 기준

다음 기준으로 공개 템플릿의 항목을 검토한다.

1. LMS R1~R20의 구현 범위를 요구사항으로 명세할 수 있는가?
2. 기능, 품질, 인터페이스, 기술적 제약을 구분할 수 있는가?
3. 요구사항별 검증 방법을 정의할 수 있는가?
4. 요구사항과 구현 작업 및 테스트 간 추적이 가능한가?
5. 프로젝트 규모에 비해 불필요하게 복잡한 항목은 없는가?

## 4. 원본 템플릿 항목 검토

| 원본 항목 | 적용 판단 | 판단 근거 | 최종 반영 항목 |
|---|---|---|---|
| Introduction | 도입 | 문서 목적과 프로젝트 범위 정의 필요 | 개요 |
| Product Overview | 도입·통합 | Phase1, Phase2의 시스템 구성 설명 필요 | 제품 개요 |
| Functional Requirements | 도입 | R1~R16의 기능 명세 필요 | FR |
| External Interfaces | 도입·간소화 | 사용자 인터페이스 및 모듈 간 입출력 정의 필요 | IR |
| Quality of Service | 도입·간소화 | 성능 및 품질 기준 정의 필요 | NFR |
| Design and Implementation Constraints | 도입·간소화 | R17의 기술 및 구현 제약 정의 필요 | CON |
| Verification | 도입 | R18~R20 및 기능별 검증 기준 필요 | VT |
| Appendixes | 도입·간소화 | LMS 요구사항과 SRS 및 검증 항목 간 추적 필요 | 추적성 표 |
| Hardware Interfaces | 제외 | 외부 하드웨어 연동 범위 없음 | - |
| Distribution | 제외 | 별도 배포 요구사항 없음 | - |
| Cost | 제외 | SRS에서 별도 비용 요구사항 관리 필요성 낮음 | - |

※ 위 판단은 프로젝트 범위에 따른 적용 방안이며, 표준이나 공개 템플릿에서 해당 항목을 반드시 제외하도록 규정한다는 의미는 아니다.

## 5. LMS 요구사항과 SRS 항목의 대응

| LMS 요구사항 | 요구사항 성격 | SRS 반영 항목 |
|---|---|---|
| R1~R16 | 기능 구현 | FR, IR |
| R17 | 기술 및 구현 제약 | CON |
| R18 | 단위 테스트 | VT |
| R19 | 통합 및 기능 테스트 | VT |
| R20 | 엣지 케이스 검증 | VT |

NFR은 개별 LMS 요구사항에만 대응시키는 것이 아니라, 프로젝트 전체에 적용할 성능 및 품질 기준을 별도로 정의한다.

## 6. 최종 결정

- ISO/IEC/IEEE 29148:2018을 SRS 작성의 참고 표준으로 선정한다.
- DIN-DKE 공개 SRS 템플릿을 문서 구조 검토 자료로 사용한다.
- LMS R1~R20을 기준으로 필요한 항목을 선정하고 프로젝트 규모에 맞게 조정한다.
- FR, NFR, IR, CON, VT로 요구사항을 구분한다.
- LMS 요구사항부터 SRS 및 검증 항목까지 추적할 수 있도록 구성한다.

## 7. 관련 문서

- [SRS Template](./SRS_TEMPLATE.md)
- [Software Requirements Specification](../SRS.md)
- [LMS Requirements](./LMS_REQUIREMENTS.md)
