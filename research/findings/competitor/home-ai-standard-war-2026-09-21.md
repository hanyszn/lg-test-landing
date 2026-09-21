# "홈 AI 표준 전쟁" — 누가 스마트홈의 "기본 에이전트" 자리를 차지하는가
Date: 2026-09-21
Scope: 삼성(Bixby/Gauss+Perplexity), 구글(Gemini for Home), 애플(Siri AI+Gemini 3 파트너십), 아마존
(Alexa+/Anthropic Claude) 4사의 홈 AI 표준 전략 비교. Matter/MCP 상호운용성 표준에서의 포지셔닝,
애널리스트 전망, LG전자 시사점까지 포함. 원칙: "출시/발표"는 정확한 날짜(YYYY-MM-DD) 기재,
"현재 이렇다"는 헤드라인 통계·비교는 2026년 발표 자료만 사용(이전 연도 자료는 배경 설명이라도 본문
제외 — 예외 없이 라벨링).

## 중심 명제 (Thesis)

**홈 AI 주도권 경쟁의 축이 "누가 최고의 자체 LLM을 만드는가"에서 "누가 가정 데이터·기기 제어의
에이전트 게이트웨이(control layer)를 장악하고, 그 접근권 자체를 과금하는가"로 이동했다.** 기기
연결 계층(Matter)은 이미 사실상 공통표준으로 정리돼 경쟁 요인에서 빠졌고, "자체 LLM 고수 vs 외부
파트너십"이라는 이분법도 4사 모두 하이브리드로 수렴하며 무의미해졌다. 대신 새로운 전장은 (1) 에이전트가
가정 데이터에 접근하는 API/MCP 계층을 누가 열고, 누구에게 유료로 게이트하는가, (2) 그 결과가 승자독식이
아니라 지역·생태계별 다자 공존으로 굳어지고 있다는 두 지점이다.

## Key findings

### 1. "컨트롤 레이어" 전쟁 — 개방형 표준을 표방하되 접근권 자체를 유료 게이트로 만드는 패턴

- **구글 Home MCP — 2026-09-16 얼리 액세스 공개.** Model Context Protocol(MCP) 서버를 통해 Claude,
  ChatGPT, Google Antigravity, Hermes, Open Claw 등 MCP 호환 AI 에이전트가 Google Home 생태계의
  기기 상태·룸/구조 정보·과거 이벤트 로그에 접근하고 기기를 직접 제어할 수 있게 됨. 기능은 기기 목록
  조회, 실시간 상태 모니터링, 파라미터 기반 기기 제어, 과거 이력·이벤트 로그 조회의 4개 영역.
  **단, 접근 자체가 Google Home Premium Advanced(월 $20 또는 연 $200) 가입자 전용으로 게이트됨** —
  "개방형 표준"을 표방하지만 실제 접근권은 유료 구독 뒤에 있는 구조.
  (source: [TechCrunch(제목·날짜, 원문 직접 열람은 EGRESS_BLOCKED)](https://techcrunch.com/2026/09/16/your-ai-agents-can-now-control-your-google-home-devices/), [Unite.AI](https://www.unite.ai/google-opens-home-mcp-early-access-to-ai-agents-for-smart-home-control/), [dev.to](https://dev.to/techaiwire/google-home-adds-an-mcp-server-gated-at-20-a-month-5gop), [progressiverobot.com](https://www.progressiverobot.com/2026/09/16/google-home-mcp-ai-agents-smart-home/))
  [2026-09-21 verifier 확인] 2026-09-16 얼리 액세스 공개, Google Home Premium Advanced($20/월) 게이트,
  Claude/ChatGPT/Google Antigravity/Hermes/Open Claw 지원 모두 재검색으로 교차확인됨(Engadget,
  AiCybr 등 추가 매체 일치).
- **삼성 SmartThings API 유료화 — 2026년 6월 발표(개별 매체 보도일 2026-06-26), 2026년 10월부터
  시행.** 비상업 개인 개발자에게 월 $4.99("Personal Plan") 과금. Home Assistant 등 무료 서드파티
  연동 생태계가 직접 타격을 받음(Home Assistant 창립자 Paulus Schoutsen이 공개적으로 "영향받을 것"
  이라 언급). 상업용 티어는 별도 예정.
  (source: [SamMobile](https://www.sammobile.com/news/smartthings-api-access-will-soon-require-a-5-monthly-payment/), [AndroidHeadlines](https://www.androidheadlines.com/2026/06/samsung-smartthings-api-monthly-fees-home-assistant.html), [Eastern Herald(2026-10 시행일 명시)](https://easternherald.com/2026/07/02/samsung-smartthings-api-fee-developers-home-assistant-october-2026/), [How-To Geek](https://www.howtogeek.com/samsung-smartthings-api-price-for-access/))
  [2026-09-21 verifier 확인] $4.99/월 "Personal Plan", 2026년 10월 시행(무료 접근은 2026년 3분기까지
  유지) 모두 재검색으로 교차확인됨(Android Authority, Gadget Hacks, Windows News 등 추가 매체 일치).
- → 구글·삼성 두 회사가 같은 시기(2026년 6~10월)에 독립적으로 같은 패턴("개방 표준 + 유료 게이트")을
  택했다는 것은 우연이 아니라, 에이전트 접근권이 업계 공통의 새로운 수익원으로 자리잡고 있다는 신호.

### 2. "자체 LLM 고수 vs 외부 파트너십" — 4사의 실제 선택은 모두 다르지만 순수 단독 고수는 없음

- **삼성 — 멀티에이전트 헤지 전략.** One UI 8.5·Galaxy S26부터 자체(Bixby/Gauss) + 외부(Gemini,
  Perplexity)를 나란히 배치해 사용자가 기본 어시스턴트를 직접 선택하게 함. 'Hey Plex'로 Perplexity를
  바로 호출 가능. 삼성은 "사용자의 78%가 이미 2종 이상의 AI 에이전트를 일상적으로 쓴다"는 자체
  리서치를 근거로 단일 자체 모델 경쟁보다 "선택권 제공"을 택했다고 설명. 가전 쪽에서는 이미
  Bixby+Perplexity "Open Q&A"가 2026-03-31 발표, 2026-09부터 한국 우선 적용 중(별도 기존 파일
  `samsung-bixby-perplexity-appliance-update-2026-09.md` 참고).
  (source: [Croma Unboxed](https://www.croma.com/unboxed/samsung-galaxy-ai-support-multi-ai-agents), [FutureFive](https://futurefive.com.au/story/samsung-brings-perplexity-to-galaxy-with-multi-agent-ai), [TechBuzz](https://www.techbuzz.ai/articles/samsung-opens-galaxy-ai-to-perplexity-in-multi-agent-push))
- **구글 — 모델은 폐쇄형 자체 개발(Gemini) 고수, 그 위의 파이프(API/MCP)만 개방(단 유료).** Gemini
  3.1 기반 Ask Home 등은 전적으로 자체 모델. 외부 파트너십을 맺은 적이 없고, 대신 위 1번 항목처럼
  에이전트 계층만 유료로 개방.
- **애플 — "브릿지 전략": 자체 모델 지연 → 외부 대형 모델 라이선스.** 2026-01-12, Apple과 Google이
  다년 계약을 공식 발표. Apple은 Google에 연 약 $1B를 지불하고, 자체 모델보다 8배 큰 커스텀
  1.2조 파라미터 Gemini 모델을 라이선스해 Siri AI·Apple Intelligence 차세대 버전에 사용. 이 모델은
  Apple의 Private Cloud Compute 인프라에서 구동되어 프라이버시 보장은 유지. 계약은 비독점적이며
  기존 OpenAI/ChatGPT 연동도 유지. 트리거는 내부 평가에서 Siri가 복잡한 질의의 약 33%를 실행하지
  못한다는 결과였고, 애플은 이 파트너십을 자체 차세대 모델(코드명 Ferret-3, 2026~2027년 목표) 개발
  시간을 버는 "브릿지"로 명시. 실제 적용은 WWDC26(2026-06, 정확한 일자는 애플 뉴스룸 상 "2026년 6월"
  로만 확인)에서 "Siri AI"로 첫 공개, Apple Intelligence 차세대 버전은 2026-09에 "오늘부터 제공"
  (Apple 뉴스룸 명시).
  (source: [TechCrunch](https://techcrunch.com/2026/01/12/googles-gemini-to-power-apples-ai-features-like-siri/), [CNBC](https://www.cnbc.com/2026/01/12/apple-google-ai-siri-gemini.html), [CNN](https://www.cnn.com/2026/01/12/tech/apple-google-gemini-siri), [Forbes](https://www.forbes.com/sites/johnkoetsier/2026/01/12/hey-siri-becomes-hey-google-as-apple-and-gemini-get-hitched/), [Apple Newsroom(WWDC26)](https://www.apple.com/newsroom/2026/06/apple-unveils-next-generation-of-apple-intelligence-siri-ai-and-more/), [Apple Newsroom(2026-09 출시)](https://www.apple.com/newsroom/2026/09/siri-ai-a-profoundly-more-capable-and-personal-assistant-is-here/))
  [2026-09-21 verifier 확인] 2026-01-12 발표, 연 약 $1B, 1.2조 파라미터(기존 대비 8배) 모두 재검색으로
  교차확인됨(CNBC 2026-01-12 원문 일치, Introl·ComputeLeap 등 추가 매체 일치).
- **아마존 — 외부 파트너(Anthropic)에 올인하되, 그 대가로 인프라 락인을 확보.** Alexa+는 Claude가
  복잡한 작업 대부분을 처리(Amazon Bedrock 경유, 2025-02-26 파트너십 공식화). 2026-04-21, Amazon은
  Anthropic에 최대 $25B를 추가 투자한다고 발표(즉시 $5B + 마일스톤 조건부 $20B, 2023년 이후 누적
  최대 $33B, Anthropic 밸류에이션 $380B 기준). 대가로 Anthropic은 향후 10년간 $100B 이상을 AWS
  기술에 지출 약정, Amazon은 Claude 학습·서빙용 최대 5GW 전용 컴퓨팅(Trainium2/3)을 확보. 즉
  "모델은 외부"이지만 "그 외부사의 클라우드 인프라 제공자가 되어 관계를 락인"하는 구조.
  (source: [CNBC(2026-04-20/21 보도)](https://www.cnbc.com/2026/04/20/amazon-invest-up-to-25-billion-in-anthropic-part-of-ai-infrastructure.html), [Anthropic 공식](https://www.anthropic.com/news/anthropic-amazon-compute), [CIO Dive](https://www.ciodive.com/news/amazon-25-billion-to-anthropic-ai-infrastructure/818123/), [CNBC(2025-02-28, Alexa+ Claude 파트너십)](https://www.cnbc.com/2025/02/28/amazon-most-powerful-new-alexa-features-being-powered-by-anthropic-ai.html))
  [2026-09-21 verifier 확인] 2026-04-20 발표(즉시 $5B + 마일스톤 최대 $20B), Trainium2/3·5GW 확보
  모두 재검색으로 교차확인됨(CNBC, Motley Fool, CloudComputing-News 등 추가 매체 일치).
- → **공통점: 4사 모두 "순수 자체 개발 단독 고수"는 없다.** 구글조차 폐쇄 자체 모델을 외부 오픈
  표준(MCP)으로 노출한다. "자체냐 외부냐"라는 이분법 자체가 무의미해지고 있으며, 모두 하이브리드로
  수렴 중이라는 것이 2026년 시점의 실질적 결론.

### 3. Matter·MCP에서의 개방/폐쇄 포지션 — 기기 계층은 이미 정리됐고, 진짜 전장은 에이전트 계층으로 이동

- **Matter(기기 연결 표준, CSA 산하) — 사실상 경쟁 요인에서 빠짐.** Matter 1.5.1(2026-03-31,
  카메라 중심 유지보수), Matter 1.6(2026-06-22, Joint Fabric 기능 추가)까지 계속 갱신되며 Apple·
  Google·Amazon·Samsung 모두 CSA 회원사로 참여. 2026년 초 기준 700개 이상 제품이 Matter 인증
  획득. Apple Home도 구 HomeKit 아키텍처 지원을 2026-02-10부로 종료하고 Matter 컨트롤러 체제로
  전환 완료.
  (source: [matter-smarthome.de](https://matter-smarthome.de/en/development/the-matter-standard-in-2026-a-status-review/), [HomeCoreOS](https://www.homecoreos.com/en/homekit/hubs-and-protocols/homekitwhat-to-expect-with-the-end-of-the-old-architecture-in-2026))
- **MCP(에이전트-데이터 계층) — 진짜 경쟁이 벌어지는 지점.** 구글이 가장 적극적으로 개방(단 유료
  게이트, 위 1번). 애플도 WWDC26에서 App Intents 확장과 함께 MCP 네이티브 지원을 발표. Anthropic이
  MCP 표준 자체의 제정자이므로 Anthropic 투자사인 아마존도 자연스럽게 올라탐. 반대로 삼성은
  SmartThings API 자체를 유료화하며 개방성이 오히려 후퇴하는 시그널을 보냄.
  (source: [MindStudio](https://www.mindstudio.ai/blog/apple-wwdc-ai-strategy-siri-app-intents-mcp), [Business Standard(원문 직접 열람 불가, 스니펫 기반)](https://www.business-standard.com/technology/tech-news/smart-home-interface-ai-agents-physical-world-126091700840_1.html))
- → **결론: 기기 연결(Matter)은 개방형으로 이미 정리됐지만, 그 위의 에이전트 지능 계층(MCP 게이트)에서
  각사가 "개방하되 유료 게이트를 세우는" 방식으로 새로운 락인 지점을 만들고 있다.**

### 4. 결말 전망 — 승자독식이 아니라 "지역·생태계별 다자 공존" + 그 안에서 구독 전환 경쟁

- **스마트스피커/허브 시장은 이미 다자 분할 상태.** Amazon·Google·Apple·Samsung·Xiaomi 5사 합산
  글로벌 출하량 점유율 약 58%(2026년 시장 추정치, 개별 업체 수치는 자료마다 편차가 커 2026년
  단일 확정치는 확인 못함 — Amazon 약 23~30%, Google 약 20~25%, Apple 약 10~15%로 추정치 범위만
  확인). 절반 이상을 5개사가 나눠 갖는 구조 자체가 승자독식과는 거리가 멈.
  (source: [SQ Magazine](https://sqmagazine.co.uk/smart-speaker-statistics/), [Scoop Market.us](https://scoop.market.us/smart-speaker-statistics/))
- **중국은 사실상 별도 블록.** Xiaomi Mi Home 생태계는 2026년 기준(MWC 2026, 2026-03 발표) 연결
  기기 7.5억 대 이상, 독자 중국어 어시스턴트 Xiao Ai를 사용해 글로벌 Matter/MCP 경쟁 구도와 분리된
  자체 생태계를 운영. Alibaba도 2026년 자체 멀티에이전트 플랫폼 Wukong을 발표.
  (source: [VRSUS(MWC 2026)](https://www.vrsus.io/xiaomi-shows-off-its-human-x-car-x-home-ai-ecosystem-at-mwc-2026/))
- **"멀티-LLM 가전"이 업계 설계 전제로 자리잡음.** 삼성의 멀티에이전트 전략 자체가 "승자독식은
  일어나지 않는다"는 업계 판단을 반영한 설계 — 단일 승자를 상정하지 않고 애초에 여러 에이전트가
  공존하는 UX를 기본값으로 설계.
- → **종합 전망: 북미·유럽은 Google(Gemini, Apple과 연합) 축 vs Amazon(Anthropic Claude) 축의
  양강 구도 + 삼성의 헤지형 멀티에이전트가 그 사이에서 유통되는 구조, 중국은 별도 독자 블록으로
  사실상 분리 — "승자독식"도 "완전한 단일표준 공존"도 아닌 "2~3개 대형 블록 + 지역 분할"로 수렴할
  가능성이 높다. 단, 이번 세션에서 이 결론을 명시적으로 "승자독식 vs 다자공존"이라는 프레임으로 직접
  분석한 애널리스트 리포트(Gartner/IDC/Counterpoint 등 정식 발간물)는 확인하지 못했다 — 위 종합
  전망은 이번 세션에서 수집한 개별 사실들을 조합한 것이며, 정식 애널리스트 코멘트로 뒷받침되지
  않은 추론임을 명시한다(Open questions 참고).**

## LG전자 관점 시사점 (상세)

### 현재 위치 진단

LG전자는 이 경쟁 구도에서 "각 요소는 갖추고 있으나 통합된 전략 서사가 없는" 상태로 진단된다.

- **허브**: ThinQ ON(AI홈 허브, DQ-X AI 칩 탑재, 생성형 AI 기반 자연어 음성 명령·컨텍스트 이해 지원)
- **에이전트**: 씽큐 클로(ThinQ Claw, [2026-09-21 verifier 정정] 원문 영문 표기는 "ThinQ Clo"가 아니라
  "ThinQ Claw"다 — LG 공식 뉴스룸(lg.com, PR Newswire) 및 채널라이프 등 다수 매체가 "ThinQ Claw"로
  표기하며, 오픈소스 에이전트 프레임워크 "OpenClaw"를 기반으로 명명된 것으로 확인됨. 아래 및
  Open questions 섹션의 "ThinQ Clo" 표기도 함께 정정함) — 2026-09-04 IFA 2026에서 최초 공개, LLM
  기반 실행형 에이전트로 카카오톡 등 외부 메신저로 집 밖에서도 대화 가능. [2026-09-21 verifier 확인]
  IFA 2026 발표 시점(2026-09-04~08) 기준 노범준 LG전자 HS AI홈솔루션사업개발담당 상무가 PoC·
  내외부 베타테스트를 진행 중이며 연말 중 공식 출시를 목표로 한다고 밝혔고(다수 매체, 예:
  이투데이·이데일리·시대일보 2026-09-05 보도), 커머스 제휴·구독형 서비스 모델도 검토 중이라는
  발언도 원문과 일치함을 확인. 연내 정식 출시 예정(LG전자 노범준 임원, 2026-09-04 현지 테크 브리핑).
  어떤 LLM을 기반으로 하는지는
  이번 세션에서 확인하지 못함(자체 EXAONE 기반인지, 외부 모델 라이선스인지 불명확 — Open questions
  참고).
- **개방형 커넥티비티**: 2024-07-03, 네덜란드 스마트홈 플랫폼 앳홈(Athom) 지분 80% 인수(현금
  약 692억원, 3년 내 잔여 20% 인수 예정 — 2024년 사실이므로 배경 정보로만 인용). 앳홈의 허브
  '호미(Homey)'는 5만여 종 기기를 Wi-Fi·블루투스·지웨이브·Matter·Thread로 연결하는 개방형 플랫폼이며,
  인수 후에도 브랜드·운영체계를 독립 유지하기로 약속. IFA 2026에서 호미 기반 홈에너지관리(HEMS)를
  공개.
- **파트너십**: MS와 전략적 협력(2025-01-07 CES 2025 발표, 프로젝트명 Q9 — 이동형 AI홈 허브/로봇에
  MS 음성인식·합성 기술 적용 계획, 2025년 사실이므로 배경 정보로만 인용). LG AI 데브콘 2026에서는
  엔비디아·MS·구글클라우드·AWS 등 복수 클라우드사와 협력 소개.
- **자체 모델**: EXAONE 3.5가 LG 그램 AI 2026 노트북의 온디바이스 AI(문서 요약·검색·번역, "Gram
  Chat On-Device")에 탑재 — 다만 이는 PC 제품 라인이며, ThinQ ON/씽큐 클로 같은 가전·홈 에이전트에
  EXAONE이 실제로 쓰이는지는 확인하지 못함.

→ 종합하면 LG는 이미 삼성(멀티에이전트)·애플(브릿지 라이선스)·아마존(외부 올인+인프라 락인) 각
전략의 요소를 조금씩 갖고 있지만, 대외적으로 "우리는 이런 이유로 이 조합을 택했다"는 일관된 서사로
정리되어 있지 않다.

### 구체적으로 어느 편에 서야 하는가

1. **컨트롤 레이어를 조기에 개방하라.** 앳홈 호미의 Matter/Thread 개방성을 활용해 자체 MCP 서버를
   2026년 내 공개하고, 구글 Home MCP(2026-09-16)처럼 서드파티 에이전트(Claude, ChatGPT 등)가 LG
   가전을 직접 제어할 수 있게 해야 한다. 이를 하지 않으면 구글·아마존의 에이전트가 LG 가전을 자사
   생태계의 "종속 기기"로 흡수해버리는 리스크가 있다 — Matter로 기기 계층은 이미 개방했지만, 에이전트
   계층에서 LG가 침묵하면 사용자는 결국 구글/아마존 에이전트를 통해 LG 가전에 명령을 내리게 되고,
   그 관계의 주도권(브랜드 접점, 데이터, 향후 과금 권한)은 LG가 아니라 구글/아마존이 갖는다.
2. **LLM 선택은 "애플식 투트랙"을 공식화하라.** 지금처럼 여러 파트너십(MS, 클라우드 3사, EXAONE)이
   산발적으로 존재하는 상태를, "허브·온디바이스 저지연/프라이버시 시나리오는 자체 EXAONE" +
   "씽큐 클로 같은 복잡한 대화형 에이전트는 외부 대형 모델을 라이선스"하는 애플식 투트랙 전략으로
   명시적으로 정리하고 대외 커뮤니케이션해야 한다. 지금은 이 구분이 시장에 전달되지 않고 있다.
3. **독자노선(자체 고수 단독) 또는 특정 빅테크 올인 시 리스크를 명시적으로 인지하라.**
   - **자체 고수만 고집할 경우**: 삼성 Bixby가 자체 고수 끝에 2026-03-31 결국 Perplexity로
     전환한 선례가 보여주듯, 자체 모델의 성능 격차가 벌어진 뒤 뒤늦게 파트너십으로 전환하면 그
     사이 이미 지불한 개발비·잃은 시간을 만회하기 어렵다.
   - **특정 빅테크에 올인할 경우**: 그 빅테크의 정책 변경(가격 인상, API 유료화, 정책 전환)에
     그대로 종속된다. 삼성 SmartThings가 2026-10부터 API를 유료화한 사례가 보여주듯 "무료 개방"은
     언제든 뒤집힐 수 있고, 이때 후속 대응 여력이 없는 파트너는 그대로 비용을 떠안는다.
   - **결론**: LG는 파트너 다변화(MS + 자체 EXAONE + 복수 클라우드사 + 오픈 표준)를 유지하되,
     "우리가 표준(모델)을 소유하지 않아도, 표준 위에서 사용자 접점(가전 설치기반 + 공간 데이터)을
     가장 많이 가진 자가 된다"는 전략으로 명시적으로 포지셔닝해야 한다. 앳홈 인수는 이 전략에 정확히
     부합하는 자산이지만, 아직 이를 "LG의 홈 AI 표준 전쟁 포지션"으로 연결하는 시장 커뮤니케이션이
     약하다 — IFA 2026 발표들도 개별 기능(씽큐 클로, HEMS) 나열에 그치고 있어, "왜 이 조합인가"에
     대한 통합 서사를 마케팅/IR 차원에서 별도로 구축할 필요가 있다.

## Open questions / gaps

- 씽큐 클로(ThinQ Claw)가 어떤 LLM(자체 EXAONE인지, 외부 라이선스 모델인지, 혹은 하이브리드인지)을
  쓰는지 이번 세션에서 확인하지 못했다 — LG 공식 뉴스룸(`lg.co.kr`, `news.lge.co.kr` 등)이
  EGRESS_BLOCKED로 직접 열람이 막혀 있어 후속 세션에서 원문 확인이 필요.
  (다음 세션 참고용 검색 실마리: "씽큐 클로 LLM", "ThinQ Claw model architecture", IFA 2026 LG
  기술 브리핑 상세 자료)
- "승자독식 vs 다자공존" 결말에 대한 정식 애널리스트 리포트(Gartner/IDC/Counterpoint/CCS Insight
  등)의 명시적 코멘트를 이번 세션에서 찾지 못했다 — 위 4번 항목의 전망은 개별 사실을 조합한
  추론이며, 공식 애널리스트 인용으로 보강 필요.
- 스마트스피커 시장 점유율의 2026년 단일 확정 수치(자료마다 23~30%/20~25%/10~15% 등 범위가
  달라 일치하지 않음) — 확정치를 얻으려면 유료 시장조사 리포트(Counterpoint, Canalys 등) 원문
  확인 필요.
- Apple Siri AI의 정확한 일반 사용자 출시일(WWDC26 발표는 2026-06, 신규 Apple Intelligence는
  2026-09 "오늘부터 제공"으로 확인됐으나 Siri AI 개별 기능의 지역별 순차 출시 일정은 세부 확인 못함).
- `techcrunch.com`, `www.business-standard.com`, `biz.heraldcorp.com`, `www.newspim.com`,
  `www.fnnews.com`, `www.koit.co.kr`, `view.asiae.co.kr`, `www.emarketer.com`, `www.mckinsey.com`
  등 다수 1차 소스 도메인이 이번 세션 환경에서 EGRESS_BLOCKED로 직접 열람이 안 되어, WebSearch
  스니펫 기반으로만 인용했다 — 원문 대조 재확인이 필요.
