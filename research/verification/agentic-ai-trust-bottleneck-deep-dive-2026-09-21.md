# Verification — 에이전틱 AI의 신뢰 병목 — 표면적 결론을 넘어선 구체적 메커니즘
Date: 2026-09-21
Target: `research/findings/competitor/agentic-ai-trust-bottleneck-deep-dive-2026-09-21.md`

Scope note: 사용자 요청의 우선 재검증 항목 3건(Google Gemini for Home 리뷰 통계, EU AI Act
고위험 영역 및 2026년 옴니버스 개정 시행일, Ecovacs/Amazon Buy for Me 사건 사실관계) 모두 집중
재검증. 이 파일은 4개 대상 파일 중 재검증 결과가 가장 깨끗했다 — 아래 confirmed 항목 외에 정정이
필요한 오류는 발견하지 못했다.

## Result: PASS

## Issues found
- 없음. 우선 검증 대상 3건 모두 구체 수치·날짜·인용이 재검색으로 정확히 일치했다.

## Confirmed items ([2026-09-21 verifier 확인] 태그로 파일 내 직접 표시)
1. **Google Home 앱 리뷰 통계(2026-04-13~2026-09-08, 147일간, 4,000건 분석, 53.1% 별점 1점,
   1,340건 중 136건이 전환을 명시적 원인 지목)** — Unstar 블로그(unstar.app) 자체는 WebFetch
   EGRESS_BLOCKED로 원문 직접 열람은 못했으나, 독립적인 두 차례의 WebSearch 질의(각각 "53.1%"
   특정 검색, 일반 검색)에서 정확히 동일한 수치(4,000건, 53.1%, 136건, 147일, 2026-04-13~09-08)가
   재현되어 신뢰도가 높다. 다만 **이 통계의 원출처가 공식 리서치 기관이 아니라 Unstar라는 단일
   블로그의 자체 분석**이라는 점, 방법론(리뷰 표본 추출 방식, "전환을 원인으로 지목"이라는 감성분류
   기준)이 별도로 공개 검증되지는 않았다는 한계는 여전히 남는다 — 아래 Unverifiable claims 참고.
2. **EU AI Act Annex III 고위험 8개 영역에 스마트홈/일반 가전이 명시적으로 포함되지 않는다는 주장**
   — euaiact.com, artificialintelligenceact.eu 교차확인으로 뒷받침됨. 추가로 "핵심 인프라" 항목은
   AI가 "안전 구성요소"로 쓰이는 것뿐 아니라, **배포자(deploying entity)가 Critical Entities
   Resilience Directive상 "critical entity"로 지정되어 있어야 한다**는 누적 조건이 있음을 새로
   확인했다 — 일반 가정은 critical entity가 아니므로, 이 조건은 파일의 "일반 가전 AI는 원칙적으로
   8개 영역 어디에도 해당하지 않는다"는 결론을 더 강하게 뒷받침한다(파일은 이를 "unverified 최종
   결론"으로 신중하게 다뤘는데, 이번 재검증으로 그 신중한 결론이 옳았음이 추가로 확인된 셈).
3. **2026년 옴니버스 개정(Regulation (EU) 2026/1744) 관련 날짜 — 정확히 일치**: 2026-07-24 공포,
   2026-07-27 발효, Annex III(독립형 고위험 AI) 의무 2027-12-02로 연기, Annex I(제품내장형) 의무
   2028-08-02로 연기, 제5조(2025-02-02부터 시행 중)·GPAI 의무(2025-08-02부터 시행 중)·제50조는
   원 일정 유지 — Cloud Security Alliance, Modulos, White & Case, alpacax.com, sakaradigital.com
   등 5개 이상의 독립 매체가 동일한 날짜를 보고해 신뢰도가 매우 높음.
4. **Ecovacs Deebot X2 사건**: 2024-05-24 미네소타(변호사 Daniel Swenson)·LA 사건 동시 발생,
   텍사스 엘패소 별도 피해 사례, 2024-08-08~11 DEF CON 32에서 Dennis Giese·Braelynn Luedtke가
   블루투스 PIN 인증 취약점 공개, 2024-11 펌웨어 패치 — ABC News, incidentdatabase.ai #842,
   Malwarebytes, TechCrunch, Android Authority, digitalreviews.net 등 다수 매체로 정확히 일치
   확인. 파일의 서술과 불일치하는 부분 없음.
5. **Amazon "Buy for Me" 사건**: TechCrunch 원문(2025-04-03, "Amazon's new AI agent will shop
   third-party stores for you")으로 2025-04 출시 정확히 확인(파일이 "2025-04"로 정확히 기재).
   2026-01 반발 확산(SiliconANGLE 2026-01-06, CNBC 2026-01-06)도 정확히 일치. 무단 리스팅·재고
   미검증 문제, `branddirect@amazon.com` 옵트아웃 안내도 Modern Retail·PaymentsJournal·
   valueaddedresource.net 등 교차확인.

## Unverifiable claims
- Unstar 리뷰 분석의 세부 방법론(표본 추출·감성분류 기준) — 원문 WebFetch가 EGRESS_BLOCKED로
  차단되어 직접 대조 불가. 수치 자체는 두 독립 검색에서 재현되어 신뢰도가 높지만, "공식 통계"가
  아닌 "단일 블로그의 자체 분석"이라는 성격은 report-writer가 인용 시 명시할 것을 권고.
- Menlo Ventures(39%)와 Forrester(14%)의 소비자 신뢰 수치 차이 — 두 설문의 정확한 질문 문항·표본
  설계 차이는 이번 세션에서도 원 리포트 직접 대조로 확인하지 못했다(파일이 이미 "unverified"로
  적절히 라벨링).
- valueaddedresource.net 원문(Amazon 옵트아웃 절차에 대한 판매자 반박 인용) — WebFetch 차단으로
  직접 인용 검증 못함(파일이 이미 "unverified"로 적절히 라벨링).
- "가정용 냉난방·에너지 제어 AI가 EU AI Act '핵심 인프라 안전 구성요소'로 분류될 수 있는가"에 대한
  2026년 공식 가이드라인 여부 — 로펌 자료(2025-07)에 근거한 추정이며 이번 세션에서 2026년 공식
  가이드라인을 추가로 찾지 못했다(파일의 기존 라벨링과 동일).

## Citation rule check (CLAUDE.md)
- 정확한 날짜 표기 원칙: 준수됨. "출시/발표"류 claim에 YYYY-MM-DD가 매우 꼼꼼하게 사용되었고,
  법 조문 시행일(2025-02-02/2025-08-02/2027-12-02/2028-08-02)까지 정확히 구분되어 있음.
- 2026-only 헤드라인 원칙: 준수됨. Ecovacs(2024년), Google Nest 집단소송 배경(2025년), Alexa+
  얼리 액세스(2025-03) 등은 모두 "배경" 또는 "참고"로 명시적으로 구분되어 있고, 2026년 현재진행형
  상황(리뷰 통계, EU 옴니버스 개정, Google 대응)과 섞이지 않게 잘 분리되어 있음.
