# Verification — 토스·배달의민족·미국 대응 기업 UX 벤치마크
Date: 2026-09-21
Target: `research/findings/competitor/toss-baemin-us-ux-benchmark-2026-09-21.md`

Scope note: per task brief, effort concentrated on 6 prioritized claims. Same egress
constraint as the researcher's own session: WebFetch to `toss.tech`, `techblog.woowahan.com`,
`stripe.com`, `design.duolingo.com`, `brunch.co.kr`, `*.notion.site`, `weeklyuxuichallenge.oopy.io`
all returned `EGRESS_BLOCKED` when independently re-attempted here (confirmed directly, not
assumed) — so this pass, like the original research, relies on WebSearch snippet triangulation
across multiple independent queries rather than primary-source fetches. Where 2+ independently
phrased searches converged on the same wording/numbers, confidence is noted as higher than a
single-snippet claim.

## Result: PASS WITH NOTES

## Priority claims checked

1. **토스 TDS 생산성 지표 (30-40분→3-4분, 코드 50%↓, 4,500시간/562일/6개월) — PASS WITH NOTES.**
   - Multiple independently phrased WebSearch queries converge on identical figures, all tracing back
     to the same Toss Tech article (`toss.tech/article/toss-design-system`) plus a secondary breakdown
     found in a Notion post ("1000시간을 절약해준 디자인 시스템") by 강수영, who other search results
     identify as an actual Toss Design Platform team designer/lead — i.e. a plausible insider source,
     not a random blogger.
   - The 4,500-hour figure is internally consistent: 1 maker × ~1hr/day saved → 125hr/person over 6
     months → 4,500hr team-wide (÷8hr/day = 562.5 ≈ "562일"). The math checks out, and it clarifies a
     detail the original report didn't have: the notion post's own title says "1000시간" while its body
     states the real total is 4,500 hours — this is the source correcting/refining its own headline
     number, not a contradiction in the target report.
   - Could not reach the primary `toss.tech` article directly (blocked), so the underlying
     methodology (measurement period, what counts as "a screen," sample of teams/makers) remains
     unaudited beyond what a secondary blog post describes. The 50% code-volume reduction figure in
     particular was never corroborated by a source independent of that same one article — a related
     but distinct 2021 Slash21 conference session ("TDS로 UI 쌓기") talks about developers building
     "3-5x faster" with TDS, which is a different metric, not a second confirmation of "50%."
   - Verdict: figures are accurately represented by the target report and internally consistent, but
     still trace to a single primary source + one secondary corroboration, not independently audited
     data. Recommend keeping the report's existing "산출 기준·시점은 별도 검증 필요" caveat as-is for
     any 2027 business-plan reuse.

2. **Stripe Payment Element "매출 11.9% 상승" — PASS, with a methodology nuance worth adding.**
   - Independently confirmed: a WebSearch on the exact figure returned the sentence "Businesses using
     Stripe's Payment Element saw 11.9% more revenue on average," attributed to Stripe's own
     `stripe.com/payments/elements` product page — this matches the report's number exactly.
   - However, this appears to be an **updated version of an earlier, more fully-documented Stripe
     newsroom statistic of 10.5%** (`stripe.com/newsroom/news/payments-revenue-uplift`, dated ~April
     2023), which describes the methodology: two matched cohorts of 5,000 businesses each (one staying
     on the older Card Element, one migrating to Payment Element), matched on size/type/industry/
     geography, with revenue trajectories compared before/after migration. That newsroom piece
     explicitly caveats: "the increase in revenue may include the impact of other unobserved changes
     that businesses made at the same time they upgraded their integration" — i.e. it's a correlational
     matched-cohort estimate, not a randomized controlled experiment.
   - The target report already correctly notes "전환율이 아니라 매출 지표임에 유의" (revenue, not
     conversion). It does not mention that 11.9% is Stripe's own self-reported marketing statistic with
     a matched-cohort (not RCT) methodology, or that an earlier official figure was 10.5% — worth adding
     this nuance if the number gets quoted directly in a business-plan doc, since a reader might
     otherwise treat "11.9%" as an independently audited, single, stable figure. Also worth updating the
     citation to `stripe.com/payments/elements` (which has the exact 11.9% wording the report quotes)
     rather than only the `streamlined-checkout-processes` resources page currently cited.

3. **배달의민족 2020 "배민사장님광장" 역할 재배치 (~50 페이지/140 다이얼로그/150+ API 엔드포인트) — PASS.**
   - Independently confirmed via two separate targeted searches against `techblog.woowahan.com/6305`
     (제1편, "디자이너 편," attributed to 플랫폼 디자이너 태주희): one search returned the numbers
     verbatim — "approximately 50 pages, 140 dialogs, 10 API hosts, and connections with 150 REST/
     GraphQL endpoints" — matching the report's figures exactly (50 pages / 140 dialogs / 150+
     endpoints; report additionally cites "10개+ API 호스트" which also matches).
   - A second, differently-phrased search independently returned the role-reallocation claim nearly
     verbatim: "Planners (기획자) can now focus on defining system policies rather than spending time
     drawing screens, and designers (디자이너) can concentrate on drawing user flows and invest more
     time in UX improvements" — this is a direct match to the report's "기획자는 정책 정의에,
     디자이너는 유저 플로우/UX 개선에 집중" claim, not just a generic paraphrase.
   - Both figures and the qualitative claim are corroborated by independently phrased queries pointing
     at the same primary article; primary article itself remains unfetched (blocked), but the
     convergence across separate query phrasings raises confidence above snippet-single-source level.

4. **Duolingo 공식 Voice 프레임워크 (Expressive/Playful/Embracing/Worldly) — PASS.**
   - Independently confirmed: a WebSearch explicitly attributed to `design.duolingo.com/writing/voice`
     returned the four qualities by these exact names and near-identical descriptions to the report:
     Expressive ("using simple words and phrases to convey big feelings"), Playful ("bringing
     creativity to the conversation"), Embracing ("being a cheerleader for whoever you are"), Worldly
     ("being interested and knowledgeable with a broad worldview"). This is a close-to-verbatim match to
     the report's Korean paraphrase, not a loose approximation.
   - Direct WebFetch to `design.duolingo.com` remains EGRESS_BLOCKED, so this is still snippet-level
     confirmation rather than a primary-source read, but it is a strong match (exact names + matching
     descriptions from an independently-sourced query), materially more solid than "spot-checked and
     plausible."

5. **"AI UX라이터 제민희" — RESOLVED (was flagged unverified by the researcher).**
   - Independently confirmed via WebSearch against `techblog.woowahan.com/23836`: **"제민희" is an
     internal AI writing/review tool** built by Baemin's UX writers and developers to help review
     product copy at scale (the human UX writer team couldn't keep up reviewing every product string as
     the service grew). It is not a real person. The name is a deliberate pun/persona device: the tool
     was given a "신입 UX라이터" (junior/new-hire UX writer) persona, and "제민희" was chosen because it
     sounds like the Korean pronunciation of "Gemini" (제미나이) — the underlying model family — while
     also reading as a plausible human name, so staff could address/relate to it like a new colleague.
   - This directly resolves the researcher's flagged open question and should be pulled into both the
     Key findings/Per-company-notes text and the Open questions section: this is a concrete, well-suited
     `ux-ai-capability-research`-lens finding (AI-assisted UX writing tool, internal-capability angle)
     that the current report only has as a title-only placeholder. Recommend the researcher (or
     report-writer) update the finding text rather than carrying it forward as "미확인."

6. **토스 UX 라이팅 원칙 8개 (6개 확인, 2개 미확인) — PARTIALLY RESOLVED, but surfaces a new issue.**
   - Multiple independently phrased WebSearch queries (4 separate queries) converge on the same
     canonical 8-item list: **Predictable Hint, Weed Cutting, Remove Empty Sentences, Focus on Key
     Message, Easy to Speak, Suggest than Force, Universal Words, Find Hidden Emotion.** This resolves
     2 of the report's "미확인" items — the missing 2 principles are most likely **Predictable Hint**
     (다음 화면 힌트 제공 여부) and **Focus on Key Message** (진짜 중요한 메시지만 전달했는지).
   - **However**, this list does NOT contain "Mute Mute" anywhere — a name the target report lists as
     one of the 6 *confirmed* principles ("Mute Mute(반복 문장 제거)"). Two dedicated searches
     specifically for "뮤트뮤트" and for `"Mute Mute" Toss writing principle` returned **zero**
     corroboration of that term in any source. Every independent query instead consistently surfaces
     "Remove Empty Sentences" occupying what looks like the same conceptual slot (removing
     meaningless/repeated sentences) that the report describes for "Mute Mute."
   - This is a meaningful discrepancy: one of the six items the original researcher marked as
     "확인된 항목" (confirmed by name) does not check out under independent re-search, while a
     plausible correct replacement name ("Remove Empty Sentences") is readily available and was
     apparently missed. Recommend the report be corrected to either drop "Mute Mute" or relabel it as
     unconfirmed, and use "Remove Empty Sentences" as the (still snippet-sourced, not primary-verified)
     best candidate for that principle. This should also be corrected before any of this list is quoted
     directly in a business-plan report, since presenting a possibly-invented term as "confirmed by
     name" is worse than leaving it as an open gap.

## Other checks

- No internal contradictions found between the Key findings summary bullets and the matching
  Per-company notes detail sections for the 6 priority claims above.
- Numbers are consistent within the document itself (e.g. the TDS 4,500시간/562일 figure appears
  identically in both the Key findings bullet and the 내부 역량 강화 시사점 section).
- Did not re-verify claims outside the 6 prioritized items (Simplicity conference details, 배민체 font
  OFL licensing, Robinhood design awards, "배민 2.0"/워크체 rebrand timing, Stripe's internal "Sail"
  system, Duolingo's third-party-sourced token counts) — these were already appropriately flagged by
  the researcher as snippet-based/unverified and were out of scope for this pass; the same
  EGRESS_BLOCKED constraint would apply to them.

## Issues found

- [medium] "Mute Mute" UX writing principle — Per-company notes (토스 section) and Key findings bullet
  — listed as one of 6 principles "confirmed by name," but independent re-search across 4 differently
  phrased queries (including 2 queries targeting the term directly) found zero corroboration of this
  name anywhere, while consistently surfacing a full alternate 8-item list that uses "Remove Empty
  Sentences" for the same conceptual slot instead. This is the kind of over-confident labeling that
  should not carry into a 2027 business-plan report unchanged — recommend correcting before reuse.
- [low] Stripe 11.9% citation — Per-company notes (Stripe section) and 사업적 시사점 — the figure itself
  is correctly quoted, but the report doesn't note that (a) it's Stripe's own self-reported marketing
  stat from a matched-cohort (not RCT) study with an explicit unobserved-confounders caveat in Stripe's
  own newsroom writeup, and (b) an earlier official Stripe figure for what looks like the same
  underlying study was 10.5%, not 11.9%. Worth a one-line methodology caveat if this number is quoted
  directly in a business-plan deck.
- [info, now resolved] "AI UX라이터 제민희" — previously an open question in the target report; this
  pass independently confirmed it is an internal Baemin AI writing-review tool with a "Gemini" pun
  persona, not a person. Recommend updating the finding text (see item 5 above) rather than leaving it
  as "미확인."

## Unverifiable claims

- 토스 TDS 지표의 정확한 측정 방법론(측정 기간, 대상 팀/메이커 범위, "화면 1개"의 정의 등) —
  `toss.tech/article/toss-design-system` 원문 접근 불가로 확인 못함; secondary Notion breakdown by a
  plausible Toss insider (강수영) is internally consistent but not independently audited.
- 코드량 50% 감소 수치가 30-40분→3-4분/4,500시간 수치와 동일한 단일 원문(toss.tech) 외에 별도로
  독립 확인되는지 — 이번 조사에서 찾은 유일한 인접 데이터(Slash21 "3-5배 빠르게" 발언)는 다른 지표라
  교차검증으로 쓸 수 없었다.
- Stripe "Sail" 내부 디자인시스템 구조(토큰 체계, 컴포넌트 수) — 사내 전용이라 외부에서 검증 불가한
  것은 원 리포트의 진단과 동일하게 유지.
- Duolingo 제3자 토큰 수치(18개 컬러, 22개 컴포넌트 등, dembrandt.com/designmd.co 기반) — 원 리포트가
  이미 "공식 자료 아님"으로 적절히 플래그함; 이번 조사에서 재검증 시도하지 않음(우선순위 목록 밖).
- 배민 "워크체" 리브랜딩 정확한 공개 일정 및 배민체 서체군의 SIL OFL 라이선스 세부조항 — 우선순위
  목록 밖이라 재검증하지 않음; designcompass.org/font.woowahan.com 원문 접근 불가 상태는 동일.
