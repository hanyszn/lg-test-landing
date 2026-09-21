# "가전의 수익모델 전환" — 하드웨어 판매에서 구독/플랫폼 비즈니스로
Date: 2026-09-21
Scope: 구글 Home Premium, 삼성 SmartThings/API 과금, 유럽 가전사(일렉트로룩스/AEG, 보쉬)의 AI 요리
구독 시도, 소비자 지불의향 데이터, 손익구조(마진·CLV) 영향, LG전자 시사점. 원칙: "출시/상용화"는
정확한 날짜(YYYY-MM-DD) 기재, "현재 이렇다"는 헤드라인 통계는 2026년 발표 자료만 사용(이전 연도
자료는 배경이라도 본문에서 제외하고 라벨링).

## 중심 명제 (Thesis)

**가전업계의 구독 전환은 두 갈래로 동시에 진행 중이다 — (1) "AI 기능 자체"를 소비자에게 직접
과금하는 B2C 구독(Google Home Premium형)과 (2) 가전을 제어하는 API/에이전트 접근권 자체를 개발자·
파트너에게 과금하는 B2B2C 플랫폼 요금(Samsung SmartThings API형)이다. 그러나 두 갈래 모두 아직
매출·마진 효과를 공개적으로 증명하지 못한 초기 단계이며, 소비자의 "AI 기능 자체"에 대한 지불의향은
오히려 정체·후퇴하는 신호가 나타나고 있다 — 즉 공급 측(업계)의 구독화 드라이브가 수요 측(소비자
지불의향)보다 앞서가는 비대칭 상태다.**

## Key findings

### 1. 구글 Home Premium — 구독형 AI홈의 최대 실험, 그러나 재무 성과는 여전히 블랙박스

- **가격·출시**: 2026-06-25, Google Home Speaker($99.99)와 함께 Google Home Premium 정식 출시
  (Standard 월 $10, Advanced/Premium 월 $20 또는 연 $200). **[2026-09-21 verifier 정정] "구 Nest
  Aware Plus 대비 약 60% 인상"은 부정확하다 — Nest Aware Plus는 이미 2025-08-15부터 $15→$20/월
  ($150→$200/년)로 인상된 상태였고, Google Home Premium Advanced는 바로 그 인상된 $20/월 가격을
  그대로 승계한 것이므로 이번 출시 자체로 인한 가격 인상은 확인되지 않는다(기존 Nest Aware Plus
  가입자 기준 인상폭은 0%). "약 60~67% 인상"이라는 수치는 2020년 출시가($12/월, $120/년) 대비
  2025-08 인상 후 가격($20/월, $200/년)까지의 5년간 누적 인상률이며, 2026-06-25 Google Home
  Premium 출시와는 직접 관련이 없다(source 교차검증: [droid-life](https://www.droid-life.com/2025/07/16/your-nest-aware-prices-are-going-up-again/), [9to5google(2025-07-16)](https://9to5google.com/2025/07/16/nest-aware-price-2025/), [Google Nest Community 포럼](https://www.googlenestcommunity.com/t5/Nest-Aware/25-price-increase-US-Reasons/m-p/727974)).**
  미국·캐나다·영국·아일랜드·프랑스·스페인·이탈리아·네덜란드·덴마크·노르웨이·스웨덴·핀란드·벨기에·
  스위스·오스트리아·일본·호주·뉴질랜드 등 18개국 동시 출시, 2026-09-30 이전 구매 시 6개월 무료
  체험 제공. [2026-09-21 verifier 확인] $99.99 가격·2026-06-25 출시일·6개월 무료체험은 재검색으로
  교차확인됨.
  (source: [9to5google](https://9to5google.com/2026/06/17/google-home-speaker-launch/), [TechAdvisor](https://www.techadvisor.com/article/2927829/google-home-speaker-release-date-price-and-features-confirmed.html))
- **설치기반**: 글로벌 Nest 디바이스 보유 가구 약 5,000만(2026년 기준 추정치) — 그러나 **유료 전환율,
  구독자 수, 매출 기여도는 이번 세션 검색 범위에서 확인하지 못했다("2026년 확인 자료 없음" — Google
  은 별도 매출을 공시하지 않음).**
- **에이전트 접근권의 이중 과금 — 2026-09-16, Home MCP를 Premium Advanced($20/월) 전용으로 게이트.**
  이는 "소비자용 구독"과 "에이전트/개발자용 구독"이 사실상 같은 요금제 안에서 결합되는 구조를
  보여준다 — 즉 Google Home Premium은 단순 보안영상 저장 구독을 넘어, AI 에이전트가 집을 제어할 수
  있는 권한 자체를 유료 게이트 뒤에 두는 방식으로 진화했다.
  (source: [Unite.AI](https://www.unite.ai/google-opens-home-mcp-early-access-to-ai-agents-for-smart-home-control/), [dev.to](https://dev.to/techaiwire/google-home-adds-an-mcp-server-gated-at-20-a-month-5gop))

### 2. 삼성 SmartThings — 소비자 매출은 비공시, 대신 "플랫폼 참여자 과금"이라는 세 번째 축을 개설

- Samsung DX(Device eXperience) 부문은 분기 실적 발표에서 SmartThings 서비스 매출을 별도 항목으로
  공시하지 않는다(2026년 2분기 실적 기준, DX 부문은 QoQ 매출 9% 감소만 확인됨) — **"2026년 SmartThings
  매출 비중 확인 자료 없음"으로 명시한다.**
  (source: [Samsung Global Newsroom(2026 Q2 실적)](https://news.samsung.com/global/samsung-electronics-announces-second-quarter-2026-results))
- 대신 **2026년 6월 발표(보도 확산일 2026-06-26), 2026년 10월 시행 예정으로 SmartThings API에
  비상업 개인 개발자 대상 월 $4.99("Personal Plan") 과금을 도입.** 이는 소비자 대상이 아니라
  "생태계 참여자(개발자·연동 서비스)" 대상의 플랫폼 통행료 모델 — B2C 구독과는 다른 세 번째 수익
  축을 보여준다. Home Assistant 등 무료 연동 서비스가 타격을 받는다는 반발도 확인됨.
  (source: [SamMobile](https://www.sammobile.com/news/smartthings-api-access-will-soon-require-a-5-monthly-payment/), [Eastern Herald](https://easternherald.com/2026/07/02/samsung-smartthings-api-fee-developers-home-assistant-october-2026/))

### 3. 업계 전반 확산 — 프리미엄 오븐·쿡탑의 "AI 요리 어시스턴트"가 초기 구독 실험의 선봉, 그러나 가격 공개 사례는 드묾

- **일렉트로룩스/AEG — CamCook®+AI TasteAssist.** 요리를 자동 인식해 레시피를 설정값으로 변환하고
  조리 완료 시점을 판단하는 기능. 최초 탑재 오븐이 2026년 중반 소비자 출시 예정(**정확한 날짜
  미확인 — 2026년 중반 추정**). 구독료 부과 여부·가격은 확인하지 못함.
  (source: [Electrolux Group 공식](https://www.electroluxgroup.com/en/meet-camcook-and-ai-tasteassist-for-smarter-cooking-45815/))
- **보쉬 — Bosch Cook AI.** CES 2026(2026-01)에서 공개, Home Connect 앱 내 에이전틱 AI 요리
  어시스턴트로 실시간 조리 가이드 제공. 구독료 부과 여부·가격은 확인하지 못함.
  (source: [Homecrux](https://www.homecrux.com/bosch-ai-kitchen-at-ces-2026/357909/))
- **월풀 — 필터 정기배송 구독**은 확인되나, 이는 소모품 정기배송(하드웨어 판매의 연장)이며 "AI 기능
  자체"의 구독화 사례는 아님.
  (source: [Whirlpool 공식](https://www.whirlpool.com/services/subscriptions.html))
- **GE Appliances SmartHQ Service**는 수리기사(B2B)용 진단 도구 구독이며, 소비자향 AI 기능 구독과는
  카테고리가 다름 — 가격도 비공개.
  (source: [SmartHQ Pro](https://www.smarthqpro.com/service/pricing))
- → **결론: "AI 요리 어시스턴트"류 기능이 유럽 프리미엄 가전사들 사이에서 공통적으로 등장하고 있지만,
  구글·삼성처럼 명확한 구독 가격표를 공개적으로 부과한 사례는 이번 세션 검색 범위에서 확인되지 않았다.
  즉 "가전업계 전반의 구독 확산"은 Google/Samsung을 제외하면 아직 대부분 "기능 탑재" 단계이지
  "유료화 확정" 단계에 이르지 못한 회사가 다수다 — 이 자체를 "2026년 확인 자료 없음"으로 명시해
  둔다.**

### 4. 손익구조 영향 — 마진·CLV 정량 데이터는 빈약, "공시되지 않는다"는 사실 자체가 중요한 발견

- McKinsey의 가전 D2C 관련 인사이트 글(제목: "Direct-to-consumer e-commerce in appliances: A
  strategic growth opportunity")은 D2C·구독이 CLV와 마진 개선에 기여한다는 방향성을 제시하지만,
  이번 세션에서는 원문 사이트(`mckinsey.com`)가 EGRESS_BLOCKED로 직접 열람이 막혀 구체 수치를
  확인하지 못했다 — **인용은 제목·URL만 명시하고, 수치 인용은 하지 않는다(unverified).**
  (source: [McKinsey(원문 미확인)](https://www.mckinsey.com/industries/consumer-packaged-goods/our-insights/direct-to-consumer-e-commerce-in-appliances-a-strategic-growth-opportunity))
- 일반 구독경제 벤치마크(TSIA 등, **가전업계 전용 데이터가 아님을 명시**)에서는 서비스 계약형
  구독의 순이익 마진 목표를 45% 내외, 하드웨어 제품 마진을 30%대로 언급하는 자료가 있으나, 이는
  산업 전반의 통념 수준이며 가전 전용 실측 수치는 확인하지 못했다.
- → **"확인 자료 없음"이 많다는 사실 자체가 중요한 발견이다.** 가전업계는 아직 구독 매출을 별도
  공시하지 않고(구글·삼성 모두), 마진 개선 효과를 정량 검증한 공개 자료도 부족하다 — 이는 구독
  전환이 아직 투자자·애널리스트에게 재무적으로 증명되지 않은 초기 단계에 있다는 신호로 해석해야
  한다.

### 5. 소비자 수용도 — "AI 기능 자체"에 대한 지불의향은 낮고, 정체되어 있다 (2026년 자료 기준)

- **2026년 기준 헤드라인 — Bank of America Institute 분석(2026년 2월 결제데이터 기준, 보도 확산일
  2026-04-02/2026-06-27): 미국 가구의 약 3%만이 AI 서비스에 실제로 비용을 지불**하고 있으며, 지불
  가구의 월 지출 중앙값은 $20. 2024년 평균 대비 AI 관련 결제 가구 수는 38% 증가했고, 월 $21~40
  지출 구간 가구 비중은 2024년 대비 50% 증가, 지불 가구의 7%는 월 $100 이상 지출 — 즉 "쓰는 사람은
  더 쓰지만, 애초에 쓰는 사람 자체가 소수"라는 구조.
  (source: [Bank of America Institute 공식](https://institute.bankofamerica.com/economic-insights/consumer-ai-usage.html), [Moneywise(2026-06-27 보도)](https://moneywise.com/news/top-stories/ai-subscribers-households-bank-america-2026), [Baltimore Sun(2026-04-02 보도)](https://www.baltimoresun.com/2026/04/02/can-consumers-support-ai-just-3-of-households-are-paying-subscribers/))
- **스마트홈 특화 조사(2025년 자료 — 배경 참고용으로만 인용, 헤드라인으로 쓰지 않음)**: Parks
  Associates가 2025-07-15 발표한 "AI in the Smart Home" 연구(미국 8,000가구 대상)는 응답자의
  42~52%가 안전·보안·편의 기능을 제공하는 AI 스마트홈 어시스턴트에 월 구독료를 지불할 의향이
  있다고 답했다고 보고했다. 선호 가격대는 월 $10 이하가 가장 많고(24%), 월 $20 초과 지불 의향은
  7%에 불과. 이미 생성형 AI 앱에 비용을 지불 중인 가구의 75%는 스마트홈 AI 서비스에도 지불할
  의향이 있다고 답해, "이미 AI 구독 습관이 있는 소수"에 편중된 수요 구조를 시사한다. **이 조사는
  2025년 자료이므로 2026-only 원칙에 따라 본문 헤드라인 통계로는 쓰지 않고, 위 2026년 BofA
  데이터를 보완하는 배경 참고로만 인용한다.**
  (source: [Parks Associates(2025-07-15)](https://www.parksassociates.com/products/smart-home-products-and-services/ai-in-the-smart-home-applications-and-consumer-perceptions), [PR Newswire(2025)](https://www.prnewswire.com/news-releases/parks-associates-up-to-52-of-consumers-are-willing-to-pay-a-monthly-fee-for-an-ai-smart-home-assistant-that-offers-security-convenience-and-automation-use-cases-302505001.html))
- **[2026-09-21 verifier 정정] "국내 가전구독 시장(전체) 매출 2.48조원"이라는 서술은 부정확하다 —
  실제로는 LG전자 한 회사의 2025년 연간 가전구독 사업 매출이다.** 재검색 결과, 2조 4,800억원·전년
  대비 29% 성장 수치는 LG전자가 2026-01-30 2025년 4분기/연간 실적 컨퍼런스콜에서 발표한 **LG전자
  자체** 가전구독 매출이며(source: [데일리안](https://www.dailian.co.kr/news/view/1604753), [네이트뉴스(컨콜)](https://news.nate.com/view/20260130n26012), [헤럴드경제](https://biz.heraldcorp.com/article/10760749) 등 다수), 한국 가전구독 "시장 전체"(삼성·코웨이·쿠쿠·SK매직 등
  경쟁사 포함) 매출이 아니다. 실제로 한국 가전구독 시장 전체 규모는 이보다 훨씬 크다 — 전자신문
  보도(2025-09-17)에 따르면 2025년 **상반기만으로도 국내 시장이 3.5조원을 돌파**했다는 별도 집계가
  있어, LG 한 회사의 연간 2.48조원과는 카테고리가 다르다(source: [전자신문](https://www.etnews.com/20250917000333)). 아래 문단의 "AI 기능 자체가 아니라 하드웨어
  렌탈+케어서비스"라는 정성적 구분 자체는 LG전자 IR 자료·기사 내용과 일치해 타당하지만, 인용된
  숫자(2.48조원, 29%)는 "한국 가전구독 시장 전체"가 아니라 **"LG전자 자체 가전구독 사업의
  2025년 연간 매출"**로 재기술해야 한다. 즉 LG/삼성의 "가전구독"이 대부분 **하드웨어 초기비용
  분할납부(렌탈)+정기 케어서비스**(냉장고 도어 패널 교체, 세탁조 분해 세척 등 위생관리)를 의미하며,
  "AI 기능 자체"를 별도로 과금하는 SaaS형 구독이 아니라는 결론 자체는 유지하되, 근거 수치는 위와
  같이 정정한다. 한국 소비자가 받아들이는 것은 "목돈 부담 완화"이지 "AI 기능값 지불"이 아니라는
  해석도 유지한다.
  (source: [비즈워치(2026-06-02, 원문 EGRESS_BLOCKED으로 직접 대조는 못했으나 위 1차 소스들과
  수치가 일치)](https://news.bizwatch.co.kr/article/industry/2026/06/02/0041))
- → **종합: 공급 측(구글·삼성)은 AI 기능/API 접근권 자체를 유료화하는 쪽으로 빠르게 움직이고 있지만,
  수요 측 지불의향은 2026년 기준으로도 여전히 낮은 한 자릿수~십몇 퍼센트대에 머물러 있다. "구독으로
  전환하면 매출이 늘 것"이라는 가정은 아직 소비자 데이터로 뒷받침되지 않는다.**

## 사업적 시사점 (LG전자, 상세)

### 무엇을 유료화할 수 있는가 — 단계별 제안

1. **이미 검증된 것 (확장 여지 제한적)**: 하드웨어 렌탈+케어십형 구독(LG 시그니처/SKS 전용,
   정기방문 위생관리 등) — 이미 상당 규모로 운영 중이며 시장 자체도 성숙기에 근접(2026년 29%
   성장이 견조하지만, 이는 신규 카테고리 확장이라기보다 기존 렌탈 시장의 자연 성장일 가능성이 큼).
2. **다음 단계 — 이미 방향은 공식 언급됨, 가격·티어 설계가 남은 과제**: IFA 2026(2026-09-04)에서
   LG 노범준 임원이 씽큐 클로에 대해 "구독·커머스 모델을 검토 중"이라고 공식 언급했다 — 방향은
   맞으나 구체 가격·티어는 미정. 구글의 $10/$20 티어, 삼성의 개발자 $4.99 라인을 준거점으로 삼아,
   **(a) 가정용 AI 에이전트 구독**(가칭 "씽큐 클로 Plus", 월 $10~15대 유력 — 위 소비자 지불의향
   데이터(월 $10 이하 선호 24%, $20 초과 7%)를 감안하면 $20 이상은 초기 진입 장벽이 클 것으로
   판단)과 **(b) 개발자/파트너 API 접근료**(가칭, 월 $5대 — 삼성 사례를 준거로)의 투트랙으로
   설계할 것을 제안한다.
3. **유료화 후보 기능(구체적)**: 원격진단·예측정비(고장 예측 알림), 확장 저장(카메라/센서 이력
   장기보관 — 구글 Home Premium Advanced와 동일한 패턴), 고급 개인화(가족 구성원별 음성·선호
   프로파일), 커머스 연동(소모품 자동주문 — 이 경우 정액 구독료보다 거래수수료 모델이 더 적합할
   수 있음, 별도 검토 필요).

### 가격대

- 위 2026년 데이터(BofA: 지불 가구 월 지출 중앙값 $20이지만 전체 가구의 3%에 불과; Parks
  Associates 2025년 참고자료: 선호 상한선 $10 이하가 다수)를 종합하면, **국내외 모두 "AI 기능
  자체"에 대한 지불의향이 아직 검증되지 않은 상태**이므로 초기 고가 티어보다는 **"렌탈/구독 가입자에게
  AI 프리미엄 기능을 무료~저가로 번들해 습관화 → 이후 단계적 유료 전환"**하는 2단계 접근을 제안한다.
  이는 구글이 $99.99 스피커 구매자에게 6개월 무료체험을 얹었던 것과 동일한 패턴이다.

### 조직적으로 필요한 것

1. **구독과금 인프라**: 현행 렌탈 계약(할부·약정 기반)과는 별도로, 기능 단위 마이크로 과금(구독
   가입·해지·업그레이드·프로레이션 처리)이 가능한 SaaS형 과금 엔진이 필요하다. 이는 현재 렌탈
   조직(금융·물류 중심 역량)과는 다른 역량(프로덕트/그로스 조직)을 요구한다.
2. **리텐션 조직**: 현행 LG 렌탈은 "약정 기간+위약금" 구조로 이탈을 억제하는 방식인데, AI 기능형
   구독은 약정이 아니라 "가치 체감"으로 해지율(churn)을 낮춰야 한다 — 즉 계약 종속형이 아니라
   사용 데이터 기반의 습관형 리텐션(engagement 관리) 조직이 별도로 필요하다.
3. **데이터/API 팀**: 구글·삼성처럼 "에이전트 접근권"을 유료화하려면 그 전에 먼저 Open API/MCP를
   공개해야 한다(별도 파일 `home-ai-standard-war-2026-09-21.md`의 시사점과 직결). API 정책·요금
   정책·개발자 지원을 전담하는 조직이 현재 LG에 명확히 존재하는지는 이번 세션에서 확인하지 못했다 —
   후속 확인이 필요하다.

### 리스크

- 삼성 SmartThings의 API 유료화가 Home Assistant 등 오픈소스 커뮤니티의 반발을 낳은 사례처럼,
  LG가 앳홈(Athom) 인수 후 독립 유지를 약속한 호미(Homey)의 API를 유료화하면 "개방성"이라는 앳홈
  고유의 핵심 자산과 브랜드 신뢰가 함께 훼손될 위험이 있다. 유료화는 **앳홈/호미 계층이 아니라 LG
  자체 씽큐 클로 계층에서 먼저 시도**할 것을 권고한다.
- 소비자 지불의향이 낮은 상태(2026년 기준 미국 3%)에서 무리하게 고가 구독을 도입하면 오히려
  "AI 기능=돈 내야 하는 것"이라는 부정적 인식을 형성해 기능 자체의 채택률까지 떨어뜨릴 수 있다 —
  번들/무료체험 중심의 습관화 단계를 충분히 거친 뒤 유료 전환하는 순서가 중요하다.

## Open questions / gaps

- Google Home Premium의 실제 유료 구독자 수·매출 기여도는 이번 세션에서 확인하지 못했다(Google이
  공시하지 않음) — 향후 Alphabet 실적발표(10-Q/10-K, Q&A)에서 별도 언급이 있는지 추적 필요.
- Samsung DX 부문의 SmartThings 서비스 매출 비중은 별도 공시되지 않아 확인하지 못했다 — 삼성
  IR 자료 원문(`images.samsung.com` PDF 등) 직접 확인이 후속 세션에서 필요.
- 일렉트로룩스/AEG CamCook, 보쉬 Cook AI의 구독료 부과 여부·가격은 확인하지 못했다 — 각사 공식
  뉴스룸의 후속 발표 추적 필요.
- McKinsey의 D2C/구독-마진-CLV 관련 정량 수치는 원문 접근 차단(EGRESS_BLOCKED)으로 확인하지
  못했다 — 다음 세션에서 `mckinsey.com` 접근이 가능하면 재확인 필요.
- "AI 기능 구독 지불의향"에 대한 가전업계 전용(스마트폰이 아닌) 2026년 설문 데이터는 이번 세션에서
  찾지 못했다 — Parks Associates 등이 2026년에 동일 주제의 후속 조사를 발표했는지 후속 확인 필요.
- `techcrunch.com`, `www.mckinsey.com`, `www.emarketer.com`, `news.bizwatch.co.kr`(일부),
  `supple.kr`, `biz.heraldcorp.com` 등 다수 1차 소스가 이번 세션 환경에서 EGRESS_BLOCKED로 직접
  열람이 막혀 WebSearch 스니펫 기반으로만 인용했다 — 원문 대조 재확인 필요.
