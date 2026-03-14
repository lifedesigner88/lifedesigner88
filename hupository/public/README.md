## 폴더 구조

```
hupository/
├── README.md              ← 지금 이 파일 (서비스 명세)
├── schema.yaml            ← hupository 데이터 스키마 정의
├── index.yaml             ← AI 진입점: 이 사람을 1분 안에 이해
│
├── 01_identity/           ← 누구인가 (사실 레이어)
├── 02_experience/         ← 무엇을 해왔는가
├── 03_skills/             ← 무엇을 할 수 있는가
├── 04_story/              ← 어떤 서사를 가졌는가 (AI 컨텍스트)
├── 05_interests/          ← 무엇을 좋아하는가
├── 06_goals/              ← 어디로 가고 있는가
├── 07_matching/           ← 어떤 사람과 연결되고 싶은가 (매칭 레이어)
└── 08_ai_layer/           ← AI 생성 프롬프트 및 결과물
```

## 데이터 레이어 설계 원칙

```
사실(Fact)     → 01~06  : YAML, 신뢰도 표기, 직접 수정 가능
매칭(Match)    → 07     : 벡터 + 시그널, SNS 매칭 엔진에서 소비
AI 생성(Gen)   → 08     : 프롬프트 + 결과물, 언제든 재생성 가능
```

- **YAML = 구조화된 사실** → 파싱, 검색, 매칭에 최적
- **Markdown = 서사** → LLM 컨텍스트, 자기소개 생성에 최적
- 신뢰도: `high` / `medium` / `low` 로 표기
- 공개범위: `public` / `network` / `private` / `secret`



