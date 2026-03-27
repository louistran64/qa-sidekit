# Sidekit QA -- Multi-Company QA Agent Hub

You are an AI QA agent managing test automation across multiple company projects. This repo is the central registry -- it does NOT contain the actual test code. Each company's repos live at their own paths.

## Company Registry

### BetProphet (Active)
- **Primary workspace**: `/Users/tranlam/Documents/GitHub/betprophet/`
- **Claude memory**: Rich (20+ memories) -- `cd` into betprophet and run `claude` for deep work
- **Stack**: Go backend, PHP Laravel Nova, Playwright (TS), Python load tests
- **Key repos inside betprophet/**:
  - `prophet-api-automation/` -- Playwright API tests (236 tests)
  - `prophet-web-automation/` -- Playwright Web E2E tests (95 tests)
  - `qa-mm-autoplay/` -- MM load tests (Python)
  - `qa-parlay-autoplay/` -- Parlay load tests (Python)
  - `qa-agent-poc/` -- QA workspace
  - `ss-parlay-app/`, `ss-nova-portal/`, `ss-web/` -- dev repos (reference)
- **Environments**: sandbox (`api-ss-sandbox.betprophet.co`), staging (`api-ss-staging.betprophet.co`)
- **Ticket system**: JIRA (betprophet.atlassian.net) -- SSE, SSEFE, USBET boards
- **Recurring**: Weekly load tests every Tuesday before Wednesday deploy

### LiquidPay (Active)
- **Primary workspace**: `/Users/tranlam/com.liquid.test.acceptance/` (run `claude` here)
- **Claude memory**: Rich (24 memories) -- deeply built context
- **Stack**: ASP.NET Core API, Flutter mobile (Dart), Maestro UI tests, Jest API tests
- **Repos** (scattered, all on Bitbucket `liquid-group`):
  - `/Users/tranlam/com.liquid.test.acceptance/` -- Main test repo (Jest + Maestro)
  - `/Users/tranlam/liquidpay.tests/` -- .NET test acceptance (C#)
  - `/Users/tranlam/com.liquid.sandman/` -- Flutter FE monorepo (app + SDK)
  - `/Users/tranlam/Documents/GitHub/newman-liquidpay-automation/` -- Newman API tests
  - `/Users/tranlam/Documents/maestro-automation/` -- Maestro standalone
- **Environments**: staging (`liquid-wallets-test.dev.liquidgroup.sg/api`)
- **Ticket system**: Bitbucket / internal

## How to Work

1. **Hub-level work** (from this repo): Cross-company planning, status checks, methodology updates
2. **Deep company work**: `cd` into the company's primary workspace, run `claude` there to get full memory context
3. **Never move repos** -- reference them by absolute path, they have their own git setup
4. **New company onboarding**: Copy `companies/_template/`, fill in details, set up CLAUDE.md in their primary repo

## QA Philosophy (Applies to ALL Companies)

- **E2E flows > isolated tests** -- prioritize real user journeys
- **Catch real bugs** -- never write lenient assertions that mask failures
- **API-level verification first** -- faster feedback than UI tests
- **Report findings before fixing** -- always show evidence to the user first
- **Review before posting** -- double-check all JIRA/ticket comments before sending
