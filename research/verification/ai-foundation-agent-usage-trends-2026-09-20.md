# Verification — AI 파운데이션 모델·에이전트 실사용 동향
Date: 2026-09-20
Target: `research/reports/2026-09-20-ai-foundation-agent-usage-trends.md`

Scope note: per interview log `research/interview/2027-business-plan-report-verification-priorities-2026-09-20.md`,
effort concentrated on the three flagged quantitative claims (METR RCT, Gartner forecast, Fortune 500 MCP
adoption 28%). Most primary domains (metr.org, gartner.com, blog.modelcontextprotocol.io, etc.) were blocked
by the sandbox's egress proxy for direct WebFetch during this session; verification relies on WebSearch
snippet triangulation across independent outlets, consistent with the report's own disclosed limitation.

## Result: PASS WITH NOTES

## Priority claims checked

1. **METR RCT (felt ~20% faster, actually ~19% slower) — PASS, accurately represented.**
   - Confirmed via METR's own blog (`metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study`),
     METR's official X/Twitter account, arXiv preprint (2507.09089), and independent write-ups (ScienceBlog,
     ActuIA, Let's Data Science, Thrumos). Study design matches the report: 16 experienced open-source
     developers, 246 real tasks in their own repositories, randomly assigned AI-allowed vs. AI-disallowed.
     Result: developers were actually ~19% slower with AI tools, but believed afterward they had been ~20%
     faster (some sources note they expected a 24% speedup beforehand and still believed a 20% speedup
     afterward, despite the measured slowdown). Code quality was reportedly unchanged. This is a real, correctly
     quoted, and appropriately caveated finding (early-2025 models; not necessarily generalizable to junior
     devs, greenfield projects, or later-generation tools — the report doesn't overclaim beyond this).
   - The report additionally correctly notes METR is running a second-wave study (57 developers, 143 repos,
     800+ tasks) with preliminary, non-final results — this matches METR's `2026-02-24-uplift-update` blog post
     title/content found in search results.

2. **Gartner forecast (40% of enterprise apps integrate task-specific AI agents by 2026, up from <5% in 2025) —
   PASS, confirmed exact figures and date.**
   - Confirmed via Gartner's own newsroom press release, dated exactly 2025-08-26 as the report states
     (`gartner.com/en/newsroom/press-releases/2025-08-26-gartner-predicts-40-percent-of-enterprise-apps-will-feature-task-specific-ai-agents-by-2026-up-from-less-than-5-percent-in-2025`),
     corroborated by Yahoo Finance, CXO Insight Middle East, DevOpsDigest, and others repeating the same
     headline figures verbatim. Report's characterization as a "forecast, not yet confirmed" outcome is
     appropriate framing to carry into 2027 planning.

3. **Fortune 500 MCP adoption 28% — CONFIDENCE SHOULD BE DOWNGRADED, not just "medium."**
   - The report already flags this as "medium confidence, estimate." Our research found this number is
     **more fragile than "medium confidence" suggests**:
     - It is repeated across many 2026 blog/content-marketing sites (DEV Community, Commerce Pundit,
       Synvestable, andrew.ooo, Practical DevSecOps) but these are secondary/tertiary sources, not primary
       research.
     - The timeframes attached to the "28%" figure are **inconsistent across sources**: one source frames it
       as "Q1 2025 ... up from 12% the prior quarter" (implausible — MCP was only announced Nov 2024 and had
       negligible enterprise production deployment by Q1 2025), another as "as of July 2026," another as
       "early 2026," another simply "18 months" from launch. These are not compatible readings of the same
       underlying data point, which is a classic signature of a statistic being passed around/re-dated by
       content-mill sites without checking the original source.
     - We did find one named originating attribution: **Truto** (an API/integration vendor), per a Practical
       DevSecOps article dated 2026-06-26, which describes it as a "vendor/analyst estimate ... treated with
       caution." Truto is a commercial vendor with a product interest in MCP adoption looking high, not an
       independent research/survey firm — this materially weakens the figure's reliability versus what
       "medium confidence" implies.
   - **Recommendation**: downgrade this figure's confidence framing from "medium" to "low / unverified vendor
     estimate," explicitly name Truto as the likely originating source (with the caveat that even that
     attribution is via a secondary citation, not Truto's own page, which was not independently fetched due to
     sandbox restrictions), and avoid using the specific "28%" number in any 2027 business-plan materials
     without an independent, methodologically transparent source.
   - By contrast, the report's other MCP stats — 9,652 registry server records / 28,959 server-version
     records as of 2026-05-24, and 97M monthly SDK downloads as of 2026-03-25 — are more consistent across
     independent sources for the download figure (multiple 2026 articles converge on "97 million monthly
     downloads by March 2026" with a plausible growth trajectory from ~2M at Nov 2024 launch), though we could
     not independently confirm the exact registry counts (9,652 / 28,959) via WebFetch to the official registry
     due to sandbox egress restrictions. These are lower-priority per the interview log and were only
     spot-checked.

## Other spot checks (secondary, time-permitting)

- Cognition Devin pricing ($20/mo + $2.25/Agent Compute Unit, ~15 min/ACU): confirmed via VentureBeat, eesel AI,
  and multiple 2026 pricing-guide sites. Matches report exactly.
- Google "Works with Google Home" Gemini rollout to 800M+ devices from 2025-10-01: confirmed (see companion
  competitor-research verification file for detail); consistent with this report's cross-references to the
  same event.
- No internal contradictions found between Executive Summary bullets and body sections for the three priority
  items.

## Issues found

- [medium] Fortune 500 MCP 28% figure — where: "Anthropic(Claude) 동향 > 리서치·생태계" and "리서치 한계" — sourcing
  is thinner than "medium confidence" implies (vendor estimate, inconsistent timeframes across citing sites);
  recommend downgrading confidence label and naming the likely source (Truto) with appropriate caveats before
  this is used in 2027 planning.
- [info] Report's "출처" section again lists source types, not URLs, consistent with the competitor report's
  same limitation — recommend backfilling actual URLs before external circulation.

## Unverifiable claims

- Exact MCP registry counts (9,652 server records / 28,959 server-version records, as of 2026-05-24) — could
  not fetch `registry.modelcontextprotocol.io` directly (blocked); only indirectly corroborated via a 2026
  paper's rough figure of "10,000+ active MCP servers," which is roughly consistent but not an exact match.
- Truto's original claim/methodology for the 28% Fortune 500 figure — could not fetch Truto's own site;
  identified only via a secondary citation (Practical DevSecOps, 2026-06-26).
- 2026-07-02 Zuckerberg Meta townhall remark on AI agent development pace — report itself already flags that
  the original English-language source could not be traced; not independently re-verified here (not on
  priority list).
