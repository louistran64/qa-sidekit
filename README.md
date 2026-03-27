# Sidekit QA

Personal QA management hub for multi-company projects. Each company has its own directory with repo maps, QA playbooks, and procedures.

## Companies

| Company | Status | Repos | Claude Memory Path |
|---------|--------|-------|--------------------|
| [BetProphet](companies/betprophet/) | Active | `~/Documents/GitHub/betprophet/` | `-Users-tranlam-Documents-GitHub-betprophet` |
| [LiquidPay](companies/liquidpay/) | Active | Scattered (see README) | `-Users-tranlam-com-liquid-test-acceptance` |

## How It Works

- **This repo** = central registry, QA playbooks, shared methodology
- **Company repos** = stay at their original paths (no moves, no broken git)
- **Claude memory** = per-company, lives at each company's working directory path
- **Deep testing work** = `cd` into the company's actual repo, run `claude` there

## Adding a New Company

1. Copy `companies/_template/` to `companies/<name>/`
2. Fill in `README.md` with repo locations, environments, contacts
3. Fill in `qa-playbook.md` with test procedures
4. Set up CLAUDE.md in the company's primary repo
5. Run `claude` from that repo to start building memory

## Shared Resources

- [QA Methodology](shared/qa-methodology.md) -- core testing philosophy
- [Onboarding Checklist](shared/onboarding-checklist.md) -- new company setup steps
