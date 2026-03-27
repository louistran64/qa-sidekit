# BetProphet QA Playbook

## Recurring Tasks

### Weekly Load Tests (Every Tuesday ~11:00 AM)
- Before Wednesday deployment
- Runner: `cd ~/Documents/GitHub/betprophet && python3 weekly_load_test_runner.py`
- 5 tests: exposure-stress, backend-fairness, backend-fairness --deducemode, parlay chaos, race-condition
- Generates HTML report automatically

### Deployment QA
- Smoke tests from `QA - Product Test Cases.xlsx` (~70 tests)
- Covers: Production Smoke, Sandbox Pre-Release, Release Smoke

## Test Suites

### API Tests (prophet-api-automation)
- Run: `cd ~/Documents/GitHub/betprophet/prophet-api-automation && npx playwright test`
- Shared helpers: `src/utils/common.ts` -- `tradeHeaders()`, `partnerHeaders()`, `estimateAndPlace()`, `getBalance()`

### Web E2E Tests (prophet-web-automation)
- Run: `cd ~/Documents/GitHub/betprophet/prophet-web-automation && npx playwright test`
- Page objects: `src/pages/`, fixtures: `src/fixtures/base.ts`

### Load Tests (qa-mm-autoplay, qa-parlay-autoplay)
- MM: race condition detection, exposure stress
- Parlay: chaos testing, concurrent order placement

## Bug Investigation Workflow
1. Reproduce via API (fastest feedback)
2. Check dev repo source code for root cause
3. Document in JIRA with evidence (screenshots, API responses)
4. Always use JIRA API v2 wiki markup with `!filename.png|thumbnail!` for inline images

## Settlement Testing
- Nova API-based settlement (no UI selectors needed)
- Flow: login -> send to queue -> get outcomes -> settle -> poll status
- Nova wallet utility: `qa-mm-autoplay/src/nova_wallet.py`
