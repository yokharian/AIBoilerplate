# PR Review Workflow

> Step 1: Fetch branch. Step 2: Review vs Checklist. Step 3: Approve.

---

## 📋 Overview

This workflow guides you through reviewing Pull Requests thoroughly and efficiently.

---

## Step 1: Fetch Branch 📥

### 1.1 Get the PR Locally

```bash
# Fetch the PR branch
git fetch origin pull/<PR-NUMBER>/head:pr-<PR-NUMBER>

# Or fetch by branch name
git fetch origin <branch-name>

# Checkout the branch
git checkout pr-<PR-NUMBER>
```

### 1.2 Get Latest Main

```bash
# Ensure you have latest main for comparison
git fetch origin main
```

### 1.3 Review PR Metadata

Check on GitHub/GitLab:
- [ ] Title is descriptive
- [ ] Description explains the change
- [ ] Linked to issue/ticket
- [ ] Appropriate labels applied
- [ ] CI checks are passing

---

## Step 2: Review vs Checklist 📋

Reference: `.agent/skills/review-checklist.md`

### 2.1 Understand the Context

Before looking at code:
- [ ] Read the linked ticket/issue
- [ ] Understand what problem is being solved
- [ ] Review the acceptance criteria
- [ ] Check the PR description

### 2.2 High-Level Review

Skim the changes first:

```bash
# See what files changed
git diff main..HEAD --stat

# See the actual diff
git diff main..HEAD
```

Ask yourself:
- [ ] Does the approach make sense?
- [ ] Is the scope appropriate?
- [ ] Are there any red flags?

### 2.3 Detailed Code Review

Go through each file systematically:

#### Code Quality
- [ ] Code is readable and well-structured
- [ ] No dead code or debugging artifacts
- [ ] DRY principle followed
- [ ] Error handling is appropriate

#### Architecture
- [ ] Follows existing patterns
- [ ] No unnecessary complexity
- [ ] Dependencies are justified

#### Security
Reference: `.specify/memory/constitution.md`
- [ ] No hardcoded secrets
- [ ] Inputs are validated
- [ ] Auth/authz checks in place

#### Testing
- [ ] Tests are included
- [ ] Tests cover the right scenarios
- [ ] Tests are meaningful (not just for coverage)

### 2.4 Run the Code Locally

```bash
# Install dependencies
npm install

# Run the application
npm run dev

# Run tests
npm test

# Test the specific feature/fix manually
```

### 2.5 Check for Common Issues

- [ ] No console.log statements
- [ ] No TODO comments without tickets
- [ ] No commented-out code
- [ ] Bundle size impact acceptable
- [ ] Database migrations are correct

---

## Step 3: Approve ✅

### 3.1 Document Your Findings

Organize feedback by severity:

#### 🔴 Blockers (Must Fix)
- Security vulnerabilities
- Breaking changes
- Major bugs
- Test failures

#### 🟡 Suggestions (Should Consider)
- Performance improvements
- Better approaches
- Code style issues

#### 🟢 Nitpicks (Optional)
- Minor style preferences
- Documentation improvements
- Nice-to-haves

### 3.2 Leave Constructive Comments

Good review comment:
```
This could cause a memory leak if the component unmounts 
before the async operation completes. Consider using a 
cleanup function in useEffect or an AbortController.

Example:
useEffect(() => {
  const controller = new AbortController();
  fetchData({ signal: controller.signal });
  return () => controller.abort();
}, []);
```

Bad review comment:
```
This is wrong.
```

### 3.3 Make Your Decision

| Decision | When |
|----------|------|
| **Approve** | No blockers, maybe minor suggestions |
| **Request Changes** | Has blockers that must be addressed |
| **Comment** | Questions or suggestions, no strong opinion |

### 3.4 Submit Review

- [ ] All feedback is constructive and clear
- [ ] Blocking issues are clearly marked
- [ ] Positive feedback included where appropriate
- [ ] Available for follow-up questions

---

## 📊 Workflow Diagram

```
┌───────────┐     ┌───────────┐     ┌───────────┐
│   FETCH   │────▶│  REVIEW   │────▶│  APPROVE  │
└───────────┘     └───────────┘     └───────────┘
      │                 │                 │
      ▼                 ▼                 ▼
  Get branch       Use checklist    Document findings
  Get main         Run locally      Leave comments
  Read PR info     Check security   Make decision
```

---

## ⏱️ Time Guidelines

| PR Size | Expected Time |
|---------|---------------|
| XS (< 50 lines) | 15-30 min |
| S (50-200 lines) | 30-60 min |
| M (200-500 lines) | 1-2 hours |
| L (> 500 lines) | Request split |

If a PR is too large, ask the author to split it.

---

## ✨ Review Best Practices

1. **Be timely** — Review within 24 hours
2. **Be thorough** — Don't rubber stamp
3. **Be kind** — Critique code, not people
4. **Be specific** — Give actionable feedback
5. **Be curious** — Ask questions if unsure
6. **Be learning** — Reviews are two-way learning

---

## 🚫 Anti-Patterns

- **Blocking on style** — Use automated formatters
- **Being pedantic** — Focus on what matters
- **Rubber stamping** — Actually review the code
- **Nitpicking only** — Look at the big picture
- **Delayed reviews** — Respond promptly

---

*A good review catches bugs and shares knowledge.*

