# 📝 Team Meeting Minutes

**Date (일시):** 2026.02.20  
**Location (장소):** ZEP  
**Recorder (작성자):** 정민교  
**Attendees (참석자):** 정채림(팀장), 정민교, 이재민, 신현민, 이지민  

---

## 1. Meeting Agenda (회의 안건)
- **Project ERD (Entity Relationship Diagram) Design:** 프로젝트 데이터베이스 구조 설계
- **Entity Association Mapping:** 엔티티 간 연관관계 매핑 전략 논의
- **Role Allocation & Schedule:** 향후 일정 및 역할 분담

## 2. Key Discussions (주요 논의 사항)
- **정민교:** `Order` 도메인의 **3-Layer Architecture** (Controller - Service - Repository) 설계 및 Git 브랜치 전략/업데이트 방법에 대해 논의
- **이재민:** `@OneToMany` 및 `@ManyToOne` 어노테이션을 활용한 Entity 연관관계 매핑 방식 제안 및 `Category` Entity 생성 필요성 언급
- **신현민:** `Product` 도메인 담당으로서, 상품과 카테고리 간의 관계를 `@ManyToOne`으로 매핑하여 연결 방향성 제시
- **정채림:** 논의된 연관관계 및 `Category` Entity의 구조를 ERD 설계에 즉각 반영

## 3. Decisions Made (의사 결정 사항)
- **Category Entity 구조 확정:**
  - 단순 1차원 카테고리가 아닌, **Hierarchical Category (계층형 카테고리)** 구조로 구현하기로 결정
  - 동일한 Entity 내에서 부모(Parent)와 자식(Child) Category를 연결하는 **Self-Referencing (자기 참조)** 연관관계 매핑 적용
- **Infra & Tooling:**
  - 협업을 위한 GitHub Organization 및 공용 Repository 생성

## 4. Action Items (향후 계획 및 TODO)

### 👥 Common Tasks (공통 작업)
- **Requirement Prioritization:** 프로젝트 주요 기능을 **MoSCoW 기법**(Must have, Should have, Could have, Won't have)을 적용하여 우선순위 산정
- **Entity Implementation:** 완성된 ERD를 바탕으로, 각자 담당한 도메인의 JPA Entity 클래스 생성

### 👤 Individual Tasks (개별 역할)
- **정채림 (팀장):** 회의록 초안 작성, GitHub Organization 생성
- **정민교:** 추후 구체적 기능 담당 확정 예정 (TBD)
- **이재민, 신현민, 이지민:** 추후 세부 기능 할당 대기
