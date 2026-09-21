# 삼성전자 — Bixby+Perplexity 가전 통합 업데이트 (2026-09) — Competitor Research

Date: 2026-09-21
Scope: 기존 `research/reports/2026-09-20-competitor-research-smart-home-ux-ai.md`의 삼성 섹션이 인용한
"AI 가전 모델 1,030종"(2025년 3월 기준) 수치가 오래됐다는 사용자 지적에 따라, 더 최신(2026년) 삼성
UX/AI 가전 동향을 보강 조사. 모델 총 개수의 최신 집계는 검색 범위에서 확인되지 않았으나(아래
Open questions 참고), 그보다 UX적으로 더 의미 있는 **2026년 신규 기능 발표**를 다수 확인함.

## Key findings

- **Bixby에 Perplexity 통합 — "Open Q&A" 기능, 2026-03-31 발표, 2026-09~ 한국부터 순차 적용.**
  LLM 기반으로 고도화된 Bixby가 가전(패밀리허브 냉장고, 에어컨, 로봇청소기, 정수기, 7인치 스크린
  탑재 신형 세탁기)에 확대 적용됨. 정형화된 명령어가 아니라 자연스러운 대화체 명령을 이해하고,
  후속 질문에 맥락을 유지하며 답변. 예시: "소고기랑 고등어 넣었으니까 모드 바꿔줘"처럼 저장 행위와
  후속 요청을 연결해 이해. Perplexity 연동으로 가전과 무관한 일상 질문에도 답하는 "Open Q&A"가
  추가되어, Bixby의 역할이 "가전 조작기"에서 "홈 컴패니언"으로 확장됨.
  (source: [Korea Times](https://www.koreatimes.co.kr/business/companies/20260331/samsung-enlists-perplexity-ai-to-refine-bixby-for-home-appliances), [eWeek](https://www.eweek.com/news/samsung-bixby-upgrade-challenges-gemini/), [BigGo Finance](https://finance.biggo.com/news/XT-LQZ0BDPbb-ItTaI_I), [Perplexity 공식 블로그](https://www.perplexity.ai/hub/blog/perplexity-apis-deliver-powerful-ai-to-the-world-s-largest-android-device-maker))
- **실제 롤아웃은 2026-09부터 한국 우선 시작, 제품·모델연식·지역별로 순차 적용.** 에어컨 예시:
  "환풍 없이 켜줘" → 무풍 모드로 전원 On. 로봇청소기 예시: "조용히 청소해줘" → 저소음 모드 전환.
  다른 지역 적용 일정은 미공개.
  (source: [Android Headlines](https://www.androidheadlines.com/2026/03/samsung-bixby-upgrade-smart-home-appliances-2026.html), [MyEverydayTech](https://www.myeverydaytech.com/samsung-ai-focused-software-updates-for-refrigerators-and-laundry-appliances-sep-2026/), [Sammy Fans](https://www.sammyfans.com/2026/03/30/samsung-bixby-brings-context-aware-intelligence-to-appliances/))
- **가전에 One UI 탑재 — 기기간 통합 SW 생태계 구축.** 모바일·TV·가전에 걸친 하나의 UI 프레임워크로
  통일해, 기기를 넘나드는 일관된 사용 경험을 노림.
  (source: [인공지능신문](https://www.aitimes.kr/news/articleView.html?idxno=36167), [헤럴드경제](https://biz.heraldcorp.com/article/10560759))
- **"나우 브리프(Now Brief)" — 2026년 정식 적용.** 패밀리허브 냉장고·AI 홈 터치스크린 냉장고에서
  위치·시간·사용 습관 기반 맞춤형 정보를 제공 — 구글 Gemini for Home의 "Daily Brief"(아침 요약
  브리핑)와 개념적으로 유사한 기능이 삼성 가전에도 등장.
- **"보이스 ID" — 목소리 구분 기반 개인화.** 일정·사진·접근성 설정 등을 사용자별로 구분 적용,
  2024년 이후 출시된 스크린 탑재 냉장고로 확대.
- **"AI 비전 인사이드 2.0" — 신선식품 37종 자동 인식**(기존 버전 대비 인식 품목 확대, 정확한 이전
  버전 품목 수는 미확인).
- **"녹스 대시보드" — 32형·7형 스크린 탑재 가전에서 연결 기기(모바일·TV·가전) 보안 상태를 통합
  확인.** 개별 기기가 아니라 가전 스크린이 홈 전체의 보안 허브 역할을 겸함.
- **Bixby 호출 방식 확장 — 음성("하이 빅스비") 외에 냉장고 스크린 두 번 두드리기(더블탭)로도 호출
  가능.**
- **2024년 이후 출시된 Wi-Fi 탑재 가전에 최대 7년간 One UI 무상 업그레이드 지원.** 스마트폰과 유사한
  장기 소프트웨어 지원 모델을 가전에 적용 — 구매 시점 스펙이 아니라 "몇 년간 최신 AI 기능을 받는가"가
  가전 구매 기준에 편입되는 흐름.
  (source: [아이뉴스 계열](https://www.aitimes.kr/news/articleView.html?idxno=36167) 외 상동 기사군 — 원문은 news.samsung.com/kr 계열이나 이번 세션에서 직접 fetch 불가(EGRESS_BLOCKED), WebSearch 스니펫 기반)

## LG전자 UX/가전 관점 시사점

- **"모드 자동 전환"형 멀티스텝 명령**(저장 행위+후속 요청 연결)은 LG의 "AI Agent 전사 가이드 1.0"이
  실제로 다뤄야 할 구체적 UX 패턴의 좋은 참고 사례. LG 가이드가 이런 수준의 컨텍스트 유지형 명령을
  다루는지 재확인 필요(기존 Part 4 테마 01의 열린 질문과 연결됨).
- **"가전 조작기 → 홈 컴패니언" 역할 확장 프레임**은 이번 세션에서 조사한 미국 AI/UX 기업들의
  "별도 챗봇이 아니라 기존 흐름에 임베드" 패턴(Perplexity Email Assistant 등)과 같은 방향 — 삼성도
  같은 흐름에 올라탐. 경쟁사가 이 프레임을 먼저 점유하기 전에 LG도 포지셔닝 필요.
- **7년 무상 SW 업그레이드**는 LG의 webOS Micro 플랫폼(03번)·디자인시스템(08번) 장기 유지보수
  전략에 참고할 만한 벤치마크 — "출시 시점 완성도"가 아니라 "수년간 어떻게 진화하는가"가 경쟁
  포인트가 될 수 있음.

- **[2026-09-21 추가] 구형 가전에 최신 AI 소급 적용 — 2026-09-11 전자신문 보도.** 2021년 이후
  출시된 패밀리허브 냉장고에도 "나우 브리프(Now Brief)"(위치·시간·사용 습관 기반 개인화 정보)와
  "오늘 뭐 먹지?(What's for Today?)"(보유 식재료 기반 메뉴·레시피 추천)를 2026년 9월부터 순차
  소급 적용. 2024~2025년형 일부 세탁가전에도 Tizen 10.0·최신 Bixby를 확대 적용하며, 냉장고를
  시작으로 세탁가전·정수기·식기세척기까지 확대 예정. 2024년 이후 출시된 Wi-Fi 탑재 가전은 최대
  7년간 무상 SW 업그레이드 지원 — "출시 시점 스펙"이 아니라 "몇 년간 최신 AI를 받는가"가 가전
  구매 기준으로 이동하는 흐름을 보여주는 사례.
  (source: [전자신문](https://www.etnews.com/20260911000182))
  - 참고: "One UI를 AI 가전에 탑재"하는 더 큰 틀의 발표 자체는 2025-08-25로, 이는 **2026년 이전
    자료라 이번 2026-only 기준에서는 제외**했다. 위 2026-09-11 보도는 그 정책이 2026년에 실제
    가전에 순차 적용되고 있음을 보여주는 별개의 2026년 소식으로 인용했다.

## Open questions / gaps

- **"AI 가전 모델 1,030종" 수치를 대체할 2026년 집계 수치는 이번 검색 범위에서 확인되지 않았다.**
  CES 2026(2026-01) 발표에서도 개별 신제품 라인업 확장 소식은 많았으나 "총 몇 종"이라는 집계 발표는
  스니펫에 잡히지 않음. `news.samsung.com` 원문 직접 열람이 막혀 있어(EGRESS_BLOCKED) 추가 확인이
  필요할 수 있다. → 기존 보고서/아티팩트에서는 이 수치를 "2025.03 기준"으로 명확히 라벨링하고,
  헤드라인 스탯으로는 이번에 확인된 2026-09 Bixby+Perplexity 통합을 대신 사용하는 것을 권장.
- Bixby+Perplexity 통합이 해외(미국 등) 시장에도 언제 적용되는지는 미공개.
- "AI 비전 인사이드 2.0"의 이전 버전 인식 품목 수(비교 기준)는 미확인.
- 7년 무상 업그레이드가 모든 국가/모델에 동일 적용되는지, 조건(예: Wi-Fi 필수)의 세부 범위는
  추가 확인 필요.
