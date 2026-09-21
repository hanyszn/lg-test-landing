# 토스·배달의민족·미국 대응 기업 UX 벤치마크 — 경쟁사/업계 UX 우수사례 리서치
Date: 2026-09-21
Scope: **가전 경쟁사 리서치가 아니라 "UX 우수사례(잘하는 UX) 벤치마크" 트랙**
(`ux-ai-capability-research` 스킬 범위, AB180 사례
`research/findings/competitor/ab180-claude-code-gtm-sales-automation-2026-09-20.md`와 동일한
"업종 무관 UX 참고 사례" 성격). 조사 대상은 (1) 토스(비바리퍼블리카) — 디자인 시스템(TDS)과 UX
라이팅, (2) 배달의민족(우아한형제들) — 디자인 시스템/브랜드 아이덴티티(배민체 등)와 UX 라이팅,
(3) 두 회사와 프로필이 가장 근접한 미국 기업 각 1곳(Stripe — 토스 대응, Duolingo — 배민 대응)의
디자인 시스템·UX 관행. LG전자 자사 비교는 `own-company-research`가 이미 기록한
`webos-micro-ux-platform-2026-09-21.md`, `ux-design-system-webos-micro-2026-09-21.md`,
`ax-workflow-p2d-figma-plugin-2026-09-21.md`(이하 own-company 3건)를 참조해 아래 "내부 역량 강화
시사점"에서 구체적으로 대응시켰다.

**출처 접근성 주의**: 이번 세션의 네트워크 egress 정책상 `toss.tech`, `brunch.co.kr`, `velog.io`,
`techblog.woowahan.com`, `bcut.baemin.com`, `ditoday.com`, `designcompass.org`,
`tossmini-docs.toss.im`, `developers-apps-in-toss.toss.im`, `design.duolingo.com`,
`weeklyuxuichallenge.oopy.io`, `bailliegifford.com`, `designsystems.one` 등 다수 원문 도메인에
WebFetch로 직접 접근할 수 없었다(EGRESS_BLOCKED). 아래 내용 중 상당수는 WebSearch 도구가 반환한
요약 스니펫에 근거하며, 원문 전체 대조는 하지 못했다 — AB180 사례와 마찬가지로 **verifier 에이전트의
검증 전 단계**로 취급해야 한다. 스니펫만으로 확인된 항목은 개별적으로 명시했다.

## Key findings

- **토스는 TDS(Toss Design System)를 "디자이너 도구에 국한되지 않고 개발과 연결된 공통 언어"로
  운영하며, 화면 설계 시간 30~40분→3~4분, 코드량 50% 감소, 6개월간 약 4,500시간(562일) 절약이라는
  정량 성과를 공개했다.** (source: [토스 디자이너가 제품에만 집중할 수 있는 방법 — Toss Tech](https://toss.tech/article/toss-design-system), WebSearch 스니펫 기반 — 원문 직접 접근 불가, 수치의 산출 기준·시점은 별도 검증 필요)
- **[2026-09-21 verifier 정정] 토스는 UX 라이팅을 "8가지 라이팅 원칙"으로 시스템화했다** — 8개 전체
  확인됨: Predictable Hint(예측 가능한 힌트), Weed Cutting(의미 없는 단어 제거), Remove Empty
  Sentences(빈 문장 제거), Focus on Key Message(핵심 메시지에 집중), Easy to Speak(말하듯 쓰기),
  Suggest than Force(강요 대신 제안), Universal Words(보편적 단어 사용), Find Hidden Emotion(숨은
  감정에 공감). **원래 목록에 있던 "Mute Mute"는 verifier 재검증 결과 존재가 확인되지 않아
  삭제 — 같은 자리에 반복적으로 등장한 "Remove Empty Sentences"로 정정했다.** (source: [토스의
  8가지 라이팅 원칙들 — Toss Tech](https://toss.tech/article/21022) 등 다수 2차 정리 글의 WebSearch
  스니펫 종합, 2026-09-21 verifier가 독립 재검색으로 재확인)
- **토스는 Simplicity라는 자체 디자인 컨퍼런스를 운영한다** — 2021년 최초 개최, 2023년
  Simplicity23(2023.05.22, 23개 세션, UX리서처/라이터/인터랙션/브랜드/프로덕트/하드웨어 디자이너
  전 직군 참여), 2025년 후속 컨퍼런스도 확인됨. (source: [토스 디자인 컨퍼런스, Simplicity23](https://simplicity-23.toss.im/), [블로터 보도](https://www.bloter.net/news/articleView.html?idxno=601963))
- **배달의민족은 자사 서체("배민체" 계열, 한나체·주아체·도현체 등 11종 이상)를 SIL Open Font
  License 1.1로 완전 무료 배포**하며 상업적 사용·수정을 허용한다(폰트 파일 자체 판매만 금지).
  GitHub(`fonts-archive` 조직)에도 오픈소스로 공개돼 있다. (source: [배달의민족 폰트 다운로드](http://font.woowahan.com/), [GitHub - fonts-archive/BMHANNAPro](https://github.com/fonts-archive/BMHANNAPro))
- **배달의민족은 2020년 "배민사장님광장"(사장님용 셀프서비스 포털) 리디자인에서 약 50개 페이지,
  140개 다이얼로그, 150개+ API 엔드포인트 규모를 단순 가이드라인이 아니라 "프로토콜에 가까운"
  규칙 기반 디자인시스템으로 구축했고, 그 결과 기획자는 정책 정의에, 디자이너는 유저 플로우/UX
  개선에 집중하도록 역할을 재배분했다.** (source: [셀프서비스 디자인시스템 #1 — 디자이너 편](https://techblog.woowahan.com/6305/), [#2 — 개발자 편](https://techblog.woowahan.com/5327/), WebSearch 스니펫 기반 — 원문 직접 접근 불가)
- **배달의민족은 2025년 15주년을 맞아 "배민 2.0" 리브랜딩을 진행, 전용 컬러를 더 밝게 조정하고
  신규 서체 "워크체(WORK체)"(한글 빗침획을 블록 형태로 단순화)를 도입했다.** (source: [배달의민족, 15년 만에 '배민 2.0' 리브랜딩 — 디자인 나침반](https://designcompass.org/2025/07/23/baemin-2-rebranding/), 스니펫 기반)
- **Stripe의 내부 디자인시스템 명칭은 "Sail"이며 전체는 비공개(사내 전용)이나, 2022년 Stripe Apps
  출시와 함께 공개 컴포넌트 라이브러리 일부를 공식 문서(docs.stripe.com/stripe-apps/components)로
  공개했다.** Payment Element를 도입한 기업은 평균 11.9% 매출 증가를 기록했다(전환율이 아니라
  매출 지표임에 유의). **[2026-09-21 verifier 추가 확인] 이 11.9%는 `stripe.com/payments/elements`에서
  원문 그대로 확인됐으나, Stripe 자체 매칭 코호트(matched-cohort) 비교이지 무작위대조시험(RCT)이
  아니다 — 같은 연구로 보이는 이전 공식 발표에서는 10.5%로 제시된 적도 있고, "다른 관측되지 않은
  변화의 영향이 포함됐을 수 있다"는 Stripe 자체 단서도 있다. 2027 사업계획에 인용할 땐 이 방법론적
  단서를 함께 표기할 것.** (source: [Stripe 공식 리소스 — Build a streamlined checkout process](https://stripe.com/resources/more/streamlined-checkout-processes-how-to-boost-conversions-with-an-easier-checkout-flow), 2025.06.29 업데이트 기준, [Stripe Design System — DesignSystems.one](https://www.designsystems.one/design-systems/stripe-design) 스니펫)
- **Duolingo는 design.duolingo.com이라는 공식 디자인시스템 사이트에서 Voice/Tone 가이드까지
  공개한다.** Voice는 4가지 특성(Expressive·Playful·Embracing·Worldly)으로 고정하고, Tone은
  상황(맥락)에 따라 조정하는 "읽는 이의 상태를 읽는다(reading the room)"는 원칙을 명시한다.
  (source: design.duolingo.com/writing/voice, /writing/tone — WebSearch 스니펫 기반, 원문 직접
  접근은 EGRESS_BLOCKED로 불가)
- **Duolingo는 Apple/구글 수준의 공식 인증은 아니지만, 마스코트 캐릭터 "Duo"를 활용한 소셜미디어
  브랜드 보이스로 폭넓게 인용된다** — 예: 밸런타인데이 틱톡 답글이 127만 engagement 기록.
  "Play first, profile second"(가입 전에 먼저 앱을 체험시키는) UX 전략도 업계에서 자주 인용된다.
  (source: 여러 UX 케이스스터디 글의 WebSearch 스니펫 종합, 예: [UX Case Study: Duolingo — UsabilityGeek](https://usabilitygeek.com/ux-case-study-duolingo/))
- **Robinhood는 2015년 Apple Design Award, 2016년 Google Play "Best Use of Material Design"을
  수상**했지만, Stripe만큼 폭넓게 공개된 디자인시스템 문서 자산은 확인되지 않아 이번 조사에서는
  토스 대응 기업으로 Stripe를 우선 채택했다(선정 근거는 아래 Per-company notes 참조).
  (source: [Robinhood newsroom — The top secret Robinhood design story](https://newsroom.aboutrobinhood.com/the-top-secret-robinhood-design-story/), [Robinhood — Apple celebrates Robinhood's design](https://robinhood.com/us/en/newsroom/apple-celebrates-robinhoods-design))

## Per-company notes

### 토스 (Toss / 비바리퍼블리카)
- **TDS(Toss Design System)**: "토스 커뮤니티 전반의 공통 디자인 언어"로 정의되며, 디자이너·
  개발자·기획자가 같은 기준으로 협업하도록 함. 수백 개의 컴포넌트/템플릿으로 구성되고, 디자인
  도구에만 머물지 않고 개발과 직접 연결된 "제품을 구성하는 언어"로 운영됨. (source: [토스
  디자이너가 제품에만 집중할 수 있는 방법 — Toss Tech](https://toss.tech/article/toss-design-system))
- **파운데이션(Foundation)**: 레이아웃·컬러·타이포그래피·스페이싱·상태(state) 등을 토큰화. 자체
  디자인 에디터 "Deus"에 ShadowDOM 기반 스타일 격리를 적용하고, System/Light/Dark 컨텍스트 전환을
  지원한다고 스니펫에서 확인됨. 컬러 시스템은 "달리는 기차 바퀴 칠하기: 7년만의 컬러 시스템
  업데이트"라는 제목의 Toss Tech 아티클을 통해, 7년간 운영해온 컬러 토큰 체계를 대규모로
  개편한 사례가 존재함(제목만 확인, 본문 미확인). (source: WebSearch 스니펫 종합, [toss.tech/article/tds-color-system-update](https://toss.tech/article/tds-color-system-update))
- **UX Writing 조직 운영**: Simplicity23(2023.05.22) 세션에서 토스 UX Writer 김상훈이 "제품은
  수십 개인데 UX 라이터는 단 3명뿐"이라는 조직적 제약을, 동료(프로덕트 디자이너 등)의 라이팅
  역량을 끌어올리는 5가지 솔루션으로 해결했다고 발표. 즉 원칙 문서화(8가지 라이팅 원칙) +
  "보이스톤 메이커" 같은 셀프서비스 도구로 소수 라이터가 전사 콘텐츠 품질을 관리하는 구조.
  (source: [토스 디자인 컨퍼런스 SIMPLICITY 23 세션 정리 — velog](https://velog.io/@jsyun0412/%ED%86%A0%EC%8A%A4-%EB%94%94%EC%9E%90%EC%9D%B8-%EC%BB%A8%ED%8D%BC%EB%9F%B0%EC%8A%A4-SIMPLICITY-23-UX-Writing-%ED%98%BC%EC%9E%90%EA%B0%80-%EC%95%84%EB%8B%8C-%ED%95%A8%EA%BB%98-%EC%9E%98-%EC%93%B0%EA%B8%B0), 스니펫 기반)
- **UX 라이팅 핵심가치**: 명확함·간결함·친근함·존중·공감. 해요체(비격식체)를 전 맥락에서 일관
  적용, 능동태 위주 문장, 부정적 커뮤니케이션 최소화/긍정문 위주 서술. (source: WebSearch 스니펫,
  [UX 라이팅 — 앱인토스 개발자센터](https://developers-apps-in-toss.toss.im/design/ux-writing.html))
- **디자인 컨퍼런스 Simplicity**: 2021년 최초 개최 → 2023년 재개(Simplicity23) → 2025년 후속
  컨퍼런스까지 이어지는 정례 행사로 보임. "UX 플랫폼 트라이브" 산하에 그래픽디자인팀·프로덕트
  브랜딩팀·인터랙션팀·모바일플랫폼팀·UX라이팅팀 등으로 조직이 세분화돼 있다고 확인됨. (source:
  [토스 디자인 컨퍼런스, Simplicity23](https://simplicity-23.toss.im/), [한국금융신문 보도](https://www.fntimes.com/html/view.php?ud=202305241346347634ee0209bd21_18))

### 배달의민족 (우아한형제들)
- **배민체 서체군**: 김봉진 대표(디자이너 출신, 네이버·현대카드·네오위즈 경력)가 주도해 다수 서체를
  제작. font.woowahan.com에서 한나체·주아체·도현체·연성체·기랑해랑체·한나에어·한나프로·을지로체·
  을지로10년후체·을지로오래오래체·그리믈체 등 11종 이상을 무료 배포. SIL Open Font License 1.1
  적용으로 상업/비상업 목적의 사용·수정이 자유롭다(폰트 파일 자체의 재판매만 금지). GitHub
  `fonts-archive` 조직에 오픈소스로도 공개돼 있어, 사실상 디자인 자산을 외부 생태계(대학생, 기업
  마케팅, 과자 포장지, TV 자막 등)에 완전 개방한 사례. (source: [배달의민족 폰트 다운로드](http://font.woowahan.com/), [GitHub - fonts-archive/BMHANNAPro](https://github.com/fonts-archive/BMHANNAPro), [배민체 관련 브런치 글](https://brunch.co.kr/@businessinscdef/83) 스니펫)
- **셀프서비스 디자인시스템(2020, 배민사장님광장)**: 약 50개 페이지, 140개 다이얼로그, 10개+ API
  호스트, 150개+ REST/GraphQL 엔드포인트 규모의 사장님용 포털을 리디자인하며, "UI/UX 가이드라인 +
  UI 템플릿"을 넘어 프로토콜에 가까운 강한 규칙 기반 디자인시스템을 구축. 결과적으로 기획자는
  화면 설계 대신 시스템 정책 정의에, 디자이너는 유저 플로우/UX 개선에 더 많은 시간을 쓸 수 있게 됨.
  디자이너 관점/개발자 관점 2부작으로 기술블로그에 공개. (source: [셀프서비스 디자인시스템 #1 —
  디자이너 편](https://techblog.woowahan.com/6305/), [#2 — 개발자 편](https://techblog.woowahan.com/5327/), 스니펫 기반, 원문 미접근)
- **UX 라이팅**: 배민 첫 전담 UX 라이터(유다정) 합류 이전에도 프로덕트 디자이너들이 자체적으로 UX
  라이팅을 수행해왔고, 이후 전담 라이터가 합류해 "고객과 명확히 소통하는지" 점검·가이드로 전사
  일관성을 지키는 역할을 맡았다고 확인됨. (source: ["UX 라이팅, 배민은 이렇게 시작했어요" — bcut.baemin.com](https://bcut.baemin.com/6287/), 스니펫 기반)
- **[2026-09-21 verifier 확인] AI UX 라이터 "제민희"는 사람이 아니라 배민 사내 AI 라이팅 검토
  도구다.** "신입 UX라이터" 페르소나로 설계됐고, 이름 자체가 "제미나이(Gemini)"를 딴 말장난이다
  ("제미나이" → "제민희"). 우아한형제들이 UX 라이팅 검토 업무에 AI를 결합한 사내 도구/에이전트
  사례로, 앞서 정리한 "전담 UX 라이터(유다정)" 이후 단계의 AI 활용 사례로 볼 수 있다.
  (source: [techblog.woowahan.com/23836](https://techblog.woowahan.com/23836/), 스니펫 기반,
  2026-09-21 verifier가 독립 재검색으로 정체 확인)
- **브랜드 아이덴티티/2025 리브랜딩**: 대부분의 앱이 플랫 디자인 일색인 흐름 속에서 낙서 같은
  일러스트 아이콘과 자체 서체로 시각적 차별화를 확보. 2025년 15주년을 맞아 "배민 2.0" 리브랜딩을
  진행 — 전용 컬러를 더 밝게 조정하고 신규 서체 "워크체(WORK체)"(한글 빗침획을 블록 형태로
  단순화)를 도입, 앱 아이콘도 리디자인. (source: [배달의민족, 15년 만에 '배민 2.0' 리브랜딩 —
  디자인 나침반](https://designcompass.org/2025/07/23/baemin-2-rebranding/), [배민 앱 아이콘 리디자인 기사](https://designcompass.org/2025/11/25/the-unveiled-baemin-app-icon/), 둘 다 스니펫 기반, 원문 미접근)

### Stripe (미국 — 토스 대응 픽)
- **선정 근거**: 토스와 마찬가지로 "결제/송금이라는 신뢰가 핵심인 금융 UX"를 다루는 기업 중,
  Robinhood(디자인 어워드 수상 실적은 강하나 공개 디자인시스템 문서 자산이 상대적으로 빈약)와
  Cash App/Block(이번 조사에서는 深堀하지 않음) 대비 Stripe가 "핀테크 UX의 골드 스탠다드"로
  가장 폭넓게 인용되고, 결제 UI 컴포넌트(Stripe Elements)·개발자 문서(Stripe Docs)·전환율
  통계까지 공개적으로 가장 두텁게 문서화돼 있어 선정. (source: [Stripe's Payment UX: Why It's
  the Gold Standard](https://www.illustration.app/blog/stripe-payment-ux-gold-standard), [Behind
  the Gradient: Design at Stripe — Medium](https://uwux.medium.com/behind-the-gradient-design-at-stripe-476dcf61a51a))
- **내부 디자인시스템 "Sail"**: Stripe 전 제품이 이 시스템 위에 구축됨. 전체 문서는 비공개(사내
  전용)지만, 2022년 Stripe Apps 출시와 함께 공개 컴포넌트 라이브러리 일부를
  docs.stripe.com/stripe-apps/components에 공개. 전담 디자인 조직이 시스템을 소유하고, 컴포넌트
  변경은 내부 리뷰·버전 릴리즈 프로세스를 거친다고 확인됨(채용공고·업계 정리 글 기반 교차확인,
  Stripe 공식 1차 발표문은 확인 못함). (source: WebSearch 스니펫 종합, [Stripe 채용공고 — Staff
  Product Designer, Design Systems](https://stripe.com/jobs/listing/product-designer-design-systems/6865619))
- **Stripe Elements / Payment Element**: 커스터마이즈 가능한 embeddable 결제 UI 컴포넌트. Payment
  Element를 도입한 기업은 평균 11.9% 매출 증가를 기록(전환율 자체가 아니라 매출 지표임에 유의).
  (source: [Stripe 공식 — Build a streamlined checkout process](https://stripe.com/resources/more/streamlined-checkout-processes-how-to-boost-conversions-with-an-easier-checkout-flow), 2025.06.29 업데이트)
- **개발자 UX**: Stripe Docs가 "장문 개발자 UX"의 업계 레퍼런스로 자주 인용되며, 결제 관련 방대한
  엣지케이스(빈 상태·에러 상태 카탈로그)를 핀테크 업계에서 가장 촘촘하게 문서화한 사례로 꼽힘.
  시각 디자인은 시그니처 퍼플 그라디언트, weight-300의 절제된 타이포그래피로 표현됨. (source:
  [Behind the Gradient — Medium](https://uwux.medium.com/behind-the-gradient-design-at-stripe-476dcf61a51a), 스니펫 종합)

### Duolingo (미국 — 배민 대응 픽)
- **선정 근거**: 후보로 검토한 Mailchimp(공개 Content Style Guide 보유하나, Intuit 인수(2021) 이후
  브랜드 톤이 점차 절제되는 추세로 추정됨 — 별도 검증 필요)와 Airbnb(미니멀·절제된 톤으로 오히려
  배민의 "유쾌함/캐릭터성"과는 반대 성향) 대비, Duolingo는 마스코트 캐릭터(부엉이 "Duo") 중심의
  장난스럽고 위트 있는 브랜드 보이스가 실사용성(게임화된 학습 UX)과 결합된 정도가 가장 배민과
  근접하며, 공식 디자인시스템 사이트(design.duolingo.com)에서 Voice/Tone 가이드까지 공개하고 있어
  문서화 수준도 가장 두터워 최종 선정. (source: [Duolingo Tone of Voice — Tonelab](https://www.tonelab.so/brand/duolingo), [A sneak peek at Mailchimp's voice and tone — Medium](https://medium.com/design-bootcamp/a-sneak-peek-at-mailchimps-voice-and-tone-c8e520cea2d7))
- **공식 Voice 가이드**: Voice는 4가지 특성으로 고정 — Expressive(단순한 단어로 큰 감정 전달),
  Playful(대화에 창의성을 더함), Embracing(누구에게나 최고의 응원단이 되어줌), Worldly(비속어나
  특정 문화 레퍼런스를 피하고 폭넓은 세계관 유지). Tone은 Voice와 달리 상황(맥락)에 따라 조정하며,
  "사용자가 지금 어떤 감정 상태인지 읽고 그에 공감하며 쓴다"는 원칙을 명시. (source:
  design.duolingo.com/writing/voice, /writing/tone — WebSearch 스니펫 기반, 원문 직접 접근 불가)
- **디자인시스템 구조(제3자 정리 기준, 공식 확인 필요)**: 여러 디자인시스템 아카이빙 사이트가
  공통적으로 제시하는 수치는 18개 컬러 토큰(오울그린 CTA, 네이비 텍스트, 동물 이름을 붙인 액센트
  컬러 패밀리 등), 11개 타이포그래피 토큰(Feather Bold 디스플레이 + DIN Round 바디), 5개 코너
  래디우스, 9개 스페이싱 값(8/24/32/48/96px 스케일), 22개 컴포넌트. 버튼에 소프트 블러 대신 "같은
  색의 더 진한 톤"을 바로 아래 깔아 눌리는 느낌을 주는 하드 섀도 스타일이 특징적으로 언급됨.
  **다만 이 수치들은 Duolingo 공식 자료가 아니라 제3자가 리버스엔지니어링한 것으로 보여, 정확도는
  별도 검증이 필요하다.** (source: [Duolingo Design Tokens — Dembrandt](https://www.dembrandt.com/explorer/duolingo), [Duolingo Design System — DesignMD](https://www.designmd.co/d/duolingo) 등 다수 스니펫 종합)
- **브랜드 보이스 운영**: 소셜미디어에서 "짓궂고 위트있는" 마스코트 Duo 캐릭터를 스토리라인처럼
  운영 — 예: 밸런타인데이 틱톡 답글이 127만 engagement 기록. UX 전략으로 "Play first, profile
  second"(가입 전에 앱을 먼저 체험시켜 마찰을 낮추는 온보딩)가 자주 인용됨. (source: 여러 UX
  케이스스터디의 WebSearch 스니펫 종합)

## 사업적 시사점

- **신뢰가 핵심인 도메인(결제·송금 등)에서는 UX 품질이 곧 수치화된 사업 지표로 직결된다는 것이
  Stripe·토스 양쪽에서 공식 발표 형태로 확인된다** — Stripe의 "Payment Element 도입 시 매출
  11.9%↑", 토스의 "TDS 도입 후 화면 설계 시간 90%↓, 코드 50%↓" 같은 수치는 UX 투자를 사업 언어로
  번역한 사례다. LG전자가 가전 제품의 "신뢰가 필요한 순간"(초기 설치, 구독 결제, 펌웨어 업데이트,
  AI 에이전트 권한 설정 등)에 대한 UX 개선 투자를 경영진에 설득할 때, 이런 "정량 지표로 UX ROI를
  제시하는" 화법을 벤치마킹할 수 있다.
- **마스코트/고유서체 기반의 "브랜드다운 목소리"는 플랫 디자인이 일색인 시장에서 뚜렷한 차별화
  요인으로 작동한다** — 배민(낙서풍 일러스트+배민체)과 Duolingo(부엉이 Duo 캐릭터+게임화 톤)
  모두 "실사용성은 유지하면서 캐릭터성을 강하게 드러낸" 전략으로 시장에서 차별화됐다는 것이
  여러 2차 자료에서 공통적으로 지적된다. LG전자가 전사 AI Voice/캐릭터 아이덴티티를 설계할 때
  (own-company 기록의 `ai-voice-persona` 프로젝트와 연결), "일관된 하나의 목소리를 전 제품군에
  걸쳐 유지하는 것 자체가 경쟁우위"라는 시사점을 참고할 만하다.
- **디자인 자산(폰트·컴포넌트·Figma 파일)을 외부에 개방하는 것이 브랜드 노출과 개발자/디자이너
  커뮤니티 우호도를 높이는 채널로 작동할 수 있다** — 배민 폰트의 SIL OFL 무료 배포(대학생 과제,
  기업 마케팅, TV 자막 등 광범위한 재사용 확인)와 Duolingo Design System의 Figma 커뮤니티 파일
  공개가 그 사례다. 다만 이 개방 전략의 정량적 매출/브랜드 ROI 근거는 이번 조사에서 확인하지
  못했다 — 추정 수준의 시사점으로 취급해야 한다.

## 내부 역량 강화 시사점

이 절은 LG전자 UX연구소의 기존 own-company 기록 3건
(`research/findings/own-company/webos-micro-ux-platform-2026-09-21.md`,
`ux-design-system-webos-micro-2026-09-21.md`, `ax-workflow-p2d-figma-plugin-2026-09-21.md`)과
직접 대응시켰다.

- **LG "General Guide + 공통 컴포넌트 35종 + System Feature 시나리오 10종"(webos-micro-ux-platform)
  vs 토스 TDS**: 토스는 컴포넌트를 "디자인 도구에 국한되지 않는, 개발과 직접 연결된 공통 언어"로
  규정하고, 도입 전후의 화면 설계 시간(30~40분→3~4분)·코드량(50%↓)·누적 절감 시간(4,500시간/6개월)
  같은 정량 지표를 공개적으로 발표해왔다. LG의 35종 컴포넌트/10종 시나리오는 이번 own-company
  기록상 아직 이런 "도입 전후 생산성 비교 지표"가 집계·공개된 흔적이 없다 — 2027 사업계획에서
  webOS Micro 플랫폼의 ROI를 정량적으로 제시하려면, 토스처럼 "컴포넌트 채택 전후 설계/개발 시간"을
  내부적으로 측정·기록해두는 작업이 필요해 보인다.
- **LG "파운데이션 + 컴포넌트 표준 + Figma annotation"(ux-design-system-webos-micro) vs 토스
  파운데이션(레이아웃·컬러·타이포·스페이싱·상태 토큰화 + 자체 에디터 "Deus"의 ShadowDOM 스타일
  격리·System/Light/Dark 컨텍스트 전환)**: 토스는 파운데이션 토큰이 바뀌면 자체 디자인 툴에서
  여러 컨텍스트(라이트/다크 등)로 실시간 전파되는 구조까지 시스템화돼 있다. LG의 Figma annotation
  체계는(own-company 기록 기준으로는) 정적 문서화 수준으로 보이므로, "토큰 변경이 자동으로
  전파되는 실시간 시스템"까지 확장할 여지가 있다 — 이는 바로 아래 P2D 플러그인이 지향해야 할
  방향과도 맞닿아 있다.
- **LG "P2D" Figma 플러그인(ax-workflow-p2d-figma-plugin, 현재 PoC 개발 중) vs Duolingo Design
  System/토스 "Deus"**: 두 해외 사례 모두 디자인시스템 자체를 "플러그인/툴로 소비 가능한 형태"로
  배포하는 단계까지 나아갔다는 공통점이 있다(Duolingo는 Figma 커뮤니티 파일 공개, 토스는 자체
  에디터 "Deus" 운영). LG의 P2D가 PoC를 넘어 실전 적용될 때, 단순히 "레이아웃 자동 생성"을 넘어
  "디자인시스템 자산을 재사용 가능한 패키지 형태로 제공"하는 방향까지 목표를 확장할 참고가 된다.
- **UX 라이팅 원칙의 시스템화 — LG own-company 기록의 공백 영역**: 토스는 "라이터 3명이 수십 개
  프로덕트를 커버할 수 없다"는 조직적 제약을, 8가지 원칙 문서화 + "보이스톤 메이커" 셀프서비스
  도구로 해결했다. 배민도 전담 라이터 합류 이전부터 프로덕트 디자이너가 자체 라이팅을 수행할 수
  있도록 가이드를 운영해왔다. 반면 LG own-company 기록 3건에는 "텍스트 UX 라이팅 원칙/가이드"를
  다루는 프로젝트가 확인되지 않는다 — `ai-voice-persona-2026-09-21.md`(AI Voice, 음성 모달리티)는
  있지만 텍스트 라이팅 원칙 문서화 사례는 own-company 기록에 없어 보인다. 이는 2027 사업계획에서
  검토할 만한 공백 영역으로 제안한다(단, LG 내부에 이미 존재하나 아직 own-company-research가
  기록하지 못한 것일 수도 있음 — 확인 필요).
- **배민 셀프서비스 디자인시스템(2020, 배민사장님광장)의 "기획자는 정책 정의, 디자이너는 유저
  플로우"라는 역할 재배분 사례**는, LG P2D가 지향하는 "AX로 반복 작업을 줄이고 사람은 상위
  의사결정에 집중"이라는 방향과 정확히 같은 패턴이다 — 대규모(50페이지, 140다이얼로그) 시스템을
  프로토콜 수준으로 규칙화했을 때 조직 역할이 실제로 어떻게 재편되는지 보여주는 참고 사례로 활용
  가능하다.
- **배민 폰트의 완전 오픈소스화(SIL OFL, GitHub 공개)는 디자인 자산 개방 스펙트럼의 한쪽 극단을
  보여준다** — LG가 Figma annotation 체계나 컴포넌트 라이브러리를 사내를 넘어 협력사(OEM/ODM)나
  외부 개발자 커뮤니티에 얼마나 개방할지 논의할 때, "전면 오픈소스화까지 간 사례가 실제로 있다"는
  참고점으로 유용하다(단, 배민의 오픈소스화가 정량적으로 사업에 어떤 이익을 줬는지는 확인하지
  못했다).

## Open questions / gaps

- 이번 세션에서 `toss.tech`, `brunch.co.kr`, `velog.io`, `techblog.woowahan.com`,
  `bcut.baemin.com`, `ditoday.com`, `designcompass.org`, `tossmini-docs.toss.im`,
  `developers-apps-in-toss.toss.im`, `design.duolingo.com`, `bailliegifford.com`,
  `designsystems.one`, `weeklyuxuichallenge.oopy.io` 등 다수 원문 도메인이 EGRESS_BLOCKED로 직접
  WebFetch 접근이 불가능했다. 위 대부분의 findings는 WebSearch가 반환한 요약 스니펫에 근거한
  것으로, 원문 전체를 대조 검증하지 못했다 — **verifier 에이전트의 원문 대조 검증이 특히 필요하다.**
- ~~토스 8가지 라이팅 원칙 중 6개만 확인됨~~ → **2026-09-21 verifier 해결: 8개 전체 확인 + "Mute
  Mute" 오류 정정 완료.** 위 본문 반영됨.
- 토스 TDS의 "화면설계 30~40분→3~4분, 코드 50% 절감, 4,500시간/562일 절약" 수치 — **2026-09-21
  verifier가 수치 일관성(팀 전체 125시간/인 × 6개월 → 4,500시간 ÷ 8시간 = 562일)은 확인했으나,
  정확한 발표 시점·발표자·산출 방법론(측정 기간, 대상 팀 범위)은 원문(toss.tech) 접근 불가로
  여전히 미대조 — 재조사 필요.**
- 배민 "워크체(WORK체)" 리브랜딩의 정확한 공개 일정(2025년 7월 티징 이후 정식 공개일 등)과 세부
  디자인 의도는 designcompass.org 원문 접근 불가로 스니펫 수준만 확인했다.
- Stripe의 "Sail" 디자인시스템은 사내 전용이라 구조(토큰 체계, 컴포넌트 수 등)를 외부에서 완전히
  검증할 방법이 없다 — 공개된 부분(Stripe Apps 컴포넌트)만 검증 가능하다.
- Duolingo 관련 제3자 디자인시스템 아카이빙 사이트(dembrandt.com, designmd.co, oh-my-design.kr
  등)가 제시한 정확한 토큰 수치(18개 컬러, 22개 컴포넌트 등)는 Duolingo 공식 자료가 아니라 제3자가
  리버스엔지니어링한 것으로 보인다 — 공식 design.duolingo.com에서 직접 확인이 필요하나 이번
  세션에서는 접근 불가했다.
- ~~"AI UX라이터 제민희" 정체 미확인~~ → **2026-09-21 verifier 해결: 사람이 아니라 배민 사내 AI
  라이팅 검토 도구("제미나이" 말장난 네이밍).** 위 본문 반영됨. 다만 이 도구의 구체적 기능·워크플로우
  통합 방식은 여전히 미확인 — `ux-ai-capability-research` 관점에서 흥미로운 후속 조사 주제이므로,
  접근 가능한 세션에서 재조사할 가치가 있다.
- 미국 대응 기업 선정(Stripe, Duolingo)은 "공개 문서화 수준 + 업계 인용 빈도"를 기준으로 한 이번
  에이전트의 판단이며, 정량적 순위(예: 업계 설문조사, 수상 실적 비교표)로 뒷받침된 것은 아니다 —
  `interview` 단계에서 사용자가 다른 후보(Robinhood, Cash App/Block, Airbnb, Mailchimp)를 원할
  경우 재조사가 필요하다.
- LG own-company 기록에 "텍스트 UX 라이팅 원칙/가이드" 관련 프로젝트가 실제로 없는 것인지,
  아니면 존재하지만 아직 `own-company-research`가 기록하지 못한 것인지 확인 필요.
