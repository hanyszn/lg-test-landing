# lg-test-landing

LG 전자 신입 채용 랜딩페이지 프로토타입 (`index.html`, `design_files/`).

## Cross-session agent workflow

This repo defines three persistent subagents in `.claude/agents/` — they are
available in **any** session opened against this repo, not just the one that
created them:

- `competitor-research` — researches competitors / industry UX & AI trends
- `verifier` — fact-checks and reviews research, reports, or implementation work
- `report-writer` — synthesizes research into a polished report

They hand off state through the filesystem, not chat memory, so work
survives across sessions:

```
research/
  findings/       ← competitor-research writes here
  verification/   ← verifier writes here
  reports/        ← report-writer writes here (reads the two above)
```

Before starting new research or a new report, check these directories first
— a prior session may have already done the work.
