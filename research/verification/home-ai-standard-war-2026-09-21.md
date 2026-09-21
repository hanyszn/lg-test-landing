# Verification — "홈 AI 표준 전쟁" — 누가 스마트홈의 "기본 에이전트" 자리를 차지하는가
Date: 2026-09-21
Target: `research/findings/competitor/home-ai-standard-war-2026-09-21.md`

Scope note: 사용자 요청의 우선 재검증 항목(구글 Home MCP 날짜·가격, 삼성 SmartThings API 날짜·가격)에
집중했고, 이 파일의 나머지 대형 claim들(Apple-Google Gemini 딜, Amazon-Anthropic 투자, Matter 버전
갱신, 씽큐 클로 공개)도 함께 재검색으로 교차검증했다.

## Result: PASS WITH NOTES

## Issues found
- **[medium] "씽큐 클로(ThinQ Clo)" 영문 표기 오류 — 2곳(현재 위치 진단, Open questions) —
  정정 완료.** 재검색 결과 LG 공식 영문 표기는 "ThinQ Claw"다(LG.com 공식 뉴스룸, PR Newswire,
  channellife.com.au, dealroom.co, fonearena.com 등 다수 1차·2차 소스 일치). "ThinQ Clo"는 이번
  세션 조사 원본 파일의 오기로 판단되어 `[2026-09-21 verifier 정정]` 태그로 파일 내 직접 수정함.
  추가로, "Claw"라는 이름이 오픈소스 에이전트 프레임워크 "OpenClaw"에서 유래한 것으로 보인다는
  정황도 확인해 덧붙였다 — 흥미롭게도 이 파일 자체가 이미 구글 Home MCP의 호환 에이전트 목록에
  "Open Claw"를 언급하고 있어(1번 항목), LG의 명명이 이 생태계와 연결돼 있을 가능성을 시사한다.
- 그 외 사실관계 오류는 발견되지 않았다.

## Confirmed items ([2026-09-21 verifier 확인] 태그로 파일 내 직접 표시)
- **구글 Home MCP**: 2026-09-16 얼리 액세스 공개, Google Home Premium Advanced(월 $20/연 $200)
  전용 게이트, Claude·ChatGPT·Google Antigravity·Hermes·Open Claw 등 지원 — 재검색(Engadget,
  AiCybr, techjournal.org 등 다수)으로 정확히 일치 확인.
- **삼성 SmartThings API 유료화**: 월 $4.99 "Personal Plan"(비상업 개인 개발자 대상), 2026년 10월
  시행(2026년 3분기까지는 무료 접근 유지) — Android Authority, Gadget Hacks, Windows News 등
  추가 매체로 교차확인. 2026년 6월 발표/2026-06-26 보도 확산일도 일치.
- **Apple-Google Gemini 딜**: 2026-01-12 발표, 연 약 $1B, 기존 대비 8배 큰 1.2조 파라미터 커스텀
  Gemini 모델 라이선스 — CNBC 원문(2026-01-12), Introl, ComputeLeap 등으로 교차확인. (Introl은
  총 계약 규모를 최대 $5B로 추정한다는 부가 정보도 확인 — 파일 본문과 상충하지 않음.)
- **Amazon-Anthropic 투자**: 2026-04-20 발표, 즉시 $5B + 마일스톤 조건부 최대 $20B(총 최대 $25B
  추가, 누적 최대 $33B), Trainium2/3 기반 최대 5GW 컴퓨팅 확보, Anthropic의 향후 10년 $100B+ AWS
  지출 약정 — CNBC, Motley Fool, CloudComputing-News, Anthropic 공식 발표로 교차확인.
- **씽큐 클로 공개**: 2026-09-04 IFA 2026에서 최초 공개, 노범준 LG전자 HS AI홈솔루션사업개발담당
  상무가 PoC·내외부 베타테스트 진행 중이며 연말 중 공식 출시 목표라고 발언, 커머스 제휴·구독형
  서비스 모델 검토 중이라는 발언도 원문(이투데이·이데일리·시대일보 등 2026-09-05 보도)과 정확히
  일치 확인.

## Unverifiable claims
- 스마트스피커 시장 점유율 범위(Amazon 23~30%, Google 20~25%, Apple 10~15%) — 파일 자체가 이미
  "단일 확정치 없음"으로 적절히 라벨링. 유료 리포트(Counterpoint 등) 접근 없이는 추가 검증 불가.
- "승자독식 vs 다자공존" 결말에 대한 정식 애널리스트(Gartner/IDC 등) 인용 — 파일이 이미 "추론이며
  뒷받침 자료 없음"으로 적절히 명시. 이번 세션에서도 해당 인용을 찾지 못해 추가 확인 불가.
- 씽큐 클로의 기반 LLM(EXAONE 자체 vs 외부 라이선스) — LG 공식 뉴스룸(`news.lge.co.kr` 등)이
  EGRESS_BLOCKED로 직접 열람 불가, 이번 세션에서도 확정하지 못함(파일의 기존 Open questions와 동일).

## Citation rule check (CLAUDE.md)
- 정확한 날짜 표기 원칙: 준수됨. "출시/발표"류 claim에 YYYY-MM-DD가 일관되게 사용되었고, 불명확한
  경우("애플 뉴스룸 상 2026년 6월로만 확인" 등) 명시적으로 라벨링됨.
- 2026-only 헤드라인 원칙: 준수됨. 2024/2025년 배경 사실(앳홈 인수, MS 파트너십 등)은 모두
  "배경 정보로만 인용"이라고 명시적으로 라벨링되어 있음.
