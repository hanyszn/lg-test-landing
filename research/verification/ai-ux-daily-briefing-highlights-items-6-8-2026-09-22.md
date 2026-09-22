# Verification — AI UX Daily Briefing Highlights, items 6–8
Date: 2026-09-22
Target: `research/findings/competitor/ai-ux-daily-briefing-highlights-2026-09-21.md`,
items 6) 통합 UX / 맥락 이전성 (Context Portability), 7) App Intents / AppFunctions,
8) 조합형 디자인 시스템 (Compositional Design System) — items 1–5 in this file were
verified in earlier sessions and are out of scope here.

## Result: PASS WITH NOTES

Corrections were applied directly to the findings file in place, tagged
`[2026-09-22 verifier 정정]` (correction) or `[2026-09-22 verifier 확인]` (confirmation).
One factual date error was found and fixed (item 7). One date/citation gap was resolved
by finding the actual primary source (item 8). Item 6's user-made correction was
independently confirmed as accurate.

## Per-item findings

### Item 6 — Context Portability / Workday statistics (PASS, no errors found)

This item contains the user's own in-session correction to a conflated "40%" statistic.
I independently re-searched (WebSearch; direct WebFetch to workday.com/newsroom.workday.com
was blocked by this session's network egress policy — see "Unverifiable claims" below) and
confirmed all three sub-claims the task asked me to check:

- **(a) 2026-01-14 press release ("Companies Are Leaving AI Gains on the Table"):**
  Confirmed real, dated 2026-01-14, from Workday Newsroom. Multiple independent sources
  (search-index snippets of newsroom.workday.com/investor.workday.com/PR Newswire,
  plus re-publications on Morningstar, Yahoo Finance, barchart.com, UC Today, ERP Today,
  newkerala.com) consistently quote the figure as "nearly 40% of AI time savings lost to
  rework" and explicitly frame "rework" as fixing errors, rewriting content, and verifying/
  double-checking outputs — i.e., an AI-output-quality/trust issue, not cross-tool
  copy-pasting. The finding file's 정정 A is accurate.
- **(b) "Copy/Paste Economy" report + 2026-05-14 UK release:** Confirmed. Workday's own
  page (workday.com/en-us/perspectives/ai/copy-paste-economy-ai-productivity-tax.html,
  found via search index) and multiple secondary sources (UC Today, ComputerWeekly, Growee)
  consistently state 82% of employees (surveyed: 6,100 HR/Finance/IT/Ops professionals)
  spend significant time moving data between tools/reconciling conflicting results, and
  "1 in 5" employees (IT professionals "1 in 4") lose 7+ hours/week to this. The 2026-05-14
  Workday Newsroom UK-specific follow-up ("UK Employees Spend Nearly a Full Work Day Each
  Week Managing Disconnected AI Tools") was independently confirmed to exist at that exact
  date, based on a separate UK-only survey (The Harris Poll on behalf of Workday, 2,400 UK
  professionals) — a genuinely distinct sample from the global Copy/Paste Economy survey.
  The finding file's characterization ("같은 논지를 별도 수치로 재확인") is accurate — it does
  not claim the UK figure is identical to the global 1-in-5/1-in-4 figure, just thematically
  consistent. 정정 B is accurate.
- **(c) Are these genuinely two distinct stats, not a new conflation error?** Yes — confirmed
  independently. 정정 A (rework/quality, 2026-01-14) and 정정 B (cross-tool context transfer,
  Copy/Paste Economy report + 2026-05-14 UK release) are two separate Workday research
  efforts with different survey populations, different report titles, and different
  publication dates. The user's in-session fix did not introduce a new error.

Minor citation-quality fix applied: the file previously cited the generic homepage
`https://www.workday.com/` for the Copy/Paste Economy report; replaced with the specific
page URL, and the UK 2026-05-14 newsroom URL was added explicitly (previously only the
newsroom homepage was cited).

### Item 7 — App Intents / AppFunctions (FAIL on date attribution → corrected)

- Both frameworks are real and confirmed to exist: Apple's **App Intents** (a framework
  dating to iOS 16 / 2022, substantially expanded at WWDC 2026) and Google's
  **AppFunctions** (confirmed as the correct, official name Google/Android uses — see
  `developer.android.com/ai/appfunctions` and the AppFunctions Jetpack library).
- **Error found:** the file stated "Android의 AppFunctions(Google, 2026-06 공식 발표)" —
  i.e., that Google officially announced AppFunctions in June 2026. This is incorrect.
  Google's first substantial official detailing of AppFunctions was an Android Developers
  Blog post, **"The Intelligent OS: Making AI agents more helpful for Android apps,"
  published 2026-02-26** (URL: `android-developers.googleblog.com/2026/02/the-intelligent-os-making-ai-agents.html`).
  AppFunctions had been quietly introduced earlier (around Google I/O 2025, not prominently
  featured), was further expanded at Google I/O '26 (May 2026) and in the Android 17 launch
  post (June 2026), and a tutorial series followed in July 2026 — so there is no single
  "2026-06 official announcement" for Google's side. The original file appears to have
  conflated Apple's actual WWDC 2026 announcement date (2026-06-08, confirmed via Apple
  Newsroom: "Apple unveils next generation of Apple Intelligence, Siri AI, and more") with
  Google's AppFunctions.
- **Correction applied:** split the citation into two separate, dated sources — Apple App
  Intents → Apple Newsroom, 2026-06-08 (WWDC 2026 keynote); Google AppFunctions → Android
  Developers Blog, 2026-02-26. This aligns with CLAUDE.md's exact-date citation rule, which
  the original single "2026-06" attribution violated for the Google half of the claim.

### Item 8 — Compositional Design System / SAP Design Stories (previously flagged
unverifiable → now verified, one date corrected)

The file's own "Open questions" section had flagged this item as unverifiable (media name
only, no direct URL, not cross-checked). I found the actual primary source:

- **SAP Design Stories article: "Evolving design systems for AI driven UX"**
  (`www.sap.com/design/stories-resources/evolving-design-systems-for-ai-driven-ux`), and
  the companion SAP Design System page **"Compositional Design System and Engagement
  Layer"** (`www.sap.com/design-system/compositional-design-system-and-engagement-layer`).
- **Date correction:** the file had attributed this to "SAP Design Stories, 2026-08
  관련 게시물." The actual publish date is **2026-05-12**, timed with SAP Sapphire & ASUG
  Annual Conference 2026 (2026-05-11–13, Orlando), where SAP's "Joule Work" AI engagement
  layer (which the Compositional Design System underpins) was announced. This is now
  corrected in the file; the 2026-08-30 date that remains in the item header refers to when
  the user's daily briefing series covered/re-surfaced the item, not the SAP publish date —
  this distinction is now noted explicitly in the file to avoid future confusion.
- **Content verification:** the primary SAP source substantively confirms the file's
  claims — the Compositional Design System is described as extending a traditional design
  system with "the logic, structure, metadata, and guardrails needed for AI-driven
  experience composition," working like "a navigation system for AI to generate
  hyper-personalized UI," encoding "which combinations are valid, and what the system is
  allowed to generate" rather than a fixed component catalog, and explicitly not replacing
  SAP Fiori but adding a composition layer on top of it. This matches the file's framing of
  "고정 컴포넌트 세트 대 조합 규칙(composition rules) 시스템화."
- Given this, item 8's "unverified — flag as such" status is now resolved; I updated the
  file's Open Questions section accordingly, while leaving items 1 and 2's still-secondary-
  sourced status (Samsung/Stripe/Google primary docs not directly cross-checked) flagged
  as still open, since they were outside this verification pass's scope (6–8 only).

## Standing citation rules (CLAUDE.md) — compliance check

- **Exact-date rule:** Item 6 sources (2026-01-14, 2026-05-14) were already exact and
  confirmed correct. Item 7 had a violation (see above) — corrected to two separate exact
  dates. Item 8 had a wrong exact date ("2026-08" instead of the true 2026-05-12) — also
  corrected. No remaining season/half-year-style date language in items 6–8 after this pass.
- **2026-only rule for "current state" claims:** All primary sources now cited for items
  6–8 are 2026-dated (2026-01-14, 2026-05-14, 2026-02-26, 2026-06-08, 2026-05-12) — compliant.
  Apple App Intents' background mention of iOS 16 (2022) is contextual/historical framework
  provenance, not a "here's where competition stands now" headline claim, so it is not
  subject to the 2026-only narrative rule.

## Issues found

- [high] Item 7 — "Android의 AppFunctions(Google, 2026-06 공식 발표)" — incorrect date;
  Google's actual official detailing was 2026-02-26, not June 2026. **Corrected in file.**
- [medium] Item 8 — "SAP Design Stories, 2026-08 관련 게시물" — incorrect date; actual SAP
  publish date is 2026-05-12. **Corrected in file**, with the 2026-08-30 briefing-coverage
  date now explicitly distinguished from the SAP source's own publish date.
- [low] Item 6 — citation used the generic `workday.com` homepage instead of the specific
  report page URL. **Corrected in file** with the precise URL.

## Unverifiable claims

- Full primary-source text of the Workday 2026-01-14 press release and the "Copy/Paste
  Economy" report/2026-05-14 UK release could not be directly read end-to-end in this
  session — `newsroom.workday.com`, `www.workday.com`, `investor.workday.com`, and in fact
  nearly all external domains tested (including `sap.com`, `9to5google.com`,
  `android-developers.googleblog.com`, `blog.google`, `barchart.com`, `techradar.com`,
  `hrgrapevine.com`, `cfotech.com.au`, `uctoday.com`, `en.wikipedia.org`) returned
  `EGRESS_BLOCKED` errors from this session's network egress proxy when using WebFetch.
  Verification for items 6–8 therefore relied entirely on WebSearch's synthesized snippets
  (which do quote source pages, including the primary workday.com/sap.com/apple.com/
  android-developers.googleblog.com pages by URL and by directly-quoted text), not on
  direct full-page WebFetch reads. This is a meaningfully weaker verification standard than
  fetching and reading the primary source directly, and is flagged as a residual limitation
  for a future session with different network access to close out fully.
- The precise day of the Google Android Developers Blog "Intelligent OS" post is stated as
  2026-02-26 based on one search-engine-returned date; a companion source (9to5google)
  covered it as of 2026-02-25, so the exact publish day carries ±1 day uncertainty (month
  2026-02 is certain).
