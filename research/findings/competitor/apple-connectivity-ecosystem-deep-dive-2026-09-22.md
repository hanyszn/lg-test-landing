# Apple의 기기 간 연결성 생태계 전략 — Continuity·HomeKit·CarPlay·App Intents 심층조사
Date: 2026-09-22
Scope: Apple의 기기 간 연결성(Continuity: Handoff/Universal Clipboard/iPhone Mirroring/Universal
Control), Apple Home(HomeKit) 가전 생태계 확장, CarPlay(Ultra) 차량 연동, App Intents 기반 크로스앱
에이전트 실행의 2026년 현황. LG전자 UX디자인연구소의 핵심 미션인 "가전↔로봇, 가전↔차량이 만나는
지점의 UX"에 직접 대응하는 경쟁사 분석. 원칙: "출시/발표"는 정확한 날짜(YYYY-MM-DD) 기재, "현재
이렇다"는 헤드라인 통계·비교는 2026년 발표 자료만 사용(이전 연도 자료는 배경 설명이라도 본문
제외 — 예외 없이 라벨링).

## 중심 명제 (Thesis)

**Apple의 연결 경험이 매끄러운 이유는 개별 기능이 뛰어나서가 아니라, 실리콘(Apple Silicon)·OS(iOS/
macOS/watchOS/visionOS)·백엔드(iCloud)·프레임워크(Continuity, App Intents)라는 4개 층을 전부 자사가
설계·소유하기 때문이다.** 이 수직통합 구조는 동시에 두 얼굴을 가진다 — (1) 근거리 기기 발견·핸드오프
같은 기능을 경쟁사가 표준(Matter/MCP) 기반으로는 구조적으로 재현하기 어려운 진짜 경쟁우위이지만,
(2) 정확히 같은 이유로 서드파티 가전·자동차 OEM·타 플랫폼과의 연결에서는 각국 규제기관(EU DMA)과
정면충돌하고, 자동차 업계(GM·BMW·Rivian·Mercedes)의 저항을 사고 있으며, 2026년 기준 HomeKit
생태계에는 주요 가전 브랜드가 사실상 전무하다. LG는 Apple처럼 실리콘·OS 계층을 통제할 수 없으므로
"수직통합 자체"를 벤치마킹 대상으로 삼을 수 없다 — 대신 Apple이 여전히 채우지 못한 "이종 브랜드
가전 통합"과 "차→가전 연결"이라는 두 개의 구멍이 LG의 실질적 기회 공간이다.

## Key findings

### 1. 연결성 아키텍처가 구조적으로 강한 이유 — 4개 층을 전부 자사가 통제

- **Continuity 프로토콜 자체가 3개 무선 기술의 조합이고, 이 조합을 설계·표준화하는 주체가 Apple
  하나뿐이다.** Continuity는 iCloud(권한 확인·상태 동기화) + Bluetooth LE(iBeacon 방식 근접 기기
  탐지, BLE 광고 메시지로 "같은 Apple 계정" 기기를 서로 인지) + Wi-Fi Direct(AirDrop 방식 고속
  peer-to-peer 전송)를 결합해 동작한다. 여기에 iPhone 15 이후 기종에 탑재된 2세대 Ultra Wideband
  칩(비공식 명칭 "U2", 2023-09-12 WWDC에서 최초 소개)이 정밀 근접·공간 인식을 더해 Find My·근접
  상호작용의 정확도를 높인다. 이 조합 자체는 공개된 지 오래됐으나(2014년 iOS 8/OS X Yosemite),
  **경쟁사가 이를 그대로 재현하려면 BLE 칩·Wi-Fi Direct 스택·UWB 칩·OS 권한 체계·클라우드 계정
  시스템을 전부 자사가 통제해야 하는데, Windows/Android 생태계는 하드웨어 제조사(삼성 등)와 OS
  제공사(MS/구글)가 분리돼 있어 이 조합을 동일한 밀도로 재현하기 어렵다**는 것이 핵심 구조적
  차이다.
  (source: [AppleInsider(Continuity 가이드)](https://appleinsider.com/inside/icloud/tips/how-to-use-continuity-to-make-your-apple-devices-work-better-together), [Apple Support(Continuity 요구사항)](https://support.apple.com/en-us/108046), [TheAppleWiki(U2 칩)](https://theapplewiki.com/wiki/U2))
- **2026년 기준 Apple 활성기기 설치기반 25억 대(2.5 billion) — 2026-01-29 발표.** 2026 회계연도
  1분기(2025년 10~12월) 실적발표에서 Apple은 활성기기 설치기반이 25억 대를 돌파했다고 밝혔다(직전
  해 2.35억 대 대비 순증). 이 규모 자체가 "핸드오프할 상대 기기가 항상 주변에 있다"는 네트워크
  효과를 만들며, 타사가 동일한 밀도의 기기 보급률을 갖추지 못하면 Continuity류 기능은 애초에 체감
  빈도가 낮아질 수밖에 없다.
  (source: [MacRumors(2026-01-29)](https://www.macrumors.com/2026/01/29/apple-2-5-billion-active-devices/), [AppleInsider(2026-01-29)](https://appleinsider.com/articles/26/01/29/apple-reaches-25-billion-active-devices-after-record-breaking-quarter))
  **[2026-09-22 verifier 확인]** MacRumors·AppleInsider·9to5Mac·CNBC·Apple Newsroom(2026-01-29 실적발표)
  독립 재검색으로 "2.5billion active devices"·"직전 해 2.35B 대비 150M 순증" 수치 일치 확인.
- **2026-09-14, iOS 27·macOS 27(및 iPadOS 27 등)이 정식 출시**되며 iPhone Mirroring이 리사이즈
  가능한 창·Control Center 접근·DRM 보호 영상 재생 지원으로 업그레이드됐다(WWDC 2026, 2026-06-08
  발표분의 실제 소비자 배포). Universal Control은 Mac 1대의 키보드·트랙패드로 주변 Mac/iPad
  최대 2대를 이어서 조작하는 기능으로 계속 유지·확장 중이다. 즉 Apple은 "발표"와 "실제 일반
  사용자 배포" 사이 간격을 WWDC(6월)→가을 정식 출시(9월)의 약 3개월로 관리하며, 2026년에도 이
  주기를 그대로 반복했다.
  (source: [MacRumors(iOS 27 출시일 2026-09-09 발표, 2026-09-14 출시)](https://www.macrumors.com/2026/09/09/apple-announces-ios-27-release-date/), [iDropNews(iPhone Mirroring 업그레이드)](https://www.idropnews.com/ios-27/ios-27-macos-27-iphone-mirroring-upgrade/267101/), [Apple Support(Universal Control)](https://support.apple.com/en-us/102459))
  **[2026-09-22 verifier 확인]** 9to5Mac(2026-09-09 발표), Wikipedia(iOS 27), MacRumors(2026-09-13)
  재검색으로 2026-09-14(월) iOS 27·macOS 27·iPadOS 27·watchOS 27·tvOS 27·visionOS 27 동시 정식
  출시 사실 일치 확인. WWDC 2026-06-08 발표 사실도 일치.
- **App Intents가 "크로스앱 에이전트 실행"의 유일한 공식 경로로 격상됐다 — WWDC 2026(2026-06-08)
  에서 SiriKit 공식 폐기(deprecation) 발표, 개발자에게 2~3년 전환 유예.** 새 Siri AI(Gemini 기반,
  별도 기존 파일 `home-ai-standard-war-2026-09-21.md` 참고)는 App Intents 스키마를 채택한 앱만
  "화면 인식(onscreen awareness)"과 "개인 컨텍스트" 기반으로 크로스앱 액션을 실행할 수 있다 —
  이는 Apple이 자사 OS 권한 체계 안에서만 이 크로스앱 실행을 허용한다는 뜻이며, 동일한 수준의
  시스템 전역 크로스앱 오케스트레이션을 서드파티가 OS 밖에서 재현하기는 구조적으로 불가능하다.
  (source: [Dracode(WWDC 2026 App Intents/Siri)](https://dracode.dev/blog/2026-06-08-09-wwdc-2026-siri-2-app-intents/), [TechTimes(SiriKit 폐기)](https://www.techtimes.com/articles/318005/20260608/wwdc-2026-app-intents-replaces-sirikit-gemini-siri-migration-clock-starts.htm), [Apple Developer(App Intents 문서)](https://developer.apple.com/documentation/appintents))

→ **종합**: Apple의 연결성 우위는 "기능이 많아서"가 아니라 "무선 프로토콜 조합 + 칩셋 + OS 권한
체계 + 클라우드 계정 시스템 + 25억 대 설치기반"이 전부 한 회사 안에서 맞물려 있기 때문이다. 이
구조는 경쟁사가 파트너십이나 표준 채택만으로는 복제할 수 없는 진짜 해자(moat)다.

### 2. HomeKit·Apple Home의 2026년 가전 생태계 확장 — 확장은 카메라·보안 쪽에 집중, 서드파티 가전은 여전히 공백

- **구 HomeKit 아키텍처 지원 종료: 2026-02-10.** Apple Home은 이 시점부로 완전히 Matter
  컨트롤러 체제로 전환을 마쳤다 — Apple이 Matter 컨트롤러 역할을 자임한 것은 2022년부터지만,
  구 아키텍처를 완전히 걷어낸 것은 2026-02-10이 처음이다.
  (source: [Geeky Gadgets](https://www.geeky-gadgets.com/homekit-support-ended-february-2026/), [matter-smarthome.de](https://matter-smarthome.de/en/products/apple-finally-switches-home-architecture-for-matter/))
- **WWDC 2026(2026-06-08)에서 발표되고 2026-09-14(iOS 27) 정식 출시된 Apple Home 최대 업데이트는
  "가전 연결 확장"이 아니라 "보안 카메라 AI 기능"이다.** HomeKit Secure Video가 첫 출시(2019년) 이후
  줄곧 1080p로 제한되던 것을 4K 녹화·스트리밍으로 상향했고, Apple Intelligence가 영상 클립을
  자연어로 설명·검색(예: "택배가 배송된 장면 찾아줘")하는 기능을 추가했다. 단, 이 AI 기능은
  **카메라 대수별로 iCloud+ 상위 요금제 가입을 요구하는 유료 게이트 구조**다 — 카메라 1대는
  2TB($9.99/월), 2대는 6TB($29.99/월), 최대 5대는 12TB($59.99/월) 요금제가 필요하며, 6대 이상 지원
  여부는 공개되지 않았다. 요금제 자체의 신규 인상은 아니라는 점(기존 iCloud+ 가격 유지)은 Apple이
  명시했다.
  (source: [homekitnews(2026-06-09)](https://homekitnews.com/2026/06/09/apple-intelligence-and-4k-recording-come-to-the-home-app/), [AppleHome Authority](https://www.applehomeauthority.com/apple-home-gets-its-biggest-update-in-years-at-wwdc-2026/), [AppleInsider(요금제 상세, 2026-09-15)](https://appleinsider.com/articles/26/09/15/apple-intelligence-homekit-secure-video-summaries-cost-up-to-60-per-month), [Gizmodo](https://gizmodo.com/apple-homes-ai-security-camera-features-are-opt-in-if-you-can-afford-them-2000811813))
- **2026년 기준, 냉장고·세탁기·오븐 등 주요 생활가전 브랜드 중 Apple HomeKit/Apple Home을 직접
  지원하는 곳은 사실상 없다.** 삼성(SmartThings)·LG(ThinQ)·GE(SmartHQ)·Whirlpool/KitchenAid·
  Bosch(Home Connect)·Miele(Miele@mobile)·Electrolux 모두 각자 자체 앱을 쓰고, 전부 Alexa·Google
  Home과는 연동하지만 HomeKit과는 연동하지 않는다. Matter를 매개로 한 간접 연동이 유일한 경로인데,
  ~~**삼성은 2026년형 일부 냉장고·세탁기 모델에 Matter 지원을 발표(아직 실배송 전)했고, LG는 Matter
  가전 지원을 2027년 모델로 계획, Bosch/BSH도 Home Connect의 Matter 대응을 2027년으로 목표**하고
  있다 — 즉 2026년 시점 주요 3사 모두 "가전 자체의 Matter 지원"은 아직 실현되지 않았거나 계획
  단계다.~~ **[2026-09-22 verifier 정정] Bosch/BSH 부분은 사실과 다르다 — Bosch/BSH는 이미
  2025-01(CES 2025)에 "업계 최초 Matter 인증 가전(냉장고)"을 공개했고, Bosch 100/300/500 Series
  냉장고가 2025년 봄(미국 기준) 실제로 출시·판매됐다(BSH 공식 CES 2025 보도자료, us.bosch-press.com;
  Bosch 공식 지원 페이지 bosch-home.com/us/experience-bosch/home-connect/matter). BSH의 공개
  로드맵은 "2025년 냉장고 시작 → 2026년 가전 카테고리 1개 추가 → 2027년 3개 카테고리 추가"이며,
  "Home Connect의 Matter 대응을 2027년으로 목표"라는 원 서술은 **Bosch가 이미 2년 전에 첫 Matter
  가전을 출시했다는 사실과 정면으로 배치**되므로 삭제한다. 삼성·LG 부분은 이번 재검증에서도
  1차 출처(삼성 뉴스룸·LG전자 공식 뉴스룸)로 확정하지 못했다 — 재검색 결과 삼성 SmartThings는
  Matter 컨트롤러(허브) 역할은 이미 지원하지만 "삼성 자체 대형가전(냉장고·세탁기)이 Matter
  엔드포인트로 인증됐다"는 확정 근거는 찾지 못했고(GReverse 등 2차 매체는 오히려 "삼성 자체
  대형가전은 아직 Matter를 채택하지 않았다"고 서술), LG도 webOS/TV의 Matter 컨트롤러 지원 사실은
  다수 확인되나 "LG 냉장고·세탁기 자체가 Matter 엔드포인트로 2027년 지원 예정"이라는 구체 로드맵은
  1차 출처로 확정하지 못했다 — 이 두 회사 부분은 계속 Open questions로 남긴다.** 요컨대 2026년
  시점 "가전 자체의 Matter 엔드포인트 지원"에서 **Bosch/BSH는 이미 2025년부터 실현 단계**이고,
  삼성·LG는 확인 불가(미확정)다 — 세 회사를 "모두 2026-2027년 계획 단계"로 뭉뚱그린 원문 서술은
  과도한 일반화였다. Matter 모델이 실제로 출하되면 HomePod/Apple TV가 컨트롤러 역할을 해 Apple
  Home 앱에 자동으로 나타나는 구조이므로, 브랜드가 HomeKit 전용 작업을 따로 할 필요는 없다.
  (source: [EasyBear(2026년 HomeKit 가전 호환성 정리)](https://easybear-appliancerepair.com/blog/apple-homekit-appliance-compatibility), [DataWireSolutions(LG webOS/Matter 2027)](https://datawiresolutions.com/blog/lg-webos-smart-home-integration) — 원 출처, 삼성·LG 부분은 여전히 SEO 블로그 기반 미확정.
  **[2026-09-22 verifier 정정 출처]** [BSH/Bosch 공식 CES 2025 보도자료](https://us.bosch-press.com/pressportal/us/en/press-release-26304.html), [BSH CES 2026 보도자료(2026/2027 카테고리 확장 로드맵)](https://www.bsh-group.com/us/press/press-releases/bsh-home-appliances-at-ces-2026), [Bosch 공식 Matter 지원 페이지](https://www.bosch-home.com/us/experience-bosch/home-connect/matter))
- **LG가 HomeKit에 없다는 것은 "LG가 뒤처져서"가 아니라 업계 전체가 아직 안 들어가 있다는 뜻이다.**
  즉 HomeKit 가전 생태계는 2026년 시점 Apple 쪽에서도 확장이 정체된 영역이며, Apple의 2026년
  투자는 명백히 "카메라·보안"에 쏠려 있다 — 냉장고·세탁기 같은 대형가전 직접 연동 확장은 2026년
  Apple 자체 로드맵에서도 우선순위가 아니었다.

→ **종합**: "현재 경쟁 상황"의 헤드라인은 "Apple Home의 2026년 최대 업데이트는 가전이 아니라
보안카메라 AI(유료 게이트)"이며, 가전 브랜드 연동은 2026년에도 사실상 공백 상태다.

### 3. CarPlay(Ultra) — "차에서 시작한 작업이 집으로 이어진다"는 시나리오는 2026년 기준 확인되지 않음

- **CarPlay와 HomeKit의 연동 자체는 오래된 기능(iOS 13, 2019년)이며, 2026년에 새로 발표된
  "차→가전 연결" 신규 시나리오는 확인되지 않았다.** 기존 통합은 차고문 개폐 등 "집 반경 100m
  이내 진입/이탈 시 CarPlay 잠금화면에 관련 HomeKit 액세서리가 뜨는" 수준이거나, iPhone 위치
  기반으로 조명·온도·잠금을 자동화하는 정도다. 이는 "차에서 시작한 작업을 집 기기가 이어받는"
  능동적 연속성이 아니라, 수동적 위치 트리거에 가깝다. **2026년 확인 자료 없음** — 이번 조사에서
  CarPlay Ultra나 Apple Home이 2026년에 새로 "차량 내 작업(예: 음악·미디어·설정)을 집 기기로
  핸드오프"하는 구체적 제품 발표를 찾지 못했다.
  (source: [Apple Support(CarPlay에서 홈 제어)](https://support.apple.com/guide/iphone/control-your-home-iph11a3c5370/ios))
- **CarPlay Ultra 자체가 2026년 기준 오히려 정체돼 있다.** 2025-05-15 Aston Martin 차종(DBX S,
  DB12, Vanquish)으로 최초 출시된 이후, **2026-08-20 기준(1년 3개월 경과) 여전히 Aston Martin이
  유일한 지원 브랜드**다. 2026-05-04·2026-05-21 보도에서 Apple은 현대·기아·제네시스 등이 CarPlay
  Ultra 채택을 계획 중이라 밝혔으나, Bloomberg의 Mark Gurman은 2026-08-20 기사에서 이를 "다소
  실패작(a bit of a dud)"이라 평가했고, "애플 정도 규모의 회사에게 이런 니치한 제공 방식은
  이례적"이라 지적했다. Gurman에 따르면 2026년 하반기 중 현대 또는 기아의 최소 1개 모델(가장
  유력 후보는 현대 아이오닉 3)에 CarPlay Ultra가 탑재될 것으로 전망되나, 2026-09-22(이 조사
  시점) 기준 실제 출시 여부는 확인되지 않았다.
  (source: [MacRumors(2026-08-20, "Where is CarPlay Ultra?")](https://www.macrumors.com/2026/08/20/apple-where-is-carplay-ultra/), [MacRumors(2026-05-21)](https://www.macrumors.com/2026/05/21/carplay-ultra-future-vehicle-brands/), [9to5Mac(2026-05-04)](https://9to5mac.com/2026/05/04/carplay-ultra-automakers/))
  **[2026-09-22 verifier 확인]** 재검색으로 "2026-08-20 기준 여전히 Aston Martin 단독", Mark
  Gurman의 "a bit of a dud" 인용, 현대/기아 2026년 하반기 탑재 전망 모두 원문 그대로 일치 확인.
- **CarPlay(표준판) 자체의 보급률은 매우 높다 — 2026년 미국 신차의 약 94%가 CarPlay를 지원**하고
  (800개 이상 모델, 50개 이상 브랜드), 미국 신차 구매자의 약 80%가 "CarPlay 미지원 차량은
  고려하지 않는다"고 답했다. 단, 이 수치들은 정확한 발표 기관·조사 시점(정확한 날짜)까지는 확인하지
  못했다("2026년" 자료로 스니펫에서 확인됐으나 원문 1차 대조는 못함 — Open questions 참고).
  (source: WebSearch 종합, addcarwidgets.com 스니펫 기반, 원문 미확인)
  **[2026-09-22 verifier 확인 — 단, 원문 1차 대조는 여전히 미완료]** 재검색 결과 동일 수치(미국
  신차의 94%, 신차 구매자의 80%)가 obdeleven.com·cartechstudio.com·wifitalents.com 등 복수의
  독립된 2차 자동차 통계 매체에서도 일관되게 인용되고 있어, 특정 한 매체의 오기(誤記)가 아니라
  업계에 널리 통용되는 수치임은 추가로 확인됐다. 다만 이 수치의 최초 발표 기관·조사방법론·정확한
  조사 시점(YYYY-MM-DD)은 이번 재검증에서도 확정하지 못했다 — 원문 1차 소스 특정은 여전히 Open
  question으로 남긴다.

→ **종합**: LG UX디자인연구소가 다루는 "차→가전 연결 지점"에서, **Apple은 2026년 기준 이 영역의
실질적 제품을 내놓지 못했다.** CarPlay Ultra(차세대 CarPlay, 계기판까지 장악)조차 자동차 업계의
저항으로 1개 브랜드에 갇혀 있고, "차에서 집으로 이어지는" 시나리오는 위치 기반 자동화 수준에
머물러 있다 — 이는 Apple의 명백한 공백 지대이자, LG가 실질적으로 앞서갈 수 있는 영역이다.

### 4. Apple 연결성의 폐쇄성이 만드는 실제 실패/한계 — 2026년 구체 사례

- **Siri AI가 2026-06-08 WWDC에서 발표된 직후, EU에서는 무기한 연기됐다.** Apple은 2026-06-08~09
  Apple Newsroom을 통해 "Siri AI는 iOS 27·iPadOS 27의 EU 출시에서 제외된다"고 공식 발표했다.
  Apple의 주장은 EU 집행위원회가 DMA(디지털시장법) 해석상 타사 음성 비서에도 Siri AI와 동일한
  수준의 시스템 접근권(메시지 읽기/전송, 구매, 파일 접근, 설치된 앱 전반의 작업 실행)을 요구하는데,
  이를 안전하게 개방할 기술적 보호장치가 현재는 없다는 것이다. Apple은 수개월간 중간 단계 솔루션과
  18개월 단계적 출시안을 제안했으나 EU 집행위가 모두 거부했다고 밝혔고, 명확한 향후 일정도 제시하지
  못했다. 단, Mac·visionOS·watchOS는 DMA상 "게이트키퍼 플랫폼"으로 지정되지 않아 이 제한에서
  제외됐다.
  (source: [Bloomberg(2026-06-08)](https://www.bloomberg.com/news/articles/2026-06-08/apple-delays-siri-ai-for-iphone-users-in-eu-says-regulators-refusing-to-engage), [Engadget](https://www.engadget.com/2189932/siri-ai-for-iphones-and-ipads-will-be-delayed-indefinitely-in-the-eu/), [Apple Newsroom](https://www.apple.com/newsroom/2026/06/due-to-dma-siri-ai-delayed-in-eu-for-ios-27-and-ipados-27/) — Apple Newsroom 원문은 EGRESS_BLOCKED로 직접 열람은 못했으나 Bloomberg·Engadget 등 복수 매체가 발표 사실·날짜·내용을 교차 확인)
  **[2026-09-22 verifier 확인]** 재검색으로 Apple Newsroom URL(apple.com/newsroom/2026/06/due-to-
  dma-siri-ai-delayed-in-eu-for-ios-27-and-ipados-27/) 실존 확인, Engadget·Daring Fireball·
  ieu-monitoring 등 추가 매체로 "무기한 연기"·"명확한 일정 없음"·Craig Federighi 발언 내용 일치
  확인.
- **2026-07-08, EU 일반법원(General Court)이 Apple의 DMA "게이트키퍼" 지정 취소 소송을 전부
  기각했다.** 이로써 App Store·iOS가 DMA상 핵심 플랫폼 서비스(core platform service)라는 지정이
  확정됐고, Apple의 유일한 남은 불복 경로는 사실관계 재심리가 불가능한 법률심(CJEU 상고)뿐이다.
  즉 Apple이 자사 iOS/App Store의 폐쇄성을 규제로부터 방어하려던 시도가 2026년에 법적으로 실패한
  것이다.
  (source: [TechTimes(2026-07-08)](https://www.techtimes.com/articles/319935/20260708/apple-loses-dma-gatekeeper-fight-eu-court-closes-interoperability-challenge-window.htm), [HNGN(2026-07-09)](https://www.hngn.com/articles/271991/20260709/eu-court-upholds-apples-gatekeeper-status-under-digital-markets-act-rejects-challenge.htm), [Ashurst Perkins Coie 법률분석](https://www.ashurstperkinscoie.com/en/insights/eu-general-court-rejects-apple-challenges-to-european-commission-dma-designation-decisions/))
  **[2026-09-22 verifier 확인]** 재검색으로 2026-07-08 판결일, T-1079/23·T-1080/23 사건번호,
  iMessage 핵심 플랫폼 서비스 지정 관련 청구 각하, CJEU 상고만 남은 상황 모두 Concurrences·JURIST·
  Lawyer Monthly·dig.watch 등 복수 매체로 일치 확인.
- **DMA 상호운용성 요청 56건 중 단 1건도 해결되지 않음 — 2026-03-22 기준.** 개발자들이 JIT
  컴파일, NFC 프로토콜, Bluetooth LE Audio 등에 대한 접근을 요청했지만 "법의 적용범위 밖"이라는
  이유로 대부분 거부됐다. 또한 iMessage 대화 이력은 사실상 타 플랫폼으로 이전(export)이 불가능해
  수년치 개인 커뮤니케이션이 Apple 생태계 안에 갇혀 있다는 지적("exit penalty" 구조)도 있다 —
  즉 "기기 전환 시 데이터 이전"은 형식적으로는 지원되지만(연락처·캘린더·메시지·사진 등), 실질적
  락인 효과는 여전히 강하다는 것이 2026년 학계·정책 분석의 결론이다.
  (source: [FSFE(2026-07-24)](https://fsfe.org/news/2026/news-20260724-01.en.html), [Policy Review(exit penalty 분석)](https://policyreview.info/articles/news/exit-penalty-platform-migration), [EU DMA 공식 팩트시트(2026-05-11)](https://digital-markets-act.ec.europa.eu/factsheet-how-dma-making-smartphones-better-interoperability-and-data-portability-case-studies-2026-05-11_en))
  **[2026-09-22 verifier 확인, 출처 보완]** "56건 중 0건 해결(2026-03-22 기준)" 수치 자체는 재검색
  으로 정확히 일치 확인됐으나, 원 출처는 이 파일이 인용한 FSFE(2026-07-24) "Legal Corner" 글이
  아니라 FSFE(2026-04-20) "Apple keeps challenging its interoperability obligations under the
  DMA" 기사(fsfe.org/news/2026/news-20260420-01.html)에서 처음 보도된 수치다(2026-07-24 글은
  이후 같은 수치를 재인용하는 후속 요약 성격) — 인용 출처를 1차 보도 기준으로 보완한다. FSFE의
  JIT 컴파일·NFC·BLE Audio 요청 거부 사례, "24개월 이행 유예" 구조도 재검색으로 일치 확인.
- **자동차 업계의 CarPlay(Ultra) 저항이 2026년에도 이어지고 있다.** GM은 신형 전기차 라인업에서
  Apple CarPlay 자체를 제거하고 자체 소프트웨어 플랫폼으로 전환하는 기존 방침(2023년 결정, 배경
  정보)을 2026년에도 유지 중이며, BMW·Rivian은 CarPlay Ultra 채택에 공개적으로 회의적 입장을,
  Mercedes-Benz는 독자 OS에 투자하는 방향을 택하고 있다(2026년 시점 CarPlay Ultra 채택 브랜드
  현황, 위 3번 항목 출처와 동일). 즉 Apple의 폐쇄적 통합 방식(차량 계기판 전체 장악)이 자동차
  OEM 입장에서는 오히려 자사 브랜드 경험·데이터 주권을 빼앗기는 위협으로 인식되고 있다.
  (source: [9to5Mac(2026-05-04)](https://9to5mac.com/2026/05/04/carplay-ultra-automakers/), [MacRumors(2026-08-20)](https://www.macrumors.com/2026/08/20/apple-where-is-carplay-ultra/))

→ **종합**: Apple의 연결성 강점을 만드는 바로 그 구조(전 계층 자사 통제)가, 정확히 같은 이유로
2026년 한 해 동안 EU 규제 기관·자동차 OEM 양쪽 모두와 정면충돌했다. "폐쇄성 = 매끄러움"과
"폐쇄성 = 리스크"는 동전의 양면이며, 2026년 사례들은 후자가 실제로 비용(규제 패소, OEM 이탈,
지역별 기능 차등)으로 현실화되고 있음을 보여준다.

## LG전자 관점 시사점 (상세)

### 구조적 차이를 먼저 인정해야 한다

LG는 Apple처럼 실리콘(자체 모바일 AP)·OS(모바일/데스크톱)·클라우드 계정 시스템을 전 계층
통제하지 못한다. 따라서 "Apple처럼 폐쇄형 수직통합으로 매끄러움을 만든다"는 전략 자체는 LG의
선택지가 아니다 — 이는 실행력 부족이 아니라 사업 구조 자체의 차이이며, 2027 사업계획에서
"우리도 이렇게 하자"는 식으로 벤치마킹하면 안 되는 지점이다.

### 벤치마킹할 것 — Apple이 못 채우는 두 개의 구멍

1. **가전↔가전 이종 브랜드 통합**: 2026년 기준 Apple Home에 주요 가전 브랜드가 사실상 전무하고,
   LG 자체도 Matter 가전 지원을 2027년으로 계획하고 있다는 점(위 2번 항목, 단 출처 신뢰도 재검증
   필요)은 이 영역이 "아직 아무도 못 채운 공백"이라는 뜻이다. LG가 앳홈(Athom) 호미(Homey) 기반
   개방형 허브(기존 파일 `home-ai-standard-war-2026-09-21.md`에 상세)로 이종 브랜드(삼성 제외)
   가전까지 통합 제어하는 경험을 먼저 완성하면, Apple이 2026년에도 못 채운 "가전 생태계 허브"
   포지션을 선점할 수 있다.
2. **차→가전 연결(vehicle-to-home continuity)**: CarPlay Ultra가 2026년 하반기까지도 자동차 1개
   브랜드에 갇혀 있고, "차에서 시작한 작업이 집으로 이어지는" 시나리오를 Apple이 제품화하지
   못했다는 사실은, 이 영역이 LG UX디자인연구소의 핵심 미션(가전↔차량 연결)에서 경쟁사 공백이
   가장 뚜렷한 지점임을 뜻한다. 단, LG도 완성차 OEM이 아니므로 이 시나리오를 구현하려면 현대차
   등 완성차 업체와의 파트너십이 전제조건이다 — GM·BMW·Rivian·Mercedes가 Apple의 "계기판 전체
   장악형" 통합을 거부하고 있다는 점은, LG가 반대로 "OEM 브랜드 경험을 침해하지 않는 개방형 연결"
   방식으로 접근하면 자동차 업계의 반감을 피하면서 이 공백을 채울 여지가 있다는 뜻이기도 하다.

### 피해야 할 것 — Apple식 폐쇄성의 대가

1. **유료 게이트가 붙은 "개방"을 흉내 내지 말 것**: HomeKit Secure Video AI가 카메라 대수별로
   최대 월 $59.99까지 요구하는 것처럼, "AI 기능=프리미엄 구독" 공식을 그대로 따라가면 국내
   시장에서는 오히려 가격 저항을 부를 수 있다(기존 파일 `appliance-subscription-business-model-
   shift-2026-09-21.md`의 구독 피로도 논의와 연결).
2. **플랫폼 전체 장악형 통합은 파트너(완성차·타 가전사)의 반발을 부른다**: CarPlay Ultra가
   자동차 계기판 전체를 Apple 디자인으로 덮어씌우려다 GM·BMW·Rivian·Mercedes의 저항을 샀듯,
   LG가 차량이나 타사 가전과 연결할 때도 "LG UX가 상대 브랜드 경험을 지워버리는" 방식이 아니라
   "상대 브랜드 정체성을 유지한 채 연결 지점만 매끄럽게 하는" 방식을 택해야 파트너십이 지속
   가능하다.
3. **지역별 기능 차등의 리스크를 사업계획에 반영할 것**: Siri AI의 EU 무기한 연기 사례는, 폐쇄적
   AI 에이전트 아키텍처가 규제 환경에 따라 특정 지역에서 아예 기능을 못 낼 수 있다는 리스크를
   보여준다. LG의 씽큐 클로(ThinQ Claw) 등 에이전트형 기능을 설계할 때도 한국 개인정보보호법·
   EU GDPR/DMA 등 지역별 규제 차이를 초기 설계 단계에서 고려해야, 출시 후 특정 지역에서 기능을
   빼야 하는 사태를 피할 수 있다.

## Open questions / gaps

- **[2026-09-22 verifier 정정 반영]** LG의 2027년 Matter 가전 지원 계획, 삼성의 2026년형 일부
  모델 Matter 지원 서술은 재검증 결과 여전히 1차 출처로 확정하지 못했다(계속 Open question).
  **Bosch/BSH의 "2027년 목표" 서술은 오류로 확인되어 본문에서 정정했다** — Bosch/BSH는 이미
  2025-01(CES 2025)에 Matter 인증 냉장고를 공개, 2025년 봄 미국 실판매를 시작했고, 공식 로드맵은
  "2025 냉장고 → 2026 카테고리 1개 추가 → 2027 카테고리 3개 추가"다(BSH/Bosch 공식 보도자료로
  확인). 삼성·LG 부분은 삼성 뉴스룸, LG전자 공식 뉴스룸(news.lge.co.kr/lg.com, 이번 세션에서도
  EGRESS_BLOCKED로 직접 열람 불가)으로 1차 대조·재검증이 여전히 필요하다.
- CarPlay 보급률 수치(미국 신차의 94%, 신차 구매자의 80%가 CarPlay 미지원 시 구매 안 함)는
  addcarwidgets.com 스니펫 기반으로만 확인했고, 정확한 발표 기관·조사 시점·원문은 확인하지
  못했다.
- Apple Newsroom(apple.com), techcrunch.com 등 다수 1차 소스 도메인이 이번 세션 환경에서
  EGRESS_BLOCKED로 직접 열람이 안 되어, WebSearch 스니펫 및 2차 매체(MacRumors, Bloomberg,
  AppleInsider 등) 인용으로 교차 확인했다 — 가능하면 후속 세션에서 원문 대조가 필요하다.
- CarPlay Ultra의 "차→가전 연결" 시나리오는 이번 조사에서 "2026년 확인 자료 없음"으로 결론
  내렸으나, Apple이 비공개로 개발 중인 로드맵이 있을 가능성은 배제할 수 없다 — WWDC 2027(2027년
  예상) 발표를 후속 세션에서 확인할 필요가 있다.
- 현대차·기아·제네시스의 CarPlay Ultra 실제 탑재 모델·출시일은 2026-09-22(이 조사 시점) 기준
  미확정이다 — 2026년 하반기 중 공식 발표가 나오면 후속 세션에서 업데이트가 필요하다.
- Apple Silicon의 "성능당 전력효율" 등 구체 벤치마크 수치(M2 Max vs Intel/AMD 등)는 2026년 발표
  자료가 아니라 일반적 아키텍처 설명으로만 인용했다 — 이 파일의 "구조적 강점" 섹션은 CLAUDE.md의
  2026-only 헤드라인 규칙이 아니라 "왜 강한가"라는 구조 설명 목적이므로 예외적으로 연혁 정보를
  포함했음을 명시한다(단, 2026년 신규 수치인 "2.5B 활성기기"·"iOS 27/macOS 27 2026-09-14 출시"는
  모두 2026년 자료로 확인됨).
