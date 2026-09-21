# lg-test-landing

LG 전자 신입 채용 랜딩페이지 프로토타입 (`index.html`, `design_files/`).

## Cross-session agent workflow

This repo defines five persistent subagents in `.claude/agents/` — they are
available in **any** session opened against this repo, not just the one that
created them:

- `competitor-research` — researches competitors / industry UX & AI trends
- `own-company-research` — researches LG Electronics' (자사) own AI/UX initiatives
- `verifier` — fact-checks and reviews research, reports, or implementation work
- `interview` — after research/verification, talks with the user to surface
  gaps and turn them into concrete follow-up research/verification items
- `report-writer` — synthesizes research into a polished report (incl.
  competitor-vs-own-company gap analysis)

They hand off state through the filesystem, not chat memory, so work
survives across sessions:

```
research/
  findings/
    competitor/     ← competitor-research writes here
    own-company/    ← own-company-research writes here
  verification/      ← verifier writes here
  interview/         ← interview writes here (follow-ups for the two above)
  reports/           ← report-writer writes here (reads both findings/ subfolders + verification)
  playbooks/          ← organizational/role-evolution reference material, owned by the
                         `org-role-evolution-research` skill — NOT AI-specific and not tied to a
                         competitor or LG전자 itself (e.g. new job roles emerging industry-wide, how
                         another company structures its org). No dedicated agent writes here
                         autonomously; file things here by hand per that skill's brief.
```

Typical loop: competitor-research + own-company-research → verifier →
interview (surfaces gaps) → back to the research agents for the follow-ups
→ report-writer once it's solid.

Before starting new research, verification, or an interview pass, check
these directories first — a prior session may have already done the work.

## Related skills

- `ai-ux-trend-research` — briefs `competitor-research` for UX/AI product-trend research
  (business/market competitiveness lens)
- `ai-agent-usage-research` — briefs `competitor-research` for how practitioners actually use AI agents
- `ux-ai-capability-research` — briefs `competitor-research`/`own-company-research` for how orgs use
  AI to strengthen their *own* UX/design/research team's capability (internal workflow lens, not
  product/market strategy). Findings under this lens should include both a "사업적 시사점" and a
  "내부 역량 강화 시사점" section so `report-writer` can cover both angles.
- `org-role-evolution-research` — a third lens: how organizations and job roles themselves should
  evolve (new roles emerging, org structure tradeoffs, headcount/hiring strategy shifts) — directly
  relevant to 2027 사업계획 organizational planning, not just product or AI-tooling strategy. Owns
  `research/playbooks/`; findings should carry a "조직·인력 구조 시사점" section that `report-writer`
  keeps as its own report section, separate from the business and AI-capability lenses.

## 인용 규칙 — 정확한 날짜 표기

모든 리서치/보고서 산출물에서 "출시/상용화/발표/공개" 같은 시점 claim은 **정확한 연도+날짜
(YYYY-MM-DD, 일자가 불명확하면 최소 YYYY-MM)로 기재한다.** "2026년 봄"·"2026년 상반기" 같은
계절/반기 표현은 정확한 날짜를 찾을 수 있는데도 쓰지 않는다 — 먼저 정확한 날짜를 검색하고, 정말
못 찾을 때만 `(정확한 날짜 미확인 — 2026년 봄 추정)`처럼 추정임을 명시한다. 이 규칙은
`competitor-research`/`own-company-research`/`verifier`/`report-writer` 네 에이전트 정의 파일에도
동일하게 반영되어 있다.

## 인용 규칙 — "현재 경쟁 상황" 서술은 최신 연도 자료만 (2026-only, 2026-09-21 사용자 지시)

경쟁사·업계 동향을 "지금 이렇다"는 식으로 서술할 때는 **그 서술 시점 기준 당해 연도(현재는
2026년)에 실제 발표/적용된 자료만 본문에 싣는다.** 전년도 이전 자료는(맥락 설명 목적이라도)
본문에서 제외한다 — 예외는 없다. 대체할 최신 연도 자료가 없으면 그 항목은 "N년 확인 자료
없음"으로 명시하고 조용히 빼지 않는다(왜 빠졌는지 남겨야 다음 세션이 재조사 여부를 판단할 수
있음). 다만 이 원칙은 "경쟁사가 지금 어디까지 왔는가"를 보여주는 헤드라인 통계·비교 문장에
적용되는 것이고, 인터뷰/검증 로그(`research/interview/`, `research/verification/`) 같은
과거 세션의 감사 기록 자체를 소급 수정하라는 뜻은 아니다 — 그 파일들은 "그 시점에 무엇을
검토했는지"의 기록으로 그대로 둔다.

## Imported prior work

`research/reports/2026-09-20-*.md` were imported from the `3개 경쟁사 조사
서브 에이전트` session's branch (`claude/funny-tesla-40dplh`) — real
competitor/own-company/AI-agent-trend reports, not yet passed through this
repo's `verifier`/`interview` loop.
