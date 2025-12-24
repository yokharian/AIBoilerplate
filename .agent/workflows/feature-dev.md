# Feature Development Workflow

> Step 1: Plan. Step 2: Code. Step 3: Test (using test.md).

---

## 📋 Overview

This workflow guides you through developing a new feature from start to finish.

---

## Step 1: Plan 📝

### 1.1 Understand the Requirements

- [ ] Read the ticket/issue completely
- [ ] Identify acceptance criteria
- [ ] Note any edge cases mentioned
- [ ] Ask clarifying questions if needed

### 1.2 Check the Constitution

```
Read: .specify/memory/constitution.md
```

Ensure the planned implementation:
- Uses approved tech stack
- Follows coding standards
- Doesn't violate any rules

### 1.3 Design the Solution

- [ ] Identify affected files/components
- [ ] Plan the data model changes (if any)
- [ ] Sketch component hierarchy (if UI)
- [ ] Consider API contract (if backend)

### 1.4 Update the Plan

```
Update: .specify/memory/plan.md
```

Add your task to the "In Progress" section.

---

## Step 2: Code 💻

### 2.1 Create Feature Branch

Reference: `.agent/skills/git.md`

```bash
git checkout main
git pull origin main
git checkout -b feature/TICKET-123-feature-name
```

### 2.2 Implement the Feature

Follow the constitution's coding standards:

- [ ] Use TypeScript with strict mode
- [ ] Follow naming conventions
- [ ] Keep functions small and focused
- [ ] Handle errors appropriately
- [ ] Add loading and error states (UI)

### 2.3 Commit Frequently

```bash
git add .
git commit -m "feat(scope): implement X"
```

Use atomic commits — each commit should be a logical unit.

### 2.4 Database Changes (if needed)

Reference: `.agent/skills/db.md`

```bash
# Create migration
npx prisma migrate dev --name add_feature_table

# Generate client
npx prisma generate
```

---

## Step 3: Test 🧪

Reference: `.agent/skills/test.md`

### 3.1 Write Unit Tests

```bash
# Run tests in watch mode while developing
npm test -- --watch
```

Cover:
- [ ] Happy path
- [ ] Edge cases
- [ ] Error scenarios

### 3.2 Write Integration Tests (if API)

Test the full request/response cycle.

### 3.3 Write E2E Tests (if UI)

```bash
# Run Playwright tests
npx playwright test
```

Test the user journey.

### 3.4 Verify Coverage

```bash
npm test -- --coverage
```

Ensure coverage meets requirements (80%+).

---

## Step 4: Submit 🚀

### 4.1 Self-Review

Use the checklist: `.agent/skills/review-checklist.md`

- [ ] Code quality
- [ ] Security
- [ ] Performance
- [ ] Documentation

### 4.2 Push and Create PR

```bash
git push origin feature/TICKET-123-feature-name
```

Create PR with:
- Descriptive title: `[TICKET-123] feat: Add feature name`
- Link to ticket
- Screenshots (if UI)
- Testing notes

### 4.3 Request Review

Assign appropriate reviewers based on the change:
- UI changes → Frontend team
- API changes → Backend team
- Infra changes → DevOps team

---

## Step 5: Complete ✅

### 5.1 Address Review Feedback

Make requested changes and push updates.

### 5.2 Merge

After approval:
- Squash and merge
- Delete feature branch

### 5.3 Update Plan

```
Update: .specify/memory/plan.md
```

Move task from "In Progress" to "Completed".

---

## 📊 Workflow Diagram

```
┌─────────┐     ┌─────────┐     ┌─────────┐     ┌─────────┐
│  PLAN   │────▶│  CODE   │────▶│  TEST   │────▶│ SUBMIT  │
└─────────┘     └─────────┘     └─────────┘     └─────────┘
     │               │               │               │
     ▼               ▼               ▼               ▼
 Read ticket    Follow rules    Write tests    Create PR
 Check const.   Use git.md      Use test.md    Get review
 Design soln.   Use db.md       Check coverage Merge
```

---

*Follow this workflow for consistent feature delivery.*

