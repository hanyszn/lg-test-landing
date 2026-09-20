# lg-test-landing

LG 전자 신입 채용 랜딩페이지 프로토타입 (`index.html`, `design_files/`).

## Cross-session agent workflow

This repo defines four persistent subagents in `.claude/agents/` — they are
available in **any** session opened against this repo, not just the one that
created them:

- `competitor-research` — researches competitors / industry UX & AI trends
- `verifier` — fact-checks and reviews research, reports, or implementation work
- `interview` — after research/verification, talks with the user to surface
  gaps and turn them into concrete follow-up research/verification items
- `report-writer` — synthesizes research into a polished report

They hand off state through the filesystem, not chat memory, so work
survives across sessions:

```
research/
  findings/       ← competitor-research writes here
  verification/   ← verifier writes here
  interview/      ← interview writes here (follow-ups for the two above)
  reports/        ← report-writer writes here (reads findings + verification)
```

Typical loop: competitor-research → verifier → interview (surfaces gaps) →
back to competitor-research/verifier for the follow-ups → report-writer once
it's solid.

Before starting new research, verification, or an interview pass, check
these directories first — a prior session may have already done the work.
