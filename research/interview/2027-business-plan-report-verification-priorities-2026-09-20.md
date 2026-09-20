# Interview — 2027 사업계획용 보고서 3건 검증·후속조사 우선순위

Date: 2026-09-20
Reviewed: `research/reports/2026-09-20-competitor-research-smart-home-ux-ai.md`,
`research/reports/2026-09-20-ai-foundation-agent-usage-trends.md`,
`research/reports/2026-09-20-lg-own-ai-ux-status.md`,
`research/findings/competitor/ab180-claude-code-gtm-sales-automation-2026-09-20.md`,
`research/findings/own-company/`(비어 있음), `research/playbooks/palantir-fde-forward-deployed-engineering-2026-09-20.md`

## Follow-up verification needed

1. **경쟁사 보고서 — 수치·계약 규모 우선 검증** (→ `verifier`)
   - 삼성 SmartThings 사용자 수 공식 발표 불일치 ("4.3억" vs "5억")
   - 애플-Google Gemini 제휴 규모 (연 약 10억 달러, 미확정 표기)
   - 구글 Gemini for Home 구독가 ($10/$20)
   - Matter 카메라 지원 일정 (파트너사 출시일 vs Matter 1.5.1 릴리스일 혼동 여부)
   - 이유: 2027 사업계획에 직접 인용될 가능성이 높은 항목들.

2. **AI 트렌드 보고서 — 같은 기준(수치·통계 우선)** (→ `verifier`)
   - METR RCT: "AI 도구로 20% 빨라졌다고 느꼈지만 실제 19% 느려짐" (반직관적 — 인용 시 왜곡 위험 큼)
   - Gartner 전망: "2026년까지 기업 앱 40%가 작업 특화 AI 에이전트 통합"
   - Fortune500 MCP 구현률 28% (원 출처 자체가 "신뢰도 중간, 추정치"로 표시 — 재확인 필요)

3. **자사 현황 보고서 — 수치·타이밍 주장 우선** (→ `verifier`)
   - LG CLOiD 로드맵 (2026 테네시 세탁기 공장 실증 → 2027 가정용 PoC)
   - 이족보행 휴머노이드 2027년 1분기 공개 목표
   - AI로봇 특허출원 세계 1위(18.8%) — **2012~2021년 데이터, 2025~2026 갱신 순위 미확인** — 오래된 통계를 최신처럼 인용할 위험 명시적으로 플래그
   - EXAONE B2B 외부매출 (LG 공식 발표 아님, 증권가 추정치 수준)

## Follow-up research needed

1. **`own-company-research` 재실행** (→ `own-company-research`)
   - `research/findings/own-company/`가 현재 비어 있음 — 기존 자사 보고서는 있지만 이를 뒷받침하는
     독립 findings가 전혀 없는 상태.
   - 특히 특허 순위 최신화(2025~2026), 로봇 로드맵 최신 발표, ThinQ ON/Claw 출시 상태 업데이트,
     조직개편 관련 최신 자료를 우선 조사.

## Resolved / no action needed

- 경쟁사 리서치 대상(삼성전자·애플·구글·중국 가전 3사)은 2027 사업계획 관점에서 **충분하다고 확인** —
  추가 경쟁사 조사 불필요.
- 3개 보고서 모두 최종적으로 사용 예정, 우선순위는 경쟁사 → (AI 트렌드/자사, 동순위) 순.
