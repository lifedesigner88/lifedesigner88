# Hupository — 박세종의 공개 인간 데이터 저장소

> 한 사람의 삶, 목표, 현재 상태를 코드처럼 구조화해 공개하는 저장소.
> 이 페이지는 **사람을 위한 소개 페이지**다.

Hupository는 박세종이라는 한 사람을 더 정확하게 이해하기 위해 만든 공개 데이터 저장소입니다.
이력서 한 장으로는 담기지 않는 정체성, 경력, 목표, 관심사, 현재 상태를 YAML과 Markdown으로 정리해 두었고,
사람은 읽기 쉽게, AI는 추론하기 쉽게 설계했습니다.

이 저장소의 목적은 단순합니다.

- 내가 어떤 사람인지 더 정직하게 설명하기
- 매일의 생각과 장기 목표를 연결하기
- 협업, 채용, 네트워킹에서 더 빠르게 맥락을 공유하기

## 박세종을 빠르게 소개하면

- 1988년생, 교육자에서 개발자로 전직한 1인 창업자입니다.
- `세종클래스`를 직접 기획·개발·운영하고 있습니다.
- 교육, 커뮤니티, 기술을 연결하는 일을 오래 해왔습니다.
- 최근 몇 년은 `AI/개발 역량 고도화`, `서비스 구축`, `장기 목표 정렬`에 집중하고 있습니다.

조금 더 압축하면 이런 사람입니다.

> 교육자로 오래 살았고, 개발자로 다시 시작했고,
> 지금은 사람의 성장과 협업을 돕는 시스템을 직접 만들고 있습니다.

## 왜 이런 저장소를 공개하나

대부분의 자기소개는 결과만 보여줍니다.
하지만 실제 사람은 결과보다도 방향, 맥락, 변화 과정으로 더 잘 이해된다고 생각합니다.

그래서 Hupository는 단순한 포트폴리오가 아니라, 아래를 함께 보여주는 저장소로 만들었습니다.

- 지금 어떤 목표를 향해 가는지
- 왜 그런 선택을 하고 있는지
- 어떤 기술과 경험을 쌓아왔는지
- 어떤 가치관과 관심사 위에서 움직이는지

## 여기서 무엇을 읽을 수 있나

### 1. 정체성

- [data/01_identity/](data/01_identity/)
  가치관, 자기인식, 삶의 방향성을 담고 있습니다.

### 2. 경험과 프로젝트

- [data/02_experience/](data/02_experience/)
  교육, 커뮤니티, 개발 경험을 구조화해 두었습니다.
- [data/02_experience/projects/](data/02_experience/projects/)
  세종클래스, KIP 등 주요 프로젝트를 볼 수 있습니다.

### 3. 기술과 역량

- [data/03_skills/technical.yaml](data/03_skills/technical.yaml)
- [data/03_skills/soft.yaml](data/03_skills/soft.yaml)

### 4. 장기 목표와 현재 상태

- [data/06_goals/lifetime.yaml](data/06_goals/lifetime.yaml)
  평생 사명과 10년 단위 방향입니다.
- [data/06_goals/tree.yaml](data/06_goals/tree.yaml)
  지금 무엇에 집중하는지 더 구체적으로 볼 수 있습니다.
- [data/08_now/snapshot.yaml](data/08_now/snapshot.yaml)
  현재 상태를 가장 빠르게 파악할 수 있는 파일입니다.
- [data/08_now/decisions.yaml](data/08_now/decisions.yaml)
  중요한 방향 전환과 그 이유를 남겨둔 로그입니다.

### 5. 서사와 관심사

- [data/04_story/](data/04_story/)
  삶의 흐름을 서사적으로 이해하고 싶을 때 좋습니다.
- [data/05_interests/](data/05_interests/)
  어떤 주제에 끌리고 무엇을 공부하는지 볼 수 있습니다.

## 어디부터 읽으면 좋을까

읽는 사람마다 궁금한 게 다르니, 세 가지 경로를 추천합니다.

### 1분 코스

- [data/08_now/snapshot.yaml](data/08_now/snapshot.yaml)
- [data/06_goals/lifetime.yaml](data/06_goals/lifetime.yaml)
- [data/profile.yaml](data/profile.yaml)

지금 어떤 사람이고, 무엇을 향해 가는지 가장 빨리 파악할 수 있습니다.

### 5분 코스

- [data/profile.yaml](data/profile.yaml)
- [data/06_goals/tree.yaml](data/06_goals/tree.yaml)
- [data/02_experience/projects/](data/02_experience/projects/)
- [data/03_skills/technical.yaml](data/03_skills/technical.yaml)

협업, 채용, 프로젝트 관점에서 보기 좋은 코스입니다.

### 15분 코스

- [data/04_story/](data/04_story/)
- [data/08_now/decisions.yaml](data/08_now/decisions.yaml)
- [data/05_interests/reading/](data/05_interests/reading/)

이 사람의 생각 방식과 변화의 맥락까지 이해하고 싶다면 이 경로가 좋습니다.

## 이 저장소는 어떻게 작동하나

Hupository는 정적인 소개 페이지가 아니라, 계속 업데이트되는 개인 데이터 시스템입니다.

```text
정체성 / 경험 / 스킬 / 목표 / 현재 상태
                    ↓
             일일 기록과 주간 점검
                    ↓
      더 나은 선택과 더 선명한 자기이해
```

AI는 이 데이터를 바탕으로 생각을 정리하고, 장기 목표와 현재 행동의 정렬을 점검하는 데 쓰입니다.
하지만 이 저장소의 출발점은 어디까지나 사람입니다.
먼저 사람이 읽고 이해할 수 있어야 하고, 그 다음에 AI가 잘 읽을 수 있어야 합니다.

## 공개 원칙

- 개인식별정보와 민감정보는 공개 대상에서 분리합니다.
- 대신 삶의 방향, 실패, 방황, 전환 같은 핵심 맥락은 숨기지 않습니다.
- 좋은 모습만 전시하는 포트폴리오보다, 실제로 이해 가능한 기록을 더 중요하게 생각합니다.

## Hupository 구조를 간단히 보면

```text
hupository/
├── README.md              ← 사람용 소개 페이지
├── data/
│   ├── 01_identity/
│   ├── 02_experience/
│   ├── 03_skills/
│   ├── 04_story/
│   ├── 05_interests/
│   ├── 06_goals/
│   ├── 07_matching/
│   ├── 08_now/
│   └── 09_journal/
└── ai/
    ├── index.yaml
    ├── context/
    ├── prompts/
    └── outputs/
```

더 자세한 구조 규칙은 [data/schema.yaml](data/schema.yaml)에서 볼 수 있습니다.

## 함께 읽어주셔서 감사합니다

이 저장소는 "한 사람을 데이터로 정리하면, 더 정확하게 이해받을 수 있을까?"라는 질문에서 시작했습니다.
채용 담당자, 협업자, 친구, 커뮤니티 운영자, 혹은 우연히 들어온 누군가에게도 이 페이지가 좋은 출발점이 되면 좋겠습니다.

연결하고 싶다면 [data/profile.yaml](data/profile.yaml)이나 GitHub 프로필을 먼저 봐주세요.
