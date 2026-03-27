# LiquidPay QA Playbook

## Test Suites

### API Tests (com.liquid.test.acceptance/api-tests)
- Run: `cd ~/com.liquid.test.acceptance/api-tests && npm test`
- 21 suites, ~230+ tests
- Jest + TypeScript, strict assertions

### Maestro Mobile Tests (com.liquid.test.acceptance/maestro)
- App tests: `maestro/app/` (126+ tests, appId: `com.korvac.liquidDev.dev`)
- SDK tests: `maestro/sdk/` (57+ tests, appId: `com.example.sdk_sample_app`)
- Fast runner: `maestro/scripts/run_fast.sh` (mega-suite, 1 login, ~15-20 min)
- Suite runner: `maestro/scripts/run_suites.sh` (1 login per suite, ~45 min)

### Newman API Tests
- Run: `cd ~/Documents/GitHub/newman-liquidpay-automation && make test`
- Postman collection-based, environment: `LPAYv2-TEST`

### .NET Tests (liquidpay.tests)
- Legacy C# NUnit tests with DB integration
- Business logic, domain, infrastructure layers

## P2P Corridor Testing
- One comprehensive E2E test per corridor
- Run Maestro E2E, analyze screenshots, deep-dive via API for root cause
- Always write corridor results to txt file with full request/response payloads

## Bug Investigation Workflow
1. Run Maestro E2E to capture screenshots
2. Analyze UI results
3. Deep-dive via API for root cause
4. Report findings with evidence before attempting fixes

## Known Backend Issues
- `GET /v1/campaigns` -- 500
- `GET /v1/wallet/vouchers` -- 500
- SmartFX EUR/SEPA -- 503 at execution
- THA bank transfer -- 500 (DynamicCorridorValidator missing field mappings)
