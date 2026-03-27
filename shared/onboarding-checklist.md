# New Company Onboarding Checklist

Steps to add a new company to the Sidekit QA hub.

## 1. Create Company Directory

```bash
cp -r companies/_template companies/<company-name>
```

## 2. Fill In README.md

- [ ] Company description
- [ ] All repo paths (absolute paths on this Mac)
- [ ] Git remotes (GitHub/Bitbucket/GitLab)
- [ ] Environment URLs (staging, sandbox, production)
- [ ] Key contacts (dev lead, PM)
- [ ] Ticket system (JIRA, Linear, Bitbucket Issues)

## 3. Fill In qa-playbook.md

- [ ] Recurring test schedules
- [ ] Test suite inventory with run commands
- [ ] Bug investigation workflow
- [ ] Known issues

## 4. Set Up CLAUDE.md in Primary Repo

Create a `CLAUDE.md` at the root of the company's primary test repo:
- [ ] Project overview
- [ ] On-session-start instructions (pull repos, etc.)
- [ ] Test architecture
- [ ] Assertion rules
- [ ] Credentials reference (or pointer to secure storage)

## 5. Initialize Claude Memory

- [ ] `cd /path/to/primary/repo && claude`
- [ ] Have a session where you explore the codebase
- [ ] Let Claude build up memory naturally through your work

## 6. Update Sidekit QA Registry

- [ ] Add company row to `README.md` companies table
- [ ] Add company section to `CLAUDE.md` company registry
- [ ] Commit and push
