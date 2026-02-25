# 📝 Daily Scrum Meeting Minutes

**Date (일시):** 2026.02.24 (데일리 스크럼)  
**Location (장소):** ZEP  
**Recorder (작성자):** 신현민  
**Attendees (참석자):** 정채림(팀장), 신현민, 이지민, 이지혜, 이재민  

---

## 1. Meeting Agenda (회의 안건)
- **Git Branch & Merge Strategy:** Git 브랜치 전략 및 병합(Merge) 규칙 재정립
- **Project Scope & Presentation:** 필수(MVP) 기능 우선 진행 및 발표 자료 준비 논의
- **Troubleshooting Sync:** 더미 데이터 초기화(Data Initializer) 이슈 공유
- **Individual Progress & Code Review:** 팀원별 개발 진행 상황 및 이슈 공유

## 2. Key Discussions (주요 논의 사항)

### 📌 공통 논의 사항 (Common Rules & Troubleshooting)
- **Git & Branch Strategy:** `develop` 병합 전 로컬 환경(IntelliJ) 테스트 필수. 컴파일 에러 발생 시 병합을 금지하고 별도 브랜치에서 수정 후 PR 요청. 긴급 에러는 **Hotfix** 대응.
- **Scope Adjustment:** 튜터님 피드백을 수용하여 도전(Challenge) 과제보다는 **필수(Mandatory)** 기능 완성에 집중하고, 즉시 프로젝트 발표 자료(Presentation) 준비 체제로 전환하기로 결정.
- **Troubleshooting (Data Initializer):** 기존 데이터가 남아있는 상태에서 `Data Initializer`가 Mock 데이터를 생성하지 않아 API 조회 에러가 발생했던 원인 규명 및 공유.
- **Security:** DB 비밀번호 및 인증 암호화 키 등은 환경 변수(Environment Variables)로 분리하여 보안 유지.

### 👤 개별 현황 및 이슈 공유 (참석자 순)

- **정채림 (팀장):**
  - 전체 프로젝트의 **API 테스트(API Testing)** 수행 및 **API 명세서(API Specification)** 작성 완료
  - **Retrospective (회고):** 개발 단계에서 각종 테스트 코드 작성이 사전에 충분히 이루어지지 않은 채 진행된 점에 대해 짙은 아쉬움을 공유함

- **신현민:**
  - `Product` (상품) 도메인 최종 구현 완료
  - 팀원 피드백을 수용하여 **Refactoring (리팩토링)** 진행: 상품 서비스 로직 내 예외 처리 메서드를 별도 함수로 추출(Method Extraction)하여 코드 가독성 및 유지보수성 향상
  - `Product` Entity 내부의 불필요한 레거시(쓰레기) 코드 클린업(Clean-up) 완료

- **이지민:**
  - 오전 중 개인 TIL(Today I Learned) 작성 완료
  - 오후에 공유받은 자료(Notion, 영상)를 바탕으로 **JWT (JSON Web Token)** 기반 인증 로직을 테스트 코드로 작성해 봄
  - 다만, 프로젝트 개발 범위를 **MVP(필수 기능)**로 제한하기로 의사결정이 변경됨에 따라, 아쉽게도 이번 프로젝트 스코프에서는 해당 JWT 구현 코드는 제외(Drop)하기로 함

- **이지혜:**
  - 목록 조회 시 **Pagination(페이징)** 기능 구현 시도 중
  - 단순 페이징 외에 부가적인 **Sorting (정렬)** 및 **Status Filtering (상태 기반 필터링)** 기능은 현재 기술적 난이도가 있어, 이재민 님 등 다른 팀원에게 지원(Pair Programming)을 요청할 예정

- **이재민:**
  - `Category` (카테고리) 도메인 비즈니스 로직 및 구현 최종 완료
  - `Order` 및 `Category` 도메인 테스트 과정에서 발생한 이슈 **디버깅(Debugging)** 수행
  - 기존에 잘못 적용되었던 테스트 기법(Test Methodology)을 전체적으로 리팩토링하고 런타임(실행) 오류를 수정하는 데 리소스를 집중함
  - 추가로 이지혜 님의 기능(페이징 등) 구현을 지원하며 적극적으로 협업 진행 중

## 3. Decisions Made (의사 결정 사항)
- **Scope Definition:** JWT 등 추가 기능 구현을 중단하고 핵심 필수 기능 안정화 우선 처리
- **Strict Quality Control:** 철저한 로컬 테스트 기반의 Git 병합 규칙 시행 및 TDD 부재로 인한 버그 최소화를 위해 꼼꼼한 API 수동 테스트 병행

## 4. Action Items (향후 계획 및 TODO)
- **공통 (Common Tasks):** 확정된 API를 바탕으로 명세서 최신화 및 발표 자료(PPT/Markdown) 초안 작성 돌입
- **이재민 & 이지혜:** 페이징, 정렬, 필터링 등 복잡한 조회(Query) 로직 페어 프로그래밍 진행
- **전체 팀원:** `develop` 병합 전 철저한 사전 검증 및 코드 리뷰

## 5. Next Meeting (차기 회의 계획)
- **Date (일정):** 2026.02.25
- **Agenda (예상 의제):** 발표 자료 기획안 리뷰 및 통합 테스트(Integration Test) 진행 상황 점검
