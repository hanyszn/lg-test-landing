# Verification — "가전의 수익모델 전환" — 하드웨어 판매에서 구독/플랫폼 비즈니스로
Date: 2026-09-21
Target: `research/findings/competitor/appliance-subscription-business-model-shift-2026-09-21.md`

Scope note: 사용자 요청의 우선 재검증 항목(한국 "가전구독" 매출 2.48조원/+29%/2026년이 AI 기능 구독이
아니라 하드웨어 렌탈이라는 구분이 정확한지)에 집중했고, 그 과정에서 이 수치의 **출처 범위 자체**에
오류를 발견해 정정했다. 구글 Home Premium 가격 관련 부수적 claim("Nest Aware Plus 대비 60% 인상")도
함께 검증하다 별도 오류를 발견해 정정했다.

## Result: FAIL → 정정 완료 후 PASS WITH NOTES

두 건의 사실관계 오류가 있었으나 모두 파일 내에서 직접 정정했으므로, 정정 반영 후 기준으로는
PASS WITH NOTES로 평가한다(정정 전 상태만 보면 결론에 영향을 주는 오류였으므로 FAIL로 기록).

## Issues found (모두 정정 완료)
1. **[high] "2026년 국내 가전구독 매출 약 2조 4,800억원, 전년 대비 29% 성장"은 "한국 가전구독
   시장 전체"가 아니라 LG전자 한 회사의 2025년 연간 가전구독 사업 매출이다.**
   - 재검색 결과 이 수치는 LG전자가 2026-01-30 2025년 4분기/연간 실적 컨퍼런스콜에서 발표한
     **LG전자 자체** 가전구독 매출임을 다수의 1차 소스(데일리안, 네이트뉴스 컨콜 기사, 헤럴드경제
     등)로 확인했다.
   - 반면 한국 가전구독 "시장 전체"(삼성·코웨이·쿠쿠·SK매직 등 경쟁사 포함) 규모는 이보다 훨씬
     크다 — 전자신문(2025-09-17)은 "국내 시장이 2025년 **상반기만으로 3.5조원을 돌파**"했다고
     별도로 보도하고 있어, LG 한 회사의 연간 2.48조원과 전혀 다른 카테고리의 숫자다.
   - 왜 중요한가: 이 파일의 핵심 논지 중 하나가 "한국 가전구독 시장은 크지만 AI 기능 구독이 아니라
     하드웨어 렌탈"이라는 구분인데, "시장 전체 매출"로 잘못 표기하면 report-writer나 의사결정자가
     시장 규모를 실제보다 훨씬 작게(약 1/1.5배 이하로) 오인할 위험이 있었다. 정성적 결론(하드웨어
     렌탈 vs AI 기능 구독 구분) 자체는 LG전자 IR 자료와 일치해 타당했으므로 유지했고, 근거 수치만
     "LG전자 자체 매출"로 재기술했다. `research/findings/competitor/appliance-subscription-business-model-shift-2026-09-21.md`
     의 Key findings 5번과 "사업적 시사점" 1번 항목 모두에 `[2026-09-21 verifier 정정]` 태그로
     수정 반영함.
2. **[medium] "Google Home Premium Advanced(월 $20) — 구 Nest Aware Plus 대비 약 60% 인상"은
   부정확하다.** 재검색 결과 Nest Aware Plus는 이미 2025-08-15부터 $15→$20/월($150→$200/년)로
   인상된 상태였고, 2026-06-25 Google Home Premium Advanced는 그 인상된 $20/월 가격을 그대로
   승계했다 — 즉 **이번 출시로 인한 가격 인상은 없었다**(기존 Nest Aware Plus 가입자 기준 인상폭
   0%). "60~67% 인상"이라는 수치 자체는 실재하지만, 이는 2020년 출시가($12/월) 대비 2025-08 인상
   후까지의 5년간 누적 인상률이며 2026-06-25 출시와는 직접 관련이 없다. `[2026-09-21 verifier 정정]`
   태그로 파일 내 직접 정정.

## Confirmed items ([2026-09-21 verifier 확인] 태그로 파일 내 직접 표시)
- Google Home Speaker $99.99, 2026-06-25 출시(18개국), 2026-09-30 이전 구매 시 6개월 무료체험 —
  재검색으로 일치 확인(9to5google, TechAdvisor, 9to5toys).
- Google Home Premium 가격 체계(Standard $10/월, Advanced $20/월 또는 $200/년) 자체는 정확.
- 삼성 SmartThings API $4.99/월·2026년 10월 시행 — `home-ai-standard-war` 파일 검증과 동일한
  결과로 재확인.
- Bank of America Institute "미국 가구 3%만 AI 서비스 결제, 지불 가구 월 지출 중앙값 $20" —
  moneywise.com, Yahoo Finance, thenationaldesk.com 등 재검색으로 수치 일치 확인.

## Unverifiable claims
- McKinsey D2C/구독-마진-CLV 정량 수치 — `mckinsey.com` EGRESS_BLOCKED로 확인 불가(파일이 이미
  "unverified"로 적절히 라벨링).
- 일렉트로룩스/AEG CamCook, 보쉬 Cook AI의 구독료 부과 여부·가격 — 이번 세션에서도 확인하지 못함
  (파일의 기존 "확인 자료 없음" 라벨링과 동일).
- Google Home Premium 실제 유료 구독자 수·매출 기여도 — Google 비공시, 확인 불가(파일의 기존
  라벨링과 동일).

## Citation rule check (CLAUDE.md)
- 정확한 날짜 표기 원칙: 대체로 준수됨. 단, 위 issue 1번에서 지적했듯 "2026년 매출"이라는 연도
  귀속이 실제로는 "2025년 매출(2026-01-30 발표)"이었어야 하는데 혼동이 있었다 — 이는 날짜 자체의
  표기 문제라기보다 통계의 출처(회사 vs 시장) 오귀속 문제이므로 별도 issue로 기록.
- 2026-only 헤드라인 원칙: 이 항목도 issue 1번과 연결된다 — "2026년 국내 가전구독 매출"이라는
  헤드라인이 실제로는 2025년 실적(2026-01-30 컨콜에서 발표)이었다는 점에서, 엄밀히는 "2025년 실적을
  2026년 초 발표"로 라벨링했어야 한다. 정정문에 이를 반영함. 그 외 항목(Bosch/Electrolux 2025년
  자료를 배경으로만 인용, Parks Associates 2025년 자료를 헤드라인이 아닌 배경으로만 인용)은 이미
  올바르게 라벨링되어 있었다.
