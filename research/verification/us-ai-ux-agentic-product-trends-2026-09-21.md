# Verification — 미국 AI/UX 선도기업 최신 에이전트 도입 동향
Date: 2026-09-21
Target: `research/findings/competitor/us-ai-ux-agentic-product-trends-2026-09-21.md`

Scope note: per task brief, effort concentrated on the 7 prioritized items the original
researcher self-flagged in "Open questions / gaps." Re-confirmed the same EGRESS_BLOCKED
constraint independently for `openai.com`, `claude.com`, `blog.google`, `stateofaidesign.com`,
`gartner.com`, `releasebot.io`, `dev.to`, `digitalapplied.com`, `harvey.ai` (no bypass attempted).
Notably, Anthropic's own docs/product subdomains — `platform.claude.com`, `code.claude.com` — and
`github.com/anthropics/*` were **not** blocked, unlike the marketing/blog domain `claude.com`, and
were used to get genuine primary-source confirmation for two of the seven priority items.

## Result: PASS WITH NOTES

## Priority items checked

1. **EGRESS_BLOCKED domains (openai.com/claude.com/blog.google/stateofaidesign.com) — CONFIRMED, unchanged.**
   Independently re-attempted WebFetch to all four; all returned EGRESS_BLOCKED, matching the
   researcher's own finding exactly. Findings file updated with a same-result confirmation note.
   New information: `platform.claude.com` and `code.claude.com` (official Anthropic docs, distinct
   subdomains from `claude.com`) and `github.com/anthropics/*` were reachable and used to resolve
   items 2 and 3 below with actual primary-source text, not just aggregator snippets.

2. **Anthropic 2026-09 update (auto permission policies, ant CLI sessions connect, commerce agent
   blueprint) — RESOLVED, corrected in findings from "single aggregator, low confidence" to
   primary-source confirmed.**
   - Fetched `platform.claude.com/docs/en/managed-agents/permission-policies` directly (via a
     GitHub mirror) and `platform.claude.com/docs/en/cli-sdks-libraries/cli/sessions-connect`
     directly (WebFetch succeeded, not blocked) — both are official Anthropic docs, not
     releasebot.io. Confirmed: `auto` permission policy is a real 3-way evaluator (execute/deny/
     ask), explicitly documented as "not a human checkpoint" (approved calls run before review);
     `ant beta:sessions connect` is real, requires CLI v1.32.0+, beta-labeled.
   - Fetched `github.com/anthropics/commerce-agents` directly (Apache-2.0, real repo, shopping +
     merchant agent reference implementations, guardrails that stage merchant writes for human
     approval, no live checkout/payment execution) — this is Anthropic's own GitHub org, a primary
     source, not an aggregator.
   - Cross-corroborated by multiple independent outlets (InfoWorld, Techzine Global, AlphaSignal,
     byteiota, QATechTools, PYMNTS, qz.com) for dates/details.
   - Findings file corrected: the "단일 애그리게이터 출처, 신뢰도 낮음" framing is no longer
     accurate and was updated in three places (Track 1 bullet, Open questions, Per-company notes).

3. **"/goal" (Claude Code v2.1.139) vs "Outcomes" (Code with Claude) — RESOLVED as genuinely distinct features.**
   - Fetched `code.claude.com/docs/en/goal` directly (official Anthropic docs, primary source).
   - Confirmed: `/goal` is a **Claude Code (CLI tool)** session-scoped slash command (introduced
     ~v2.1.139, ~May 2026 per multiple secondary sources — the doc itself doesn't state a version
     intro date) built on a "Stop hook" mechanism, evaluated each turn by a small fast model
     (default Haiku).
   - `Outcomes` is a **Claude Managed Agents (cloud platform)** feature: a rubric authored by the
     developer, graded by an independent grading model, triggering rework loops on failure.
   - These are different products (Claude Code CLI vs. Managed Agents platform) that share a
     conceptual pattern (a judge model decides "done"), not the same feature under two names.
   - Could not locate the specific SitePoint article the original researcher cited, but the
     underlying fact (the command exists, what it does) is now confirmed via Anthropic's own docs,
     so the "single unverified source" concern is resolved even though that specific article
     wasn't independently found.

4. **OpenAI "Sponsored Agents" — experimental-stage labeling confirmed accurate; added detail found via re-search.**
   Multiple independent outlets (Unite.AI, PYMNTS, Search Engine Roundtable, qz.com, Remote Work
   Europe) consistently describe: US-only test with named advertisers (Newegg, Best Buy, Lowe's,
   VistaPrint), a clearly labeled conversation UX distinct from ChatGPT's own answers, and an
   international expansion date of 2026-09-23. This is materially more than the original "정식
   출시 여부, 사용자 UX 미확인" — the UX and rollout plan are now reasonably well described by
   secondary sources (still not an openai.com primary fetch, since that domain is blocked). The
   "(미확정/실험 단계)" label itself remains accurate and was kept. Findings updated with the new
   detail, tagged as an addition rather than a correction of an error.

5. **MCP adoption statistics — mixed result; one figure flagged as a likely error, others triangulated against a primary source for the first time.**
   Fetched `blog.modelcontextprotocol.io/posts/2025-12-09-mcp-joins-agentic-ai-foundation/`
   directly (this is the primary AAIF/MCP announcement, already cited by the researcher but not
   previously fetched). Findings:
   - **97 million monthly SDK downloads**: matches the primary source's exact wording ("over 97
     million monthly SDK downloads") — but that wording is from the **2025-12-09** post, not
     "2026년 3월" as the finding states. The number being identical three months later, with no
     stated update, suggests the "2026-03" framing is likely a secondary site recycling the
     Dec-2025 figure rather than a fresh March measurement. Flagged, not asserted as wrong per se.
   - **5,800+ MCP servers — likely an error.** The same Dec-2025 primary source states "10,000+
     active servers," and the official MCP Registry API counted 9,652 server records as of
     2026-05-24 (per a digitalapplied.com update found via search) — both larger than, and earlier
     than, the "5,800+ as of March 2026" the finding cites. A later date showing a smaller number
     than an earlier primary-source figure is internally inconsistent. Corrected in the findings
     file with an explicit inline flag and a recommendation to use the primary-source figures
     (10,000+ Dec-2025, or 9,652 May-2026 Registry API) instead.
   - **28% of Fortune 500 companies — confidence downgraded further.** Independent MCP-adoption
     critique pieces found via search explicitly call this figure out as circulating "without a
     named, checkable source." Could not find a primary source. Left as-is in the findings body
     (not asserted wrong) but flagged more strongly as unreliable for reuse in a business-plan doc.
   - **41% of surveyed software orgs in limited/broad production — confidence upgraded.** A revised
     version of the digitalapplied.com article names Stacklok's "2026 Software Report" as the
     source, and states it explicitly replaced an earlier, unsourced "78%" claim. This is now a
     named source, even though Stacklok's original report was not independently fetched.
   - AAIF founding-member/platinum-member claim (Anthropic/Block/OpenAI co-founders; AWS/Google/
     Microsoft/Cloudflare/Bloomberg support) matches the primary source's wording closely enough
     to count as confirmed, though the primary source's exact phrase was "with support from"
     rather than explicitly using the word "platinum member" — minor wording gap, not flagged as
     an error in the file since "플래티넘 멤버" terminology is standard Linux Foundation usage for
     that tier and is plausible, just not verbatim-confirmed.

6. **Gartner's two press releases (40% app adoption vs. 40%+ project cancellation) — CONFIRMED, dates and quotes exact.**
   Re-searched and located the exact press-release wording for both:
   - 2025-08-26 (updated 2025-09-05): "Forty percent of enterprise applications will be integrated
     with task-specific AI agents by the end of 2026, up from less than 5% today."
   - 2025-06-25: "Over 40% of agentic AI projects will be canceled by the end of 2027, due to
     escalating costs, unclear business value or inadequate risk controls" (Gartner analyst
     Anushree Verma).
   Both dates, both percentages, and the framing in the findings file are accurate. The phrase
   "같은 시기" (same period) is slightly loose — the two releases are ~2 months apart — but not a
   substantive error since both are from 2025. Tagged as confirmed in the file; no content
   correction needed.

7. **Harvey "~6x task completion" — CONFIRMED as Harvey's self-reported figure relayed via Anthropic's own blog, not third-party audited.**
   Multiple independent write-ups (FindSkill.ai, a Sean Kim blog post, etc.) consistently describe
   this as Harvey's own "internal testing" result, cited by Anthropic as a customer case study on
   `claude.com/blog` (which remains EGRESS_BLOCKED for direct fetch). No source found describing
   independent/third-party audit of the 6x figure. The original finding's existing caveat ("Harvey
   자체 수치, 제3자 검증 여부 불명") was already accurate; findings file updated to tag this as
   confirmed rather than leave it as an open uncertainty, and notes the "불명" could arguably be
   tightened to "not third-party verified" since no search turned up any such verification.

## Other checks

- Numbers/dates within the document remain internally consistent after edits — no new
  contradictions introduced between the Key findings, Per-company notes, and Open questions
  sections; the stale "출처 신뢰도 낮음" line in Per-company notes → Anthropic was also updated to
  match the corrected Track 1 text (it had been missed in the original open-questions-only framing
  and would otherwise have contradicted the corrected bullet above it).
- Did not attempt to independently re-verify claims outside the 7 prioritized items (ChatGPT Work,
  Workspace Agents, Gemini Spark/Daily Brief/Enterprise Agent Platform, Notion/Linear/Perplexity/
  Figma/Airbnb sections, Smashing Magazine's 4 design principles) — these were not flagged by the
  researcher as priority gaps and were out of scope per the task brief.

## Issues found

- [medium] MCP "5,800+ servers" figure — Track 3 MCP bullet — contradicted by the primary AAIF
  announcement (10,000+ active servers, 2025-12-09) and the official MCP Registry API (9,652
  records, 2026-05-24), both larger than and predating the cited "5,800+ as of March 2026." Likely
  an error or stale/miscounted figure from a secondary aggregator. Corrected inline in the findings
  file with a recommendation to use the primary-source numbers instead if this is reused in the
  2027 business plan.
- [low] MCP "9,700만 건, 2026년 3월 기준" — the number itself matches the primary source exactly,
  but that primary source is dated 2025-12, not 2026-03; the "as of March 2026" framing looks like
  it may be a secondary site recycling the December figure rather than a fresh data point. Flagged
  inline; not asserted as definitively wrong since download counts could plausibly have plateaued.
- [low] MCP "포춘 500대 기업 28%" — independent critique pieces explicitly call this an unsourced/
  uncheckable figure circulating among secondary MCP-adoption articles. Recommend not quoting this
  specific percentage directly in a 2027 business-plan document without a caveat.
- [info, resolved] Anthropic 2026-09 update (auto permission policies / ant CLI sessions connect /
  commerce agent blueprint) — previously flagged by the researcher as single-aggregator/low-
  confidence; now confirmed via Anthropic's own docs (`platform.claude.com`) and GitHub
  (`anthropics/commerce-agents`), corrected in three places in the findings file (Track 1, Open
  questions, Per-company notes).
- [info, resolved] "/goal" vs "Outcomes" — previously flagged as unclear whether same feature under
  different names; confirmed via `code.claude.com/docs/en/goal` (primary source) that these are two
  distinct products (Claude Code CLI command vs. Claude Managed Agents platform feature) that share
  a conceptual "judge model decides completion" pattern.
- [info] OpenAI Sponsored Agents — UX and international-rollout details were addable beyond what
  the original researcher found; the "(미확정/실험 단계)" characterization itself was already
  accurate and is unchanged.

## Unverifiable claims

- The exact original text of `openai.com`, `claude.com` (blog), `blog.google`, and
  `stateofaidesign.com` posts remain unverifiable in this session — same EGRESS_BLOCKED constraint
  as the original researcher, re-confirmed independently, no bypass attempted.
- Stacklok's "2026 Software Report" (source of the 41% MCP production-adoption figure) — found only
  via a secondary citation (digitalapplied.com's revised article); the Stacklok report itself was
  not fetched.
- The specific SitePoint article on Claude Code's `/goal` command that the original researcher
  cited — not located in this session's searches; the underlying fact it reported (the `/goal`
  command's existence and behavior) was independently confirmed via Anthropic's own docs instead.
- Anthropic's own blog post ("New in Claude Managed Agents") describing Dreaming/Outcomes/
  multi-agent orchestration/webhooks and the Harvey 6x case study — `claude.com/blog` itself remains
  EGRESS_BLOCKED; all corroboration is via secondary write-ups that describe or quote it.
- Exact date Anthropic added "auto" permission policies (multiple secondary sources gave slightly
  different September 2026 dates — e.g. Sept 10 vs Sept 14 — and the primary docs page itself
  carries no publish date) — not resolved to a single exact date.
