---
session: 2026-W13
period: "2026-03-23 ~ 2026-03-29"
generated_on: "2026-03-23"
based_on:
  prev_session: "hupository/data/09_journal/2020s/2026/03/W12/session.md"
  note: "3/22(일) ~ 3/23(월) 세션 — W13 시작일, 3/25 MVP 데드라인 대응"
---

## 1. 지난 주 숙제 체크

W12 assigned_goals 결과 — W13 종료 후 채움.

| 숙제 | 목표 ID | 결과 | 비고 |
|------|---------|------|------|
| 3/24(화) 은평청년네트워크 일자리창업분과 모임 참석 | G-LIFE | null | |
| 3/25(수) 소마 결과 확인 후 분기 전략 실행 | G-AI-03 | null | |
| PersonaMirror MVP 완료 | G-PM-01 | null | |
| 3/27(금) 클래스101 미팅 + 진행 여부 결정 | G-SEJONG-03 | null | |
| 세종클래스 인생 2026 W12 영상 촬영·업로드 | G-SEJONG-01 | null | |

---

## 2. 장기목표 정렬 진단 ★

### 핵심 방향성 재확인 (3/22 세션)

> **Hupository 데이터 기반 PersonaMirror를 만들어 나가는 것 — 소마·클래스101과 관계없이 평생의 과업.**

### 각 활동의 PersonaMirror 기여 맥락

| 활동 | PersonaMirror 기여 |
|------|-------------------|
| SW마에스트로(소마) | 합격 시 → 팀원·네트워크·지원금·사무실 + 17기 450명 초기 유저 |
| 클래스101 | Hupository 프로젝트 인지도 확산 채널 |
| 은청넷·은평축제·서울시민예산위원 | 인생 컨설팅 기술 스킬 홍보 채널 |
| 세종클래스 인생 2026 | 인생 컨설팅 기록 + 홍보 플랫폼 |

alignment_status: aligned ✅

### PersonaMirror 3개 목표 확정

1. **바이브코딩으로 어디까지 가능한지 테스트** (최상위 목표) — 공부 예정
2. **방향성을 데모 프로젝트로 잠재 팀원에게 어필**
3. **소마 커뮤니티 팀 매칭 기능** = PersonaMirror의 자연스러운 확장

→ 흐름: 바이브코딩으로 만든다 → 데모가 된다 → 팀 매칭으로 확장
→ 소마 커뮤니티 플랫폼 = PersonaMirror 첫 번째 실용 유즈케이스 (별도 프로젝트 아님)

---

## 3. 3/25 14:00 MVP 분기 전략

### 합격 시
- 소마 지원방(800명) 운영자에게 계획 전달 + 합격자 모집
- MVP 링크 즉시 공개
- 합격자 니즈(팀 매칭) 반영한 기능 1순위

### 탈락 시
- 소마 커뮤니티 방향성 제거
- 개인 프로젝트 전환: AI 인생컨설팅 원하는 사람들 모집
- 클래스101 강의 제작 병행

---

## 4. 3/25 14:00 전 MVP 목표

### 반드시 완료

| # | 목표 | 완료 기준 |
|---|------|----------|
| 1 | 박세종 페르소나 데이터 완성 | ✅ 완료 (3/22) |
| 2 | 데모 페이지 완성 | ✅ 완료 (3/21) |
| 3 | GET `/persona/:id` 배포 | 외부 URL로 접근 가능 |
| 4 | POST `/persona/:id/ask` 동작 | 질문 → Claude API 응답 |
| 5 | 합격자 모집 메시지 초안 | 운영자에게 보낼 텍스트 준비 |

### 있으면 좋음

| # | 목표 |
|---|------|
| 6 | 랜딩 1페이지 (3줄 설명) |
| 7 | 탈락 시 개인 프로젝트 전환 메시지 초안 |

### 일정

```
3/23(월) 오전~오후  → 배포 파이프라인 구축 (최우선)
3/23(월) 오후~저녁  → GET /persona/:id 배포 확인
3/24(화) 오전       → POST /ask 동작 확인
3/24(화) 저녁 19:00 → 은평청년네트워크 모임
3/25(수) 오전       → QA + 모집 메시지 완성
3/25(수) 14:00      → 소마 결과 → 즉시 분기 실행
```

---

## 5. 배포 인프라 현황

### 보유 자원
- AWS Lightsail 4GB (Docker 설치 완료, 서비스 2개 운영 중)
- 도메인: huposit.kr
- 레포: https://github.com/lifedesigner88/260312-demo-infra

### 현재 인프라 구조
- **리버스 프록시**: Caddy
- **배포 방식**: GHCR 이미지 pull → docker compose
- **자동화**: GitHub Actions (SSH → compose up)
- **현재 서비스**:
  - `vue-spring.huposit.kr` → :3000
  - `rr7-fullstack.sejongclass.kr` → :8080

### PersonaMirror 배포 계획
- 서브도메인: `persona.huposit.kr` (미확정)
- 추가 작업:
  1. `persona-mirror/compose.yaml` 추가 (rr7-fullstack 패턴 복사)
  2. Caddyfile에 서브도메인 추가
  3. GitHub Actions workflow 추가
  4. PersonaMirror 이미지 GHCR 푸시

### 미확인
- PersonaMirror repo Dockerfile 존재 여부 (미확인)
- 서브도메인 확정 (persona.huposit.kr 예정)

---

## 6. 다음 주 하위목표 (숙제) — 미확정

(세션 진행 중)

---

## 7. 컨설턴트 메모

- 인프라 패턴이 이미 검증되어 있음 (Caddy + GHCR + GitHub Actions). PersonaMirror는 패턴 복사로 빠르게 추가 가능.
- 3/25 14:00 이 분기점. 합격/탈락 두 시나리오 모두 준비하는 게 정신 건강에 좋다.
- 오늘(3/23)이 사실상 유일한 풀타임 개발일. 배포 파이프라인 완성이 최우선.
