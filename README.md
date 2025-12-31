<div align="center">

<img src="https://img.shields.io/badge/AI_Agents-19+-blueviolet?style=for-the-badge" alt="19+ AI Agents" />
<img src="https://img.shields.io/badge/Zero_Drift-100%25-success?style=for-the-badge" alt="Zero Drift" />
<img src="https://img.shields.io/badge/Config_Files-1_Hub-orange?style=for-the-badge" alt="1 Hub" />

# 🤖 Universal Context Architecture

### Stop "Context Drift" in Multi-Agent AI Teams

<br />

[![Use this template](https://img.shields.io/badge/⚡_Use_this_template-238636?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yokharian/AIBoilerplate/generate)

<br />

*One source of truth for **Cursor, Claude Code, GitHub Copilot, Gemini, Amazon Q,** and **14+ AI coding assistants.***

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
<td align="center">➕<br/><b>14 more...</b></td>
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

You end up with **duplicated rules**, **conflicting instructions**, and AI assistants that **hallucinate different
project conventions**.

<br />

---

<br />

## 💡 The Solution

### Governor & Consumer Pattern

Instead of maintaining 19 different config files, use a **hub-and-spoke architecture**:

```
✨ After: Harmony
                         ┌─────────────────────┐
                         │     AGENTS.md       │
                         │     (The Hub)       │
                         │  Single Source of   │
                         │      Truth          │
                         └──────────┬──────────┘
                                    │
           ┌────────────┬───────────┼───────────┬────────────┐
           │            │           │           │            │
           ▼            ▼           ▼           ▼            ▼
     .cursorrules  CLAUDE.md   GEMINI.md   copilot.md    19 more...
        │            │           │           │            │
        └────────────┴───────────┴───────────┴────────────┘
                                 │
                      "Read AGENTS.md first"
```

Every vendor-specific config contains just **one instruction**:

> *"System: Read /AGENTS.md before doing anything."*

<br />

---

<br />

## 🗂️ Architecture

```
📁 Your Project
│
├── 🎯 AGENTS.md                      ← THE HUB: Entry point for all AI agents
│
├── 📂 .agents/
│   │
│   ├── 📚 skills/                ← KNOWLEDGE (Atomic, Reusable)
│   │   ├── create-prd/
│   │   │   └── SKILL.md             "Create Product Requirements Documents"
│   │   └── generate-tasks/
│   │       └── SKILL.md             "Generate task lists from PRDs"
│   │
│   └── 🎭 sub-agents/            ← PERSONAS (Specialized Roles)
│       ├── ultra-think.md           "Default for all SDLC tasks"
│       └── project-manager.md       "I am the Project Manager"
│
├── 📂 .specify/
│   │
│   ├── 📂 memory/               ← GOVERNANCE (The Law)
│   │   ├── constitution.md          Tech Stack & Rules
│   │   └── plan.md                  Current Tasks & Sprint
│   │
│   └── 📂 features/            ← FEATURE DOCUMENTATION
│       └── 📂 [feature-name]/
│           ├── prd.md               Product Requirements Document
│           └── tasks.md             Task list for implementation
│
└── 📂 [Pointer Files]            ← REDIRECTORS (Thin Wrappers)
    ├── .cursorrules                 → "Read AGENTS.md"
    ├── CLAUDE.md                    → "Read AGENTS.md"
    ├── GEMINI.md                    → "Read AGENTS.md"
    └── ... (19 total)               → "Read AGENTS.md"
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

[![Use this template](https://img.shields.io/badge/⚡_Use_this_template-238636?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yokharian/AIBoilerplate/generate)

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

The `project-manager` sub-agent automatically maintains `.specify/memory/plan.md` as you work through features. However, you can also manually edit it to set initial sprint goals:

```markdown
## Current Sprint: User Authentication

### In Progress
- [ ] Implement OAuth2 flow
- [ ] Add password reset

### Up Next
- [ ] Two-factor authentication
```

**Note:** When you create PRDs and generate tasks using the `project-manager` sub-agent, it will automatically update this plan file with progress, moving tasks between sections and updating metrics as work progresses.

</td>
</tr>
<tr>
<td>

### Step 4️⃣ &nbsp; Start Coding

Open your project in **any AI-powered IDE**. The AI will automatically:

1. 📖 Read the pointer file (`.cursorrules`, `CLAUDE.md`, etc.)
2. 🎯 Navigate to `AGENTS.md`
3. 📜 Load your constitution and plan
4. ✅ Follow your rules **consistently**

</td>
</tr>
</table>

<br />

---

<br />

## Feature Development Workflow

Build features step-by-step with AI: define requirements, plan tasks, and implement iteratively.

### Quick Guide

**1. Create a PRD** (Product Requirements Document)

```text
Use @.agents/sub-agents/project-manager.md
I want to build a feature: [Describe your feature]
```

The PRD is saved to `.specify/features/[feature-name]/prd.md`.

**2. Generate Tasks**

```text
Take @.specify/features/my-feature/prd.md and generate tasks using @.agents/skills/generate-tasks/SKILL.md
```

Tasks are saved to `.specify/features/[feature-name]/tasks.md`.

**3. Implement Tasks**

```text
Please start on task 1.1 from @.specify/features/my-feature/tasks.md
```

The AI will implement one task at a time. Review and approve each change before moving to the next task.

**4. Track Progress**

Tasks are automatically marked complete, and `.specify/memory/plan.md` updates automatically.

### Tips

- Be specific when describing features
- Use `project-manager` for planning, `ultra-think` (default) for coding
- Review each task before approving the next one

<br />

---

<br />

## 🔌 Supported AI Tools

<div align="center">

|      IDE / CLI       |            Config File            | Status |
|:--------------------:|:---------------------------------:|:------:|
|      **Cursor**      |          `.cursorrules`           |   ✅    |
|     **Windsurf**     |         `.windsurfrules`          |   ✅    |
| **Roo Code / Cline** |           `.clinerules`           |   ✅    |
|  **GitHub Copilot**  | `.github/copilot-instructions.md` |   ✅    |
|   **Claude Code**    |            `CLAUDE.md`            |   ✅    |
|    **Gemini CLI**    |            `GEMINI.md`            |   ✅    |
|     **Amazon Q**     |           `AMAZON_Q.md`           |   ✅    |
|    **Auggie CLI**    |           `.auggie.md`            |   ✅    |
|    **CodeBuddy**     |           `.codebuddy`            |   ✅    |
|      **Qoder**       |        `.qoder/context.md`        |   ✅    |
|     **OpenCode**     |            `.opencode`            |   ✅    |
|       **Amp**        |             `.amp.md`             |   ✅    |
|    **Kilo Code**     |              `.kilo`              |   ✅    |
|    **Qwen Code**     |              `.qwen`              |   ✅    |
|     **IBM Bob**      |           `.bob/config`           |   ✅    |
|      **Jules**       |             `.jules`              |   ✅    |
|       **SHAI**       |              `.shai`              |   ✅    |
|    **Codex CLI**     |            `CODEX.md`             |   ✅    |
|      **Goose**       |            `goosehints`             |   ✅    |

</div>

<br />

---

<br />

## 🧠 How It Works

<table>
<tr>
<th width="33%">📚 Skills</th>
<th width="33%">🎭 Sub-Agents</th>
<th width="33%">📜 Governance</th>
</tr>
<tr>
<td valign="top">

**Atomic knowledge modules**

Each skill is a reusable piece of domain knowledge.

```
create-prd/
├─ PRD structure
├─ Clarifying questions
└─ Requirements format

generate-tasks/
├─ Task breakdown
├─ Sub-task generation
└─ Progress tracking
```

</td>
<td valign="top">

**Specialized personas**

Sub-agents are experts that use specific skills.

```
ultra-think.md (default)
├─ Focus: SDLC tasks
├─ Coding, refactoring
├─ Architecture, debugging
└─ Testing, craftsmanship

project-manager.md
├─ Uses: create-prd
├─ Uses: generate-tasks
└─ Focus: Feature development
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

❌ 19 config files to maintain

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

> System: Read /AGENTS.md before doing anything.

---

## Instructions

Before performing any task, you MUST:

1. Read `AGENTS.md` — The central hub for all project context
2. Read `.specify/memory/constitution.md` — The rules and tech stack
3. Check `.specify/memory/plan.md` — Current tasks and priorities

---

*This file redirects [Tool Name] to the Universal Context Architecture.*
```

</details>

<details>
<summary><b>📚 Adding a New Skill</b></summary>

<br />

1. Create a directory in `.agents/skills/` (e.g., `my-skill/`)
2. Create a `SKILL.md` file inside the directory
3. Follow the format of existing skills (see `.agents/skills/create-prd/SKILL.md` for reference)
4. Include metadata, goal, process, and output format

**Example:**

```markdown
---
name: my-skill
description: Brief description of what this skill does
---

# My Skill

## Goal
To accomplish X...

## Process
1. Step one
2. Step two

## Output
- Format: Markdown
- Location: `/output/`
```

</details>

<details>
<summary><b>🎭 Adding a New Sub-Agent</b></summary>

<br />

1. Create a file in `.agents/sub-agents/`
2. Define the persona and role
3. List which skills it uses
4. Add specific instructions and workflow

**Example:**

```markdown
# Security Engineer Sub-Agent

> I am the Security Engineer. I review code for vulnerabilities.

## My Skills
- `.agents/skills/security-audit/SKILL.md`

## My Focus
- OWASP Top 10
- Input validation
- Authentication flows

## My Workflow
1. Review code for security issues
2. Generate security report
3. Recommend fixes
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

[![Use this template](https://img.shields.io/badge/⚡_Use_this_template-238636?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yokharian/AIBoilerplate/generate)

<br />

---

<sub>Inspired by Spec-Kit and the Governor & Consumer pattern</sub>

</div>
