# LiquidPay

Digital wallet platform -- P2P transfers, cross-border payments, merchant QR.

## Repo Map

Repos are scattered across multiple locations (all on Bitbucket `liquid-group`):

| Repo | Path | Type | Stack | Description |
|------|------|------|-------|-------------|
| `com.liquid.test.acceptance` | `/Users/tranlam/com.liquid.test.acceptance/` | QA (owned) | Jest TS + Maestro | Primary test repo |
| `liquidpay.tests` | `/Users/tranlam/liquidpay.tests/` | QA (owned) | C# .NET NUnit | Legacy test acceptance |
| `newman-liquidpay-automation` | `~/Documents/GitHub/newman-liquidpay-automation/` | QA (owned) | Newman/Postman | API collection tests |
| `maestro-automation` | `/Users/tranlam/Documents/maestro-automation/` | QA (owned) | Maestro YAML | Standalone mobile tests |
| `com.liquid.sandman` | `/Users/tranlam/com.liquid.sandman/` | Dev (ref) | Flutter/Dart | FE monorepo (app + SDK) |

## Environments

| Env | API Base URL | Client Key |
|-----|-------------|------------|
| Staging | `https://liquid-wallets-test.dev.liquidgroup.sg/api` | `FYyAUE5iBrN6KCdcc2xDPHcdsUIMDBEO` |

## Key Info

- Auth: AWS Cognito, mocked OTP `123123`
- Required headers: `X-Client-Key`, `WalletTenantId`, `X-Device-UDID`
- Login uses `username`/`password` fields (not `email`)
- Backend: ASP.NET Core (Sandman API), 172 endpoints total
- Mobile: Flutter app + SDK (AAR/XCFramework)

## Claude Memory

Run `cd ~/com.liquid.test.acceptance && claude` for deep work. Rich memory includes:
- Staging API credentials and auth patterns
- Known backend bugs (campaigns 500, vouchers 500, SmartFX issues)
- P2P corridor mapping (bank transfer vs UPI/DuitNow per wallet)
- Maestro test architecture (testlet pattern, suite runner)
- SDK testing status
- FE update plan and breaking changes
