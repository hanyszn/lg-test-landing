# Verification — 경쟁사 리서치: 스마트홈 UX·AI 전략
Date: 2026-09-20
Target: `research/reports/2026-09-20-competitor-research-smart-home-ux-ai.md`

Scope note: per interview log `research/interview/2027-business-plan-report-verification-priorities-2026-09-20.md`,
effort was concentrated on the four flagged quantitative/timing claims. WebFetch access to most primary
domains (news.samsung.com, blog.google, forbes.com, cnbc.com, emarketer.com, blog.smartthings.com,
matter-smarthome.de, homekitnews.com, t3.com, neowin.net, jrattechworks.com, matteralpha.com) was blocked
by the sandbox's egress proxy during this session, mirroring the network restriction the original report
itself flags. Verification below therefore relies on WebSearch snippet triangulation across multiple
independent secondary outlets rather than direct primary-source fetches — the same limitation the report
already discloses.

## Result: PASS WITH NOTES

## Priority claims checked

1. **Samsung SmartThings user count discrepancy ("4.3억" vs "5억") — CONFIRMED REAL, both current/official.**
   - 430M figure: Samsung EVP Cheolgi Kim (Head of Digital Appliances) cited "430 million users" at Samsung's
     main CES 2026 press event (Jan 2026), up from 350M reported Sept 2024. Corroborated by multiple
     independent outlets (SamMobile, Sammyfans, SammyGuru, Malaysian Wireless).
   - 500M figure: cited separately at Samsung's CES 2026 "Tech Forum" panel ("When Everything Clicks: How
     Open Ecosystems Deliver Impactful AI"), per mobilityground.com's writeup of that specific panel.
   - Both are dated to the same CES 2026 timeframe and both are attributed to official Samsung
     spokespeople/venues, not researcher error — the report's characterization is accurate. Neither figure is
     more "authoritative" in a documented sense; 430M appears more widely repeated across outlets (the primary
     press-conference number), which is a useful signal but not a confirmed correction/retraction of 500M.
   - Note: some outlets frame 500M as a *2026 year-end projection* built on the 430M base+growth trend rather
     than a second contemporaneous headcount — if that framing is accurate, the two numbers may not be a true
     "discrepancy" but "current count vs. year-end target." The report should ideally caveat this alternative
     reading, since our secondary sources are not fully consistent on this point either. Recommend the report
     soften "동일 시기 발표 불일치" to acknowledge this ambiguity, or track down the original Tech Forum
     transcript to confirm 500M was presented as a present-tense headcount rather than a projection.

2. **Apple–Google Gemini deal size (~$1B/year) — PASS, correctly hedged.**
   - Confirmed the partnership itself was officially, jointly announced by Apple and Google on 2026-01-12
     (matches report's date). Apple and Google's joint statement did **not** disclose deal terms ("Apple
     declined to comment on the terms of the deal" — multiple outlets).
   - The ~$1B/year figure originates from a Bloomberg report dated 2025-11-05 (pre-announcement), citing
     anonymous sources ("people with knowledge of the matter"), reporting a custom 1.2-trillion-parameter
     Gemini model. It has since been repeated consistently by CNBC, TechCrunch, CNN, and others, but remains
     **unconfirmed by either company** as of this verification. The report's "미확정 표기"/hedged phrasing
     ("~10억 달러 수준으로 알려졌다") is accurate and should stay hedged — do not upgrade this to a confirmed
     figure in downstream materials (e.g., the 2027 business plan).

3. **Google Gemini for Home pricing ($10/mo Standard, $20/mo Advanced) — PASS, confirmed exactly.**
   - Multiple sources (Android Authority, TheNextWeb, Gadget Hacks, and Google's own store product page
     `store.google.com/product/google_home_premium`) confirm: Standard $10/mo ($100/yr) — Gemini Live,
     Ask Home automation help, 30-day video history; Advanced $20/mo ($200/yr) — adds Gemini camera features,
     Home Brief, searchable video history. Matches the report's figures and feature breakdown exactly.

4. **Matter camera timeline (partner launches "early 2026" vs. Matter 1.5.1 spec release "2026-03-31") —
   PASS, distinction is real, but flag a timing-proximity risk.**
   - Matter 1.5.1 (CSA/Connectivity Standards Alliance minor spec update refining camera/video-doorbell
     behavior: multi-stream delivery, HEIC snapshots, HLS/DASH upload) was released 2026-03-31 — confirmed via
     homekitnews.com and csa-iot.org listings in search results. This is a **standards-body spec release**,
     organizationally unrelated to any single vendor's product ship date.
   - SmartThings' Matter 1.5 camera-category support was announced 2025-12-19 (Samsung EVP announcement,
     corroborated by Forbes, Neowin, HomeKit News, T3 headlines/snippets).
   - Partner camera products (Aqara, Eve, Xthings/Ulticam IQ V2) are described across sources as launching
     "early 2026" / "2026 H1", with at least one aggregated source specifically placing rollout as
     "starting in March 2026" and an Xthings product blurb saying "available later this month" in an article
     that appears to be from around March 2026. **This means at least one partner camera's actual ship date
     may land in the same month as the Matter 1.5.1 spec release (March 2026)**, even though the two remain
     conceptually distinct (vendor product ship vs. spec version release). The report's correction is directionally
     right and should stand, but "early 2026" is doing a lot of work covering a window that, per some sources,
     extends into March — right up against the spec date. Recommend the report tighten this to "2026년 1분기
     (자료에 따라 3월 포함)" rather than leaving "early 2026" bare, to reduce future conflation risk rather than
     just assert non-conflation.

## Other spot checks (secondary, time-permitting)

- Google Assistant→Gemini replacement on 800M+ "Works with Google Home" devices, effective 2025-10-01: confirmed
  by droid-life, Engadget, Tom's Guide (rollout continued through October, matches report's phrasing).
- No contradictions found between the Executive Summary and body sections on the four priority items — the
  report's own internal "정정 사항" / "중요 정정" callouts for the Apple and Samsung items are consistent with
  what we independently found.

## Issues found

- [minor] Samsung 430M vs 500M framing — where: "경쟁사별 분석 > 삼성전자 > 생태계 구조" and "리서치 한계" — the
  report presents this as a flat "공식 발표 자체의 불일치" without considering the alternative reading that 500M
  could be a forward-looking projection rather than a second concurrent headcount; recommend adding that caveat
  explicitly rather than asserting pure inconsistency.
- [minor] Matter camera "early 2026" phrasing is imprecise given evidence some partner cameras ship as late as
  March 2026, i.e., the same month as the Matter 1.5.1 spec release — recommend narrowing the date range stated
  in the report to reduce future conflation risk.
- [info] Report's own "출처" section provides source *types* only, no URLs — this was already flagged by the
  report itself as a limitation; still true, still worth fixing before the report is cited externally in 2027
  planning materials (a reviewer cannot re-verify individual figures without URLs).

## Unverifiable claims

- Exact original Samsung Tech Forum transcript/press material for the "500 million" figure — could not fetch
  news.samsung.com directly (blocked by sandbox egress); relied on a single secondary aggregator
  (mobilityground.com). Recommend a follow-up session with WebFetch access to news.samsung.com to pull the
  primary source directly.
- Apple "HomePad" (J490) pricing ($350) and fall-2026 launch consensus — report already flags this as
  Bloomberg/Gurman-sourced rumor; not independently re-verified here since it was not on the priority list and
  the report's own hedging is already appropriately cautious.
- Xiaomi–Google Gemini partnership "under consideration" (미확정) — not independently re-verified; report already
  flags as unconfirmed/rumor-level, consistent with our understanding.
- Precise scope of Google's multi-country/multi-language Gemini for Home expansion (spring 2026) — not
  independently re-verified; report already flags as partially cross-verified only.
