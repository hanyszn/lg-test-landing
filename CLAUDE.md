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
```

Typical loop: competitor-research + own-company-research → verifier →
interview (surfaces gaps) → back to the research agents for the follow-ups
→ report-writer once it's solid.

Before starting new research, verification, or an interview pass, check
these directories first — a prior session may have already done the work.

## Related skills

- `ai-ux-trend-research` — briefs `competitor-research` for UX/AI product-trend research
- `ai-agent-usage-research` — briefs `competitor-research` for how practitioners actually use AI agents

## Imported prior work

`research/reports/2026-09-20-*.md` were imported from the `3개 경쟁사 조사
서브 에이전트` session's branch (`claude/funny-tesla-40dplh`) — real
competitor/own-company/AI-agent-trend reports, not yet passed through this
repo's `verifier`/`interview` loop.
