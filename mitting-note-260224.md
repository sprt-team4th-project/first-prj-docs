# 📝 Daily Scrum Meeting Minutes

**Date (일시):** 2026.02.24 (데일리 스크럼)  
**Location (장소):** ZEP  
**Recorder (작성자):** 신현민  
**Attendees (참석자):** 정채림(팀장), 신현민, 이지민, 이지혜, 이재민  

---

## 1. Meeting Agenda (회의 안건)
- **Git Branch & Merge Strategy:** Git 브랜치 전략 및 병합(Merge) 규칙 재정립
- **Project Scope & Presentation:** 프로젝트 목표 범위(Scope) 조정 및 발표 자료 준비 논의
- **Troubleshooting Sync:** 더미 데이터 초기화(Data Initializer) 관련 이슈 공유
- **Domain Progress:** 상품(Product) 및 카테고리(Category) 도메인 개발 완료 보고

## 2. Key Discussions (주요 논의 사항)
- **Git & Branch Strategy (공통 규칙):**
  - `develop` 브랜치 병합 시 컴파일 에러(빨간불)가 있는 상태로 올리는 것을 엄격히 금지함
  - 팀원 코드 병합 전, 반드시 로컬 환경(IntelliJ)에서 직접 테스트 진행 필수
  - 에러 발생 시 즉시 병합하지 않고 별도의 브랜치 생성 후 수정하여 다시 **PR (Pull Request)** 요청하기로 합의
  - 병합 이후 발생하는 긴급 에러는 `fix` 브랜치를 생성하여 **Hotfix** 형태로 신속하게 대응할 것
- **Mentor Feedback (튜터님 피드백 반영):**
  - 프로젝트 개발 범위 관련하여 '도전(Challenge)' 기능까지 무리하게 진행할 경우, 가장 중요한 발표 자료(Presentation)의 퀄리티가 무너질 수 있음을 지적받음
  - **방향성 수정:** 도전 과제보다는 **필수(Mandatory)** 기능 완성에 집중하고, 즉시 발표 자료 준비 단계로 전환하기로 결정
- **Security & Environment Variables (보안 설정):**
  - DB 비밀번호 및 JWT 토큰 암호화 기법 등의 민감 정보는 환경 변수(Environment Variables)로 철저히 분리
  - 해당 변수들은 Git 프로젝트에 추적/공유되지 않으므로 보안 유출 위험이 없음을 팀원 간 재확인
- **Troubleshooting (Data Initializer & API 테스트):**
  - **이슈:** API 명세서 작성을 위해 슈퍼 관리자 및 고객 더미(Dummy) 데이터를 생성 후 Postman 테스트를 진행했으나 응답 에러 발생. DB 직접 조회 결과 데이터 미저장 상태 확인
  - **원인 분석:** `Data Initializer`가 기존 데이터가 '없는 상태'를 전제로 Mock 데이터를 삽입하도록 설계됨. 그러나 이전 테스트 과정에서 남아있던 1건의 데이터 때문에 초기화 로직이 정상 동작하지 않아(Mock 데이터 미생성) 조회가 실패했던 것
- **신현민:**
  - `Product` (상품) 도메인 최종 구현 완료
  - 팀원 피드백을 수용하여 **Refactoring (리팩토링)** 진행: 상품 서비스 로직 내 예외 처리 메서드를 별도 함수로 추출(Method Extraction)하여 코드 가독성 및 유지보수성 대폭 향상
  - `Product` Entity 내부의 불필요한 레거시(쓰레기) 코드 클린업(Clean-up) 완료
- **이재민:**
  - `Category` (카테고리) 도메인 비즈니스 로직 및 구현 최종 완료

## 3. Decisions Made (의사 결정 사항)
- **Scope Adjustment:** 무리한 추가 기능 구현을 멈추고, 핵심 필수 기능 안정화 및 프로젝트 발표 자료 준비 체제로 전환
- **Strict Merge Policy:** 로컬 환경에서 검증되지 않은 코드의 `develop` 병합 전면 금지 및 철저한 Hotfix 프로세스 도입

## 4. Action Items (향후 계획 및 TODO)

### 👥 Common Tasks (공통 작업)
- **QA & Testing:** `develop` 병합 전 개별 로컬 환경(IntelliJ)에서 철저한 사전 검증 및 단위 테스트 수행
- **Documentation:** 확정된 필수 기능을 바탕으로 API 명세서 최신화 및 발표 자료(PPT/Markdown) 초안 기획 시작

### 👤 Individual Tasks (개별 역할)
- **신현민, 이재민:** 담당 도메인(Product, Category) 구현 완료에 따른 최종 PR 작성 및 코드 리뷰 대기
- **전체 팀원:** 발표 자료에 들어갈 본인 담당 도메인의 주요 트러블슈팅 사례 및 아키텍처 다이어그램 정리

## 5. Next Meeting (차기 회의 계획)
- **Date (일정):** 2026.02.25
- **Agenda (예상 의제):** 발표 자료 기획안 리뷰 및 통합 테스트(Integration Test) 진행 상황 점검
