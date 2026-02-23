# 📝 Daily Scrum Meeting Minutes

**Date (일시):** 2026.02.23 (데일리 스크럼)  
**Location (장소):** ZEP  
**Recorder (작성자):** 정민교  
**Attendees (참석자):** 정채림(팀장), 신현민, 이지민, 정민교, 이지혜, 이재민  

---

## 1. Meeting Agenda (회의 안건)
- **Project Status Sync:** 각 도메인별 프로젝트 개발 진행 상황 공유
- **Domain Implementation Review:** 세부 API 구현 내용 및 아키텍처 설계 이슈 점검

## 2. Key Discussions (주요 논의 사항)
- **이지민:** - `Admin` (관리자) 도메인 Write 기능(정보 수정, 역할 및 상태 변경, 삭제) API 구현 완료
  - 관리자 목록 및 상세 조회 API 구현 완료 (검색, 정렬, 필터, **Pagination(페이징)** 기능 완벽 지원)
  - 담당 필수 기능(MVP) 개발 모두 완료
- **이지혜:** - `Customer` (고객) 도메인 상세 조회 비즈니스 로직 구현 완료
- **이재민:** - `Category` 도메인 Entity 설계 및 CRUD 로직 개발 진행 중
  - **DDD (Domain-Driven Design, 도메인 주도 설계)** 및 **OOP (Object-Oriented Programming, 객체지향 설계)** 원칙을 반영하여 견고한 레이어드 아키텍처(Layered Architecture)를 구성하는 데 집중하며 퀄리티를 높이는 중
- **신현민:** - 팀 피드백 반영 중이며, `Product` (상품) 도메인 기본 CRUD 개발 진행
  - 상품 조회 및 검색 기능과 재고(Stock) 상태 자동 갱신 비즈니스 로직 작성 중
- **정채림 (팀장):** - 전체 팀원 코드 리뷰(Code Review) 및 Git 브랜치/머지(Merge) 관리 전담
- **정민교:** - `Order` 도메인 단건 조회(`GET`) API 구현 완료
  - `Customer` 도메인 UD (Update/Delete) 로직 작성 완료
  - **Authorization (권한 분리):** 회원 정보 수정은 본인만, 상태 변경 및 탈퇴(삭제) 처리는 관리자만 가능하도록 접근 제어 설정
  - **Soft Delete (논리적 삭제):** 계정 삭제 시 DB에서 완전히 삭제(Hard Delete)하지 않고, 이력 추적 및 데이터 보존을 위해 Soft Delete 패턴 적용 완료
  - 회원가입 시 이메일 중복 검증(Duplicate Check) 로직 추가 구현

## 3. Decisions Made (의사 결정 사항)
- **Architecture & Quality Focus:** 기능 구현뿐만 아니라 DDD, Soft Delete 등 실무적인 객체지향 설계와 데이터 무결성을 고려하며 코드를 고도화하기로 함

## 4. Action Items (향후 계획 및 TODO)

### 👥 Common Tasks (공통 작업)
- **Code Integration:** 본인이 구현한 API 로직 테스트 및 타 도메인과의 연동 준비
- **Code Review:** 팀장 주도하에 PR(Pull Request) 리뷰 후 메인 브랜치 병합 진행

### 👤 Individual Tasks (개별 역할)
- **이재민, 신현민:** `Category` 및 `Product` 도메인 남은 설계 및 CRUD 로직 완성
- **정민교, 이지혜, 이지민:** 구현 완료된 기능 리팩토링 및 연관 도메인 개발 지원

## 5. Next Meeting (차기 회의 계획)
- **Date (일정):** (다음 데일리 스크럼 일정 TBD)
- **Agenda (예상 의제):** 도메인 간 통합 진행 상황 점검 및 트러블슈팅 공유
