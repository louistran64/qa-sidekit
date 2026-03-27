# BetProphet

Sports betting platform -- B2B SaaS for sportsbook operators.

## Repo Map

All repos live inside `/Users/tranlam/Documents/GitHub/betprophet/`:

| Repo | Type | Stack | Description |
|------|------|-------|-------------|
| `prophet-api-automation/` | QA (owned) | Playwright TS | 236 API tests, 20 files |
| `prophet-web-automation/` | QA (owned) | Playwright TS | 95 Web E2E tests, 21 files |
| `qa-mm-autoplay/` | QA (owned) | Python | MM load tests, race conditions |
| `qa-parlay-autoplay/` | QA (owned) | Python | Parlay load tests, chaos |
| `qa-agent-poc/` | QA (owned) | Mixed | QA workspace, scripts, evidence |
| `ss-parlay-app/` | Dev (ref) | Go | Parlay backend, order flow |
| `ss-nova-portal/` | Dev (ref) | PHP Laravel Nova | Admin portal (ops UI) |
| `ss-web/` | Dev (ref) | Web | Consumer-facing web app |
| `ss-wallet-app/` | Dev (ref) | - | Wallet service |
| `ss-trade-app/` | Dev (ref) | - | Trade service |
| `ss-auth-app/` | Dev (ref) | - | Auth service |
| `ss-mobile/` | Dev (ref) | - | Mobile app |
| `isv-embed-fe/` | Dev (ref) | - | ISV embed frontend |

## Environments

| Env | API Base URL | Nova URL |
|-----|-------------|----------|
| Sandbox | `https://api-ss-sandbox.betprophet.co` | `http://nova-ss-sandbox.betprophet.io` (Tailscale) |
| Staging | `https://api-ss-staging.betprophet.co` | - |

## Key Contacts

- Dev team: Danh Nguyen (parlay), Sanford Leach (FE/auth)
- Ticket system: JIRA `betprophet.atlassian.net` (SSE, SSEFE, USBET boards)

## Claude Memory

Run `cd ~/Documents/GitHub/betprophet && claude` for deep work. Rich memory includes:
- SBX/staging test credentials
- JIRA API access patterns
- Nova settlement via API (no UI needed)
- Weekly load test procedures
- Active ticket tracking (FN-324, SSEFE-2482 epic)
