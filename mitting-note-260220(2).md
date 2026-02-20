# 📝 Daily Scrum Meeting Minutes

**Date (일시):** 2026.02.20 (데일리 스크럼)  
**Location (장소):** ZEP  
**Recorder (작성자):** 정민교  
**Attendees (참석자):** 정채림(팀장), 신현민, 이지민, 정민교, 이지혜, 이재민  

---

## 1. Meeting Agenda (회의 안건)
- **Project Status Sync:** 프로젝트 진행 상황 공유
- **Weekend Work Plan:** 주말 ZEP 참여 인원 및 작업 계획 공유
- **Next Steps & Role Allocation:** 향후 일정 및 역할 분담

## 2. Key Discussions (주요 논의 사항)
- **정민교:** - `Order` 도메인의 **3-Layer Architecture** 구성 및 `GET` 관련 API 명세서 작성
  - 현재 목록 조회(List)만 구현 완료. 이재민 님의 `Order` CUD(생성/수정/삭제) 구현이 완료되면 단건 조회 API 추가 구현 예정
- **이지혜:** - `Customer` (고객 관리) Entity 설계 및 생성 예정 (내일 저녁까지 완료 목표)
- **이재민:** - 팀원 Entity 코드 리뷰 및 Fix 진행
  - `Category` 계층형 구조(대/중/소분류) 설계를 위한 연관관계 매핑 진행
  - `Order` 도메인의 3-Layer Architecture 뼈대 구축 및 `POST` (주문 생성) 로직 완벽 구현
- **정채림 (팀장):** - 전체 프로젝트 진행 상황 모니터링 및 Git Merge 수행
  - 블로커(Blocker) 발생 및 개발 지연 시 즉각적인 팀 내 공유 당부
- **신현민:** - `Product` 도메인 기본 스캐폴딩(3-Layer, `Enum`, Entity) 진행 중 (WIP)
  - Java `Record` 클래스의 장점(보일러플레이트 코드 감소, `private final` 필드 기본 제공, 불변성 보장)과 `Builder` 패턴을 적극 활용하여 핵심 비즈니스 로직에 집중할 수 있는 환경 구성 제안
- **이지민:** - 관리자(Admin) 인증 API (회원가입, 로그인, 로그아웃) 구현 완료
  - 회원가입 Request DTO를 `Record`로 구현하고 **Bean Validation**(`@Valid`) 적용
  - 로그인 로직 상태별 분기 처리, 세션(Session) 만료 시간 24시간 설정
  - 보안 강화를 위한 쿠키 **HttpOnly** 옵션 적용
  - 프로젝트 전역에서 사용할 **Global Error Code (공통 에러 코드)** 작성

## 3. Decisions Made (의사 결정 사항)
- **Category Entity 구조 확정:**
  - 단순 1차원 구조가 아닌 **Hierarchical Category (계층형 카테고리)**로 구현
  - 부모-자식 카테고리를 연결하는 **Self-Referencing (자기 참조)** 매핑 적용

## 4. Action Items (향후 계획 및 TODO)

### 👥 Common Tasks (공통 작업)
- **Task Prioritization:** 본인 담당 작업 진행 시 **MoSCoW 기법**(Must, Should, Could, Won't)을 적용하여 우선순위 기반으로 개발 진행
- **Entity Implementation:** ERD 최종안을 바탕으로 각자 할당된 도메인의 JPA Entity 클래스 생성 완료하기

### 👤 Individual Tasks (개별 역할)
- **정채림 (팀장):** 회의록 초안 작성, GitHub Organization 생성
- **정민교:** `Order` GET 단건 조회 대기 및 추후 구체적 기능 담당 확정 예정 (TBD)
- **이재민, 신현민, 이지민:** 본인 담당 도메인 개발 지속 및 추가 세부 기능 할당 대기

## 5. Next Meeting (차기 회의 계획)
- **Date (일정):** 2026.02.23
- **Agenda (예상 의제):** 결제 시스템 연동 진행도 재확인 및 이슈 점검
