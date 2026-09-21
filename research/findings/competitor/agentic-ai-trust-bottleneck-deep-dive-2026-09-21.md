# 에이전틱 AI의 신뢰 병목 — 표면적 결론을 넘어선 구체적 메커니즘
Date: 2026-09-21
Scope: 스마트홈 및 인접 소비자 도메인(쇼핑 에이전트, 음성 AI, 로봇청소기)에서 실제 발생한 에이전틱 AI 신뢰 실패 사건, 정량적 불신 원인 데이터, 기업별 UX 신뢰 확보 패턴, EU AI Act 고위험 규제의 정확한 조문, 성공/실패 기업 대비 분석. 대상 기업: Google(Gemini for Home), Amazon(Alexa+, Buy for Me), Ecovacs, Apple(Siri), Microsoft(Copilot), Samsung(빅스비/스마트싱스, 배경 확인용).

이 파일은 "에이전틱 AI는 기능보다 신뢰가 중요하다"는 이미 알려진 결론을 반복하지 않고, 그 신뢰가 구체적으로 왜·어떻게 무너지는지, 무엇이 회복시키는지를 사건·수치·UI 디테일 단위로 파고든다.

---

## Key findings

### 1) 실제 신뢰 붕괴 사건 3건 (날짜·서비스·피해·대응까지)

**사건 A — Ecovacs Deebot X2 로봇청소기 원격 탈취·욕설 사건 (2024-05, 2024년 10월 대대적 보도)**
- 2024-05-24, 미국 로스앤젤레스와 미네소타에서 각각 Ecovacs Deebot X2 로봇청소기가 해커에게 원격 장악되어 스피커로 인종차별적 욕설을 내뱉고, LA 사례에서는 반려견을 쫓아다니도록 원격 조종당하는 사건이 발생했다 (source: [ABC News](https://www.abc.net.au/news/2024-10-11/robot-vacuum-yells-racial-slurs-at-family-after-being-hacked/104445408), [incidentdatabase.ai #842](https://incidentdatabase.ai/cite/842)).
- 텍사스 엘패소에서도 별도 피해자가 한밤중 로봇청소기가 욕설을 내뱉어 전원을 뽑았다는 사례가 보도됨 — 첫 사건 발생 5일 뒤 (source: incidentdatabase.ai #842).
- 근본 원인은 AI의 "판단 오류"가 아니라 블루투스 PIN 인증이 취약해 최대 450피트(약 130m) 밖에서 접속·탈취가 가능했던 보안 설계 결함. 2024-08-08~11 DEF CON 32에서 연구자 Dennis Giese·Braelynn Luedtke가 이 취약점을 공개 발표했다 (source: [TechCrunch](https://techcrunch.com/2024/08/09/ecovacs-home-robots-can-be-hacked-to-spy-on-their-owners-researchers-say/)).
- **회사 대응**: DEF CON 발표 직후 Ecovacs는 "소프트웨어 수정은 하지 않겠다"는 취지로 소극적으로 대응했으나, 언론 보도 확산 후 입장을 바꿔 2024-11 펌웨어 업데이트를 배포했다. 그러나 보안 연구자는 이 패치가 "취약점을 막기에 불충분하다"고 재반박했고, 피해자는 회사로부터 사전 통지를 전혀 받지 못했다고 비판했다 (source: [Malwarebytes](https://www.malwarebytes.com/blog/news/2024/10/robot-vacuum-cleaners-hacked-to-spy-on-insult-owners), [incidentdatabase.ai #842]).
- **시사점**: 이 사건은 "에이전틱 AI가 잘못 판단했다"기보다 "자율 제어권을 가진 기기의 보안이 뚫리면 사용자가 물리적 공간에서 직접 공격당하는 경험을 한다"는, 스마트홈 특유의 신뢰 리스크를 보여준다 — 오작동보다 더 무서운 것은 "탈취"다.

**사건 B — Amazon "Buy for Me" 에이전틱 쇼핑, 무단 리스팅·오배송 (2025-04 출시, 2026-01 반발 확산)**
- Amazon은 2025-04 "Buy for Me" 기능을 발표, Amazon 쇼핑 앱 안에서 AI가 타 브랜드 웹사이트 상품을 대신 구매해주는 기능을 시작했다 (source: [Retail Dive](https://www.retaildive.com/news/amazon-buy-for-me-agentic-ai-third-party-sites/745047/)).
- 문제는 AI가 자동으로 상품 리스팅(제목·설명)을 생성해 Amazon 마켓플레이스에 게시하는데, 정작 해당 브랜드는 Amazon 셀러 계정을 개설한 적도, 판매에 동의한 적도 없었다는 것. 2026-01 SiliconANGLE·CNBC 보도로 반발이 확산됐다 (source: [SiliconANGLE](https://siliconangle.com/2026/01/06/amazons-ai-agents-spark-backlash-retailers-listing-products-without-knowledge/), [CNBC](https://www.cnbc.com/2026/01/06/amazons-ai-shopping-tool-sparks-backlash-from-some-online-retailers.html)).
- 실질적 소비자 피해: 일부 브랜드는 "이미 품절되었거나 애초에 판매한 적 없는 상품"이 Amazon에서 판매되고 있었다고 밝혔다 — 즉 에이전트가 실시간 재고·판매 자격을 검증하지 않은 채 주문을 처리해 소비자에게 잘못된 배송/미배송 경험을 안겼다 (source: [Modern Retail](https://www.modernretail.co/technology/brands-are-upset-that-buy-for-me-is-featuring-their-products-on-amazon-without-permission/)).
- **회사 대응**: Amazon은 브랜드가 `branddirect@amazon.com`으로 이메일을 보내면 옵트아웃할 수 있다고 안내했지만, 다수 판매자는 "안내만큼 빠르거나 쉽지 않다"고 반박했다 (source: valueaddedresource.net, via WebSearch — 원문 WebFetch 차단으로 직접 인용 미검증, unverified 표기).
- **시사점**: 이 사건은 "에이전트가 사용자를 위해 한 행동이 제3자(브랜드)의 동의 없는 대상화로 이어질 수 있다"는, 소비자-플랫폼 2자 관계를 넘어선 에이전틱 AI 특유의 신뢰 문제를 보여준다. 사용자 입장에서도 "내가 주문한 게 정말 정품/정상 재고인가"를 신뢰할 수 없게 만든다.

**사건 C — Google Home/Nest, Assistant→Gemini 전환에 따른 대규모 기기 오작동 및 집단소송 (2025년 배경 → 2026년 현재진행형)**
- 배경(2025년): Google Nest Hub/Nest Hub Max/Nest Mini/Nest Audio 기기가 음성 명령에 반응하지 않거나 무작위로 꺼지고 켜지며, 기기 간 연결이 끊기는 결함이 이어지자, 2025-11-24 Lieff Cabraser·Kaplan Gore 로펌이 연방 집단소송을 제기했다 (source: [BusinessWire](https://businesswire.com/news/home/20251124006331/en/Lieff-Cabraser-and-Kaplan-Gore-Announce-Filing-of-Federal-Class-Action-Lawsuit-Against-Google-Over-the-Defective-Google-Nest-Hub-Google-Nest-Hub-Max-Google-Nest-Mini-and-Google-Nest-Audio-Devices)).
- **2026년 현재 상황**: Gemini로 전환된 Google Home 앱의 최근 리뷰 4,000건(2026-04-13~2026-09-08, 147일간)을 분석한 결과 53.1%가 별점 1점이었고, 120자 이상 구체적 불만을 남긴 1,340건 중 136건이 명시적으로 "Assistant→Gemini 전환"을 원인으로 지목했다 — 이 비율은 5개월간 거의 변하지 않았다 (source: [Unstar](https://unstar.app/blog/google-home-gemini-voice-commands-worse-reviews-2026), WebSearch로 확인, 원문 직접 인용은 WebFetch 차단으로 미검증). 사용자들은 "음성 인식이 더 불안정해졌고 앱이 느려졌으며 이전 버전으로 돌아갈 공식적인 방법이 없다"고 지적한다.
- 별개로 진행 중인 사생활 침해 소송(Google Assistant가 의도치 않게 활성화되어 대화를 녹음·제3자 검수업체에 전달한 사건)은 2026-08-27까지 클레임 접수, 2026-10-01 최종 승인 심리가 예정되어 있으며 Google·Alphabet이 6,800만 달러를 지급하기로 합의했다 (source: [ClaimDepot](https://www.claimdepot.com/settlements/google-assistant-privacy-litigation)).
- **회사 대응(2026년)**: Google은 "여러 집에 있는 조명을 모두 끄는" 명령이 엉뚱한 집을 건드리는 문제, "주방을 꺼줘"가 관련 없는 기기까지 묶어버리는 문제 등을 구체적으로 인정하고 기기 타겟팅 로직을 수정했다고 밝혔으며, Chief Product Officer가 직접 문제를 인정하고 "2026년 가을 출시분에서 대규모 개선"을 공언했다 (source: [Android Police](https://www.androidpolice.com/google-fixes-geminis-biggest-google-home-frustrations/)).
- **시사점**: 이 사건은 "LLM 기반 에이전트는 확률적으로 동작하기 때문에 과거의 결정론적 음성비서보다 예측 불가능성이 근본적으로 높다"는 구조적 문제를 보여준다 — 템플릿 매칭 방식(결정론적, "맞는 문구"를 쓰면 100% 동작)에서 LLM 방식(확률적, 매번 다르게 해석될 수 있음)으로 전환하는 순간 신뢰가 흔들리는 것은 개별 버그가 아니라 아키텍처 전환의 본질적 비용이다.

**참고 — Alexa+도 유사한 신뢰 문제 보고 (2025-03 얼리 액세스 시작, 2026년까지 지속)**
- Amazon은 2025-03부터 Alexa+를 단계적으로 출시했고, 2026-02 미국에서 정식 공개했다. 2026년 초 Wired 등의 실사용 테스트에서 "작업을 절반만 완료하거나 중간에 명령을 이해하지 못하는" 현상, 발표 당시 언급됐던 기능(Grubhub 음성 주문, 아이 동화 모드 등)의 미구현이 지적됐다 (source: [uprisera.com](https://uprisera.com/blog/en/alexa-plus-failing-amazon-ai-assistant-struggles-2026), WebSearch로 확인).

### 2) 불신의 "정확한 이유" — 정량 데이터

여러 2026년 설문이 서로 다른 질문/모집단을 사용해 수치가 다르므로, 출처별로 구분해 제시한다 (하나의 수치로 뭉뚱그리지 않음).

- **Menlo Ventures "State of Consumer AI" (2026)**: 미국 소비자의 39%만이 AI 에이전트가 일상적 구매를 대신하는 것을 신뢰하며, 고가 품목 구매의 경우 신뢰 비율이 34%로 더 낮아진다 (source: [Menlo Ventures](https://menlovc.com/perspective/2026-the-state-of-consumer-ai/)).
- **Forrester (Forbes 기고, 2026-02-02)**: 미국 소비자 중 AI가 주문을 대신 넣는 것을 신뢰하는 비율은 14%에 불과하며, Z세대(29%)·밀레니얼(30%)이 상대적으로 신뢰도가 높다 (source: [Forbes/Forrester](https://www.forbes.com/sites/forrester/2026/02/02/agentic-commerces-next-phase-hinges-on-closing-the-consumer-trust-gap/)). — Menlo(39%)와 Forrester(14%) 수치 차이가 큰데, 설문 문항·표본이 다른 것으로 추정되며 원 설문 방법론까지는 확인하지 못함 (unverified, 추가 확인 필요).
- **Quad/Morningstar (2026-04-13 발표)**: 미국 소비자의 75%가 "AI 쇼핑 추천 결과가 광고비로 좌우된다면 신뢰를 잃겠다"고 답했고, 동일하게 75%가 "브랜드가 AI 에이전트 노출에 돈을 낸다면 그 브랜드를 덜 신뢰하겠다"고 답함 (source: [PR Newswire](https://www.prnewswire.com/news-releases/75-of-americans-say-they-would-lose-trust-in-ai-shopping-if-results-were-sponsored-302739901.html)).
- **Klaviyo "Consumer Trust in AI" (2026)**: 소비자 53.9%가 "AI가 사기(fraud) 위험을 높인다"고 인식하며, 55%가 "AI 에이전트가 대신 구매하는 것이 불편하다"고 답했다. 43%는 "개인정보가 오용되면 해당 브랜드와 완전히 거래를 끊겠다"고 응답. 57%는 "브랜드가 고객 지원을 AI 위주로 운영하면 신뢰가 떨어진다"고 답했는데 이는 전년 53%에서 상승한 수치다. 14%는 "AI 에이전트가 스스로 AI임을 명확히 밝히지 않으면 신뢰를 잃는다"고 답했다 (source: [Klaviyo](https://www.klaviyo.com/solutions/ai/consumer-trust-in-ai)).
- **세대별 차이**: "즐겨 찾는 브랜드가 마케팅 대부분에 AI를 쓰면 신뢰가 떨어진다"는 응답이 Z세대 54%, X세대 33%, 베이비부머 32%로, 오히려 젊은 세대가 AI 남용에 더 민감했다 (source: Klaviyo, 상동).

→ **뻔한 결론이 아닌 지점**: "신뢰가 중요하다"가 아니라, **트랜잭션(구매·결제) 단계에서 신뢰가 가장 먼저, 가장 크게 무너진다**는 것 — 정보 탐색·추천 단계의 신뢰와 실제 "내 돈을 쓰는" 단계의 신뢰는 수치상 완전히 다른 층위다(14~39% vs 정보성 상호작용에 대한 신뢰는 이보다 높은 경향). LG전자 AI 홈 맥락에서 "기기 제어 자동화"도 이 트랜잭션적 신뢰(예: 가스밸브 잠금, 난방 조절, 구매)에 해당하므로 동일한 저신뢰 구간에 놓인다.

### 3) 실제 제품에 적용된 구체적 UX 패턴 (기업/사례별)

1. **"3버튼 확인" 패턴 (업계 공통, 다수 에이전틱 제품에서 관찰)**: "진행(Proceed)"과 "취소(Cancel)" 2개 버튼만 두는 대신 "수정(Edit)"을 추가한 3버튼 구조. 이진 선택이 실제 사용자의 애매한 심리 상태(완전 승인도 완전 거부도 아닌 "일부만 바꾸고 싶다")를 반영하지 못한다는 문제의식에서 나온 패턴 — 예: 되돌릴 수 없는 작업(이메일 발송, 예약, 데이터 삭제) 전에 "무엇을 하려는지 미리 보여주고" 승인을 구하되, 승인 UI에 수정 경로를 항상 열어둔다 (source: [Eleken](https://www.eleken.co/blog-posts/agentic-ux-examples)).
2. **"미리보기 → 확인 → 실행(preview → confirm → commit)" 3단계 흐름**: 파괴적/비가역적 작업일수록 확인 화면을 접힌 패널(collapsed panel)에 숨기지 않고 영향 범위를 명시적으로 펼쳐 보여주는 것이 권장 패턴. 일반적인 "정말 하시겠습니까?" 식 뭉뚱그린 확인창은 안티패턴으로 지목된다 (source: [Smashing Magazine, 2026-02](https://www.smashingmagazine.com/2026/02/designing-agentic-ai-practical-ux-patterns/), WebSearch로 확인).
3. **행동 기록 + 되돌리기(Undo) 타임라인**: 에이전트가 수행한 모든 작업을 시간순으로 남기고, 가능한 경우 되돌리기 버튼을 제공하는 것이 "가장 보편적으로 통하는 신뢰 메커니즘"으로 꼽힌다. 단, 이메일 200통 발송처럼 물리적으로 되돌릴 수 없는 작업은 애초에 "사후 사과 화면"이 아니라 "사전 확인 체크포인트"로 설계해야 한다는 것이 핵심 — 되돌리기는 만능이 아니다 (source: Smashing Magazine, 상동).
4. **점진적 자율성(Progressive Autonomy)**: 에이전트를 처음에는 "감독 모드"(모든 행동에 승인 필요)로 시작시키고, 사용자가 신뢰를 쌓을수록 에이전트의 자율 권한 범위를 넓혀가는 패턴. 신뢰를 "한 번에 다 주거나 안 주거나"가 아니라 "단계적으로 위임"하는 구조로 설계한다 (source: Smashing Magazine, 상동).
5. **Google Home/Gemini의 스코프 좁히기(수정 사례, 2026)**: "모든 조명을 꺼줘"라는 명령이 여러 집(멀티홈) 계정에서 엉뚱한 집까지 건드리던 문제를 "현재 위치한 집으로 한정"하도록 수정, "주방을 꺼줘"가 무관한 기기까지 묶던 문제를 "주방에 배정된 조명만"으로 좁히고, 제조사 메타데이터를 활용해 "Table Glow" 같은 커스텀 이름의 기기도 정확히 "램프"로 분류하도록 개선 — 즉 신뢰 회복 UX는 "더 화려한 설명 UI"가 아니라 "명령의 물리적 적용 범위를 정확히 좁히는 것" 자체였다 (source: [Android Police](https://www.androidpolice.com/google-fixes-geminis-biggest-google-home-frustrations/)).
6. **Apple의 "구조화된 의도(structured intent) + 결정론적 실행" 접근**: Apple은 차세대 Siri를 자율 에이전트로 만들되 대화의 모호성을 자유롭게 확률적으로 해석하게 두지 않고, 구조화된 의도(structured intents)와 결정론적 실행(deterministic execution), 앱 상태·권한에 대한 명확한 구분(disambiguation)에 기반하도록 설계 방향을 잡았다 — 메시지 전송·송금·파일 변경처럼 사용자가 즉시 체감하는 실수를 막기 위한 설계 철학이다. Private Cloud Compute를 통한 상태 비저장(stateless) 처리, 검증 가능한 투명성(attestation)도 동일한 신뢰 확보 장치로 제시된다 (source: [ValueAdd VC](https://valueaddvc.com/blog/apple-intelligence-2026-what-apples-ai-actually-does-and-what-it-still-cant), WebSearch로 확인).
7. **Microsoft Copilot(2026)의 권한 스코핑**: Microsoft 365 Copilot의 선언적 에이전트(declarative agent)마다 Microsoft Entra Agent ID를 자동 발급해, 각 에이전트가 접근할 수 있는 커넥터 권한·조건부 액세스 정책·DLP(데이터유출방지) 거버넌스를 개별적으로 스코핑한다. 또한 에이전트가 실행 전 사용자 확인을 요구하도록 기본 설계되어 있고, 이를 전역적으로 끄는 공식 설정은 제공되지 않는다 — "기본값을 확인 요구로 강제"하는 것 자체가 신뢰 장치다 (source: [Microsoft Learn](https://learn.microsoft.com/en-my/answers/questions/5921449/copilot-declarative-agent-always-shows-confirmatio)).

### 4) EU AI Act — "고위험 규제"의 정확한 내용과 스마트홈 적용 여부

**뭉뚱그리지 않고 정리하면:**

- Annex III(제6조 2항 관련)가 정의하는 고위험 AI 8개 영역은 ① 생체인식(biometrics) ② 핵심 인프라(critical infrastructure) ③ 교육·직업훈련 ④ 고용 ⑤ 필수 민간·공공서비스 접근(신용평가 등) ⑥ 법 집행 ⑦ 이주·망명·국경관리 ⑧ 사법 행정·민주적 절차이다 (source: [euaiact.com](https://www.euaiact.com/annex/3), [Timelex](https://www.timelex.eu/en/blog/7-steps-identify-if-your-ai-system-high-risk-under-ai-act)).
- **스마트홈/가전 자체는 이 8개 영역에 명시적으로 포함되지 않는다.** 다만 "핵심 인프라" 항목이 "전기·가스·난방·수도 공급의 안전 구성요소(safety component)로 사용되는 AI 시스템"을 고위험으로 규정하므로, 가정용 냉난방(HVAC) 자동제어 AI나 스마트 계량기 제어 AI 등 에너지 공급에 안전 구성요소로 관여하는 경우 이 조항에 걸릴 가능성이 있다 — 로봇청소기·냉장고 등 일반 가전 AI는 원칙적으로 8개 영역 어디에도 해당하지 않는 것으로 보인다(다만 라디오 장비 규제와 결합 시 별도 판단 필요, unverified 최종 결론).
- 무선기기(radio equipment) 지침과 결합해, 스마트 가전 등 "무선 신호를 송수신하는 통상적 제품"에 탑재된 AI가 안전 구성요소(safety component)로 작동하는 경우 별도로 고위험 분류될 수 있다는 논의가 있다 (source: [Global Policy Watch](https://www.globalpolicywatch.com/2025/07/when-is-a-safety-component-of-radio-equipment-a-high-risk-ai-system-under-the-eu-artificial-intelligence-act/) — 2025-07 자료, 배경 설명용).
- 고위험으로 분류된 AI 시스템에 실제로 부과되는 의무는 제9~15조에 구체적으로 명시된다: **제9조** 전체 생애주기(설계~시판 후 모니터링)에 걸친 문서화된 위험관리체계 구축, **제10조** 학습·검증·테스트 데이터셋의 편향 탐지·완화 의무를 포함한 데이터 거버넌스, **제11조** 시판 전 준수를 입증하는 기술문서 작성, **제12조** 위험 식별과 사후 모니터링을 위한 자동 이벤트 로깅(기록보존), **제13조** 배포자가 출력을 해석할 수 있도록 하는 투명성·사용설명서 제공, **제14조** 인간의 감독(human oversight)을 가능하게 하는 설계, **제15조** 정확성·견고성·사이버보안 기준 충족 (source: [AI Act Service Desk](https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-15), [hyperproof.io](https://hyperproof.io/ultimate-guide-to-the-eu-ai-act/)).
- **시행 시기(2026년 최신 변경 사항, 매우 중요)**: 원래 Annex III 고위험 의무는 2026-08-02부터 적용될 예정이었으나, 2026년 옴니버스 개정(Regulation (EU) 2026/1744, 2026-07-24 공포, 2026-07-27 발효)으로 **독립형(standalone) 고위험 AI 시스템(Annex III) 의무는 2027-12-02로, 이미 EU 제품안전법 적용을 받는 제품에 내장된 AI(Annex I) 의무는 2028-08-02로 각각 연기**되었다. 다만 제50조(투명성·AI 생성 콘텐츠 라벨링), GPAI(범용 AI) 제공자 의무(2025-08-02부터 이미 적용 중), 제5조 금지행위 규제(2025-02-02부터 이미 적용 중)는 원래 일정대로 유지된다 (source: [Gibson Dunn](https://www.gibsondunn.com/eu-ai-act-omnibus-agreement-postponed-high-risk-deadlines-and-other-key-changes/), [Cloud Security Alliance](https://labs.cloudsecurityalliance.org/research/csa-research-note-eu-ai-act-high-risk-deadline-omnibus-20260/)).
- **시사점**: "EU AI Act가 스마트홈을 고위험으로 규제한다"는 식의 단순화는 부정확하다. 오히려 (1) 스마트홈 일반 가전은 8개 고위험 영역에 직접 해당하지 않고, (2) 설령 해당 의무가 발생하더라도 실제 적용 시점이 2027-12-02(또는 2028-08-02)로 미뤄져 있어 단기적으로 LG전자 가전 AI 자체에 직접적 강제 규제 리스크는 낮다. 반면 이미 시행 중인 제5조(금지행위)·제50조(AI 생성물 라벨링) 의무는 지금 당장 적용되므로, "AI 홈 허브가 사용자와 대화할 때 AI임을 명확히 고지"하는 투명성 요건은 이미 실무적으로 챙겨야 한다.

### 5) 신뢰 확보 성공 기업 vs 실패 기업 — 무엇이 차이를 만드는가

- **실패 패턴(Google, Amazon 초기)**: 대규모 사용자 기반에 기능을 먼저 배포하고 사후에 버그를 수정하는 "선배포-후수정" 전략. Google은 Assistant→Gemini 전환을 강행한 뒤 5개월 넘게 동일 비율(136/1,340건, ~10%)의 불만이 개선되지 않았고, 결국 집단소송(2025-11-24)까지 이어졌다. Amazon도 "Buy for Me"를 브랜드 동의 없이 자동 적용한 뒤에야 옵트아웃 절차를 사후 마련했다. 공통점은 **"동의를 구하지 않고 먼저 실행한 뒤, 문제가 커지면 대응한다"**는 순서다.
- **신중 전략(Apple)**: Apple은 차세대 Siri를 2025년에서 2026년으로 연기했고, 자율 에이전트 기능을 결정론적 실행·구조화된 의도 처리가 가능해질 때까지 의도적으로 늦췄다. 업계에서는 이를 "속도에서 밀리지만 버블이 흔한 분야에서 신중함의 가치를 검증하는 사례"로 평가한다 — 다만 이 전략이 "성공"인지는 2026년 시점에서도 아직 결과로 증명되지 않았다(신중함=성공을 보장하지 않음, unverified 결론).
- **부분 성공 패턴(Google의 사후 대응)**: Google은 실패를 인정한 뒤 "명령의 적용 범위를 좁히는" 구체적 기술 수정을 신속히 공개하고 CPO가 직접 책임 있는 커뮤니케이션을 했다는 점에서, 최소한 "실패를 은폐하지 않고 구체적으로 무엇을 고쳤는지 공개"하는 방식은 참고할 만하다.
- **차이를 만드는 핵심 요인**: (1) 자율 실행 전 "명시적 동의/확인" 절차를 기본값으로 두었는가, (2) 실패 시 "무엇이, 왜 잘못됐는지"를 구체적으로 공개했는가, (3) 사용자가 언제든 이전 방식(비-AI 경로)으로 되돌아갈 수 있는 탈출구를 남겨뒀는가 — 세 가지 모두에서 "예"인 기업이 없다는 점이 2026년 현재 업계의 공통된 약점이다.

---

## 사업적 시사점 (LG전자)

1. **"AI 홈 허브가 기기를 직접 제어하는 자동화"는 EU 규제보다 사용자 신뢰 붕괴 자체가 더 큰 단기 리스크다.** EU AI Act 고위험 의무는 2027-12-02까지 유예됐으므로 규제 대응을 이유로 기능 출시를 늦출 명분은 약하다. 반대로 Google/Amazon 사례처럼 "선배포 후수정"으로 갔다가는 국내에서도 유사한 집단 불만·신뢰 붕괴가 가능하므로, 규제보다 UX 설계(확인·되돌리기·범위 좁히기)에 자원을 먼저 투입해야 한다.
2. **"3버튼 확인 + 미리보기→확인→실행" 패턴, "명령의 물리적 적용 범위를 명시적으로 좁히는" 설계를 LG 씽큐 온/AI 홈 자동화 실행 전 단계에 표준으로 채택할 것.** Google이 실제로 고친 것이 "설명을 더 화려하게 한 것"이 아니라 "이 집 vs 저 집, 이 방 vs 저 방을 정확히 구분하는 스코프 로직"이었다는 점이 시사하듯, LG도 멀티디바이스·멀티스페이스 환경(예: 여러 대의 씽큐 기기, 여러 방)에서 명령 대상 식별 정확도를 최우선 신뢰 지표로 삼아야 한다.
3. **트랜잭션적 자동화(가스밸브 제어, 구매·주문 대행 등)는 정보성 응답과 다른 신뢰 구간에 있다는 점을 제품 로드맵에 반영할 것.** 소비자 설문에서 구매 대행 신뢰도가 14~39%에 불과한 반면 단순 정보 응답 신뢰는 이보다 높다 — AI 홈 로드맵에서 "실행형" 기능(자동 주문, 밸브/난방 제어)은 "정보형" 기능보다 훨씬 보수적인 확인 절차(기본값 감독 모드, 점진적 자율성)를 적용해야 하며, 초기 출시 시 이 둘을 동일한 신뢰 수준으로 마케팅하면 안 된다.
4. **하지 말아야 할 것**: Ecovacs 사례처럼 "보안 취약점 보고 후 소극적으로 대응하다 여론 악화 후 태도를 바꾸는" 순서를 피할 것. 보안 연구자가 사전 비공개 보고를 하는 관행이 업계에 있으므로, LG는 사전 신고 채널과 신속 패치·투명 공개 프로세스를 미리 문서화해 둬야 한다. 또한 EU AI Act 고위험 의무가 늦춰졌다고 해서 제5조(금지행위)·제50조(AI임을 고지하는 투명성 의무)까지 미룰 수 있다고 오해해서는 안 된다 — 이 두 조항은 2025년부터 이미 시행 중이다.

---

## Open questions / gaps

- Amazon "Buy for Me" 관련 valueaddedresource.net 원문은 네트워크 접근이 차단되어 WebSearch 요약만으로 인용했다 — 직접 인용문 검증 필요.
- Menlo Ventures(39%)와 Forrester(14%)의 소비자 신뢰 수치 차이가 큰데, 두 설문의 정확한 질문 문항·표본 설계 차이를 원 리포트에서 직접 확인하지 못했다(unverified) — report-writer가 인용 시 두 수치를 병기하고 출처를 명확히 구분할 것을 권고.
- "가정용 냉난방·에너지 제어 AI가 EU AI Act의 '핵심 인프라 안전 구성요소'로 분류될 수 있는가"는 로펌 자료(Global Policy Watch, 2025-07)를 근거로 한 추정이며, 2026년 시점 공식 가이드라인으로 확정된 사안인지는 추가 법률 자문이 필요하다(unverified).
- 스마트홈/가전 도메인에서 "에이전트가 스스로 판단해 원치 않는 구매를 실행"한 명확한 1건짜리 사례(자동 가격 체결 등)는 이번 조사에서 확인하지 못했다 — Amazon Auto-Buy(목표가 도달 시 자동구매) 기능 자체의 오작동 사례는 검색되지 않았고, 대신 "Buy for Me"의 무단 리스팅 사례로 대체했다. 추가 조사 시 Auto-Buy 관련 소비자 불만을 별도로 찾아볼 가치가 있음.
- Google Home 집단소송(2025-11-24 제기)의 2026년 하반기 진행 상황(기각/화해/재판 일정)은 이번 조사에서 업데이트를 확인하지 못했다 — 별개 진행 중인 6,800만 달러 사생활 침해 합의(2026-10-01 최종 승인 심리)와 혼동하지 않도록 주의.
