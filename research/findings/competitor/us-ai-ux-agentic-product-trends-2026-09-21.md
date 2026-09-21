# 미국 AI/UX 선도기업 최신 에이전트 도입 동향 — Competitor/Industry Research
Date: 2026-09-21
Scope: 기존 리서치(스마트홈 가전 AI UX, AI 에이전트 실무 활용 트렌드, 토스/배민/미국 UX 벤치마크)와
겹치지 않는 새 화두로, **"제품에 AI를 도입하는 방식(에이전틱 UX)"** 축에 집중. 3개 트랙으로 조사:
(1) 미국 AI 파운데이션 모델 기업(Anthropic/OpenAI/Google)의 최근 3~6개월 신규 에이전트 제품,
(2) 미국 소비자/B2B 프로덕트 기업(Notion, Linear, Perplexity, Figma, Airbnb)의 최근 AI 기능 도입
사례, (3) 업계 전반 AI/UX 트렌드 방향 시그널(Gartner, MCP 표준화, 에이전틱 UX 디자인 패턴).

**출처 접근성 주의**: 이번 세션의 네트워크 egress 정책상 `openai.com`, `claude.com`, `blog.google`,
`stateofaidesign.com` 도메인에 WebFetch로 직접 접근할 수 없었다(EGRESS_BLOCKED). 이들 공식
출처를 인용한 항목은 WebSearch가 반환한 스니펫(다수는 해당 공식 도메인을 직접 인용하는 2차 기사)에
근거하며, 원문 전체 대조는 하지 못했다 — **verifier 에이전트의 원문 대조 검증이 필요하다.**
반대로 `notion.com/releases`, `config.figma.com`, `help.figma.com`, `theregister.com`,
`gartner.com` 뉴스룸 등은 검색 스니펫 자체가 해당 공식/1차 도메인에서 나온 것으로 비교적 신뢰도가
높다.

**[2026-09-21 verifier 확인]** 동일한 EGRESS_BLOCKED 제약을 재확인했다(`openai.com`, `claude.com`,
`blog.google`, `stateofaidesign.com` 모두 직접 접근 불가, 우회 시도 없음). 다만 Anthropic의 별도
공식 서브도메인인 `platform.claude.com`(Claude Developer Platform 공식 문서), `code.claude.com`
(Claude Code 공식 문서), 그리고 `github.com/anthropics/*`(Anthropic 공식 GitHub 조직)는 이번
세션에서 직접 접근 가능했다 — `claude.com`(마케팅/블로그 도메인)과는 별개 서브도메인이라 egress
정책상 차단되지 않은 것으로 보인다. 이를 활용해 아래 Anthropic 2026-09 업데이트, "/goal vs
Outcomes" 항목은 1차 문서로 직접 대조·해결했다(자세한 내용은 해당 항목 및 Open questions 참고).

## Key findings

### 트랙 1 — 미국 AI 파운데이션 모델 기업의 최신 에이전트 제품 (Anthropic / OpenAI / Google)

- **Anthropic, 2026-05-06~07 "Code with Claude" 컨퍼런스(샌프란시스코)에서 Claude Managed Agents에
  Dreaming·Outcomes·멀티에이전트 오케스트레이션·웹훅 4개 기능을 동시 공개.**
  - *Dreaming*: 에이전트가 유휴 시간에 과거 세션과 메모리 스토어를 스스로 복기해 반복 패턴을
    추출하고 메모리 노트를 작성 — "자동 업데이트" 또는 "사람 검토 후 반영" 중 선택 가능.
  - *Outcomes*: 개발자가 성공 기준(rubric)을 작성하면 독립된 채점 모델이 산출물을 평가하고,
    실패 시 재작업 루프가 자동 트리거됨. Anthropic 자체 테스트에서 난이도 높은 작업의 성공률이
    최대 10%p 개선됐다고 발표.
  - *멀티에이전트 오케스트레이션*: 리드 에이전트가 복잡한 작업을 하위 작업으로 쪼개 서브에이전트에
    분배.
  - 법률 AI 스타트업 Harvey가 파일럿을 진행해 작업 완료율이 약 6배 상승했다고 보고됨(Harvey 자체
    수치, 제3자 검증 여부 불명). **[2026-09-21 verifier 확인]** 복수 독립 매체(FindSkill.ai,
    Sean Kim 블로그 등)가 "Harvey의 내부 테스트(internal testing)에서 약 6배 상승"이라고 동일하게
    보도하며, 이는 Anthropic 자사 블로그(claude.com/blog, EGRESS_BLOCKED)가 고객 사례로 인용한
    Harvey 자체 발표 수치라는 점이 일관되게 확인된다 — 독립 감사기관 등 제3자 검증 수치라는 근거는
    어디에도 없었다. 기존 "Harvey 자체 수치, 제3자 검증 여부 불명" 라벨은 정확하며 유지할 것.
  (source: [New in Claude Managed Agents — claude.com/blog](https://claude.com/blog/new-in-claude-managed-agents) — 직접 접근 불가(EGRESS_BLOCKED), [Let's Data Science](https://letsdatascience.com/blog/anthropic-dreaming-claude-managed-agents-self-improving-may-6), [SiliconANGLE](https://siliconangle.com/2026/05/06/anthropic-letting-claude-agents-dream-dont-sleep-job/), [Developers Digest](https://www.developersdigest.tech/blog/claude-managed-agents-dreaming-outcomes-multi-agent), [MindStudio](https://www.mindstudio.ai/blog/code-with-claude-2026-new-agent-features) 스니펫 종합)
  - **이 항목은 "자율적 다단계 실행"이 명확히 확인되므로 "에이전틱" 표현 사용이 타당하다.**
- **Anthropic, 2026년 9월 기준 Claude Developer Platform에 Managed Agents용 자동 권한 정책(auto
  permission policies), ant CLI의 베타 "세션 연결(sessions connect)"(라이브 세션 원격 제어),
  커머스 에이전트 블루프린트(참조용 쇼핑·판매자 에이전트 + 가드레일)를 추가.**
  **[2026-09-21 verifier 확인]** 세 항목 모두 Anthropic 공식 문서/저장소로 원문 대조를 완료했다 —
  자동 권한 정책은 `platform.claude.com/docs/en/managed-agents/permission-policies`(호출을
  자동실행/차단/사람 승인대기 3가지로 판정하며, "auto는 사람 체크포인트가 아니다 — 승인된 호출은
  누군가 검토하기 전에 이미 실행된다"는 경고 문구 확인), ant CLI 세션 연결은
  `platform.claude.com/docs/en/cli-sdks-libraries/cli/sessions-connect`(CLI v1.32.0 이상 필요,
  `ant beta:sessions connect` 명령, 베타 표기 확인), 커머스 에이전트 블루프린트는 GitHub
  `anthropics/commerce-agents`(Apache-2.0, 쇼핑/판매자 에이전트 레퍼런스 구현, 실제 결제·주문
  확정은 하지 않고 체크아웃·판매자 쓰기는 사람 승인 대기 상태로 스테이징하는 가드레일 확인)로
  각각 직접 확인됨. InfoWorld·Techzine Global·AlphaSignal·byteiota·QATechTools·PYMNTS·qz.com 등
  다수의 독립 매체에서도 교차 확인되어, "단일 애그리게이터 출처·신뢰도 낮음" 평가는 더 이상
  유효하지 않다 — releasebot.io는 최초 발견 경로였을 뿐, 내용 자체는 1차 출처로 검증됐다.
  (source: [releasebot.io/updates/anthropic](https://releasebot.io/updates/anthropic),
  [platform.claude.com — 자동 권한 정책](https://platform.claude.com/docs/en/managed-agents/permission-policies),
  [platform.claude.com — sessions connect](https://platform.claude.com/docs/en/cli-sdks-libraries/cli/sessions-connect),
  [github.com/anthropics/commerce-agents](https://github.com/anthropics/commerce-agents))
- **OpenAI, 2026-07-09 "ChatGPT Work" 출시** — 목표(outcome)를 입력하면 여러 앱·파일에서 정보를
  수집해 최종 결과물(스프레드시트, 슬라이드, 리포트, 소형 웹앱)을 만들어내는 에이전트. 복잡한
  프로젝트를 여러 단계로 쪼개 수 시간 동안 독립적으로 이어서 수행하며, Slack·Gmail·Google Drive·
  Salesforce 등 수십 개 도구에 Plugins 디렉터리로 연결. 일정 기반 실행(scheduled run)도 지원.
  Pro/Enterprise/Edu 사용자로 먼저 출시 후 Plus/Business로 확대.
  (source: [BNN Bloomberg](https://www.bnnbloomberg.ca/business/artificial-intelligence/2026/07/09/openai-launches-chatgpt-work/), [Digital Applied](https://www.digitalapplied.com/blog/chatgpt-work-openai-agent-launch-2026), [AIToolsReview](https://aitoolsreview.co.uk/insights/chatgpt-work) — openai.com 공식 발표문은 EGRESS_BLOCKED로 직접 대조 못함)
  - **"자율적으로 수 시간 이어서 멀티스텝 실행"이 명시적으로 확인되므로 "에이전틱" 표현 사용 타당.**
- **OpenAI, 2026-04-22 "Workspace Agents" 도입** — 클라우드에서 상시 실행되는 공유 에이전트로,
  노트북을 닫아도 장시간 워크플로우가 계속 실행됨(ChatGPT Work의 전신 격 기능으로 추정).
  (source: [chatlyai.app](https://chatlyai.app/news/openai-chatgpt-workspace-agents-april-2026), 스니펫 기반 — 원문 미검증)
- **OpenAI, 2026-09-16 "Sponsored Agents"(광고주가 후원하는 에이전트) 테스트 발표** — 대화
  안에서 상품을 추천/판매하려는 봇. **[2026-09-21 verifier 확인 — 세부사항 보강]** 독립 매체
  다수(Unite.AI, PYMNTS, Search Engine Roundtable, qz.com, Remote Work Europe 등)가 동일하게
  보도한 바로는: 미국 내 일부 광고주(Newegg·Best Buy·Lowe's·VistaPrint 등) 대상 테스트이며,
  광고에서 "스폰서드 에이전트"와의 대화로 들어가는 것은 ChatGPT 자체 답변과 분리된, 명시적으로
  라벨링된 별도 대화라고 함(사용자 UX 골자는 확인됨). 국제 시장으로는 2026-09-23부터 확대 예정.
  다만 이 설명도 OpenAI 공식 발표문(openai.com, EGRESS_BLOCKED) 원문이 아니라 2차 보도 스니펫
  종합이므로 **정식 전면 출시 여부·최종 UX는 여전히 유동적**일 수 있다. **(미확정/실험 단계 —
  이 표기는 유지)**
  (source: [The Register](https://www.theregister.com/ai-and-ml/2026/09/16/openais-new-sponsored-agents-are-happy-to-chat-about-selling-you-things/5296946/), [Unite.AI](https://www.unite.ai/openai-tests-sponsored-agents-and-rolls-out-ai-tools-for-chatgpt-ads/), [PYMNTS](https://www.pymnts.com/news/artificial-intelligence/2026/openai-tests-sponsored-ai-agents-in-chatgpt-ads/))
- **Google, 2026-05-19 I/O 2026에서 "Gemini Spark" 공개** — Google Cloud 전용 가상머신에서 24시간
  구동되는 개인용 에이전트로, 기기가 꺼져 있어도 백그라운드에서 계속 작업을 이어간다. Gemini 3.5와
  "Google Antigravity" 하니스 기반으로 리서치·계획·후속 실행 같은 장기 과업(long-horizon task)을
  수행. 출시 시점에는 구글 자사 도구와 우선 연동, 향후 MCP를 통한 서드파티 연동 예정이며, 이후
  Chrome에 "에이전틱 브라우저"로 통합될 계획. 초기에는 신뢰 테스터 대상, 이후 미국 Google AI Ultra
  구독자 베타로 확대.
  (source: [blog.google — I/O 2026 공식 발표](https://blog.google/) 원문 EGRESS_BLOCKED, [Let's Data Science](https://letsdatascience.com/news/google-launches-gemini-spark-personal-ai-agent-50839617), [CTO Magazine](https://ctomagazine.com/google-io-2026-ai-agents-gemini-spark/), [Techlicious](https://www.techlicious.com/blog/google-gemini-spark-agent-io-2026/) 스니펫 종합)
  - **"기기 꺼진 상태에서도 백그라운드로 장기 과업을 자율 수행"이 확인되므로 "에이전틱" 표현 사용
    타당.**
- **Google, 같은 I/O 2026에서 "Daily Brief" 에이전트 공개** — 메일함·캘린더·할 일 목록을 종합해
  매일 아침 요약본을 만들고 우선순위와 다음 행동을 제안. (source: 위와 동일 스니펫 종합)
- **Google Cloud Next '26(2026-04, 공식 일자 미확인)에서 "Gemini Enterprise Agent Platform" 공개**
  — Agent Studio, 업그레이드된 Agent Development Kit, Agent Runtime, Agent-to-Agent
  오케스트레이션, Agent Gateway/Identity/Registry/Observability/Simulation/Evaluation 등 엔터프라이즈
  에이전트 인프라 풀세트. (source: [Virtualization Review](https://virtualizationreview.com/articles/2026/04/24/google-cloud-next-26-gemini-enterprise-agent-platform-leads-ai-centric-news.aspx), [Google Cloud Blog](https://cloud.google.com/blog/products/ai-machine-learning/innovations-from-google-io-26-on-google-cloud))

**트랙 1 시사점 (LG전자 UX/가전 관점)**: 세 파운데이션 모델 기업 모두 "질문하면 답하는 대화형
챗봇"에서 "기기가 꺼져 있거나 사용자가 자리를 비워도 백그라운드에서 장시간·멀티스텝을 자율
수행하는 에이전트"로 명확히 축을 옮기고 있다(Gemini Spark의 "노트북을 닫아도 계속 실행",
ChatGPT Work의 "수 시간 이어서 독립 수행", Claude의 Dreaming/멀티에이전트 오케스트레이션). 가전은
원래부터 "사용자가 지켜보지 않아도 알아서 동작하는" 제품군이라는 점에서 이 흐름과 구조적으로
잘 맞는다 — 세탁기·에어컨·로봇청소기 같은 기기가 "백그라운드 상시 에이전트"라는 프레임을 먼저
차지할 기회가 있다. 동시에 MCP가 세 회사 모두의 표준 연동 프로토콜로 수렴하고 있으므로(트랙 3
참조), LG 가전 AI 에이전트의 외부 서비스 연동 전략에서 MCP 호환성을 검토할 필요가 있다.

### 트랙 2 — 미국 소비자/B2B 프로덕트 기업의 최근 AI 에이전트 도입 사례

- **Notion — 2026-02-24 "Custom Agents" 출시**: 기존 "프롬프트를 줘야 응답하는 개인용 Agent"와
  달리, Custom Agents는 24/7 자율 실행되며 반복 업무(FAQ 응답, 현황 취합, 워크플로우 자동화)를
  스스로 처리하는 "AI 팀원"으로 설계됨. **2026-05월 Notion 개발자 플랫폼 출시** — 샌드박스에서
  커스텀 코드를 돌리는 "Workers", 외부 에이전트(Claude Code, Cursor, Codex, Decagon) 연동 지원.
  **2026-09-15 "Notion 3.7"**: 팀 전체가 재사용 가능한 AI 지침을 공유하는 "Skills" 라이브러리,
  회의 후속 업무 자동화, 서브에이전트, 더 풍부한 도구 연결, 모델 선택 UI 개편, 신규 "Notion
  Agents" iOS 앱 출시.
  (source: [TechCrunch](https://techcrunch.com/2026/05/13/notion-just-turned-its-workspace-into-a-hub-for-ai-agents/), [Notion 공식 릴리즈 노트 2026-09-15](https://www.notion.com/releases/2026-09-15), [Dataconomy](https://dataconomy.com/2026/05/14/notion-launches-developer-platform-for-ai-workflows-and-agents/))
  - UX 패턴: 별도 챗봇 창이 아니라 **워크스페이스의 "정식 팀원"으로 에이전트를 취급** — 태스크
    할당, 스레드 멘션이 가능.
- **Linear — 2026-03-24 "Linear Agent" 퍼블릭 베타 출시**(베타 기간 전 플랜 무료). 워크스페이스
  컨텍스트(이슈·프로젝트·팀·히스토리)를 이해하고 대화를 통해 실제 행동(이슈/프로젝트/마일스톤
  생성·수정, 고객 요청 요약, 스레드 코멘트 관리)을 수행하는 "정식 워크스페이스 멤버"로 동작 —
  이슈에 할당하거나(assign) 프로젝트에 추가하거나 코멘트에서 멘션해 트리아지를 맡길 수 있음.
  **2026-07-20 "Loops" 출시**(Business/Enterprise, AI 크레딧 필요) — 일정 또는 이벤트 기반으로
  자연어로 정의한 반복 자동화를 실행. Linear CEO는 3월 발표에서 "이슈 트래킹은 죽었다"고 선언하며
  에이전틱 전환을 공식화.
  (source: [The Register](https://www.theregister.com/software/2026/03/26/linear-adopts-agentic-ai-as-ceo-declares-issue-tracking-dead/5227428/), [devclass](https://www.devclass.com/development/2026/03/27/linear-moves-sideways-to-agentic-ai-as-ceo-declares-issue-tracking-dead/5211661/), [usecarly.com](https://www.usecarly.com/blog/linear-ai/))
- **Perplexity Comet — 2026년 상반기 내내 "브라우저 확장 → OS 레벨 에이전트"로 확장**. 2026-04
  "Personal Computer(Mac)" 기능으로 브라우저 창을 넘어 로컬 OS까지 에이전트 작업 범위를 확대.
  Max 구독자 대상 "Email Assistant"는 **이메일 스레드에 참조(CC)로 추가하면** 일정 조율·답장
  초안 작성·작업 완료까지 자율 수행 — 별도 챗봇 창이 아니라 **기존 이메일 워크플로우에 참조자로
  끼어드는** UX. 2026-03 기준 Deep Research는 프롬프트만으로 PPT·스프레드시트·대시보드 등
  결과물을 직접 생성. 엔터프라이즈 대상 MDM 배포 지원.
  경쟁 구도상 특기할 점: **OpenAI는 독립형 Atlas 브라우저를 접고(2026-08-09부로 서비스 중단)
  ChatGPT 내 에이전트 기능으로 방향을 틀었지만, Perplexity는 독립 브라우저 전략(Comet)을
  유지**하고 있어 "에이전틱 브라우저"를 둘러싼 전략이 회사별로 갈리는 상황.
  (source: [itechguides.com](https://www.itechguides.com/openai-and-perplexity-enter-browser-wars-to-take-on-chrome-what-changed-by-august-2026/), [nohacks.co](https://nohacks.co/blog/agentic-browser-landscape-2026), [beginnersinai.org](https://beginnersinai.org/whats-new-perplexity-2026/))
- **Figma — 2026-06-23~25 "Config 2026"(샌프란시스코, Moscone Center)에서 "Figma Agent" 오픈
  베타 공개**. 디자인 파일 안에서 직접 디자인을 생성·변형하고, 반복 작업을 자동화하고, 디자인
  피드백을 받을 수 있는 **캔버스 내장형(in-canvas) 에이전트** — 별도 채팅창이 아니라 파일 안에서
  네이티브하게 동작하는 재사용 플러그인을 직접 만들거나(레이어 재정렬, 일관된 스페이싱 적용,
  텍스트/컬러 찾기-바꾸기 등), 캔버스 위에 WebGPU 셰이더를 직접 생성할 수 있음. 관리자는 조직
  단위로 AI 기능을 토글해 끌 수 있음(거버넌스 통제).
  (source: [Figma 공식 Config 2026 페이지](https://config.figma.com/san-francisco/), [Figma Blog — The Figma Design Agent is Here](https://www.figma.com/blog/the-figma-agent-is-here/), [aidatainsider.com](https://aidatainsider.com/news/figma-unveils-ai-agents-and-code-native-design-tools-at-config-2026/))
- **Airbnb — 2026-02-13 Brian Chesky, 검색·탐색·고객지원 전반에 AI 내재화 계획 발표**. 이후
  "대화형 검색"(필터값이 아니라 자연어로 의도를 표현) 출시. 신규 "AI 리뷰 하이라이트" 기능은
  숙소별 수백 개 리뷰를 스크롤하지 않아도 입지·특징 편의시설·가족 친화도 등을 자동 요약. AI 고객
  지원 에이전트는 2026년 2분기 기준 50개 이상 언어를 지원하며, **AI 에이전트로 시작한 문의의
  약 45%가 사람 개입 없이 해결**됨(추후 음성 통화 지원으로 확대 예정). 호스트용 "Smart Setup"은
  사진+주소만으로 숙소 리스팅을 자동 생성.
  (source: [TechCrunch](https://techcrunch.com/2026/02/13/airbnb-plans-to-bake-in-ai-features-for-search-discovery-and-support/), [Fast Company](https://www.fastcompany.com/91545629/airbnb-is-adding-ai-hotel-bookings-and-social-features-in-its-biggest-app-overhaul-in-years), [rentalscaleup.com](https://www.rentalscaleup.com/airbnb-ai-strategy-2026-summer-release/))

**트랙 2 시사점 (LG전자 UX/가전 관점)**: 다섯 사례 모두 "별도 AI 챗봇 탭"이 아니라 **기존 사용
흐름/화면 안에 에이전트를 녹여 넣는(embedded-in-context)** 방향으로 수렴한다 — Figma는 캔버스
안에, Linear는 이슈/코멘트 스레드 안에, Airbnb는 검색·리뷰 안에, Perplexity는 이메일 스레드의
"참조(CC)" 자리에 에이전트를 배치한다. 만약 LG 가전 AI UX가 여전히 "AI 버튼을 누르면 별도
챗봇 화면이 뜨는" 구조에 머물러 있다면, 이 흐름은 "기존 조작 흐름(리모컨, 앱 홈 화면, 설치
마법사 등) 안에 자연스럽게 녹아든 에이전트"로 재설계할 필요가 있음을 시사한다. 또한 Notion·
Linear는 에이전트를 "워크스페이스의 정식 멤버"(할당·멘션 가능)로 취급하는데, 이는 스마트홈
생태계에서 "각 기기별 에이전트를 가족 구성원처럼 다루는" UX 메타포로 확장해볼 여지가 있다.

### 트랙 3 — 업계 전반 AI/UX 트렌드 방향 시그널

- **Gartner, 2025-08-26 보도자료: "2026년 말까지 기업 애플리케이션의 40%가 특정 작업 전용(task-
  specific) AI 에이전트를 탑재할 것"(2025년 5% 미만에서 상승)** — 다만 Gartner는 같은 시기
  (2025-06-25 보도자료) "2027년 말까지 에이전틱 AI 프로젝트의 40% 이상이 비용 급증·불명확한
  사업 가치·부족한 리스크 통제로 취소될 것"이라는 경고성 전망도 함께 내놓았다. **에이전틱 AI
  도입 자체보다 "신뢰할 수 있게 끝까지 실행하는 것"이 관건이라는 시그널.**
  (source: [Gartner 뉴스룸 — 40% 예측](https://www.gartner.com/en/newsroom/press-releases/2025-08-26-gartner-predicts-40-percent-of-enterprise-apps-will-feature-task-specific-ai-agents-by-2026), [Gartner 뉴스룸 — 프로젝트 취소 예측](https://www.gartner.com/en/newsroom/press-releases/2025-06-25-gartner-predicts-over-40-percent-of-agentic-ai-projects-will-be-canceled-by-end-of-2027))
  - **[2026-09-21 verifier 확인]** 두 보도자료의 날짜·정확한 문구를 재검색으로 대조했다. (1)
    2025-08-26 보도자료(2025-09-05 갱신) 원문: "Forty percent of enterprise applications will be
    integrated with task-specific AI agents by the end of 2026, up from less than 5% today." (2)
    2025-06-25 보도자료 원문(Gartner 애널리스트 Anushree Verma 발언 포함): "Over 40% of agentic AI
    projects will be canceled by the end of 2027, due to escalating costs, unclear business value or
    inadequate risk controls." findings의 인용은 날짜·수치·취지 모두 정확하다 — "같은 시기"라는
    표현은 두 보도자료가 실제로는 약 2개월 차이(2025-06-25 vs 2025-08-26)라 다소 느슨하지만,
    같은 해(2025년) 안이라는 점에서 실질적 오류는 아니다.
- **Model Context Protocol(MCP)이 사실상 업계 공통 표준으로 자리잡는 중**: 2025-12-09 Anthropic이
  MCP를 리눅스 재단 산하 신설 "Agentic AI Foundation(AAIF)"에 기증했고, Anthropic·Block·OpenAI가
  공동 창립사로, AWS·Google·Microsoft·Cloudflare·Bloomberg가 플래티넘 멤버로 참여했다. 2026년
  3월 기준 MCP SDK 다운로드는 월 9,700만 건(2024년 11월 출시 후 18개월 만에 970배 성장) [아래
  verifier 각주 참고], 5,800개 이상의 MCP 서버 [2026-09-21 verifier 정정 — 아래 참고] · 300개
  이상의 클라이언트가 존재하고, 포춘 500대 기업의 28%가 MCP를 배포 [2026-09-21 verifier: 신뢰도
  낮음, 아래 참고], 설문에 응한 소프트웨어 조직의 41%가 제한적 또는 광범위한 프로덕션 단계에
  있다고 보고됨 [2026-09-21 verifier 확인 — 아래 참고].
  2026-07-28에는 상태 비저장(stateless)·캐시 가능·라우팅 가능한 구조로 발전시키는 새 스펙이
  공개됨. (source: [Model Context Protocol 공식 블로그 — 2026-07-28 스펙](https://blog.modelcontextprotocol.io/posts/2026-07-28/), [digitalapplied.com — MCP 채택 통계](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol), [guptadeepak.com](https://guptadeepak.com/the-complete-guide-to-model-context-protocol-mcp-enterprise-adoption-market-trends-and-implementation-strategies/) — 통계 출처는 대부분 2차 집계 사이트로 교차검증 필요)
  - **[2026-09-21 verifier 정정] 서버 개수 불일치.** Anthropic·Linux Foundation의 1차 발표문
    (`blog.modelcontextprotocol.io/posts/2025-12-09-mcp-joins-agentic-ai-foundation/`, 2025-12-09)
    은 이미 그 시점에 "10,000개 이상의 active MCP 서버"라고 명시했고, 공식 MCP Registry API도
    2026-05-24 기준 9,652개의 최신 서버 레코드(28,959개 서버/버전 레코드 전체)를 집계했다 — 두
    수치 모두 findings가 인용한 "2026년 3월 기준 5,800개 이상"보다 크다. 시점상 더 나중인 2026-03
    수치가 그보다 앞선 2025-12 수치보다 작은 것은 앞뒤가 맞지 않는다 — "5,800개"는 다른 카운팅
    방식(특정 2차 집계 사이트의 자체 카운트)이거나 오래된/오기재된 수치일 가능성이 높다. 2027
    사업계획에 인용할 때는 "5,800개"보다 1차 출처의 "10,000개 이상"(2025-12, AAIF 발표) 또는
    "9,652개"(2026-05, 공식 Registry API) 쪽을 우선 사용할 것을 권고한다.
  - **[2026-09-21 verifier 확인 — 부분]** 월 9,700만 다운로드 수치는 1차 출처(위 AAIF 발표문,
    2025-12-09)의 "over 97 million monthly SDK downloads" 문구와 정확히 일치한다. 다만 그 1차
    출처의 시점은 2025년 12월이며 findings가 표기한 "2026년 3월"이 아니다 — 3개월 뒤에도 정확히
    동일한 숫자가 보고된다는 것은, 실측이 갱신되지 않은 채 2차 집계 사이트들이 2025-12 수치를
    2026-03 수치인 것처럼 재인용했을 가능성을 시사한다. "970배/18개월" 산수도 2024-11 출시 기준
    18개월 후는 2026-05경이라 "2026년 3월"과는 약 2개월 어긋난다(2차 출처 자체의 근사 표현으로
    보이며 findings의 오류는 아님). 수치 자체는 1차 출처로 확인되나, "2026년 3월 시점"이라는
    표기는 신뢰하지 말 것을 권고한다.
  - **[2026-09-21 verifier: 신뢰도 낮음, 정정 보류]** 포춘 500대 기업 28% 배포 수치는 재검색
    결과 복수의 독립 MCP 통계 비평 글에서 "명시된 출처 없이 반복 인용되는 수치"로 별도 지적되고
    있음을 확인했다 — 검증 가능한 1차 소스(named survey/report)를 찾지 못했다. 2027 사업계획에는
    인용하지 않거나, 인용 시 "출처 불명확" 캐비엇을 반드시 유지할 것을 권고한다(수치 자체를
    틀렸다고 단정할 근거도 없어 findings 본문은 수정하지 않고 각주만 남긴다).
  - **[2026-09-21 verifier 확인]** 41% 프로덕션 단계 수치는 digitalapplied.com 기사의 최신판이
    Stacklok의 "2026 소프트웨어 리포트"를 named 1차 소스로 명시하며(이전 판의 미확인 "78%" 수치를
    이 41% 수치로 대체했다고 그 기사 스스로 밝히고 있음), 다른 통계들보다 출처가 비교적 명확하다.
    다만 Stacklok 원문 자체는 이번 세션에서 직접 대조하지 못했다(unverifiable claims 참고).
- **"에이전틱 UX"가 하나의 독립된 디자인 분과로 굳어지는 흐름** — Smashing Magazine(2026-02)은
  에이전틱 AI UX의 핵심 설계 원칙으로 (1) 투명성(의도·자율성 경계·추론 과정·결과를 명확히
  전달), (2) 사용자 통제/개입(일시정지·수정·취소·되돌리기 권한을 에이전트 UX의 예외가 아니라
  기본 기능으로 취급), (3) 감사 추적(무엇을 검토했고 왜 그 선택을 했는지 전체 과정을 사용자가
  볼 수 있게 함), (4) 고위험 작업(대규모 송금, 대출 조건 변경, 계정 삭제 등)에서의 사람 개입
  에스컬레이션을 제시하며 "디자이너의 역할이 화면 배치에서 신뢰·통제·복구를 설계하는 일로
  이동한다"고 정리했다.
  (source: [Smashing Magazine — Designing For Agentic AI](https://www.smashingmagazine.com/2026/02/designing-agentic-ai-practical-ux-patterns/))
- **디자이너 대상 설문(참고용, 정확한 수치는 재검증 필요)**: Designer Fund·Foundation Capital이
  2026년 3월 60개국 이상 906명의 디자이너를 대상으로 진행한 "AI in Design Report 2026"이 존재하며
  AI 도구 채택이 디자인 조직 구조·채용 계획에까지 영향을 주고 있다고 보고한다. 다만
  `stateofaidesign.com` 원문은 이번 세션에서 EGRESS_BLOCKED로 직접 대조하지 못해, 구체적 수치
  인용은 보류한다. **(unverified — 원문 접근 필요)**
  (source: [moonexstudio.com 2차 인용](https://moonexstudio.com/blog/ux-ui-designers-2026-ai-adoption/), [artificialstudio.ai 2차 인용](https://www.artificialstudio.ai/blog/ai-design-report-2026))

**트랙 3 시사점 (LG전자 UX/가전 관점)**: 신뢰·투명성·통제권 UX가 에이전틱 제품의 핵심 설계
요소로 부상하고 있다는 점은, LG 가전이 향후 "세탁 코스를 알아서 바꾼다", "온도를 알아서
조절한다" 같은 실제 물리적 행동을 자율 수행하는 에이전트를 내놓을 때 특히 중요해진다 — 단순
기능 추가가 아니라 "왜 이렇게 했는지 설명", "즉시 되돌리기/취소", "고위험 동작 전 사용자
확인" 같은 컨트롤 UX 자체를 2027 로드맵의 정식 항목으로 넣어야 한다는 신호다. 동시에 Gartner의
"40% 프로젝트 취소" 경고는 에이전틱 기능을 서둘러 탑재하는 것보다 "신뢰할 수 있게 끝까지
실행되는" 소수의 기능에 집중하는 편이 안전하다는 반대 신호이기도 하다. MCP의 사실상 표준화는
LG 가전 AI 에이전트가 외부 서비스(캘린더, 배달앱, 스마트홈 허브 등)와 연동할 프로토콜 전략에
직접적인 참고가 된다.

## Per-company notes

### Anthropic
- Claude Managed Agents: Dreaming(자가학습형 메모리), Outcomes(rubric 기반 채점+재작업 루프),
  멀티에이전트 오케스트레이션, 웹훅 — 2026-05-06/07 Code with Claude에서 공개.
- 2026-09 기준 자동 권한 정책, ant CLI 세션 연결 베타, 커머스 에이전트 블루프린트 추가
  **[2026-09-21 verifier 정정]** (Anthropic 공식 문서·GitHub로 원문 대조 완료, 더 이상
  "출처 신뢰도 낮음" 아님 — 위 트랙 1 해당 항목 참고).

### OpenAI
- ChatGPT Work(2026-07-09) — 목표 지향형 멀티스텝 자율 실행, 앱 연동 Plugins 디렉터리, 예약 실행.
- Workspace Agents(2026-04-22) — 클라우드 상시 실행 에이전트.
- Sponsored Agents(2026-09, 미확정) — 광고 후원형 대화 에이전트, 테스트 단계.
- Atlas 독립 브라우저는 2026-08-09부로 서비스 종료, 에이전트 기능은 ChatGPT 본체로 통합하는
  방향으로 전략 선회.

### Google
- Gemini Spark(2026-05-19 I/O) — 상시 백그라운드 개인 에이전트, Google Antigravity 하니스,
  MCP 서드파티 연동 예정, Chrome 에이전틱 브라우저 통합 예정.
- Daily Brief(2026-05-19 I/O) — 메일/캘린더/할일 종합 아침 브리핑 에이전트.
- Gemini Enterprise Agent Platform(2026-04 Google Cloud Next) — Agent Studio/Runtime/Gateway/
  Identity/Registry/Observability/Simulation/Evaluation 풀세트.

### Notion
- Custom Agents(2026-02-24, 24/7 자율), 개발자 플랫폼+Workers(2026-05), Skills+서브에이전트+
  iOS 앱(Notion 3.7, 2026-09-15).

### Linear
- Linear Agent 퍼블릭 베타(2026-03-24) — 워크스페이스 정식 멤버형 에이전트.
- Loops(2026-07-20) — 자연어 기반 예약/이벤트 자동화.
- CEO가 "이슈 트래킹은 죽었다"고 공개 선언(2026-03-26 보도).

### Perplexity (Comet)
- 브라우저 확장 → OS 레벨(Personal Computer on Mac, 2026-04) 확장.
- Email Assistant — 이메일 스레드 CC 방식의 임베디드 에이전트(Max 구독자).
- Deep Research가 프롬프트에서 바로 PPT/스프레드시트/대시보드 산출(2026-03 기준).
- OpenAI Atlas 종료와 대비되는, 독립 에이전틱 브라우저 전략 유지.

### Figma
- Figma Agent 오픈 베타(Config 2026, 2026-06-23~25) — 캔버스 내장형 에이전트, 파일 내 네이티브
  플러그인/셰이더 생성, 조직 단위 AI 기능 온오프 거버넌스.

### Airbnb
- 대화형 검색, AI 리뷰 하이라이트, AI 고객지원(2026 Q2 기준 50+ 언어, 문의의 약 45% 무인 해결),
  호스트용 Smart Setup(사진+주소로 리스팅 자동 생성).

## Open questions / gaps

- **[2026-09-21 verifier 확인 — 재확인됨, 미해결]** `openai.com`, `claude.com`, `blog.google`,
  `stateofaidesign.com` 원문은 이번 verifier 세션에서도 동일하게 EGRESS_BLOCKED로 직접 접근하지
  못했다(우회 시도 없음). 다만 Anthropic의 별도 공식 서브도메인 `platform.claude.com`,
  `code.claude.com`, `github.com/anthropics/*`는 차단되지 않아 이를 통해 아래 두 항목은 1차
  문서로 해결했다. `openai.com`·`blog.google`·`stateofaidesign.com`에 준하는 대체 공식 도메인은
  찾지 못해 해당 출처들은 여전히 2차 기사 스니펫에 의존한다 — 접근 가능한 세션에서 재확인 권장.
- **[2026-09-21 verifier 정정 — 해결됨]** Anthropic의 2026-09 업데이트(자동 권한 정책, ant CLI
  세션 연결, 커머스 에이전트 블루프린트)는 verifier가 Anthropic 공식 문서(`platform.claude.com`)
  및 공식 GitHub(`anthropics/commerce-agents`)로 원문 대조를 완료했다 — 더 이상 단일 애그리게이터
  출처가 아니다. 자세한 내용은 위 "트랙 1 — Anthropic" 해당 항목의 verifier 각주 참고.
- **[2026-09-21 verifier 정정 — 해결됨]** "/goal"과 "Outcomes"는 **서로 다른 별개 기능**임을
  Anthropic 공식 문서(`code.claude.com/docs/en/goal`)로 확인했다. "/goal"은 **Claude Code(CLI
  코딩 도구)**의 세션 범위 슬래시 명령으로 v2.1.139(2026-05 무렵)에 도입되었으며, 매 턴 종료 후
  별도의 소형 판정 모델(기본 Haiku)이 완료 조건 충족 여부를 판단하는 "Stop hook" 메커니즘 기반
  이다. 반면 "Outcomes"는 **Claude Managed Agents(클라우드 에이전트 플랫폼)** 기능으로, 개발자가
  작성한 rubric을 독립된 채점 모델이 평가해 재작업 루프를 트리거하는 방식이다 — 제품 자체가
  다르다(Claude Code CLI vs. Managed Agents 플랫폼). 개념적으로는 "판정 모델이 완료 여부를
  결정한다"는 설계 패턴을 공유한다. "SitePoint 단일 출처" 우려는 공식 문서로 대체 검증되어
  해소됐다(SitePoint 원문 자체는 이번 세션 검색에서 발견되지 않았으나, 핵심 사실은 1차 출처로
  확인됨). (source: [code.claude.com/docs/en/goal](https://code.claude.com/docs/en/goal))
  - **[2026-09-21 verifier 확인 — 보강, 완전 해소는 아님]** OpenAI "Sponsored Agents"는 여전히
    초기 테스트 단계가 맞다(미국 일부 광고주 대상). 사용자 UX(별도 라벨링된 대화, ChatGPT 본답변과
    분리)와 국제 확대 일정(2026-09-23~)은 이번 재조사로 확인됐다 — 자세한 내용은 위 "트랙 1 —
    OpenAI" 해당 항목 참고. 정식 전면 출시 여부와 장기 UX 방향은 여전히 유동적이므로 "다음
    세션에서 후속 조사 가치가 있다"는 원 researcher의 판단은 유효하게 유지한다.
- **[2026-09-21 verifier 정정 — 부분 해결]** MCP 채택 통계는 1차 출처(AAIF 공식 발표,
  2025-12-09)와 대조를 완료했다 — 위 트랙 3 MCP 항목의 인라인 각주 참고. 요약: 월 9,700만
  다운로드는 1차 출처와 수치는 일치하나 표기된 시점("2026년 3월")이 실제로는 1차 출처의 시점
  (2025년 12월)일 가능성이 높고, 5,800개 서버 수치는 1차 출처(10,000개 이상, 2025-12)·공식
  Registry API(9,652개, 2026-05)와 모순되어 오류로 추정되며, 포춘 500대 28% 수치는 named 1차
  소스를 찾지 못해 신뢰도가 낮고, 41% 프로덕션 단계 수치는 Stacklok 2026 소프트웨어 리포트라는
  비교적 명확한 출처가 새로 확인됐다.
- "AI in Design Report 2026"(Designer Fund·Foundation Capital, 906명·60개국, 2026-03 설문)의
  구체적 수치는 원문(stateofaidesign.com) 접근 불가로 이번 findings에 반영하지 않았다 — LG UX
  조직 벤치마크에 유용할 수 있으므로 접근 가능한 세션에서 재조사 권장.
  (`ux-ai-capability-research` 렌즈와도 연결될 수 있음.) **[2026-09-21 verifier 확인 — 미해결]** 이번 verifier 세션에서도
  `stateofaidesign.com`은 동일하게 EGRESS_BLOCKED로 확인되어, 원 researcher의 접근 제약과
  동일하다(우회 시도 없음) — 계속 재조사 필요 항목으로 남겨둔다.
  - **결과 문서 형식 참고**: 이번 파일은 `ai-ux-trend-research` 스킬(사업/시장 경쟁력 렌즈)에
  가깝게 작성했다. 만약 `ux-ai-capability-research`(내부 역량 강화) 또는
  `org-role-evolution-research`(조직·인력 구조) 렌즈로도 이 소스들을 재해석하고 싶다면, 해당
  스킬 브리프에 맞춰 "내부 역량 강화 시사점"/"조직·인력 구조 시사점" 섹션을 별도로 추가하는 후속
  작업이 필요하다 — 이번 조사는 요청받은 대로 사업/제품 전략 축(트랙별 시사점 메모)만 작성했다.
