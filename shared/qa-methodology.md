# Sidekit QA Methodology

Core testing philosophy applied across all companies.

## Principles

1. **E2E flows over isolated tests** -- prioritize real user journeys that chain multiple endpoints/screens
2. **Catch real bugs** -- strict assertions, never mask failures with lenient checks
3. **API-first verification** -- faster feedback loop than UI tests; use UI tests for visual/flow validation
4. **Report before fix** -- always show evidence (screenshots, API responses) to stakeholders before attempting fixes
5. **Review before posting** -- double-check all external communications (JIRA, Slack, tickets)

## Test Pyramid (Per Company)

```
         /  UI E2E  \          Maestro / Playwright browser
        / API E2E    \         Playwright API / Jest / Newman
       / Integration   \       DB + service integration
      /  Unit (dev owns) \     Dev team responsibility
```

QA owns the top two layers. Dev owns the bottom two.

## Standard QA Agent Behaviors

These apply to Claude agents across ALL company projects:

- **On session start**: Pull latest code for all relevant repos
- **Bug identification**: If a test completes the flow but the app shows an error, that IS a real bug
- **Grouped assertions**: Default to suite tests with soft+hard checkpoint pattern
- **Strict UI match**: API tests must match actual UI flows, not test arbitrary API paths
- **Speed priority**: Minimize login overhead, use mega-suite patterns where possible
- **No over-engineering**: Don't add proxy layers, abstractions, or "improvements" beyond what's asked

## Evidence Standards

- Screenshots with annotations for UI bugs
- Full request/response payloads for API bugs
- Reproduction steps that anyone can follow
- Environment + timestamp on all evidence
