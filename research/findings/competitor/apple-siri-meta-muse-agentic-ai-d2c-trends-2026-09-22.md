# Apple Siri AI 에이전틱 개편 · Meta Muse · 기기/서비스 간 AI 연동 및 D2C 확장 — 경쟁사·업계 리서치
Date: 2026-09-22
Scope: (1) Apple Siri AI의 LLM 기반 재설계(발표일·출시일·실제 크로스앱 실행 범위), (2) Meta의
신규 개인 에이전틱 AI 제품 "Muse"의 정체 규명 및 스마트홈/D2C 관련성, (3) 기기 간·서비스 간 AI
연동 및 제조사 D2C 확장의 업계 전반 시그널(에이전틱 결제 프로토콜, 가전사 자체 D2C AI 사례 등).
기존 파일(`apple-connectivity-ecosystem-deep-dive-2026-09-22.md`, `home-ai-standard-war-2026-09-21.md`,
`samsung-bixby-perplexity-appliance-update-2026-09.md`, `google-gemini-for-home-2026-updates-2026-09-21.md`,
`xiaomi-human-car-home-ecosystem-deep-dive-2026-09-22.md`)와 중복되는 내용(HomeKit 가전 생태계,
CarPlay Ultra, App Intents/SiriKit 폐기, Apple-Google $1B/년 Gemini 라이선스 계약, 4사 자체모델 vs
외부파트너십 비교)은 재조사하지 않고 참조만 함. 원칙: "출시/발표"는 정확한 날짜(YYYY-MM-DD) 기재,
"현재 이렇다"는 헤드라인 비교는 2026년 발표 자료만 사용.

## Key findings

### 1. Apple Siri AI — 발표(2026-06-08)와 소비자 출시(2026-09-14)는 별개 시점, 실제 크로스앱 실행은 제한적 "에이전틱"

- **발표: 2026-06-08(WWDC 2026), 개발자 프리뷰.** Apple Newsroom "Apple introduces Siri AI, a
  profoundly more capable and personal assistant"에서 최초 공개. 이는 기존 파일
  `home-ai-standard-war-2026-09-21.md`에도 "2026-06(정확한 일자는 애플 뉴스룸 상 '2026년 6월'로만
  확인)"이라고 적혀 있었으나, 이번 조사에서 **정확한 날짜가 2026-06-08(WWDC 기조연설일)임을
  확정**했다.
  (source: [Apple Newsroom(2026-06-08 발표)](https://www.apple.com/newsroom/2026/06/apple-introduces-siri-ai-a-profoundly-more-capable-and-personal-assistant/))
- **소비자 출시: 2026-09-14, iOS 27·iPadOS 27·macOS 27·watchOS 27·visionOS 27과 함께 정식 배포.**
  단 **베타 상태**로 출시됐고, 일일 사용량 한도(daily usage caps)가 걸려 있으며, Apple은 향후
  "확장 접근(expanded access)"을 유료로 제공하겠다고 예고했으나 구체적 가격·출시일은 밝히지
  않았다. iCloud+ 상위 요금제에 이 확장 접근이 포함될 것이라고만 언급.
  (source: [Apple Newsroom(2026-09-14 출시)](https://www.apple.com/newsroom/2026/09/siri-ai-a-profoundly-more-capable-and-personal-assistant-is-here/), [AppleInsider(2026-09-09, 사용량 한도·유료화 예고)](https://appleinsider.com/articles/26/09/09/siri-ai-will-launch-in-beta-complicated-by-daily-usage-caps-future-paid-access), [MacRumors(2026-09-09)](https://www.macrumors.com/2026/09/09/apple-siri-ai-usage-limits/), [Engadget(2026-09-14 출시 확정)](https://www.engadget.com/2254005/ios-27-with-siri-ai-will-be-available-on-september-14/))
- **언어·지역 제한: 영어만으로 출시, 프랑스어·일본어·한국어·포르투갈어·스페인어는 2026-10 지원
  예정(정확한 날짜 미확인 — 2026년 10월 중으로만 확인).** EU는 DMA(디지털시장법) 이슈로 **iOS
  27·iPadOS 27·watchOS 27에서는 Siri AI가 제외**되고, **macOS 27·visionOS 27에서는 이용 가능**하다
  — 즉 "EU 전체 무기한 연기"가 아니라 **플랫폼별로 차등 적용**된다는 것이 2026-09-14 실제 출시
  시점에 확정된 세부 내용이다(기존 파일에는 2026-06-08 발표 시점의 "EU 무기한 연기" 사실만 있었고,
  Mac/Vision Pro는 예외라는 점은 이미 명시돼 있었으나 watchOS까지 포함해 이번에 재확인).
  (source: [ppc.land(Apple ships Siri AI to EU Macs but not to EU iPhones)](https://ppc.land/apple-ships-siri-ai-to-eu-macs-but-not-to-eu-iphones/), [MacObserver(Mac/EU 예외)](https://www.macobserver.com/tips/round-ups/siri-ai-mac-eu-exclusion-macos-absent/), [gagadget(2026-09-14, US/UK 출시·EU 배제)](https://gagadget.com/en/725942-ios-27-is-out-now-siri-ai-arrives-for-us-and-uk-but-the-eu-gets-left-behind/))
- **실제 확인된 크로스앱 시나리오(과장 없이) — "1회 사용자 요청 → 백엔드에서 여러 앱에 걸친
  다단계 실행"이 확인됨:**
  1. 가족이 메시지(Messages)에서 언급한 활동을 찾아, 메일(Mail)에서 관련 안내문을 가져오고,
     필요한 재료를 미리 알림(Reminders)에 추가 — **3개 앱(Messages→Mail→Reminders)에 걸친 실행이
     한 번의 자연어 요청으로 이뤄짐**. 이는 "온스크린 인식"이 아니라 "개인 컨텍스트(personal
     context)" 기능이 여러 앱의 개인 데이터를 검색·연결·실행까지 하는 사례로, 실제 자율적 다단계
     실행이 확인되므로 "에이전틱"이라 표기할 수 있는 근거가 된다.
  2. 온스크린 인식(onscreen awareness): 스포츠 웹사이트를 보다가 "다가오는 홈경기를 캘린더에
     추가해줘"라고 요청하면, 화면의 텍스트를 읽고 날짜를 수동 복사할 필요 없이 캘린더 앱에 일정을
     추가 — 웹페이지→캘린더 앱 실행이라는 크로스앱 액션.
  3. 카메라+개인 컨텍스트 결합: 과일가게에서 카메라로 두 상자의 복숭아를 비추고 "엄마가 보낸
     레시피에 어느 쪽이 맞아?"라고 물으면 Mail의 레시피와 카메라 이미지를 대조해 답변 — 단, 이
     사례는 **답변만 하고 실행(액션)은 하지 않으므로 "에이전틱"이 아니라 "멀티모달 질의응답"**으로
     구분해야 한다(과장 방지).
  (source: [iClarified(2026, 베타 기능 상세)](https://www.iclarified.com/102225/apple-launches-siri-ai-beta-with-personal-context-onscreen-awareness-and-app-actions), [TechRepublic("7 Things You Can Actually Do")](https://www.techrepublic.com/article/news-siri-ai-ios-27-features/), [MacObserver(Personal Context 상세)](https://www.macobserver.com/tips/round-ups/siri-ai-personal-context-what-apple-says-it-can-see/), [Apple Newsroom(2026-06-08)](https://www.apple.com/newsroom/2026/06/apple-introduces-siri-ai-a-profoundly-more-capable-and-personal-assistant/))
- **자율성 수준에 대한 정확한 평가**: 위 사례들은 모두 **사용자가 매번 자연어로 명령을 내려야
  시작되는 "요청 기반 다단계 실행(request-triggered multi-step execution)"**이지, 사용자 개입 없이
  백그라운드에서 스스로 목표를 설정해 지속 작업하는 "자율 에이전트"는 아니다. 아래 2번 항목의
  Meta Muse(사용자가 앱을 연결해두면 이후 최소 감독으로 지속 작업)와는 자율성 수준에서 뚜렷한
  차이가 있다 — Siri AI는 "단발성 명령의 다단계 백엔드 처리", Muse는 "연결 후 지속적 대행"에 더
  가깝다. 이 차이를 뭉뚱그려 둘 다 동일하게 "에이전틱 AI"로 부르면 자율성 수준을 과장하게 되므로
  구분해서 서술한다.

→ **종합**: LG전자 맥락에서 중요한 것은 Siri AI가 "가전 제어"에 쓰이는 사례가 아니라(가전
브랜드는 HomeKit에 없음 — 기존 파일 참고), **"여러 개인 데이터 소스·앱에 걸친 단일 자연어 요청의
다단계 실행"이라는 UX 패턴 자체**다. LG의 씽큐 클로(ThinQ Claw) 등 자사 에이전트가 목표로 할
수준의 참고 벤치마크가 된다.

### 2. Meta "Muse" — 2026-09-08 미국 출시, 스마트홈 포함 9개 카테고리 연동, 가전 브랜드 직접 연동은 미확인

- **정체 규명**: 사용자가 언급한 "메타의 뮤즈"는 **Meta의 신규 개인 AI 에이전트 "Muse"**로 확정.
  이름이 비슷한 다른 후보(뮤직 관련 프로젝트, Ray-Ban 스마트글라스 코드명 등)는 검색 결과 이
  제품과 혼동될 만한 별도 실체가 확인되지 않았다 — "Muse"가 유일하고 명확한 매치.
- **출시일: 2026-09-08, 미국 우선 출시(18세 이상), 웹(muse.ai)·iOS·Android 앱·WhatsApp 챗봇으로
  제공.** 향후 Meta의 AI 안경(Ray-Ban 등)에도 탑재 예정이라고 Meta가 밝힘(정확한 날짜 미정).
  기반 모델은 Meta Superintelligence Labs의 첫 플래그십 모델 **Muse Spark(1.3, 100만 토큰 컨텍스트
  윈도우)로, 2026-09-02에 별도 공개**됐다(Muse 출시보다 6일 앞선 모델 공개).
  (source: [Meta Newsroom(2026-09-08 발표)](https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/), [TechCrunch(2026-09-08)](https://techcrunch.com/2026/09/08/meta-debuts-its-muse-ai-agent-will-consumers-trust-it/), [Axios(2026-09-08)](https://www.axios.com/2026/09/08/meta-debuts-muse-personal-ai-agent), [Bloomberg(2026-09-08)](https://www.bloomberg.com/news/articles/2026-09-08/meta-announces-muse-ai-agent-for-personal-tasks-and-organization), [Engadget(사용 가이드)](https://www.engadget.com/2256577/how-to-get-started-with-meta-s-new-ai-agent-muse/))
- **연동 카테고리: 이메일·캘린더·결제·건강/피트니스·쇼핑·스마트홈·외식·음악·이벤트 등 최소
  9개 영역.** 사용자가 앱/서비스를 하나씩 개별적으로 옵트인 연결해야 하며, 언제든 접근 권한을
  회수할 수 있다("opt-in 투명성" 구조). 공식 API가 없는 서비스는 사용자가 제공한 자격증명으로
  접속하거나 브라우저 접근으로 대체하며, Muse가 자체 보안 VM("Muse Secure VM", 전용 브라우저 탑재)
  위에서 직접 통합 코드를 작성·실행하는 "커스텀 커넥터" 기능까지 지원한다.
  (source: [TechCrunch(2026-09-08)](https://techcrunch.com/2026/09/08/meta-debuts-its-muse-ai-agent-will-consumers-trust-it/), [Meta Newsroom](https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/))
- **스마트홈 연동의 구체 실체는 "브랜드 네이티브 통합"이 아니라 "범용/브라우저 기반" — 가전
  브랜드 공식 파트너십은 확인되지 않음.** 재검색 결과 SmartThings·Google Home·Alexa 등 특정
  스마트홈 플랫폼과의 공식 커넥터가 출시 시점에 기본 탑재됐다는 1차 출처는 찾지 못했다.
  아이폰 Muse 앱에서 "보낼 수 있는 스마트홈 명령 목록을 나열하도록" 지시할 수 있다는 사용법
  소개만 확인됐고, 실제로는 사용자가 각 서비스의 공개 API 키를 직접 제공하거나 Muse가 브라우저로
  해당 서비스 웹앱을 조작하는 방식일 가능성이 높다 — **"메타가 가전사와 직접 제휴해 스마트홈을
  지원한다"는 근거는 이번 조사에서 확인되지 않았고, unverified로 남긴다.**
  (source: WebSearch 종합, 원문 1차 대조 실패 — about.fb.com·ai.meta.com·techcrunch.com이 이번
  세션 환경에서 EGRESS_BLOCKED로 직접 열람 불가)
- **가격: 무료 티어 + 유료 2단계("Power" $20/월, "Maximum" $100/월)**, 사용량에 따라 상위 티어로
  유도하는 구조. Meta는 대다수 사용자가 무료 티어에 머물 것으로 예상한다고 밝힘.
  (source: [datacamp.com](https://www.datacamp.com/blog/muse-agent), [tech-insider.org](https://tech-insider.org/meta-muse-personal-ai-agent-launch-2026/))
- **D2C 관련 파트너십: Shopify와의 제휴로 "Shop Pay" 기반 에이전틱 체크아웃 지원, 2026-09
  발표(구체 일자 미확인 — Muse 출시일 전후로 추정).** Universal Commerce Protocol을 매개로 Muse가
  Shopify 카탈로그를 탐색해 사용자 대신 구매까지 완료할 수 있고, **Shopify 입점 판매자(머천트)는
  기본값으로 Muse에서 발견·구매 가능한 상태**가 된다 — 이는 제조사·브랜드가 대형 리테일 플랫폼을
  거치지 않고 AI 에이전트를 새로운 소비자 접점(distribution channel)으로 활용할 수 있게 된
  사례로, LG가 관심 갖는 D2C 확장과 직접 관련된다. 대조적으로 **Amazon은 자사 쇼핑 사이트에서
  Muse의 접근을 차단**했다(2026-09-21 보도) — 대형 마켓플레이스가 서드파티 에이전트에 문을 닫는
  긴장 관계도 함께 나타나고 있다.
  (source: [The Register(2026-09-21, Amazon이 Muse 차단)](https://www.theregister.com/ai-and-ml/2026/09/21/amazon-shows-metas-muse-ai-shopping-agent-the-door/5297777), [thepaypers.com(Shopify-Muse Shop Pay 제휴)](https://thepaypers.com/payments/news/meta-partners-with-shopify-to-bring-shop-pay-checkout-to-muse-ai), [Seeking Alpha](https://seekingalpha.com/news/4645292-meta-shopify-team-up-to-enable-purchases-through-muse-ai))
- **신뢰·보안 리스크가 출시 직후부터 불거짐(2026-09).** 상원 소위원회 청문회에서 전직 Meta UX
  리서처가 "Meta는 자사 제품의 안전성·사용 실태에 대해 진실을 말한다고 신뢰할 수 없다"고 증언;
  설문에서 응답자의 58%가 "어떤 AI 에이전트에도 비밀번호를 공유하지 않겠다"고 답함; 보안연구자
  Patrick Wardle이 macOS 앱에서 로컬 소프트웨어가 음성 전사 처리 위치를 바꿀 수 있는 제로데이
  취약점을 발견; Meta 내부 직원 테스트에서도 개인정보 노출·불안정 동작 등의 결함이 출시 전부터
  제기됐다는 보도.
  (source: [Forbes(2026-09-09)](https://www.forbes.com/sites/gabrielalinzainescu/2026/09/09/meta-launches-muse-personal-ai-agent-as-staff-flag-security-flaws/), [CNBC(2026-09-08)](https://www.cnbc.com/2026/09/08/meta-personal-ai-agents-public-reckoning-privacy-safety.html), [TechTimes(제로데이, 2026-09-21)](https://www.techtimes.com/articles/327842/20260921/meta-muse-ai-assistant-suffers-zero-day-vulnerability-despite-promise-privacy-security.htm))
- **가전/디바이스 맥락 판단**: Muse는 **소셜/커머스/개인비서 영역의 제품이지 가전·디바이스
  제조업과는 무관**하다 — Meta가 하드웨어(Ray-Ban 스마트글라스 등)를 만들긴 하지만 Muse 자체는
  냉장고·세탁기 같은 가전을 직접 제어하는 제품이 아니다. 다만 "스마트홈"을 연동 카테고리 중
  하나로 공식 포함시켰다는 사실 자체는, **가전 제어권이 이제 가전사의 자체 앱이 아니라 범용
  개인 AI 에이전트로 이동할 수 있다는 압력**을 보여주는 신호로서 LG에 시사점이 있다(아래 LG전자
  시사점 참고).

→ **종합**: Meta Muse는 "여러 브랜드/앱/디바이스에 걸쳐 사용자를 대신해 행동하는 에이전트"의
2026년 최신 사례이자, "제조사가 유통사(Amazon)를 우회해 에이전트(Muse)·플랫폼(Shopify)을 통해
소비자에 직접 도달"하는 D2C 신호이기도 하다. 단, 스마트홈 연동이 가전 브랜드와의 공식 파트너십
기반인지, 범용 API/브라우저 기반의 임시방편인지는 이번 조사에서 확정하지 못했다(Open questions).

### 3. 기기 간·서비스 간 AI 연동 및 D2C 확장 — 업계 전반 시그널(2026년)

- **에이전틱 결제 프로토콜이 2026년 들어 실사용 단계로 진입 — 이는 "기기가 스스로 소비자 대신
  구매를 실행"하는 인프라의 토대다.**
  - **Mastercard "Agent Pay for Machines"(AP4M)가 2026-06-10 정식 출시.** 이는 사람이 매번
    승인하는 소액 반복 결제가 아니라, **기기/시스템 간 고빈도·저액 자동 결제를 디지털 백그라운드에서
    지속 실행**하도록 설계된 프로토콜이다(예: 재고 소진 시 자동 재주문 같은 시나리오에 적용 가능한
    구조). 30개 이상 기업(Coinbase, Stripe, Adyen 등)이 참여했고, 에이전트 권한·자격증명은 초기에
    Polygon·Solana·Base 블록체인에 기록되는 방식으로 시작했다.
    (source: [Mastercard 공식(2026-06-10)](https://www.mastercard.com/us/en/news-and-trends/press/2026/june/mastercard-launches-agent-pay-for-machines.html), [Fortune(2026-06-10)](https://fortune.com/2026/06/10/mastercard-ai-payments-protocol-launch-agentic-finance/), [CoinDesk(2026-06-10)](https://www.coindesk.com/business/2026/06/10/mastercard-prepares-for-a-future-where-ai-agents-make-payments-with-latest-introduction))
  - **Mastercard·Santander·PayOS가 2026-03(정확한 날짜 미확인 — 2026년 3월 중으로만 확인) 유럽
    최초의 "AI 에이전트가 은행의 실제 결제 인프라를 통해 완결한 실거래(live end-to-end payment)"를
    성사시켰다.** 파일럿 단계를 넘어 실제 은행 인프라 기반 거래라는 점에서 유의미하다.
    (source: [ffnews.com](https://ffnews.com/newsarticle/mastercard-launches-agent-pay-for-machines-to-unlock-super-fast-always-on-payments/) — Santander/PayOS 실거래 사실은 이 기사에서 언급된 것으로, 원 발표 1차 출처는 이번 조사에서 별도 확정하지 못함, Open question 참고)
  - **Visa Trusted Agent Protocol(TAP)은 2026년 초 기준 파트너 100개 이상, 그중 30개 이상이
    샌드박스 테스트, 20개 이상이 프로덕션 통합 중.** 단, 이 수치의 정확한 발표일(YYYY-MM-DD)은
    확정하지 못했고("2026년 초"라는 스니펫 정보로만 확인) 2025-12-18 Visa 공식 발표(배경정보,
    2025년 자료라 헤드라인에는 미사용)에서 "2026년 홀리데이 시즌까지 수백만 소비자가 AI 에이전트로
    구매를 완료할 것"이라 전망했다는 점만 배경으로 남긴다.
    (source: [Visa 공식(2025-12-18, 배경정보)](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.21961.html) — 2026년 파트너 수 확정 1차 출처는 Open question)
  - **2026년 확인 자료 없음**: 위 결제 프로토콜들이 실제 "가전제품이 스스로 소모품(세제·필터·
    잉크 등)을 재주문"하는 구체적 상용 사례로 이어졌다는 2026년 발표는 이번 조사에서 찾지 못했다
    — 인프라는 갖춰졌으나 가전 적용 사례는 아직 공개되지 않은 것으로 보인다.
- **가전업계 자체의 D2C+AI 결합 사례 — GE Profile "Kitchen Assistant" 냉장고(2026-01-02 CES 2026
  공개, 2026-04 출시 예정, MSRP $4,899).** LG의 직접 경쟁사인 GE Appliances(Haier 소유)가
  내놓은 사례로, (1) 외장 디스펜서에 내장된 바코드 스캐너로 스캔한 품목을 SmartHQ 앱의 장보기
  목록에 자동 추가하고 **Instacart(식료품 배달 서비스)와 직접 동기화**해 주문·배송까지 이어지는
  구조, (2) 크리스퍼 서랍을 카메라로 촬영해 재고를 파악하는 "FridgeFocus", (3) Taste of Home 등
  외부 레시피 매체와의 통합. **"냉장고 자체가 식료품 재주문·배송의 진입점이 되는" 구조는 가전
  제조사가 유통(마트)을 거치지 않고 소비자의 소비 행위 자체에 AI로 직접 개입하는 D2C 확장의
  구체적 예시**다.
  (source: [BusinessWire(2026-01-02)](https://www.businesswire.com/news/home/20260102642086/en/GE-Profile-Unveils-Game-Changing-Smart-Refrigerator-with-Kitchen-Assistant-Revolutionizing-Grocery-Shopping-and-Meal-Planning), [TWICE(CES 2026)](https://www.twice.com/product/appliances/kitchen/ge-profile-introduces-new-smart-refrigerator-with-kitchen-assistant), [Abt Blog](https://www.abt.com/blog/ces-2026-ge-profile-smart-refrigerator-kitchen-assistant))
- **"제조사 → 에이전트 → 소비자" 직접 채널이 대형 마켓플레이스 우회 수단으로 부상 — Amazon의
  Muse 차단(위 2번 항목)이 역설적으로 이를 보여준다.** Amazon이 자사 사이트에서 제3자 에이전트
  접근을 막는 동안, Shopify는 반대로 입점 브랜드를 Muse에 노출시켜 "마켓플레이스 없이 에이전트로
  직접 판매"하는 경로를 열었다. 이는 향후 가전 제조사가 자사 D2C 채널(예: LG의 자사몰)을 AI
  에이전트에 노출시킬지, 아니면 Amazon처럼 문을 닫을지에 대한 전략적 선택지가 이미 업계에서
  갈리기 시작했음을 뜻한다.

## LG전자 시사점 (기기 간 서비스/D2C 관점) — 사실과 명확히 구분

*아래는 위 사실관계를 근거로 한 리서치자의 해석이며, 사실(finding)이 아니라 시사점(implication)이다.*

1. **Apple Siri AI의 "1회 요청 → 여러 앱에 걸친 다단계 실행" 패턴은 LG의 씽큐 클로(ThinQ Claw) 등
   자사 에이전트 UX 설계의 구체적 참조점이 될 수 있다.** 단, Siri AI도 아직 "사용자가 매번 명령을
   내려야 하는" 수준이라는 점에서 LG가 이보다 한 단계 더 나아간 "가전 상태 기반 선제적 제안"을
   차별화 포인트로 삼을 여지가 있다.
2. **Meta Muse가 "스마트홈"을 범용 개인 AI 에이전트의 표준 연동 카테고리로 공식 편입시킨 것은,
   가전 제어의 진입점이 가전사 자체 앱(ThinQ 등)에서 벗어나 제3자 범용 에이전트로 이동할 수
   있다는 압력 신호다.** 단, 이번 조사에서는 Muse-가전 브랜드 간 공식 파트너십이 확인되지
   않았으므로, 이 압력이 "임박한 위협"인지 "아직 먼 가능성"인지는 후속 확인이 필요하다(Open
   questions 참고). LG 입장에서는 (a) 자체 에이전트 경쟁력을 키우거나 (b) 오히려 Muse류 범용
   에이전트에 씽큐 API를 개방해 새로운 접점으로 활용하는 두 갈래 선택지가 있다.
3. **GE Profile의 "냉장고=재주문 진입점" 모델은 LG가 이미 하는 것(ThinQ 앱 내 소모품 주문 등,
   자사 리서치 영역이라 이 파일에서는 다루지 않음)과 얼마나 격차가 있는지 own-company-research
   에이전트가 비교해볼 가치가 있다.** 특히 "바코드 스캔 → 외부 배송 서비스(Instacart) 직접
   동기화"라는 구체적 UX 디테일은 벤치마킹 대상이다.
4. **Mastercard Agent Pay for Machines처럼 "기기가 스스로 결제까지 실행"하는 인프라가 2026년에
   실사용 단계로 들어섰다는 사실은, LG가 가전-소모품 자동재주문형 구독모델(기존 파일
   `appliance-subscription-business-model-shift-2026-09-21.md` 참고)을 설계할 때 결제 프로토콜
   계층까지 함께 검토해야 함을 시사한다** — 단, 2026년 시점 가전 적용 실사례는 아직 확인되지
   않았으므로 "지금 당장 채택 가능"이 아니라 "인프라가 막 갖춰지기 시작한 단계"로 이해해야 한다.
5. **Amazon의 Muse 차단 vs Shopify의 Muse 개방이라는 상반된 선택은, LG도 향후 자사 D2C 채널을
   AI 에이전트(자사든 타사든)에 얼마나 개방할지에 대한 전략적 결정이 필요함을 보여준다.** 이는
   순수 사실이 아니라 유추이므로, 사업전략 논의 시 별도 검증이 필요하다.

## Open questions / gaps

- **Meta Muse의 스마트홈 연동이 SmartThings·Google Home·Alexa 등과 공식 파트너십을 맺은 것인지,
  아니면 사용자 제공 API 키/브라우저 기반의 범용 방식인지 1차 출처로 확정하지 못했다.** about.fb.com,
  ai.meta.com이 이번 세션에서 EGRESS_BLOCKED로 직접 열람 불가했던 것이 원인 — 후속 세션에서
  프록시 우회 없이 접근 가능한 환경에서 원문 대조가 필요하다.
- **Shopify-Muse Shop Pay 제휴의 정확한 발표일(YYYY-MM-DD)을 확정하지 못했다** — Muse 출시일
  (2026-09-08) 전후로 발표된 것으로 추정되나 원문 1차 대조 미완료.
- **Mastercard·Santander·PayOS의 "유럽 최초 AI 에이전트 실거래" 정확한 날짜(2026년 3월 중으로만
  확인)와 1차 출처(Mastercard/Santander 공식 보도자료)를 확정하지 못했다.**
- **Visa TAP의 "파트너 100개 이상" 수치의 정확한 발표일을 확정하지 못했다** — "2026년 초"라는
  스니펫 정보로만 확인, 2026년 신규 공식 발표 원문 대조 필요.
- **가전제품이 Mastercard Agent Pay for Machines나 Visa TAP 같은 프로토콜을 실제로 채택해
  소모품을 자동 재주문한 2026년 상용 사례는 이번 조사에서 찾지 못했다** — "2026년 확인 자료
  없음"으로 명시. 후속 세션에서 CES 2026/IFA 2026 발표 중 이런 사례가 있었는지 재확인 필요.
- Apple Newsroom(apple.com), about.fb.com, ai.meta.com, techcrunch.com 등 다수 1차 소스 도메인이
  이번 세션 환경에서 EGRESS_BLOCKED로 직접 열람이 안 되어, WebSearch 스니펫 및 2차 매체 인용으로
  교차 확인했다 — 가능하면 후속 세션에서 원문 대조가 필요하다.
