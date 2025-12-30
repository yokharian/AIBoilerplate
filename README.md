<div align="center">

<img src="https://img.shields.io/badge/AI_Agents-19+-blueviolet?style=for-the-badge" alt="19+ AI Agents" />
<img src="https://img.shields.io/badge/Zero_Drift-100%25-success?style=for-the-badge" alt="Zero Drift" />
<img src="https://img.shields.io/badge/Config_Files-1_Hub-orange?style=for-the-badge" alt="1 Hub" />

# 🤖 Universal Context Architecture

### Stop "Context Drift" in Multi-Agent AI Teams

<br />

[![Use this template](https://img.shields.io/badge/⚡_Use_this_template-238636?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yokharian/AIBoilerplate/generate)

<br />

*One source of truth for **Cursor, Claude Code, GitHub Copilot, Gemini, Amazon Q,** and **16+ AI coding assistants.***

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
│       └── project-manager.md       "I am the Project Manager"
│
├── 📂 .specify/memory/           ← GOVERNANCE (The Law)
│   ├── constitution.md              Tech Stack & Rules
│   └── plan.md                      Current Tasks & Sprint
│
├── 📂 tasks/                      ← OUTPUT (Generated Documents)
│   ├── prd-[feature-name].md        PRD documents
│   └── tasks-[feature-name].md       Task lists
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
2. 🎯 Navigate to `AGENTS.md`
3. 📜 Load your constitution and plan
4. ✅ Follow your rules **consistently**

</td>
</tr>
</table>

<br />

---

<br />

## 🚀 Feature Development Workflow

This repository provides a structured workflow for building features with AI assistance, from ideation to implementation.

<details>
<summary><b>💡 The Core Idea</b></summary>

Building complex features with AI can sometimes feel like a black box. This workflow aims to bring structure, clarity, and control to the process by:

1. **Defining Scope:** Clearly outlining what needs to be built with a Product Requirement Document (PRD).
2. **Detailed Planning:** Breaking down the PRD into a granular, actionable task list.
3. **Iterative Implementation:** Guiding the AI to tackle one task at a time, allowing you to review and approve each change.

This structured approach helps ensure the AI stays on track, makes it easier to debug issues, and gives you confidence in the generated code.

</details>

<details>
<summary><b>📋 Workflow: From Idea to Implemented Feature</b></summary>

Here's the step-by-step process using the skills in this repository:

#### 1. Create a Product Requirement Document (PRD)

First, lay out the blueprint for your feature. A PRD clarifies what you're building, for whom, and why.

You can create a lightweight PRD directly within your AI tool of choice:

1. Ensure you have the `create-prd` skill accessible (`.agents/skills/create-prd/SKILL.md`).
2. In your AI tool, initiate PRD creation:

    ```text
    Use @.agents/skills/create-prd/SKILL.md
    Here's the feature I want to build: [Describe your feature in detail]
    Reference these files to help you: [Optional: @file1.py @file2.ts]
    ```

#### 2. Generate Your Task List from the PRD

With your PRD drafted (e.g., `prd-MyFeature.md`), the next step is to generate a detailed, step-by-step implementation plan for your AI Developer.

1. Ensure you have `generate-tasks` skill accessible (`.agents/skills/generate-tasks/SKILL.md`).
2. In your AI tool, use the PRD to create tasks:

    ```text
    Now take @prd-MyFeature.md and create tasks using @.agents/skills/generate-tasks/SKILL.md
    ```

#### 3. Examine Your Task List

You'll now have a well-structured task list, often with tasks and sub-tasks, ready for the AI to start working on. This provides a clear roadmap for implementation.

#### 4. Instruct the AI to Work Through Tasks (and Mark Completion)

To ensure methodical progress and allow for verification, instruct the AI to work through the task list one sub-task at a time.

1. In your AI tool, tell the AI to start with the first task (e.g., `1.1`):

    ```text
    Please start on task 1.1 from the generated task list.
    ```

    The AI will attempt the task and then prompt you to review.

#### 5. Progress

The AI will continue working through the remaining tasks in the list, checking them off as completed (`- [ ]` → `- [x]`).

While it's not always perfect, this method has proven to be a very reliable way to build out larger features with AI assistance.

</details>

<details>
<summary><b>✨ Benefits</b></summary>

* **Structured Development:** Enforces a clear process from idea to code.
* **Step-by-Step Verification:** Allows you to review and approve AI-generated code at each small step, ensuring quality and control.
* **Manages Complexity:** Breaks down large features into smaller, digestible tasks for the AI, reducing the chance of it getting lost or generating overly complex, incorrect code.
* **Improved Reliability:** Offers a more dependable approach to leveraging AI for significant development work compared to single, large prompts.
* **Clear Progress Tracking:** Provides a visual representation of completed tasks, making it easy to see how much has been done and what's next.

</details>

<details>
<summary><b>💪 Tips for Success</b></summary>

* **Be Specific:** The more context and clear instructions you provide (both in your initial feature description and any clarifications), the better the AI's output will be.
* **Correct File Tagging:** Always ensure you're accurately tagging the PRD filename (e.g., `@prd-MyFeature.md`) when generating tasks.
* **Patience and Iteration:** AI is a powerful tool, but it's not magic. Be prepared to guide, correct, and iterate. This workflow is designed to make that iteration process smoother.

</details>

<details>
<summary><b>📁 Files in this Repository</b></summary>

* **`.agents/skills/create-prd/SKILL.md`**: Guides the AI in generating a Product Requirement Document for your feature.
* **`.agents/skills/generate-tasks/SKILL.md`**: Takes a PRD markdown file as input and helps the AI break it down into a detailed, step-by-step implementation task list.
* **`.agents/sub-agents/project-manager.md`**: The Project Manager sub-agent that orchestrates the PRD and task generation workflow.
* **`AGENTS.md`**: The central hub that routes AI assistants to the appropriate sub-agents and skills.
* **`.specify/memory/constitution.md`**: Defines your tech stack, coding standards, and project rules.
* **`.specify/memory/plan.md`**: Tracks current tasks, sprint goals, and progress.

</details>

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
|      **Goose**       |            `GOOSE.md`             |   ✅    |

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
