# Hupository — 박세종의 인간 데이터 저장소

> **Human Repository Service** — 한 사람의 삶을 코드처럼 버전 관리하는 개인 데이터 인프라

---

## 이 저장소는 무엇인가

**Hupository**는 박세종(lifedesigner88)이 설계한 **자기 자신에 대한 구조화된 데이터 시스템**이다.
이력서·자기소개서·목표·관심사·19년간의 연도별 회고를 YAML/JSON/Markdown으로 체계화하여,
AI 서비스가 소비할 수 있는 형태와 사람이 읽을 수 있는 형태 모두를 동시에 지원한다.

```
한 사람의 삶  →  구조화된 데이터  →  AI · 서비스 · 사람이 함께 읽는 저장소
```

---

## 사람 요약: 박세종

| 항목 | 내용 |
|------|------|
| 생년 | 1988년 9월 12일 (만 37세) |
| 정체성 키워드 | 라이프디자이너, 교육자, 개발자, 커뮤니티 빌더 |
| 현재 상태 | 1인 창업자 — 세종클래스(sejongclass.kr) 운영 중 |
| 기술 스택 | Python · TypeScript · React · Spring Boot · Supabase · AWS · K8s |
| 핵심 서사 | 10년간 교육/커뮤니티 운영 → 37세에 개발자 전직 → 교육×기술 통합 서비스 창업 |
| 연락처 | lifedesigner88@gmail.com |
| GitHub | https://github.com/lifedesigner88 |

**19년의 궤적 (2007–2026)**

```
2007–2010   방황과 재부팅      대학 입학 · 조울증 진단 · 망막수술 · 너울가지 1기 참여
2011–2015   정체성 선언        '라이프디자이너' 선언 · 너울가지 8기 운영 (5년) · 대학 졸업
2016–2019   국제 무대          WYR 국제캠프 PM (12개국 · 100여 명 · 매년 1주)
2020–2022   지식의 폭발        코로나 · 뇌과학·물리 독서 200권 · 수학과외 · 대입 컨설팅
2023–2024   개발세계 입문      한화시스템 BEYOND SW캠프 · 120일 개근 · KIP 프로젝트 1위
2024–2025   부트캠프 운영 보조  엔코아(PlayData) 입사 · 4개 반 120명 수강생 관리
2025–2026   퇴사 · 1인 창업    세종클래스 풀스택 단독 기획·개발·운영 · SW마에스트로 도전
```

---

## 저장소 구조

```
hupository/
├── README.md
│
├── data/                         ← 단일 정규 데이터 레이어 (모두 공개)
│   ├── profile.yaml              ← 기본 정보 · 연락처 · 소개문
│   ├── schema.yaml               ← 서비스 소비용 데이터 스키마
│   ├── sources.yaml              ← 블로그 URL · 연도별 회고 포스트 링크
│   │
│   ├── 01_identity/              ← 정체성 · 가치관 · 페르소나 · 정체성 전환 이력
│   ├── 02_experience/            ← 경력 · 학력 · 프로젝트 상세
│   │   └── projects/             ← 세종클래스 · KIP · WYR 등
│   ├── 03_skills/                ← 기술/소프트 스킬 · 숙련도 레벨
│   ├── 04_story/                 ← 6챕터 서사 마크다운 + arc.yaml
│   │   └── chapters/             ← 2007-2010 / 2011-2015 / ... / 2025-2026
│   ├── 05_interests/             ← 관심 도메인 · 독서 목록
│   │   ├── interests.yaml        ← 관심사 + 독서 성향 요약
│   │   ├── reading_list.yaml     ← 독서 목록 인덱스
│   │   └── reading/              ← 연도별 독서 데이터 (2021-2026, 총 180권)
│   │       └── stats.yaml        ← 통계 + 카테고리 분포 + 독서 성향 분석
│   ├── 06_goals/                 ← 단기/장기 목표
│   ├── 07_matching/              ← 매칭 벡터 · 신호 · 선호
│   └── timeline/                 ← 2007–2026 연도별 회고 원본
│
├── ai/                           ← AI 소비 레이어 (진입점 + 생성 출력물)
│   ├── index.yaml                ← AI 진입점: 1분 요약 + 전체 navigation
│   ├── outputs/                  ← 자기소개서 · 이력서 · 태그 · 추론 프로필
│   └── prompts/                  ← LLM 컨텍스트 주입 프롬프트
│
└── secret/                       ← 전화번호 등 PII만 (.gitignore 처리)
```

---

## 레이어 설명

### `data/` — 단일 정규 소스

모든 데이터의 유일한 원본. 사람이 직접 편집하는 레이어.
19년치 연도별 회고, 경력 기술서, 관심사, 독서 목록, 서사 마크다운이 모두 여기에 있다.

### `ai/` — AI 소비 레이어

`ai/index.yaml`이 진입점. 이 파일 하나로 이 사람을 1분 안에 파악할 수 있다.
`outputs/`는 AI가 생성한 자기소개서·이력서·태그를 보관한다. 손으로 편집하지 않는 레이어.

### `secret/` — PII 전용 (.gitignore)

전화번호 등 절대 공개하지 않을 개인식별정보만 보관. Git에 커밋되지 않는다.

---

## 핵심 설계 철학

**"내 삶을 코드처럼 다룬다"**

1. **버전 관리** — 과거의 나를 덮어쓰지 않고, 변화를 이력으로 남긴다
2. **단일 소스** — 중복 없이 data/ 한 곳에서 관리한다
3. **구조화** — 느낌이 아닌 데이터로 자신을 기술한다
4. **완전 공개** — PII를 제외한 모든 데이터는 공개 (자살 시도·조울증·종교 포함)
5. **파생 분리** — 사실(data/)과 AI 생성 결과(ai/outputs/)를 명확히 구분한다

---

## 주요 프로젝트

### 세종클래스 (2025–현재)
- **URL:** https://sejongclass.kr
- **설명:** 수학·물리·코딩·라이프디자인 강의 플랫폼
- **특징:** 단독 풀스택 개발 (디자인·개발·결제·배포 전 과정)
- **스택:** PostgreSQL · Supabase · TypeScript · React Router · TossPayments · Vercel · CloudFlare · Shadcn UI

### KIP — Knowledge Intelligence Platform (2024)
- **설명:** 문서 권한·검색·해시태그·버전 관리 통합 지식 플랫폼
- **결과:** 한화시스템 BEYOND SW캠프 최종 프로젝트 **1위 (6팀 중)**
- **스택:** Spring Boot · Vue.js · Nuxt.js · MariaDB · AWS · K8s · Terraform · Elasticsearch · Firebase

---

## 데이터 읽는 방법

| 목적 | 추천 진입점 |
|------|-------------|
| 이 사람이 누구인지 빠르게 파악 | `ai/index.yaml` |
| 서사적 맥락으로 이해 | `data/04_story/chapters/*.md` |
| 기술 스킬 확인 | `data/03_skills/technical.yaml` |
| 경력/프로젝트 매칭 | `data/02_experience/` |
| 정체성 · 가치관 · 전환 이력 | `data/01_identity/` |
| 19년 성장 궤적 전체 | `data/timeline/year_reviews.yaml` |
| 독서 목록 (연도별) | `data/05_interests/reading/` |
| 독서 통계 · 성향 분석 | `data/05_interests/reading/stats.yaml` |
| AI 자기소개서/이력서 출력물 | `ai/outputs/` |

---

*Last updated: 2026-03-18 · Schema v1.0*
