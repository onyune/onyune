# Archive

이력서·포트폴리오·자기소개서의 대표 프로젝트(Book2OnAndOn) 외의 프로젝트 기록입니다.
메인 [README](../README.md)에서는 노출하지 않지만 참고용으로 보관합니다.

---

## Re:fill — 프랜차이즈 재고관리 시스템 (Serverless 기반)

> 기간: 2025.03.10 ~ 2025.06.06
> 역할: **팀장 (PM) 및 백엔드 개발 (4인 프로젝트)**

<img src="refill.png" height="20" align="center"/>

- Firebase Serverless 기반 실시간 재고 관리 및 **자동 발주 스케줄링** 구현
- Cloud Firestore(NoSQL) 스키마 설계 및 비정규화(Denormalization) 패턴 적용
- 계층형 컬렉션 구조 설계를 통한 데이터 접근 경로 최적화 및 읽기 비용 절감
- 초대 코드 기반의 가맹점 가입 프로세스 및 **보안 규칙(Security Rules)** 연동

---

## NHN-CHAT — Java TCP Messenger (클라이언트-서버 메신저 시스템)

> 기간: 2026.01.28 ~ 2026.02.05 (2주)
> 역할: **백엔드 개발 및 TCP 소켓 통신 구현 (2인 프로젝트)**

- **Maven 멀티 모듈 아키텍처(Common, Server, Client)** 구조를 도입해 모듈 간 의존성을 분리하고 확장성·유지보수성을 향상
- **TCP Socket** 통신으로 다중 사용자의 실시간 접속 및 브로드캐스팅 환경 구축
- TCP 스트림의 경계를 명확히 구분하기 위해 헤더에 데이터 길이를 명시하는 **Text-based Length-Prefix 프로토콜을 직접 설계**
- 공통 통신 규격을 정의하고 Jackson으로 **JSON Payload**를 직렬화/역직렬화
- 사용자 인증, 채팅방 상태 관리(생성/목록/입장/퇴장), 1:1 귓속말 등 핵심 도메인 설계·구현

---

## NHN Shopping Mall — Java Servlet 기반 쇼핑몰 시스템

> 기간: 2026.03.09 ~ 2026.03.20 (2주)
> 역할: **백엔드 개발 (2인 팀 프로젝트)**

- Spring MVC 동작 원리를 이해하기 위해 **FrontServlet + ControllerFactory 기반 커스텀 MVC 프레임워크를 직접 설계**하고 이후 Spring MVC로 마이그레이션
- Java Reflection API와 커스텀 `@RequestMapping` 어노테이션으로 **URL·HTTP Method 기반 컨트롤러 자동 탐색·등록 시스템** 구현
- `ThreadLocal` 기반 `DbConnectionThreadLocal`로 **요청 단위 DB 커넥션 관리 및 트랜잭션(commit/rollback) 처리**
- `HttpFilter`로 인코딩, 인증, 권한(ROLE_ADMIN/ROLE_USER) 검사를 **필터 체인으로 일괄 처리**
- 포인트 지급 로직을 **WorkerThread + BlockingQueue 구조로 분리**해 메인 요청 흐름과 결합도를 낮추고 비동기 처리

---

## AI Library — 공공 도서 데이터 기반 AI 검색 플랫폼 (RAG · Vector · MCP)

> 기간: 2026.06.22 ~ 2026.07.02
> 역할: **백엔드 개발 (4인 팀 프로젝트, batch / core / telegram 멀티 레포)**

**Tech** · Java 21 · Spring Boot 3.5 · Spring AI (Google GenAI / Ollama) · PostgreSQL + pgvector · Redis · Caffeine · RabbitMQ · JPA / QueryDSL · Telegram Bot API · KOMORAN

- 키워드 → 벡터 → 하이브리드 → RAG로 이어지는 검색을 **Strategy 패턴(Keyword/Vector/Hybrid/Auto)** 으로 설계·구현
- 사용자 피드백 기반 **선호도 벡터(User Preference Vector)** 를 계산해 개인화 랭킹에 반영
- **Redis 기반 시멘틱 캐싱** 도입 및 캐시 임계치 튜닝으로 벡터 검색 비용 절감
- Telegram Bot에 **의도 분석(Intent) 틀**을 붙여 대화형 검색 UI와 피드백 수집 흐름 구현
- Spring AI **`@Tool` 기반 오케스트레이션**으로 도서관정보나루 API 17종을 8개 Function으로 통합
