# 샤오미 "人車家全生態"(Human x Car x Home) 통합 생태계 — 심층조사

Date: 2026-09-22
Scope: 샤오미 HyperOS/HyperOS 4의 "人車家"(사람-차-집) 통합 아키텍처, Xiaomi SU7/SU7 Ultra EV와
스마트홈 연동의 구체 시나리오·판매 실적, 로봇(CyberOne 휴머노이드·로봇청소기)과의 통합 현황,
서구권/글로벌 시장에서의 신뢰·UX 완성도 격차(안전 리콜·프라이버시·개방성), 하이센스·TCL의 유사
전략과의 비교, LG전자(가전↔로봇, 가전↔차량 연결 미션)에 대한 시사점까지 포함. 기존 4개 파일에서
"세부 UX는 격차 존재"로만 각주 처리됐던 중국 브랜드 경쟁축을 정면으로 파고든다. 원칙: "출시/발표"는
정확한 날짜(YYYY-MM-DD, 불명확하면 YYYY-MM) 기재, "현재 이렇다"는 헤드라인 통계·비교는 2026년
발표 자료만 사용(이전 연도 자료는 배경 설명이라도 라벨링하여 구분).

## 중심 명제 (Thesis)

**샤오미의 "人車家" 전략은 LG가 이미 조사한 "홈 AI 표준 전쟁"(구글·삼성·애플·아마존, 다른 파일
참고)과 본질적으로 다른 경쟁 구도다 — 후자는 자신이 만들지 않은 기기 위에 "에이전트 접근권"이라는
소프트웨어 계층을 올리는 싸움인 반면, 샤오미는 스마트폰(진입점)·자동차(노드)·가전(단말)을 모두
자사 하드웨어로 수직계열화해 놓고 그 위에 HyperOS라는 단일 OS를 깔아버리는 방식이다. 2026년
2분기 기준 연결기기 11.6억 대, AIoT 플랫폼 월간활성이용자(MAU) 7억 6,650만 명이라는 규모는
실제로 증명된 숫자이고, SU7·SU7 Ultra는 2026년 7월까지 누적 70만 대 이상 인도되며 "차량도
스마트홈 단말 중 하나"라는 서사를 중국 시장에서는 이미 현실화했다. 그러나 이 통합은 ① 여전히
중국 내수·자사 하드웨어 중심의 폐쇄형 생태계(Matter 인증 기기는 극소수)이고, ② EU向 차량 판매는
2027년에야 시작되는 "아직 증명되지 않은 해외 버전"이며, ③ 2025~2026년 사이 연달아 터진 SU7
안전사고(전동식 도어 손잡이가 정전 시 잠기는 등)가 보여주듯 "커넥티드·스마트"를 앞세운 설계가
오프라인/저전력 상황에서의 안전 폴백(fallback)을 설계하지 못하면 치명적 실패로 이어질 수 있다는
것을 실증한 사례이기도 하다. 즉 샤오미는 위협이자 동시에 "커넥티드 UX 설계의 반면교사" 양쪽
모두로 읽어야 한다.**

## Key findings

### 1. HyperOS "人車家" 아키텍처 — 실제로 무엇을 하는가

- **개념 정의**: HyperOS는 스마트폰용 구 MIUI를 대체해 2024-10 HyperOS 2부터 자동차(스마트 콕핏)까지
  적용 범위를 넓혔고, 2026년 시점 공식 슬로건은 "폰이 진입점(入口), 차가 노드(节点), 태블릿·TV·
  가전이 단말(终端)"이라는 구조다. 이 구조를 실제로 구현하는 크로스디바이스 연결 프레임워크의
  이름이 **HyperConnect(跨端智联)**이며, 기기 간 실시간 동적 네트워킹으로 "여러 기기가 하나처럼
  협업"하는 것을 목표로 한다.
  (source: [Baidu Baike "Xiaomi HyperOS"](https://baike.baidu.com/en/item/Xiaomi%20HyperOS/945111), [Xiaomi HyperConnect 공식](https://hyperos.mi.com/continuity), 2024~2026년 아키텍처 설명 종합 — 아키텍처 자체의 정의이므로 특정 연도 헤드라인이 아니라 배경 설명으로 인용)
- **HyperOS 3의 "人車家" 실전 적용 — 2026년 자료 기준**: HyperOS 3의 "인차가 전생태" 전략이
  2026년 실제로 효과를 냈다고 평가되며, 예시로 (1) 폰-차량 간 내비게이션이 승차 시 자동 전환,
  (2) 집을 나설 때 조명이 자동으로 꺼지는 시나리오가 언급된다. HyperOS 4는 "人車家 전생태를 위해
  처음부터 설계된 시스템"으로 소개된다.
  (source: [텐센트뉴스](https://news.qq.com/rain/a/20260428A04YBQ00), 2026-04-28)
- **모바일 AI 에이전트 "Xiaomi miclaw"(小米龙虾)** — 자체 파운데이션 모델 **MiMo** 기반, **2026-03-06
  제한적 비공개 베타** 시작. LG의 "씽큐 클로(ThinQ Claw)"와 이름·컨셉이 묘하게 겹치는 지점이 있다
  (양사 모두 "손톱/집게" 이미지의 실행형 에이전트를 자사 오픈소스 에이전트 프레임워크 위에 얹었다는
  공통점 — 단, ThinQ Claw는 OpenClaw 기반, miclaw는 MiMo 기반으로 계보는 다름). miclaw는 "人車家"
  전 생태계를 아우르는 것이 처음 구현된 에이전트로 소개되며, 폰·PC·태블릿 등 여러 단말에 배포 가능,
  50개 이상의 시스템 툴·생태계 서비스를 캡슐화한 "추론-실행 엔진"으로 동작(사용자 입력 수신 →
  모델이 자율적으로 도구 선택·파라미터 결정 → 실행 → 결과 반영을 태스크 완료까지 반복). Mi Home
  플랫폼의 10억 대 이상 IoT 기기를 제어할 수 있다고 소개됨. **2026-04, PC/Mac/스크린 스피커용
  다단말 베타 추가 오픈**.
  (source: [IT之家](https://www.ithome.com/0/926/401.htm), [53AI](https://www.53ai.com/news/LargeLanguageModel/2026030745937.html), [观察者网](https://www.guancha.cn/economy/2026_03_06_809060.shtml), [小米澎湃OS 개발자 공지](https://dev.mi.com/xiaomihyperos/announcement/detail?id=41), [量子位(PC판 베타)](https://www.qbitai.com/2026/04/403867.html), 2026-03-06/2026-04)
- **HyperOS 4 출시 타임라인 — 정확한 날짜**: **2026-08-13** 공식 발표(전통적 발표 행사 없이 곧바로
  중국 내 베타 프로그램 신청 오픈), 중국 베타는 **2026-08-14~2026-09-17** 사이 3차례로 나눠 순차
  배포, 안정 버전(stable) 일부 기기 배포는 **2026-09-07**로 확인됨(베타 종료 시점보다 이른 점은
  기기별 순차 배포 특성으로 추정 — 정확한 정합성은 이번 세션에서 재확인 못함, Open questions 참고).
  글로벌 베타 모집은 **2026-09-10** 시작, 글로벌 첫 펌웨어는 2026년 9월 말~10월 초 예정. HyperOS 4는
  러스트(Rust) 코어 재작성, 40% 성능 개선, MiMo·miclaw 기반 오프라인 AI, 기기 간 파일 전송 속도
  300% 개선을 표방.
  (source: [Gizchina](https://www.gizchina.com/xiaomi-phones/hyperos-4-is-dropping-in-august), [Gizmochina(2026-06-20)](https://www.gizmochina.com/2026/06/20/xiaomi-hyperos-4-update-supported-devices-release-date-and-more/), [en.xiaomi-miui.gr](https://en.xiaomi-miui.gr/hyperos-4-features-release-date-2026/), 2026-08~09)
- **연결 규모 — 2026년 실적으로 검증된 숫자**: 샤오미 2026년 2분기(2026-04~06) 실적 발표(**발표일
  2026-08-18**, 자체 홍콩거래소 공시·IR 캘린더로 확인)에 따르면 **AIoT 플랫폼 연결기기(스마트폰·
  태블릿 제외) 11.6억 대**(전년 동기 대비 17.4% 증가), **AIoT MAU 7억 6,650만 명**(사상 최고치),
  **5대 이상 기기를 보유한 이용자 2,460만 명**(전년 동기 대비 20.2% 증가), IoT·라이프스타일 부문
  매출 313억 위안. 직전 분기(2026년 1분기, 2026-01~03) 기준으로는 연결기기 11.2억 대, IoT 매출
  247억 위안이었다 — 즉 2026년 한 해에만 분기별로 꾸준히 규모가 커지고 있음이 자체 IR 자료로
  확인된다.
  (source: [Xiaomi 공식 X(Twitter) 계정](https://x.com/Xiaomi/status/2089683744730890253), [Xiaomi IR 이벤트 캘린더](https://ir.mi.com/events/event-details/2026-interim-results-announcement), [KuCoin](https://www.kucoin.com/news/flash/xiaomi-q2-2026-revenue-falls-6-1-amid-high-r-d-and-capital-expenditure), [Investing.com](https://www.investing.com/news/company-news/xiaomi-q2-2026-slides-ev-growth-and-ai-gains-offset-smartphone-pressure-93CH-4865316), 2026-08-18 발표)

### 2. Xiaomi SU7/SU7 Ultra × 스마트홈 연동 — 구체 시나리오와 2026년 판매 실적

- **CarIoT 아키텍처(자동차를 스마트홈 노드로)**: SU7은 1,000종 이상의 샤오미 스마트홈 기기와
  연동을 지원하며, 자동 탐색·비밀번호 없는 접속·자동화 시나리오 설정이 가능한 "CarIoT 생태계"를
  구성한다. 차량의 16.1형 3K 중앙 디스플레이에서 집 안 기기 대부분을 직접 제어할 수 있고, 역으로
  **"어떤 샤오미 스마트홈 기기에서도 차량을 제어"**할 수 있다고 소개된다(이는 2024년 SU7 최초
  출시 시점부터 있던 아키텍처 설명으로, 특정 연도 헤드라인이 아니라 배경 정보로 인용 — 다만 아래
  IFA 2026·MWC 2026 시연으로 2026년에도 동일 아키텍처가 유효함을 재확인).
  (source: [TechRadar](https://www.techradar.com/vehicle-tech/hybrid-electric-vehicles/xiaomi-reveals-more-about-its-debut-su7-ev-including-the-hyperos-iot-ecosystem), 2024년 배경)
- **구체 시나리오 — "귀가 전 조건 예측" 이상의 것 (IFA 2026, 2026-09-04~08 시연 기준)**: 시간·
  위치·날씨 등 맥락 정보를 활용해 운전자가 도착하기 전 조명·에어컨을 미리 조정하는 것은 기본이고,
  **차 안에서 집의 커튼을 열고 닫거나 에어컨을 켜고 끄는 등, 차량 자체가 "또 하나의 스마트홈
  컨트롤 포인트"로 기능**하도록 설계돼 있다. 즉 "차→집" 뿐 아니라 "집 제어를 차 화면으로 옮겨오는"
  양방향 구조라는 점이 핵심이며, 별도 앱 전환 없이 차량 인포테인먼트 화면 자체가 홈 컨트롤 패널이
  된다는 것이 경쟁사(예: 국내 완성차·가전사의 "도착 전 에어컨 예약" 수준 기능) 대비 실질적 차별점.
  (source: WebSearch 종합, IFA 2026 데모 요약 — 원문 다수가 EGRESS_BLOCKED로 직접 열람 불가하나
  [Yahoo Autos](https://autos.yahoo.com/ev-and-future-tech/articles/ifa-2026-xiaomi-wants-smart-153705239.html), [Euronews](https://www.euronews.com/next/2026/09/06/ifa-2026-xiaomi-wants-its-smart-home-cars-on-european-roads-by-2027), [fonearena](https://www.fonearena.com/blog/491337/xiaomi-380-products-xiaomi-auto-human-x-car-x-home-ecosystem-ifa-2026.html) 등 복수 매체 스니펫 교차 일치, 2026-09)
- **IFA 2026 부스 규모·유럽 진출 로드맵**: 베를린 IFA 2026(**2026-09-04~08**)에 샤오미 최초 참가,
  3,300㎡ 이상(역대 최대 해외 부스)에 380여 개 제품·기술을 "AI Tomorrow", "AI Today", "Human x
  Car x Home" 3개 구역으로 나눠 전시. 이 자리에서 **EU 시장 전기차 출시 목표를 2027년**으로 공식
  발표하고, 독일 8개 자동차 딜러 그룹(Emil Frey Germany, Ernst Dello Group, Autohaus Dinnebier,
  Hahn Automobile, LUEG Mobility Group, Fett & Wirtz, SPT Avior, Penske-Jacobs)과 의향서(LOI)
  체결식을 가졌다 — 즉 **2026-09 시점까지도 "人車家" 서사의 차량 축은 중국 내수에서만 실현된
  상태이고, 유럽에서는 딜러망 계약 단계일 뿐 실제 판매는 시작되지 않았다.**
  (source: WebSearch 종합 [fonearena](https://www.fonearena.com/blog/491337/xiaomi-380-products-xiaomi-auto-human-x-car-x-home-ecosystem-ifa-2026.html), [Carscoops](https://www.carscoops.com/2026/09/xiaomi-launch-europe-germany/), [Euronews](https://www.euronews.com/next/2026/09/06/ifa-2026-xiaomi-wants-its-smart-home-cars-on-european-roads-by-2027), 2026-09)
- **MWC 2026(2026-03-02~05, 바르셀로나) 시연**: 샤오미 프레스 콘퍼런스에서 "Human x Car x Home"을
  핵심 주제로 재확인, SU7 Ultra와 컨셉트카 "Xiaomi Vision GT"를 전시하며 스쿠터(Electric Scooter
  6)·Mijia 가전 라인업까지 AIoT 확장을 시연 — "AI가 화면을 넘어 실물 세계로 이동한다"는 메시지를
  반복.
  (source: WebSearch 종합 [Il Sole 24 Ore](https://en.ilsole24ore.com/art/xiaomi-mwc-2026-electric-car-becomes-centre-of-intelligent-ecosystem-AISpC0iB), [Speed.ph](https://www.speed.ph/xiaomi-ai-powered-human-x-car-x-home-ecosystem-mwc-2026/), 2026-03)
- **SU7/SU7 Ultra·YU7 판매 실적 — 2026년 자료**: 2026-04-23 기준 SU7+YU7 누적 인도 65.5만 대
  돌파, **2026-07 기준 두 차종 합산 누적 인도 70만 대 초과**. SU7 단일 차종은 2026-07 월 판매
  21,044대로 "20만 위안 이상 세단 판매 4개월 연속 1위"(레이쥔 CEO 발표). 2026-08 월간 인도량도
  3만 대 초과 유지. **2026 페이스리프트(2026-03-20 공식 데뷔)**는 Max 트림에 라이다(LiDAR)와
  듀얼 챔버 에어 서스펜션을 기본 탑재, 후석에 6개 통합 스크린을 제어하는 업그레이드 리모트 패널을
  추가.
  (source: [IT之家(2026-07 인도량)](https://m.ithome.com/html/984428.htm), [IT之家(레이쥔 발표)](https://www.ithome.com/0/988/768.htm), [网通社(누적 70만대)](http://www.news18a.com/news/storys_255285.html), [Phandroid(2026-03-20 페이스리프트)](https://phandroid.com/2026/03/20/xiaomis-upgraded-su7-models-make-their-official-debut/), 2026년)

### 3. 로봇 라인업과의 통합 현황 — 2026년 기준

- **CyberOne 휴머노이드 — 2026년 신세대 모델**: **2026-08-19** 베이징 세계로봇대회(WRC,
  2026-08-19~23)에서 신세대 CyberOne 공개, 자사 EV 공장에서 4개월간 실지 훈련을 거쳐 너트 체결
  공정 성공률을 약 90%→98%로 끌어올림(신장 약 1.70m, 무게 66kg). **IFA 2026(2026-09-04~08)에서도
  유럽 최초 공개**하며 "EV 공장에서 성능 검증 중"임을 재확인했고, 전시 부스는 CyberOne을 "人車家"
  더 큰 생태계 서사 안에 명시적으로 배치 — 즉 로봇을 별도 사업이 아니라 HyperOS가 연결하는 "기기
  카테고리 중 하나"로 포지셔닝한다. **다만 2026-09 시점까지 CyberOne의 공식 가격·스펙 공개·상용화
  일정은 없다(미공개로 확인).**
  (source: [BigGo Finance(WRC)](https://finance.biggo.com/news/ba425dbf-72e3-42cf-bada-583533e1057e), 2026-08-19; [Tempo.co](https://en.tempo.co/read/2117842/xiaomi-to-present-humanoid-robot-at-2026-world-robot-conference), [Humanoza](https://humanoza.com/robots/xiaomi-cyberone), 2026-09 — 로보틱스 파일 `robotics-physical-ai-expansion-deep-dive-2026-09-21.md`와 CyberOne 관련 사실 교차 일치 확인됨)
- **로봇청소기 — HyperOS Connect를 통한 가전 간 트리거 연동(구체 사례)**: 샤오미 로봇청소기는
  HyperOS Connect로 공기청정기·가습기 등 타 기기와 연동해 **"외출 시 자동 청소 시작 → 청소 완료
  후 공기청정 자동 트리거"** 같은 조건부 자동화를 실행한다 — 이는 `robotics-physical-ai-expansion-deep-dive-2026-09-21.md`에서 "확인 불가"로 남겨뒀던 "로봇청소기가 다른 가전을 직접 제어하는
  사령탑 역할" 사례에 해당하는 구체적 반례를 제공한다(단, "청소기가 사령탑"이라기보다 HyperOS라는
  상위 OS가 두 기기를 조건부로 엮는 방식). 2026년 신모델 **Robot Vacuum H50 Pro**(흡입력 15,000Pa,
  자동세척 스테이션, 유럽 판매가 €399.99부터)와 **Robot Vacuum and Mop 6**(중국 출시)이 이 방식을
  이어감.
  (source: [Basic Tutorials](https://basic-tutorials.com/news/xiaomi-smart-tech-devices-2026-new-tvs-home-appliances-and-robot-vacuum-for-the-connected-home/), [en.xiaomi-miui.gr](https://en.xiaomi-miui.gr/xiaomi-robot-vacuum-and-mop-6-released-in-china/), 2026년)
- **휴머노이드 로봇 관련 장기 투자 규모(배경, 별도 파일과 중복 확인)**: 샤오미는 2026~2030년
  AI·OS·자체 반도체·전기차·로보틱스·스마트제조에 2,000억 위안(약 38조원) 이상, 그중 AI에만 향후
  3년간 6,000억 위안(약 115조원) 이상 투자 계획을 밝혔다 — 로보틱스 세부 배분액은 별도 공개되지
  않음.
  (source: `robotics-physical-ai-expansion-deep-dive-2026-09-21.md`에서 이미 확인된 사실 재인용, WebSearch 종합, 2026년 발표 기준)

### 4. "세부 UX는 격차 존재" 각주 검증 — 실제로 어떤 약점이 있는가 (균형 있게)

기존 조사의 "하드웨어·OS 경쟁력 빠르게 확보 중, 세부 UX는 격차 존재"라는 한 줄을 검증한 결과,
막연한 "UX 완성도가 낮다"보다 훨씬 구체적이고 중대한 약점 세 갈래가 확인됐다 — 단순 품질 문제가
아니라 **"연결·스마트 기능이 안전·프라이버시·개방성이라는 비기능 요구사항과 충돌하는" 구조적
패턴**이다.

**(1) 차량 UX/HMI 완성도 — 전문 평가기관의 구체 지적**
- 자동차 HMI 전문 평가기관 SBD Automotive의 SU7 인카 HMI 벤치마킹에서 **입력 방식의 제한성,
  ADAS(운전보조) 기능의 불충분한 라벨링, ACC(어댑티브 크루즈 컨트롤) 작동 중 전방 차간거리
  표시(headway display) 부재**가 약점으로 지적됐다 — 단, 같은 평가는 이 문제들이 OTA로 해결
  가능하며 해결 시 기존 상위권 평가 차량보다 높은 점수를 받을 잠재력이 있다고도 평가함(원문
  `sbdautomotive.com`이 EGRESS_BLOCKED로 직접 열람 불가, WebSearch 스니펫 기반 — 평가 시점
  정확한 날짜 미확인).
  (source: [SBD Automotive(원문 미확인, 스니펫 기반)](https://www.sbdautomotive.com/post/in-car-hmi-ux-evaluation-benchmarking-xiaomi-su7))

**(2) 안전 UX — "전동식 스마트 도어 손잡이"가 정전 시 탈출 실패로 이어진 구체 사례 (2025~2026)**
- **2025-03-29**(2025년 배경 사실): 안후이성 퉁링 고속도로에서 SU7 표준형이 운전보조 모드
  주행 중 수몰 방지 방벽에 시속 116km로 충돌, AEB(자동긴급제동)가 작동하지 않음(장애물 유형이
  당시 인식 시스템에 등록돼 있지 않았다고 샤오미 설명) — 대학생 3명 사망. 이 사고를 계기로
  **2025-09**(추정, 생산기간 2024-02-06~2025-08-30 차량 기준) **SU7 116,877대 리콜** —
  중국 시장감독총국은 "고속 운전보조 시스템의 인식·경고·대응 능력이 특정 조건에서 불충분"하다고
  판단(2단계 자율주행 기준 미달).
  (source: [Business & Human Rights Centre](https://www.business-humanrights.org/en/latest-news/china-fatal-accident-involving-xiaomi-su7-electric-vehicle-claims-three-lives-raising-concerns-over-autonomous-driving-technology-and-ev-safety/), [SCMP](https://www.scmp.com/business/china-business/article/3326115/xiaomi-recalls-nearly-117000-su7-vehicles-after-fatal-crash-raises-safety-concerns), 2025년 사실이므로 배경으로만 인용)
- **2025-10**(2025년 배경 사실): 청두에서 SU7 Ultra가 고속 충돌 후 저전압 시스템이 다운되며
  **전동식(버튼식) 도어 손잡이가 잠겨 탈출하지 못한 채 화재로 사망**하는 사고 발생 — SU7은
  플러시(flush) 외관을 위해 기계식 손잡이 없이 전자 버튼에만 의존하는 설계였음.
  (source: [Gasgoo Autonews](https://autonews.gasgoo.com/articles/news/chengdu-xiaomi-su7-ultra-accident-appraisal-results-released-low-voltage-system-power-failure-caused-doors-to-fail-to-open-2026984491967324161), 사고 자체는 2025년 배경)
- **2026-02-26/27, 청두 사고 정식 조사 결과 발표 — 2026년 확인된 사실**: 저전압 시스템 전원
  차단이 전자제어 도어 손잡이의 잠김을 유발했다는 사실이 공식 감정 결과로 확정됨. 같은
  **2026-02-27**, 샤오미는 설계·제품·엔지니어링·제조 전 단계에 "원 보트 거부권(one-vote veto
  power)"을 갖는 **안전자문위원회(Safety Advisory Committee) 신설**을 발표 — AP 통신을 인용한
  다수 미국 지역매체(WSAU, WIN 98.5, KELO-AM, WTVB 등)가 동일 날짜·동일 내용으로 일치 보도.
  **2026-03-20**, 페이스리프트 SU7에 **기계식 외부 도어 손잡이를 추가 복원**, 전 트림 라이다 기본
  탑재, 후석 시트 아래에 메인 배터리와 완전히 분리된 도어락 전용 백업 전원 장착 등 안전 개선을
  공식 발표. 이와 별개로 중국 정부는 **자동차 도어 손잡이 안전 기술기준(GB 48001-2026)을 제정**,
  **2027-01-01부터 모든 외부 도어 손잡이에 기계식 해제 장치 의무화**를 확정했다(산업 전체
  규제 대응, 샤오미 사고가 직접적 계기 중 하나로 거론됨).
  (source: [Gasgoo(청두 조사 결과)](https://autonews.gasgoo.com/articles/news/chengdu-xiaomi-su7-ultra-accident-appraisal-results-released-low-voltage-system-power-failure-caused-doors-to-fail-to-open-2026984491967324161), [CnEVPost(370,000대 리콜 압박, 원문 EGRESS_BLOCKED, 스니펫 기반)](https://cnevpost.com/2026/02/27/xiaomi-pressured-to-recall-370000-evs-door-handle-safety-hazard/), [ClaimsJournal(안전위 신설)](https://www.claimsjournal.com/news/national/2026/03/02/335982.htm), [WSAU](https://wsau.com/2026/02/27/xiaomi-launches-safety-advisory-committee-after-ev-accidents-in-china/), [Caixin Global(2026-03-20 안전 개선)](https://www.caixinglobal.com/2026-03-20/xiaomi-revamps-su7-with-safety-upgrades-after-fatal-crashes-102425437.html), 2026-02~03)
- → **LG 관점에서 가장 중요한 시사점**: 이 사건은 단순 "중국차는 위험하다"는 이야기가 아니라,
  **"연결·스마트"를 위해 설계한 기능(전자식 손잡이 — 공력 성능·미감·"스마트 카" 이미지를 위한
  선택)이 전원이 끊기는 예외 상황에서 물리적 안전 폴백을 갖추지 못하면 그 자체가 생명을 위협하는
  결함이 된다**는, 커넥티비티 UX 설계 원칙 차원의 반면교사다. 가전↔로봇, 가전↔차량이 "만나는
  지점"을 다루는 조직이라면 정확히 이 지점 — 즉 "네트워크·전원이 살아있을 때의 매끄러운 경험"과
  "네트워크·전원이 끊겼을 때의 안전한 성능 저하(graceful degradation)"를 반드시 짝으로 설계해야
  한다는 근거로 직접 인용할 수 있는 사례다.

**(3) 프라이버시·데이터 신뢰 — EU GDPR 이슈 (2025년 제소, 2026년 시점 미해결 상태로 확인)**
- **2025-01-16**(2025년 배경 사실): 오스트리아 프라이버시 단체 noyb가 그리스·이탈리아·벨기에·
  네덜란드·오스트리아 5개국 감독기구에 TikTok·AliExpress·SHEIN·Temu·WeChat과 함께 **샤오미를
  포함한 6개 중국 기업이 유럽 이용자 개인정보를 중국으로 이전하면서 GDPR 44/46조(적정성 요건)를
  위반**했다는 취지로 제소. 샤오미는 투명성 보고서에서 중국 당국의 개인정보 접근 요청에 "매우 큰
  규모로" 응하고 있음을 자인한 것으로 noyb는 주장. noyb는 데이터 이전 중단 명령과 전 세계 매출
  4%까지의 과징금을 요청함.
  - **2026년 확인 자료 없음**: 이번 조사에서 2026년 시점의 최종 제재·판단 결과(감독기구의 확정
    조치)는 확인하지 못했다 — WebSearch 스니펫 중 일부가 "2026년 7월에 제소"라는 취지로도
    나타났으나, 원문(noyb.eu)이 EGRESS_BLOCKED로 직접 대조가 불가능했고 교차확인 결과 실제 제소일은
    2025-01-16으로 판단된다(2026년 관련 보도는 기존 2025년 제소 건의 재조명·후속 취재일 가능성이
    높음 — 다음 세션에서 noyb.eu 직접 열람으로 재확인 필요).
  (source: [Agence Europe](https://agenceurope.eu/en/bulletin/article/13560/7/ngo-noyb-sues-chinese-companies-tiktok-aliexpress-shein-temu-wechat-and-xiaomi-for-failing-to-comply-with-gdpr), [DataGuidance](https://www.dataguidance.com/news/eu-noyb-filed-complaints-against-tiktok-aliexpress), [BornCity(2025-01-19)](https://borncity.com/win/2025/01/19/noyb-complains-about-data-transfer-to-tiktok-aliexpress-co/), 2025년 배경)

**(4) 폐쇄형 생태계 — Matter 개방 표준 참여는 사실상 극히 미미**
- 2026년 기준 Matter 기기 인증 레지스트리(Matter Survey)에 등재된 샤오미 인증 제품은 **매터-OT
  듀얼커넥티비티 모듈, 셀프 설치 스마트락(2개 모델), 스마트 LED 전구 등 5종 수준**에 불과하다 —
  최근 리트로핏 스마트락으로 Matter 카테고리를 한 개 더 늘렸고 릴레이·카메라 제품의 Matter 인증
  준비 정황도 있으나, **연결기기 11.6억 대(2026-06-30 기준) 규모에 비하면 Matter 인증 비중은
  통계적으로 무의미한 수준**이다. 이는 `home-ai-standard-war-2026-09-21.md`에서 이미 지적한
  "중국은 사실상 별도 블록" 진단을 정량적으로 뒷받침한다 — 즉 **샤오미의 "人車家" 통합은 압도적으로
  강력하지만, 그 통합은 "샤오미 자사 하드웨어 안에서"만 성립하고, 이미 타사(삼성·LG·구글 생태계)
  기기를 보유한 해외 소비자가 부분적으로만 편입되기는 사실상 어렵다.** 서구권에서 구글/삼성/애플이
  Matter를 공동 인프라로 밀고 있는 것과 정반대 방향의 전략적 선택이다.
  (source: [Matter Survey — Xiaomi 벤더 페이지](https://matter-survey.org/vendor/xiaomi-4718), [MatterDevices.io](https://matterdevices.io/manufacturer/xiaomi/), [Matter Alpha](https://www.matteralpha.com/news/xiaomi-expands-global-Matter-listings-with-a-new-retrofit-lock), 2026년 6월 기준 등재 상태)

**(5) 유럽 진출 실행 리스크 — 투자자도 아직 확신하지 못함 (2026년 자료)**
- IFA 2026(2026-09) 발표 직후 시점까지도 샤오미 주가는 **2026년 연초 대비 약 31~33% 하락**한
  상태였고, 이는 마진이 낮은 해외(EU) 확장 전략에 대한 투자자들의 회의적 시각을 반영한다는 분석이
  다수 매체에서 공통적으로 제기됐다 — "실제 유럽 인도 실적이나 인도(India) 시장 관련 명확성이
  나오기 전까지는 성장 스토리를 신뢰하지 않겠다"는 것이 투자자 반응으로 요약된다. 별도로 프랑스
  파리 법원에서는 Sun Patent Trust가 샤오미를 상대로 LTE-Advanced 표준특허(SEP) 167개 패밀리에
  대한 **글로벌 FRAND 요율 결정**을 최초로 구하는 소송(피소 규모 약 $300M 추정)을 진행 중 — 유럽
  진출 확대 시점에 특허 리스크도 함께 커지는 구조다.
  (source: [Ad-hoc-news.de](https://www.ad-hoc-news.de/boerse/news/unternehmensnachrichten/xiaomi-s-german-dealer-bet-eight-retail-groups-a-2027-deadline-and-a/70087091), [Carscoops](https://www.carscoops.com/2026/09/xiaomi-launch-europe-germany/), [World IP Review](https://www.worldipreview.com/patent/xiaomi-faces-global-frand-litigation-in-france-and-india), [ip fray](https://ipfray.com/sun-patent-trust-sues-xiaomi-over-lte-a-standard-essential-patents-asks-for-global-frand-rate-determination-in-france-also-sues-in-india/), 2026-09 주가 시점 기준)

### 5. 하이센스·TCL 비교 — 유사 전략을 취하지만 "차량" 축이 없다는 결정적 차이

- **하이센스** — 자체 스마트홈 통합 플랫폼 "ConnectLife"를 중심으로 CES 2026(2026-01)에서
  풀-시나리오 스마트홈 생태계를 시연했고, 2026년 하이센스 글로벌 파트너 컨퍼런스에서는 TV·연결
  가전뿐 아니라 **자동차 전장(automotive electronics)까지 포함하는 전사 AI 로드맵**을 발표했다
  — 그러나 이는 완성차(EV) 브랜드가 아니라 **차량용 부품·전장 공급**에 가까운 것으로 파악되며,
  샤오미처럼 자사 브랜드 완성차를 스마트홈의 "노드"로 직접 소유·판매하는 구조는 아니다.
- **TCL** — IFA 2026에서 태양광 발전·배터리 저장·히트펌프·가정 수요관리를 묶은 "Inspiration
  Habitat" 커넥티드 에너지 전시를 선보이며 홈에너지 축에 집중했고, 로봇·가사 컴패니언(가칭
  'AiMe', 로보틱스 파일에서 이미 확인) 개발도 병행 중이나 마찬가지로 **자체 완성차 사업은 없다.**
  대중 분석은 "TCL은 대담한 수평 확장, 하이센스는 핵심 사업의 안정적 심화"라는 식으로 두 회사의
  전략 성향 차이를 구분한다.
- → **결론**: 하이센스·TCL도 "AI로 가전·에너지·(부분적으로) 자동차 전장을 엮는다"는 방향성은
  샤오미와 공유하지만, **차량을 자사 브랜드의 완성 하드웨어로 직접 소유하고 그 위에 자사 OS를
  까는 수준의 수직계열화는 샤오미만의 독자적 포지션**이다. 이것이 이번 조사에서 샤오미를 별도로
  심층조사해야 했던 근거이기도 하다 — 하이센스·TCL은 "가전-가전" 통합의 확장판인 반면, 샤오미는
  "가전-로봇-차량"을 모두 아우르는 유일한 사례이기 때문.
  (source: [Hisense USA 공식](https://www.hisense-usa.com/post/hisense-appliance-innovations-and-ai-powered-home-assistance-coming-to-ces-2026), [PR Newswire](https://www.prnewswire.com/news-releases/hisense-showcases-a-full-scenario-smart-home-ecosystem-at-ces-2026-302654727.html), [TechEdgeAI](https://techedgeai.com/hisense-unveils-ai-growth-strategy-to-expand-smart-home-ecosystem-and-enterprise-ai-innovation/), [Sustainable Business Magazine](https://sustainablebusinessmagazine.net/renewableenergy/tcl-showcases-home-energy-ecosystem-at-ifa-2026/), [36Kr(TCL/하이센스 전략 비교)](https://eu.36kr.com/en/p/3992413236811648), 2026년)

## LG전자 관점 시사점

### 구조적 차이 — 왜 LG는 샤오미와 "같은 방식"으로는 싸울 수 없는가

샤오미의 강점은 **모바일(진입점)을 자사가 소유**하고 있고, 이제 **차량(노드)까지 자사 브랜드로
소유**하게 됐다는 데서 나온다. LG전자는 2021년 모바일 사업을 철수했고, 완성차 사업도 하지 않는다
— 대신 VS사업본부를 통해 **차량용 부품/전장(인포테인먼트, 램프 등)을 완성차 OEM에 공급**하는
B2B 구조를 갖는다. 즉 LG는 "진입점(폰)"도 "노드(차량 브랜드)"도 직접 소유하지 못한 채, 오직
"단말(가전)"만 강한 상태에서 연결 전략을 짜야 한다 — 이는 하이센스·TCL이 처한 구조적 제약과
같은 종류이고, 샤오미가 가진 근본적 이점(수직계열화로 인한 OS 전 계층 통제)은 LG가 원천적으로
복제할 수 없는 지점이라는 것을 냉정하게 인지해야 한다.

### 그럼에도 참고할 것

1. **"차량 화면 = 홈 컨트롤 패널" 양방향 설계를 LG인포콘/VS사업본부와 함께 검토할 가치가 있다.**
   샤오미 IFA 2026 시연의 핵심은 "도착 전 에어컨 예약"이 아니라 "차량 화면에서 집의 커튼·조명을
   직접 조작하는 양방향성"이었다 — LG는 완성차를 만들지 않지만, VS사업본부가 특정 OEM에 공급하는
   인포테인먼트 시스템에 "ThinQ 연동 패널"을 탑재 제안하는 방식으로 유사한 경험을 부분적으로
   재현할 수 있다. 이는 완성차 브랜드 소유 없이도 "가전↔차량이 만나는 지점"이라는 이 조직의
   미션에 정확히 부합하는 실행 경로다.
2. **에이전트 이름·컨셉의 우연한 수렴("씽큐 클로" vs "miclaw")을 오히려 적극 활용하라.** 양사가
   독립적으로 "집게 모양 실행형 에이전트"라는 유사한 메타포에 도달했다는 것은, 이 UX 패턴(에이전트가
   여러 기기에 걸쳐 작업을 "붙잡고 실행"한다는 이미지)이 업계에서 자연발생적으로 수렴하고 있다는
   신호로 해석할 수 있다 — LG는 이를 대외 커뮤니케이션에서 "우리도 같은 방향을 보고 있다"는
   근거로 활용하되, 기능적으로는 miclaw의 "50개 이상 시스템 툴을 캡슐화한 추론-실행 엔진" 수준의
   구체성(현재 씽큐 클로는 이 정도의 기술적 디테일이 공개되지 않음 — `home-ai-standard-war-2026-09-21.md`
   Open questions 참고)을 따라잡을 필요가 있다.
3. **"연결이 끊겼을 때"를 설계 요구사항 1순위로 명문화하라.** SU7 도어 손잡이 사고는 이 조직의
   미션(가전↔로봇, 가전↔차량 연결 UX)에 가장 직접적으로 적용 가능한 반면교사다 — 클로이드(CLOiD)가
   냉장고 문을 열고 세탁기를 조작하는 식의 물리적 개입을 이미 시연한 상태이므로(로보틱스 파일
   참고), "로봇이 가전을 조작하는 도중 네트워크·전원이 끊기면 어떻게 안전하게 정지·복귀하는가"
   같은 시나리오를 2027 사업계획의 UX 요구사항에 명시적으로 포함시킬 것을 제안한다. 이는 단순
   장애 대응이 아니라, 커넥티드 경험을 설계할 때 "매끄러움"과 "안전 폴백"을 처음부터 짝으로
   설계해야 한다는 원칙을 조직 차원에서 채택해야 함을 뜻한다.
4. **"개방형 표준(Matter/앳홈-호미) 전략은 옳은 선택임을 샤오미 사례가 역으로 증명한다.**
   샤오미의 11.6억 대 연결기기는 압도적이지만 Matter 인증은 5종 수준에 그쳐, 비(非)샤오미
   기기 보유자를 포섭하지 못하는 폐쇄형 구조라는 한계가 뚜렷하다. LG가 앳홈(Athom) 인수와
   Matter/Thread 개방성을 유지하는 전략(다른 파일 참고)은, "자사 하드웨어만으로 규모를 만들 수
   없는" LG의 구조적 제약을 오히려 강점으로 바꾸는 선택이라는 것이 샤오미와의 대비를 통해 더
   분명해진다 — 유럽·북미 시장에서는 "이미 여러 브랜드 기기를 보유한 가정"을 포섭하는 개방형
   전략이 샤오미식 폐쇄형 수직계열화보다 오히려 유리할 수 있다.
5. **유럽에서 샤오미의 차량 축은 아직 미실현이라는 "시간 창"이 있다.** 샤오미 EV의 EU 판매는
   2027년부터다 — 즉 2026~2027년은 LG가 VS사업본부·완성차 OEM 파트너십을 통해 "가전↔차량 연결
   경험"의 유럽 표준을 먼저 제시할 수 있는 마지막 시간 창일 수 있다. 다만 투자자들도 샤오미의
   유럽 EV 확장에 회의적(주가 약 31~33% 하락, 2026-09 기준)이라는 점은, "중국 브랜드가 온다"는
   위협을 과장할 필요는 없으며 유럽 소비자 신뢰·딜러망·인증 같은 비-UX 장벽이 여전히 크다는
   균형 잡힌 시각도 함께 가져가야 함을 시사한다.

## Open questions / gaps

- HyperOS 4의 "베타 배포(~2026-09-17)"와 "안정 버전 배포(2026-09-07)" 날짜가 서로 앞뒤가 맞지
  않는 것처럼 보이는 점을 이번 세션에서 완전히 해소하지 못했다 — 기기별 순차 배포로 추정되나,
  Xiaomi 공식 뉴스룸(`hyperos.mi.com`, `dev.mi.com`) 원문 대조가 필요하다(다수 원문 도메인이
  EGRESS_BLOCKED로 직접 열람 불가).
- noyb의 샤오미 관련 GDPR 제소가 2026년에 별도로 새로 제기됐는지, 아니면 2025-01-16 건이
  재조명된 것인지 이번 세션에서 명확히 가르지 못했다 — `noyb.eu` 원문이 EGRESS_BLOCKED로 직접
  열람이 막혀 있어, 접근 가능한 세션에서 원문 확인이 필요하다("2026년 확인 자료 없음"으로 잠정
  처리).
- SBD Automotive의 SU7 HMI 벤치마킹 평가의 정확한 실시 날짜를 확인하지 못했다 — 원문
  (`sbdautomotive.com`)이 EGRESS_BLOCKED로 직접 열람 불가, WebSearch 스니펫에만 의존했다.
- 샤오미 로보틱스 부문 전용 R&D 인력·투자액(전사 AI 투자 6,000억 위안 중 로보틱스 세부 배분)은
  확인하지 못했다 — `robotics-physical-ai-expansion-deep-dive-2026-09-21.md`의 동일한
  Open question과 중복되며, 다음 세션에서 함께 재확인이 필요하다.
- LG 완성차 파트너십(VS사업본부가 특정 OEM 인포테인먼트에 ThinQ 연동을 실제로 제안·구현한 사례가
  있는지)은 이번 조사(경쟁사 스코프) 밖이라 확인하지 않았다 — `own-company-research` 에이전트가
  후속으로 확인할 항목으로 제안한다.
- `www.vrsus.io`, `en.xiaomi-miui.gr`, `www.mobileworldlive.com`, `www.fonearena.com`,
  `www.gadgetmatch.com`, `www.webwire.com`, `www.entnerd.com`, `autos.yahoo.com`,
  `basic-tutorials.com`, `www.mi.com`, `noyb.eu`, `finance.biggo.com`, `cnevpost.com`,
  `www.sbdautomotive.com`, `www.iotinsider.com`, `www.euronews.com`, `www.winkco.news` 등
  다수 1차 소스 도메인이 이번 세션 환경에서 EGRESS_BLOCKED로 직접 열람이 막혀 WebSearch 스니펫
  기반으로만 인용했다 — 원문 대조 재확인이 필요하다.
