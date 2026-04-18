### 👋 Hi there
<div align="center">

  ![header](https://capsule-render.vercel.app/api?type=shark&color=auto&height=210&section=header&text=Hi!%20I'm%20윤지😼&fontSize=52)
  
  </div> 

<h1 align="center">유윤지 | Yoonji Yoo</h1>

<p align="center">
  <a href="mailto:yooyoonji1121@gmail.com"><img src="https://img.shields.io/badge/Gmail-d14836?style=flat-square&logo=Gmail&logoColor=white&link=yooyoonji1121@gmail.com"/></a>&nbsp
<div align="center">

### 📞 Contact
**E-mail**: yooyoonji1121@gmail.com

### 🌐 Channel
🌏 **LinkedIn**: [https://www.linkedin.com/in/yoonji-yoo-877713286/](https://www.linkedin.com/in/yoonji-yoo-877713286/) <br/>
📚 **Blog** <br/>
[https://ll-llwhkr.tistory.com/](https://ll-llwhkr.tistory.com/) <br/>
[https://velog.io/@yj8080/posts](https://velog.io/@yj8080/posts)

</div>

---

### 📝 Introduce
#### 직접 발견하고, 이유를 찾고, 설명할 수 있는 방식으로 일하는 신입 백엔드 개발자 유윤지입니다.

사용자 경험에서 출발해 기술적 원인을 찾는 방식으로 일합니다. QA 중 응답 지연을 직접 측정해 N+1 문제를 발견하고, 어뷰징 가능성을 먼저 포착해 선제 방어한 것처럼 문제가 보이면 이유를 찾아 직접 설계하고 해결합니다.</br>
문제를 직접 정의할 수 있는 권한, 그 결과가 사용자에게 닿는다는 감각이 갖춰졌을 때 가장 깊이 몰입했고, 그 조건이 반복적으로 좋은 결과로 이어졌습니다.</br>
함께 일한 세 팀에서 기술 고민을 같이 나누기 편하고, 복잡한 흐름도 팀 전체가 이해할 수 있도록 풀어주는 사람이라는 말이 기억에 남습니다.

---

## 💡 Skills
<p>
  <img src="https://img.shields.io/badge/spring-6DB33F?style=flat-square&logo=spring&logoColor=white">
  <img src="https://img.shields.io/badge/java-007396?style=flat-square&logo=OpenJDK&logoColor=white">
  <img src="https://img.shields.io/badge/mysql-4479A1?style=flat-square&logo=mysql&logoColor=white">
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white">
  <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=Redis&logoColor=white">
  <img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=flat-square&logo=docker&logoColor=white">
  <img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white">
</p>
<p>
  <img src="https://img.shields.io/badge/html5-E34F26?style=flat-square&logo=html5&logoColor=white">
  <img src="https://img.shields.io/badge/css-1572B6?style=flat-square&logo=css3&logoColor=white">
</p>
<p>
  <img src="https://img.shields.io/badge/tableau-E97627?style=flat-square&logo=tableau&logoColor=white">
  <img src="https://img.shields.io/badge/googlecolab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white">
</p>

---

## ⚡ Projects

### 🔹 Rebra (2025.08 - 2025.09) | SSAFY
: 한국 주식 포트폴리오 리밸런싱 시뮬레이션(백테스트) 서비스

`Java` `Spring Boot` `JPA` `PostgreSQL` `Redis` `WebSocket` | BE(3명), FE(3명) | ROLE: BE + CI/CD 파이프라인 구축

https://github.com/llcodingll/Rebra

> + **외부 API 장애 대응 — On-Demand 캐싱 아키텍처 설계**
>   - 공공데이터포털 API 전면 중단으로 핵심 기능 마비 → 배포 테스트 기간 호출 로그 분석(TOP 100 집중 83% 확인)
>   - KRX CSV(2,879개 종목) DB 저장으로 검색 복구 + dataStartDate/dataEndDate로 보유 범위 추적, 미보유 구간만 선별 API 호출
>   - **배포 환경 50건 기준 API 호출 71% 감소 (201→58회)**
>
> + **Full Table Scan 제거 — 복합 인덱스 설계**
>   - On-Demand 적재 구조 도입 후 ticker + date 범위 동시 조회 시 인덱스 없이 Full Table Scan 발생
>   - 동등 조건(ticker) 선행, 범위 조건(date) 후행으로 (ticker, date) 복합 인덱스 + UNIQUE 제약 설계
>   - **Full Table Scan 제거, 중복 저장 DB 레벨 방지**
>
> + **동시 요청 Race Condition — Redisson 분산락**
>   - Check-Then-Act 패턴의 원자성 부재로 동시 요청 시 유니크 제약 위반 발생
>   - Striped Lock(JVM 경계 한계) → `stock-lock:{stockCode}` 키 기반 Redisson 분산락으로 종목 단위 격리
>   - **동시 요청 유니크 제약 위반 제거, 타 종목 병렬 처리 보장**
>
> + **Redisson 적용 후에도 지속된 stale read — OSIV 설정 수정**
>   - 락 해제 직후 후속 조회에서 dataRange가 null~null 반환 → FSS API 중복 호출 지속
>   - OSIV 기본값(true)으로 HTTP 요청 전체가 동일 영속성 컨텍스트를 공유, 1차 캐시가 커밋 이후에도 유지됨 확인
>   - `open-in-view: false` 설정으로 트랜잭션마다 독립 영속성 컨텍스트 생성
>   - **stale read 해소, 동일 종목 동시 요청 중 FSS API 호출 1회만 발생**

---

### 🔹 Kkori (2025.07 - 2025.08) | SSAFY
: AI 기반 실시간 화상 모의 면접 서비스

`Java` `Spring Boot` `JPA` `MySQL` `WebRTC` `WebSocket` | BE(3명), FE(2명) | ROLE: BE

https://github.com/llcodingll/Kkori

> + **질문 세트 수정 시 다른 사용자 복사본에 영향 — 불변 Row + 버전 매핑 설계**
>   - 공유 질문 세트 수정 시 원본 및 타 복사본 동시 변경 → 독립 수정 불가 구조
>   - Copy-on-Write(100명 → 질문 1,000개 중복), Git 스타일 분산 버전 관리(UX 비용 과도) 검토 후 기각
>   - 질문/답변 Row 불변 저장, QuestionSetVersion + Map 테이블로 버전별 구성 관리; 복제 시 Version Map만 복사, 수정 시 변경된 질문만 신규 Row 생성 후 참조 변경
>   - **질문 Row 중복 저장 없음, 원본·타 복사본 영향 없는 독립 수정 가능**

---

### 🔹 Repick (2024.11 - 2024.12) | K-Digital
: 금융권 애널리스트 리포트 기반 개인화 추천 + 커뮤니티 챗봇 서비스

`Java` `Spring Boot` `JPA` `MySQL` `Redis` `WebSocket` | BE(3명), FE(1명), MLOps(2명), PM(1명) | ROLE: BE

https://github.com/The-Naeun-Economy/comment

> + **좋아요 동시 요청 카운트 오류 — Redisson 분산락**
>   - 서비스 공개 전 직접 검증 중 좋아요 연타 시 카운트 오류 발견 → 인기 게시글 집계 왜곡
>   - UniqueConstraint(DB 부하 미해소), 비관적 락(HikariCP 풀 소진 위험) 검토 후 기각
>   - `lock:like:{userId}:{postId}` 키 기반 Redisson 분산락으로 DB 커넥션 미점유 대기
>   - **좋아요 연타 카운트 오류 해소, 동시 요청 시 DB 커넥션 1~2개로 처리**
>
> + **조회수 어뷰징 및 랭킹 왜곡 — Redis Lua Script + ZSET**
>   - 새로고침 반복으로 Top 10 랭킹 점수 무한 누적 발견
>   - EXISTS→SET→EXPIRE→INCR 순차 호출 시 Race Condition 확인 → 원자적 처리 필요
>   - userId 기반 TTL 키로 중복 조회 차단, Lua Script로 5개 명령 원자적 처리, ZSET 랭킹 전용 분리
>   - **조회수 어뷰징 차단, Top 10 조회 O(N) → O(log N + 10)**

---

### 🔹 Past-Forward (2024.02 - 2024.06) | IT 동아리
: 회고 입문자를 위한 회고 웹 애플리케이션 — **실서비스 배포, 실사용자 204명**

`Java` `Spring Boot` `Spring Data JPA` `QueryDSL` `MySQL` | BE(5명), FE(4명), DA(4명), PM(4명) | ROLE: BE 팀장, PM

https://github.com/llcodingll/past-foward-backend

> + **3N+1 쿼리로 인한 실시간 협업 동기화 지연**
>   - QA 중 5명 동시 접속 시 Long Polling 응답 1.1~1.3s 직접 측정
>   - 1:1 관계(ActionItem, KudosTarget): Projection + Fetch Join으로 단일 쿼리 통합
>   - 1:N 관계(Comment): MultipleBagFetchException 회피 위해 IN절 + Stream groupingBy 애플리케이션 매핑
>   - **3N+1 → 2쿼리, 응답 1.1~1.3s → 300~400ms**
>
> + **동시 요청 시 팀 중복 가입**
>   - QA 중 초대 수락 버튼 빠른 클릭 시 동일 사용자 중복 가입 버그 직접 발견
>   - 비관적/낙관적 락 모두 INSERT 경쟁 조건 해결 불가 판단 → DB 제약조건이 더 적합
>   - (user_id, team_id) UniqueConstraint + save() 선시도 방식, k6로 동시 100회 요청 자동화 테스트 검증
>   - **중복 가입 완전 차단, 신규 가입 쿼리 2회 → 1회**

---

## 🎓 Education

### SSAFY 13기 (삼성청년SW아카데미)
`2025.01.07 - 2025.12.31 (수료)`

삼성 주관 1년 과정 (기본 6개월 + 심화 6개월). Java 알고리즘·자료구조·Spring 백엔드, Vue.js 프론트엔드 풀스택 교육.
팀 프로젝트 3회 수행 (Kkori, Rebra, Chub). **프로젝트 경진대회 3등 수상 (Rebra)**

### K-Digital Training — 한국경제신문 with 토스뱅크 1기
`2024.06.28 - 2024.12.19 (수료)`

총 960시간. toss bank 기술 스택 기반 풀스택 과정. Java · Spring · React · AWS · DB · 배포 관리.
MLOps 트랙과 협업 프로젝트 진행. **최종 프로젝트 경진대회 2등 수상 (Repick)**

### IT 취업 동아리 (동아대학교)
`2023.06 - 현재`

DB 설계 프로젝트, 알고리즘 스터디, 프로젝트 회고 발표회 운영, 학습 블로그 공유.
Past-Forward 팀 프로젝트 수행 — 실서비스 배포, **실사용자 204명**

### 동아대학교
`2019.03 - 2024.02 (졸업)`

사회학과 + 경영정보학과 복수전공
  > + 데이터베이스시스템 / 데이터베이스구축및활용 / 시스템분석및설계
  > + 프로젝트관리 / 웹프로그래밍 / 네트워크의 이해
  > + R기반 통계 분석 / 사회통계 / 사회조사분석(캡스톤디자인)

---

## 🎯 Study
+ MySQL Database Study (2023.06 ~ 2023.09)
+ Spring Study (2024.02 ~ 03)
+ AWS Academy Cloud class (2023.12 ~ 2024.02)

## 📝 Certificate
+ Toeic Speaking Lv.6
+ Opic IM2
---

<a href="https://github.com/llcodingll"><img align="center" style="height:180px" src="https://github-readme-stats.vercel.app/api?username=llcodingll&show_icons=true&include_all_commits=true&theme=nord&hide_border=true&hide=stars,contribs&count_private=true" alt="YoonJi's github stats"/></a>
<a href="https://github.com/llcodingll"><img align="center" style="height:180px" src="https://github-readme-stats.vercel.app/api/top-langs/?username=llcodingll&layout=compact&theme=nord&hide_border=true&hide=stars,contribs&count_private=true"/></a> 

[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=llcodingll)](https://solved.ac/llcodingll/)
