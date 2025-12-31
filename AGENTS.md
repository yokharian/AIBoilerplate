# AGENTS.md — The Hub

> I am the entry point. Read Constitution, then choose a Sub-Agent.

## Quick Start

1. **Read the Constitution** → `.specify/memory/constitution.md`
2. **Check the Current Plan** → `.specify/memory/plan.md`
3. **Choose a Sub-Agent** based on your task

---

## Navigation

### 📜 Governance (The Law)

| File                              | Purpose                                                  |
|-----------------------------------|----------------------------------------------------------|
| `.specify/memory/constitution.md` | Tech Stack, Rules, and Constraints. **Never ignore me.** |
| `.specify/memory/plan.md`         | The current Task List. What we are doing right now.      |

---

### 🤖 Sub-Agents (Personas)

Choose the right agent for your task:

| Agent                     | File                                    | Specialty                                                                                                                              |
|---------------------------|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Ultra-Think** (Default) | `.agents/sub-agents/ultra-think.md`     | **Default for all SDLC tasks**: Coding, refactoring, architecture, debugging, testing. Emphasizes craftsmanship and elegant solutions. |
| Project Manager           | `.agents/sub-agents/project-manager.md` | PRD creation, task generation, progress tracking                                                                                       |

---

### 🛠️ Skills (Atomic Knowledge)

| Skill          | File                                     | Description                                |
|----------------|------------------------------------------|--------------------------------------------|
| Create PRD     | `.agents/skills/create-prd/SKILL.md`     | Create Product Requirements Documents      |
| Generate Tasks | `.agents/skills/generate-tasks/SKILL.md` | Generate step-by-step task lists from PRDs |

---

## Golden Rules

1. **Always read `constitution.md` first** — it defines what you can and cannot do
2. **Check `plan.md`** — understand the current context before acting
3. **Use skills as reference** — they contain battle-tested patterns
4. **Stay in your lane** — each sub-agent has a specific role
5. **Default to Ultra-Think** — For any SDLC task (coding, refactoring, architecture, debugging, testing), use the
   Ultra-Think sub-agent unless a more specialized agent is explicitly needed

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
│  constitution   │ │  ultra-think    │ │   create-prd    │
│     plan.md     │ │ project-manager │ │ generate-tasks  │
└─────────────────┘ └─────────────────┘ └─────────────────┘
```
