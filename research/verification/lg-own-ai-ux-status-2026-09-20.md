# Verification — LG전자 자사 AI/UX 추진 현황
Date: 2026-09-20
Target: `research/reports/2026-09-20-lg-own-ai-ux-status.md`

Scope note: per interview log `research/interview/2027-business-plan-report-verification-priorities-2026-09-20.md`,
effort concentrated on the four flagged claims (CLOiD roadmap, humanoid Q1 2027 reveal, AI robot patent
ranking, EXAONE B2B revenue disclosure). Most primary domains (lg.com, news.samsung.com-style LG newsroom
pages, heraldcorp.com, etc.) were reachable via WebSearch snippets but not always via direct WebFetch in this
sandbox; verification below is based on triangulation across multiple independent Korean and English outlets.

## Result: PASS WITH NOTES

## Priority claims checked

1. **LG CLOiD roadmap (2026 Tennessee washing-machine-plant industrial pilot → 2027 home PoC) —
   ~~PASS~~ SUPERSEDED, 2026-09-20 후속 인터뷰에서 정정됨.**
   - Original check confirmed via Bitget News (citing original reporting), Dezeen, TechEBlog, Tom's Guide, and
     FinancialContent/tokenring coverage of CES 2026 that LG plans to deploy wheeled CLOiD robots on a washing
     machine production line at its Tennessee factory "by the end of 2026" — but **none of those sources
     covered LG's own investor-facing statement**, so the "2027년 가정용 PoC" framing this verification
     originally passed was itself inaccurate.
   - **정정**: 후속 인터뷰(2026-09-20)에서 LG전자 2026-04-29 실적 컨퍼런스콜(공식 임원 발언)을 인용한
     4개 독립 매체(Daum, 데일리안, 녹색경제신문, mdtoday)를 교차 확인한 결과, 공식 목표 시점은
     "2027년 가정용 PoC"가 아니라 **"2028년 홈로봇 상용화 기반 마련"**이며 2027년은 산업 실증 확대
     구간이다. `research/reports/2026-09-20-lg-own-ai-ux-status.md`와
     `research/findings/own-company/2027-business-plan-followup-updates-2026-09-20.md`를 이 내용으로
     정정했다. **교훈**: 제품 발표 보도(CES 등)만으로는 회사의 공식 상용화 목표 시점까지 확인되지
     않을 수 있다 — 투자자 대상 실적 컨퍼런스콜을 함께 확인해야 한다.

2. **Bipedal humanoid robot public reveal targeted Q1 2027 — PASS, confirmed by multiple independent Korean
   outlets.**
   - Confirmed via 글로벌이코노믹, 한국금융신문, 헤럴드경제 (two separate articles), 딜사이트, 청년일보, and
     서플 — all reporting "2027년 1분기 공개" tied to the 2026-08-13 구광모–젠슨 황 meeting at NVIDIA's Santa
     Clara HQ (matches report's date and context exactly). Also confirmed in English via Bitget News
     ("won't go on public display until the first quarter of 2027," running NVIDIA Isaac GR00T). Consistent
     across languages and outlets — no discrepancy found.

3. **AI robot patent ranking (LG #1 worldwide, 18.8%, 2012–2021 cumulative) — PASS, and the report's own
   caveat about no 2025–2026 update is corroborated by our active search.**
   - Confirmed the underlying 2025-01-05 KIPO (특허청) announcement figures exactly: LG Electronics 1,038
     filings / 18.8% (#1), FANUC #2 (1.8%), Google #4 (1.3%), Samsung Electronics #8 (0.7%, 41 filings) — via
     ZDNet Korea, Hankyung, Seoul Shinmun, 로봇신문, Edaily, 특허뉴스, and KIPO's own site listing
     (kipo.go.kr). Data window confirmed as 2012–2021 (filings grew from 20/year in 2012 to 1,260/year in
     2021), with national breakdown China 60.0% / Korea 24.7% / US 8.1% / Japan 4.3% by applicant nationality
     — an interesting nuance the LG-firm-level "18.8%" figure doesn't contradict but sits alongside (LG is a
     single firm within Korea's 24.7% national share).
   - We actively searched for an updated 2025–2026 ranking, as instructed, and found **none**: 2026 patent
     landscape reports (e.g., Patsnap's "Humanoid Robots Patents" and "Industrial Robot AI/ML" 2026 landscape
     blogs) note that patent publication lags filing by roughly 18 months, so 2024 is treated as the most
     recent "complete" year and 2025+ data is still filling in — meaning a true apples-to-apples 2025–2026
     update to the KIPO 2012–2021 ranking is not realistically available yet from any source we could find, not
     just one LG chose not to disclose. This strengthens rather than weakens the report's existing caveat: it
     should be stated even more plainly that **no comparable updated ranking currently exists industry-wide**
     (not just "unconfirmed"), so readers don't wait for one to appear before the 2027 planning cycle.
   - The Patsnap "top five" 2026 landscape snippet found in search did not name LG specifically in a
     comparable top-line position, but the data model differs from KIPO's methodology (different technology
     scope, applicant-family counting), so it is not a valid substitute ranking — noting this so it isn't
     mistakenly treated as a contradicting data point.

4. **EXAONE B2B external revenue figures (analyst estimates only, no official LG disclosure) — PASS, still
   accurate as of verification date.**
   - Searched specifically for any official LG disclosure since the 하나증권 (Hana Securities) estimates cited
     in the report. Found only further analyst commentary (Hana Securities reiterating "外部 매출 조만간 발생"
     / "revenue recognition coming soon," "매수" rating, ₩140,000 target price, dated as recently as
     2026-09-15) and LG's own framing of intent ("해외 글로벌 기업과 제약회사, 병원, 에너지기업 등에서도 관심을
     보이고 있다" — interest, not signed/disclosed revenue) via 딜사이트, EBN/Investing.com, 인사이트코리아,
     PRESS9. No article found reporting an actual LG-disclosed revenue figure, earnings-call number, or IR
     disclosure. The report's framing ("증권가 추정치 수준, LG 공식 실적 발표는 아님") remains accurate as of
     2026-09-20.

## Other checks

- No internal contradictions found between the Executive Summary and body sections on any of the four
  priority items; the report's own "혼동 금지" framing (CLOiD vs. humanoid as separate tracks; MWC vs. CES
  content; webOS 26 vs. ChatGPT LGE.com app) held up under spot review and is consistent with what independent
  sources describe.

## Issues found

- [major, RESOLVED 2026-09-20] CLOiD 홈로봇 로드맵 — 이 검증이 처음 PASS 처리했던 "2027년 가정용
  PoC"는 부정확했다. 실제 공식 목표는 "2028년 홈로봇 상용화 기반 마련"(LG 2026-04-29 실적 컨퍼런스콜).
  원인은 이 검증이 제품 발표 보도(CES 등)만 확인하고 투자자 대상 실적 콜은 확인하지 못했기 때문 —
  후속 인터뷰·재조사로 정정 완료, 위 "Priority claims checked" 1번 항목 참고.
- [minor] AI robot patent ranking section — where: "특허 현황" and Executive Summary — recommend strengthening
  the caveat from "2025~2026년 갱신된 최신 순위는 확인되지 않았다" to explicitly state that **no methodologically
  comparable updated industry ranking appears to exist yet anywhere** (per 2026 patent-landscape research
  publication-lag norms), not merely that LG/KIPO haven't released one — this is a more accurate and slightly
  more defensible claim for 2027 planning purposes than implying an update merely hasn't been found.
- [info] Note the KIPO stat is a single-firm figure (LG Electronics, 18.8%) within a China-dominated national
  landscape (China 60.0% of filings by applicant nationality) — the report doesn't misstate this, but a reader
  skimming only the "세계 1위" framing could get an overly LG-favorable impression of Korea's/LG's relative
  position; consider surfacing the national breakdown alongside the firm-level stat for balance.

## Unverifiable claims

- "엑사원 디스커버리" patent registration claim (2026-02) — report already flags this as unconfirmed; not
  independently re-verified here (not on priority list).
- Exact figures behind LG생활건강 "람시딜" 42만 개 후보물질 하루 검토 claim — report already flags as
  LG/LG생활건강-sourced via media, no independent third-party verification; not independently re-verified here
  (not on priority list).
- Precise ThinQ Claw commercial launch date — report already states this is unconfirmed; not independently
  re-verified here (not on priority list).
- Whether the Samsung-facing "엑사원 타뷸러 공급 가능" comment has progressed to an actual deal since
  2026-09-20 — searched but found no evidence either way beyond the original "openness in principle" framing
  the report already uses; genuinely unconfirmable with available tools/access in this session.
