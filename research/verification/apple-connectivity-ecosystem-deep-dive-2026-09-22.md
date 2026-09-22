# Verification — Apple의 기기 간 연결성 생태계 전략 (Continuity·HomeKit·CarPlay·App Intents)
Date: 2026-09-22
Target: `research/findings/competitor/apple-connectivity-ecosystem-deep-dive-2026-09-22.md`

Scope note: 사용자 요청의 우선 재검증 항목(LG/삼성/Bosch Matter 가전 로드맵, CarPlay 보급률 수치)과
저자가 스스로 재검증 필요로 플래그한 항목에 집중했고, 핵심 날짜·수치 claim(Siri AI EU 무기한 연기,
EU 일반법원 DMA 소송 기각, DMA 상호운용성 요청 56건, CarPlay Ultra Aston Martin 단독, Apple 활성기기
25억 대, iOS 27/macOS 27 출시일)도 독립 재검색으로 교차검증했다.

## Result: PASS WITH NOTES

## Issues found
- **[high] Bosch/BSH Matter 가전 지원 시점 오류 — 2번 항목("HomeKit·Apple Home의 2026년 가전
  생태계 확장") — 정정 완료.** 원문은 "Bosch/BSH도 Home Connect의 Matter 대응을 2027년으로 목표"라고
  서술했으나, 재검색 결과 **Bosch/BSH는 이미 2025-01(CES 2025)에 업계 최초 Matter 인증 냉장고(100
  Series)를 공개하고 2025년 봄 미국 시장에 실제 출시·판매했다**(BSH 공식 CES 2025 보도자료,
  us.bosch-press.com). BSH의 공식 확장 로드맵은 "2025년 냉장고 → 2026년 카테고리 1개 추가 → 2027년
  카테고리 3개 추가"이며, "2027년 목표"라는 원문 서술은 Bosch가 이미 2년 전에 시장 진입을 마쳤다는
  사실과 정면으로 배치된다. 본문에 `[2026-09-22 verifier 정정]` 태그로 직접 수정했고, Open questions
  섹션도 함께 갱신했다. 이 오류는 저자가 스스로 "SEO 블로그 출처만 확인, 재검증 필요"로 플래그한
  항목이었고, 실제로 재검증 결과 오류였다 — 저자의 자체 플래그가 정확히 작동한 사례.
- **[medium] 삼성·LG의 Matter 가전 로드맵은 재검증 후에도 미확정 — 여전히 Open question.** 재검색
  결과 삼성 SmartThings는 Matter *컨트롤러*(허브) 역할은 이미 지원하지만 "삼성 자체 대형가전(냉장고·
  세탁기)이 Matter *엔드포인트*로 인증됐다"는 1차 출처 확정 근거는 찾지 못했다 — 오히려 일부 2차
  매체(GReverse)는 "삼성 자체 대형가전은 아직 Matter를 채택하지 않았다"고 서술해 원문의 "2026년형
  일부 모델 발표"와 다소 배치되는 뉘앙스가 있다. LG도 webOS/TV의 Matter *컨트롤러* 지원 사실은 다수
  확인되나(webOS 23+ Matter 인증, LG 공식 지원 페이지), "LG 냉장고·세탁기 자체가 Matter 엔드포인트로
  2027년 지원 예정"이라는 구체 로드맵은 1차 출처(LG전자 공식 뉴스룸)로 확정하지 못했다 — 삼성 뉴스룸·
  LG전자 공식 뉴스룸이 이번 세션에서도 EGRESS_BLOCKED였다. 원문의 해당 서술에 불확실성 라벨은 이미
  있었으나(SEO 블로그 기반이라는 점), 재검증 후에도 확정하지 못했다는 점을 본문·Open questions에
  명시적으로 반영했다.
- **[low] CarPlay 보급률 수치(미국 신차 94%, 구매자 80%)의 1차 출처는 여전히 미확정.** 재검색으로
  obdeleven.com·cartechstudio.com·wifitalents.com 등 복수의 독립된 2차 자동차 통계 매체에서 동일
  수치가 일관되게 인용됨을 추가로 확인해, 특정 매체의 단순 오기가 아니라는 점은 보강됐다. 다만 최초
  발표 기관·조사방법론·정확한 조사 시점(YYYY-MM-DD)은 이번 재검증에서도 특정하지 못했다 — 원문이
  이미 "원문 미확인"으로 적절히 라벨링했고, 이 판단을 유지한다.

## Confirmed items ([2026-09-22 verifier 확인] 태그로 파일 내 직접 표시)
- **Apple 활성기기 25억 대**: 2026-01-29 실적발표, 직전 해 2.35B 대비 150M 순증 — MacRumors,
  AppleInsider, 9to5Mac, CNBC로 교차확인.
- **iOS 27·macOS 27 등 정식 출시**: 2026-09-14(월), WWDC 2026-06-08 발표 — 9to5Mac, MacRumors,
  Wikipedia로 교차확인.
- **CarPlay Ultra — 2026-08-20 기준 여전히 Aston Martin 단독**: Mark Gurman의 "a bit of a dud"
  인용, 현대/기아 2026년 하반기 탑재 전망 모두 MacRumors 원문과 일치.
- **Siri AI EU 무기한 연기**: 2026-06-08/09 발표, Apple Newsroom URL 실존 확인, "명확한 일정 없음"·
  Craig Federighi 발언까지 Engadget·Daring Fireball·ieu-monitoring 등으로 교차확인.
- **EU 일반법원 DMA 게이트키퍼 소송 기각**: 2026-07-08, 사건번호 T-1079/23·T-1080/23, iMessage 관련
  청구 각하, CJEU 상고만 남음 — Concurrences·JURIST·Lawyer Monthly·dig.watch로 교차확인.
- **DMA 상호운용성 요청 56건 중 0건 해결**: 2026-03-22 기준 수치 자체는 정확히 일치 확인됨. 단, 파일이
  인용한 FSFE(2026-07-24) 글은 이 수치의 1차 보도가 아니라 FSFE(2026-04-20) "Apple keeps challenging
  its interoperability obligations under the DMA" 기사의 재인용이었음을 확인해 출처를 보완했다.

## Unverifiable claims
- CarPlay 보급률(94%/80%)의 원 발표 기관·조사 시점 — 위 issues 참고, 1차 소스 미확정.
- 현대·기아·제네시스의 CarPlay Ultra 실제 탑재 모델·출시일 — 2026-09-22 시점 미확정이라는 원문 서술
  그대로 유지(향후 발표 시 후속 세션에서 갱신 필요).
- CarPlay Ultra의 "차→가전 연결" 비공개 로드맵 존재 여부 — 원문이 이미 "2026년 확인 자료 없음"으로
  적절히 라벨링, 이번 세션에서도 반증/입증 자료를 찾지 못함.

## Citation rule check (CLAUDE.md)
- 정확한 날짜 표기 원칙: 준수됨. "출시/발표"류 claim에 YYYY-MM-DD가 일관되게 사용됐고, 불확실한
  경우(CarPlay 보급률 조사 시점 등) 명시적으로 라벨링됨. 계절/반기 표현("2026년 봄" 등) 사용 없음.
- 2026-only 헤드라인 원칙: 준수됨. Continuity 프로토콜 자체의 연혁(2014년, 2023-09-12 UWB 칩 등)은
  "구조 설명 목적"으로 명시적으로 예외 처리·라벨링되어 있고, 2026년 신규 수치(2.5B 활성기기, iOS
  27/macOS 27 2026-09-14 출시)는 모두 2026년 자료로 확인됨. GM의 CarPlay 제거 결정(2023년)도
  "배경 정보"로 명시적으로 라벨링됨.
