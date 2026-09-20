---
name: ai-ux-trend-research
description: 경쟁사의 UX·AI 제품 동향을 조사할 때 쓰는 스킬. 스마트홈 가전사(삼성/애플/구글/중국 가전 등)뿐 아니라 Anthropic(Claude), Google(Gemini), OpenAI 같은 AI 파운데이션 모델 기업들의 UX·에이전트 기능 동향까지 조사 범위에 포함시킨다. "UX·AI 트렌드 조사해줘", "경쟁사 AI 동향 조사", "엔트로픽/제미나이/클로드 동향도 봐줘" 같은 요청에 사용한다.
---

# AI/UX 경쟁 동향 리서치 스킬

이 스킬은 `competitor-research` → `verifier` → `interview` → `report-writer` 4단계 상시 에이전트
파이프라인을 "UX·AI 제품 동향" 조사에 맞게 스코핑하는 브리프 템플릿이다. 매번 새로 브리프를 쓰지
않고 아래 틀에 조사 대상만 채워서 파이프라인을 돌린다.

> [가져온 스킬] 원래 `3개 경쟁사 조사 서브 에이전트` 세션(브랜치 `claude/funny-tesla-40dplh`)에서
> `competitor-researcher → research-verifier → report-writer` 3단계 파이프라인용으로 작성됐던 것을,
> 이 저장소의 상시 에이전트 이름(`competitor-research`/`verifier`/`interview`/`report-writer`)에
> 맞춰 갱신한 버전이다. 조사 범위·원칙 등 본문 내용은 원본과 동일하다.

## 언제 쓰는가

- 스마트홈/가전/디바이스 UX 경쟁사 조사에 "AI 어시스턴트·에이전트 기능"이 핵심 축일 때
- AI 파운데이션 모델 기업(Anthropic, Google, OpenAI 등)의 제품 UX·에이전트 동향 자체를 조사할 때
- 위 두 축을 같이 봐야 할 때 (예: "가전사들이 어떤 AI 모델/파트너십을 쓰는지" + "그 모델을 만드는 회사들의 UX 방향")

## 조사 범위 (기본 템플릿)

브리프를 쓸 때 아래 3개 트랙을 기본으로 포함하고, 요청에 따라 트랙을 추가/축소한다.

### 트랙 1 — 디바이스/가전 UX·AI 통합 동향
대상 예: 삼성전자, 애플, 구글(디바이스), 중국 가전사 등. 조사 항목:
- 어떤 AI 모델(자체 개발 vs 외부 파트너십)을 제품에 탑재하는지
- 어시스턴트가 명령형(command)인지 에이전틱(agentic, 스스로 계획·실행)인지
- 화면/음성/자동화 등 UX 표현 방식
- 최신(가능한 한 최근 12개월) 발표·출시·파트너십

### 트랙 2 — AI 파운데이션 모델 기업의 UX·에이전트 제품 동향
대상: **Anthropic(Claude, Claude Code, Claude Agent SDK/API)**, **Google(Gemini, Gemini for Home/Workspace 등)**,
**OpenAI(ChatGPT, Agents/Operator류 제품)** — 요청에 따라 추가(예: Meta, xAI 등). 조사 항목:
- 각 사가 "에이전트"를 어떻게 제품화하는지 (자율성 수준, 도구 사용, 멀티스텝 실행)
- 컨슈머 UX 방향(대화형 vs 통합형 vs 임베디드) 변화
- 개발자/엔터프라이즈 대상 에이전트 도구(SDK, API, MCP 등) 동향
- claude.com/anthropic.com, blog.google, openai.com 등 공식 발표를 1차 출처로 우선 사용

### 트랙 3 (선택) — 산업 전반의 UX/AI 트렌드 시그널
- 업계 컨퍼런스(CES, IFA, Google I/O, Anthropic/OpenAI 개발자 행사 등) 발표
- 애널리스트/업계 매체 보도 (단, 루머는 반드시 "(미확정)" 표기)

## 파이프라인 실행 방법

1. **브리프 작성**: 위 템플릿에 실제 조사 대상(회사명)과 기간(예: 최근 12개월)을 채워 하나의 리서치
   브리프 텍스트를 만든다.
2. **`competitor-research` 에이전트**에 브리프를 그대로 전달해 리서치를 실행한다 (출처 URL 필수,
   불확실한 정보는 "unverified"로 표기하도록 지시 — 에이전트 자체 지침에 이미 포함되어 있음). 결과는
   `research/findings/`에 저장된다.
3. 결과를 **`verifier` 에이전트**에 전달해 각 claim을 재검색·교차검증한다 (`research/verification/`에 저장).
4. **`interview` 에이전트**로 사용자와 함께 빈틈·추가 조사 필요 항목을 짚고, 후속 조치를
   `research/interview/`에 남긴다 — 필요하면 2~3단계를 반복한다.
5. 검증된 결과를 **`report-writer` 에이전트**에 전달해 최종 보고서(`research/reports/`, 필요 시 pptx)로 정리한다.
   - 보고서 구조는 트랙별 섹션(디바이스 UX / AI 파운데이션 모델 기업 / 산업 시그널) +
     Executive Summary + LG전자 시사점 + 리서치 한계 순으로 구성할 것을 권장한다.

## 원칙

- Anthropic/Claude 관련 정보는 특히 최신성이 중요하다 — 모델/제품 이름과 출시 시점을 반드시
  공식 출처(anthropic.com, claude.com)로 재확인한다.
- "에이전틱(agentic)"이라는 표현을 남발하지 말고, 실제로 자율적 다단계 실행이 확인된 경우에만
  그렇게 표기한다 (단순 챗봇 UX 개선과 구분).
- 이 스킬은 조사 스코프 정의용이다 — 실제 웹 리서치·검증·인터뷰·보고서 작성은 항상 4단계 상시
  에이전트 파이프라인(`competitor-research` → `verifier` → `interview` → `report-writer`)에 위임한다.
