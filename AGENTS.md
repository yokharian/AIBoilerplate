# AGENTS.md — The Hub

> I am the entry point. Read Constitution, then choose a Sub-Agent.

## Quick Start

1. **Read the Constitution** → `.specify/memory/constitution.md`
2. **Check the Current Plan** → `.specify/memory/plan.md`
3. **Choose a Sub-Agent** based on your task

---

## Navigation

### 📜 Governance (The Law)

| File | Purpose |
|------|---------|
| `.specify/memory/constitution.md` | Tech Stack, Rules, and Constraints. **Never ignore me.** |
| `.specify/memory/plan.md` | The current Task List. What we are doing right now. |

---

### 🤖 Sub-Agents (Personas)

Choose the right agent for your task:

| Agent | File | Specialty |
|-------|------|-----------|
| QA Engineer | `.agent/sub-agents/qa.md` | Testing, bug fixes, quality assurance |
| DevOps Engineer | `.agent/sub-agents/devops.md` | Deployment, CI/CD, infrastructure |
| Tech Lead | `.agent/sub-agents/tech-lead.md` | PR reviews, architecture decisions |

---

### 🔄 Workflows (Processes)

| Workflow | File | Steps |
|----------|------|-------|
| Feature Development | `.agent/workflows/feature-dev.md` | Plan → Code → Test |
| Bug Fix | `.agent/workflows/bug-fix.md` | Reproduce → Fix → Verify |
| Deploy | `.agent/workflows/deploy.md` | Lint → Build → Ship |
| PR Review | `.agent/workflows/pr-review.md` | Fetch → Review → Approve |

---

### 🛠️ Skills (Atomic Knowledge)

| Skill | File | Description |
|-------|------|-------------|
| Git | `.agent/skills/git.md` | Standard Git commands and conventions |
| Database | `.agent/skills/db.md` | SQL queries and migrations |
| Testing | `.agent/skills/test.md` | Jest, Playwright, and testing patterns |
| Review Checklist | `.agent/skills/review-checklist.md` | PR review checklist |

---

## Golden Rules

1. **Always read `constitution.md` first** — it defines what you can and cannot do
2. **Check `plan.md`** — understand the current context before acting
3. **Follow the workflow** — don't skip steps
4. **Use skills as reference** — they contain battle-tested patterns
5. **Stay in your lane** — each sub-agent has a specific role

---

## Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                     AGENTS.md (HUB)                         │
│                    "The Entry Point"                        │
└─────────────────────────────────────────────────────────────┘
                              │
          ┌───────────────────┼───────────────────┐
          ▼                   ▼                   ▼
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│   GOVERNANCE    │ │   SUB-AGENTS    │ │     SKILLS      │
│  constitution   │ │   qa.md         │ │   git.md        │
│  plan.md        │ │   devops.md     │ │   db.md         │
│                 │ │   tech-lead.md  │ │   test.md       │
└─────────────────┘ └─────────────────┘ └─────────────────┘
                              │
                              ▼
                    ┌─────────────────┐
                    │    WORKFLOWS    │
                    │  feature-dev    │
                    │  bug-fix        │
                    │  deploy         │
                    │  pr-review      │
                    └─────────────────┘
```
