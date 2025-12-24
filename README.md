<div align="center">

<img src="https://img.shields.io/badge/AI_Agents-18+-blueviolet?style=for-the-badge" alt="18+ AI Agents" />
<img src="https://img.shields.io/badge/Zero_Drift-100%25-success?style=for-the-badge" alt="Zero Drift" />
<img src="https://img.shields.io/badge/Config_Files-1_Hub-orange?style=for-the-badge" alt="1 Hub" />

# 🤖 Universal Context Architecture

### Stop "Context Drift" in Multi-Agent AI Teams

<br />

[![Use this template](https://img.shields.io/badge/⚡_Use_this_template-238636?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AhmedCalworker/Universal-Context-Architecture/generate)

<br />

*One source of truth for **Cursor, Claude Code, GitHub Copilot, Gemini, Amazon Q,** and **15+ AI coding assistants.***

<br />

[Quick Start](#-quick-start) · [How It Works](#-how-it-works) · [Supported Tools](#-supported-ai-tools) · [Customize](#%EF%B8%8F-customization)

</div>

<br />

---

<br />

## 🤔 The Problem

We're in the era of **Multi-Vendor AI Development**. Your team might be using:

<table>
<tr>
<td align="center">🖱️<br/><b>Cursor</b></td>
<td align="center">🤖<br/><b>Claude Code</b></td>
<td align="center">🐙<br/><b>GitHub Copilot</b></td>
<td align="center">💎<br/><b>Gemini CLI</b></td>
<td align="center">☁️<br/><b>Amazon Q</b></td>
<td align="center">➕<br/><b>13 more...</b></td>
</tr>
</table>

<br />

**The catch?** Every tool has its own config file. They all drift apart over time.

```
😵 Before: Chaos
┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐
│ .cursorrules│  │  CLAUDE.md  │  │  GEMINI.md  │  │ copilot.md  │
│   v1.2      │  │   v1.5      │  │   v1.0      │  │   v1.3      │
│  (outdated) │  │  (current)  │  │  (wrong)    │  │  (missing)  │
└─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘
      ↓                ↓                ↓                ↓
   Different        Different        Different        Different
   conventions      conventions      conventions      conventions
```

You end up with **duplicated rules**, **conflicting instructions**, and AI assistants that **hallucinate different project conventions**.

<br />

---

<br />

## 💡 The Solution

### Governor & Consumer Pattern

Instead of maintaining 18 different config files, use a **hub-and-spoke architecture**:

```
✨ After: Harmony
                         ┌─────────────────────┐
                         │       AI.md         │
                         │    (The Hub)        │
                         │  Single Source of   │
                         │      Truth          │
                         └──────────┬──────────┘
                                    │
           ┌────────────┬───────────┼───────────┬────────────┐
           │            │           │           │            │
           ▼            ▼           ▼           ▼            ▼
     .cursorrules  CLAUDE.md   GEMINI.md   copilot.md    18 more...
        │            │           │           │            │
        └────────────┴───────────┴───────────┴────────────┘
                                 │
                      "Read AI.md first"
```

Every vendor-specific config contains just **one instruction**:

> *"System: Read /AI.md before doing anything."*

<br />

---

<br />

## 🗂️ Architecture

```
📁 Your Project
│
├── 🎯 AI.md                      ← THE HUB: Entry point for all AI agents
│
├── 📂 .agent/
│   │
│   ├── 📚 skills/                ← KNOWLEDGE (Atomic, Reusable)
│   │   ├── git.md                   "Here are our Git commands"
│   │   ├── db.md                    "Here's how to run migrations"
│   │   ├── test.md                  "Here's how to run tests"
│   │   └── review-checklist.md      "Here's the PR checklist"
│   │
│   ├── 🔄 workflows/             ← PROCESSES (Step-by-step)
│   │   ├── feature-dev.md           Plan → Code → Test
│   │   ├── bug-fix.md               Reproduce → Fix → Verify
│   │   ├── deploy.md                Lint → Build → Ship
│   │   └── pr-review.md             Fetch → Review → Approve
│   │
│   └── 🎭 sub-agents/            ← PERSONAS (Specialized Roles)
│       ├── qa.md                    "I am the QA Engineer"
│       ├── devops.md                "I am the DevOps Engineer"
│       └── tech-lead.md             "I am the Tech Lead"
│
├── 📂 .specify/memory/           ← GOVERNANCE (The Law)
│   ├── constitution.md              Tech Stack & Rules
│   └── plan.md                      Current Tasks & Sprint
│
└── 📂 [Pointer Files]            ← REDIRECTORS (Thin Wrappers)
    ├── .cursorrules                 → "Read AI.md"
    ├── CLAUDE.md                    → "Read AI.md"
    ├── GEMINI.md                    → "Read AI.md"
    └── ... (18 total)               → "Read AI.md"
```

<br />

---

<br />

## 🚀 Quick Start

<table>
<tr>
<td>

### Step 1️⃣ &nbsp; Use This Template

Click the button below to create your own copy:

[![Use this template](https://img.shields.io/badge/⚡_Use_this_template-238636?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AhmedCalworker/Universal-Context-Architecture/generate)

</td>
</tr>
<tr>
<td>

### Step 2️⃣ &nbsp; Define Your Constitution

Edit `.specify/memory/constitution.md`:

```yaml
# Your Tech Stack
Frontend: React 18 + TypeScript + Tailwind
Backend:  Node.js + Express + Prisma
Database: PostgreSQL
Cloud:    AWS

# Your Rules
- TypeScript everywhere, no `any`
- All functions must be documented
- Tests required for new features
```

</td>
</tr>
<tr>
<td>

### Step 3️⃣ &nbsp; Set Your Plan

Edit `.specify/memory/plan.md`:

```markdown
## Current Sprint: User Authentication

### In Progress
- [ ] Implement OAuth2 flow
- [ ] Add password reset

### Up Next
- [ ] Two-factor authentication
```

</td>
</tr>
<tr>
<td>

### Step 4️⃣ &nbsp; Start Coding

Open your project in **any AI-powered IDE**. The AI will automatically:

1. 📖 Read the pointer file (`.cursorrules`, `CLAUDE.md`, etc.)
2. 🎯 Navigate to `AI.md`
3. 📜 Load your constitution and plan
4. ✅ Follow your rules **consistently**

</td>
</tr>
</table>

<br />

---

<br />

## 🔌 Supported AI Tools

<div align="center">

| IDE / CLI | Config File | Status |
|:---------:|:-----------:|:------:|
| **Cursor** | `.cursorrules` | ✅ |
| **Windsurf** | `.windsurfrules` | ✅ |
| **Roo Code / Cline** | `.clinerules` | ✅ |
| **GitHub Copilot** | `.github/copilot-instructions.md` | ✅ |
| **Claude Code** | `CLAUDE.md` | ✅ |
| **Gemini CLI** | `GEMINI.md` | ✅ |
| **Amazon Q** | `AMAZON_Q.md` | ✅ |
| **Auggie CLI** | `.auggie.md` | ✅ |
| **CodeBuddy** | `.codebuddy` | ✅ |
| **Qoder** | `.qoder/context.md` | ✅ |
| **OpenCode** | `.opencode` | ✅ |
| **Amp** | `.amp.md` | ✅ |
| **Kilo Code** | `.kilo` | ✅ |
| **Qwen Code** | `.qwen` | ✅ |
| **IBM Bob** | `.bob/config` | ✅ |
| **Jules** | `.jules` | ✅ |
| **SHAI** | `.shai` | ✅ |
| **Codex CLI** | `CODEX.md` | ✅ |

</div>

<br />

---

<br />

## 🧠 How It Works

<table>
<tr>
<th width="25%">📚 Skills</th>
<th width="25%">🔄 Workflows</th>
<th width="25%">🎭 Sub-Agents</th>
<th width="25%">📜 Governance</th>
</tr>
<tr>
<td valign="top">

**Atomic knowledge modules**

Each skill is a reusable piece of domain knowledge.

```
git.md
├─ Branch naming
├─ Commit format
└─ PR process
```

</td>
<td valign="top">

**Step-by-step processes**

Workflows chain skills into complete procedures.

```
feature-dev.md
├─ Step 1: Plan
├─ Step 2: Code
└─ Step 3: Test ↗️
         └── test.md
```

</td>
<td valign="top">

**Specialized personas**

Sub-agents are experts that use specific skills & workflows.

```
qa.md
├─ Uses: test.md
├─ Uses: bug-fix.md
└─ Focus: Quality
```

</td>
<td valign="top">

**The source of truth**

Constitution = the law
Plan = current state

```
memory/
├─ constitution.md
│  └─ "Never ignore me"
└─ plan.md
   └─ "Here's what we're doing"
```

</td>
</tr>
</table>

<br />

---

<br />

## ✨ Before vs After

<table>
<tr>
<th>😵 Before</th>
<th>✨ After</th>
</tr>
<tr>
<td>

❌ 18 config files to maintain

❌ Rules drift between tools

❌ Duplicated documentation

❌ AI invents conventions

❌ Context gets lost mid-task

❌ Team members get different AI behavior

</td>
<td>

✅ 1 hub file + thin pointers

✅ Consistent rules everywhere

✅ Single source of truth

✅ AI follows YOUR conventions

✅ Context is preserved

✅ Same AI behavior for everyone

</td>
</tr>
</table>

<br />

---

<br />

## 🛠️ Customization

<details>
<summary><b>➕ Adding a New AI Tool</b></summary>

<br />

Create a new pointer file for any AI tool:

```markdown
# [Tool Name] Configuration

> System: Read /AI.md before doing anything.

---

## Instructions

Before performing any task, you MUST:

1. Read `AI.md` — The central hub for all project context
2. Read `.specify/memory/constitution.md` — The rules and tech stack
3. Check `.specify/memory/plan.md` — Current tasks and priorities

---

*This file redirects [Tool Name] to the Universal Context Architecture.*
```

</details>

<details>
<summary><b>📚 Adding a New Skill</b></summary>

<br />

1. Create a file in `.agent/skills/`
2. Start with a tagline: `> Here is how to [do X].`
3. Add commands, conventions, examples
4. Reference it from relevant workflows

**Example:**

```markdown
# Docker Skill

> Here is how to build and run containers.

## Commands

\`\`\`bash
docker build -t myapp .
docker run -p 3000:3000 myapp
\`\`\`
```

</details>

<details>
<summary><b>🔄 Adding a New Workflow</b></summary>

<br />

1. Create a file in `.agent/workflows/`
2. Define numbered steps
3. Reference skills with links
4. Keep it action-oriented

**Example:**

```markdown
# Hotfix Workflow

> Step 1: Branch. Step 2: Fix. Step 3: Deploy.

## Step 1: Create Hotfix Branch

Reference: `.agent/skills/git.md`

\`\`\`bash
git checkout -b hotfix/critical-issue main
\`\`\`

## Step 2: Apply Fix
...
```

</details>

<details>
<summary><b>🎭 Adding a New Sub-Agent</b></summary>

<br />

1. Create a file in `.agent/sub-agents/`
2. Define the persona and role
3. List which skills and workflows it uses
4. Add specific instructions

**Example:**

```markdown
# Security Engineer Sub-Agent

> I am the Security Engineer. I review code for vulnerabilities.

## My Skills
- `.agent/skills/review-checklist.md`

## My Focus
- OWASP Top 10
- Input validation
- Authentication flows
```

</details>

<br />

---

<br />

<div align="center">

## 🌟 Star History

If this helps your team, consider giving it a ⭐

<br />

**Built with ❤️ for the Multi-Agent AI Era**

*Stop context drift. Start shipping.*

<br />

[![Use this template](https://img.shields.io/badge/⚡_Use_this_template-238636?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AhmedCalworker/Universal-Context-Architecture/generate)

<br />

---

<sub>Inspired by Spec-Kit and the Governor & Consumer pattern</sub>

</div>
