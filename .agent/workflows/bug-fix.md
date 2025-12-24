# Bug Fix Workflow

> Step 1: Reproduce. Step 2: Fix. Step 3: Verify.

---

## 📋 Overview

This workflow guides you through fixing bugs systematically.

---

## Step 1: Reproduce 🔍

### 1.1 Gather Information

- [ ] Read the bug report completely
- [ ] Note the expected vs actual behavior
- [ ] Identify the environment (browser, OS, etc.)
- [ ] Check for error messages/stack traces

### 1.2 Reproduce Locally

```bash
# Get latest code
git checkout main
git pull origin main

# Set up environment matching the report
npm install
npm run dev
```

### 1.3 Confirm the Bug

- [ ] Follow the exact steps from the report
- [ ] Verify you see the same behavior
- [ ] Take screenshots/recordings if helpful

### 1.4 If Cannot Reproduce

- Ask for more details
- Check if it's environment-specific
- Try different browsers/devices
- Check if already fixed in main

---

## Step 2: Fix 🔧

### 2.1 Create Bug Fix Branch

Reference: `.agent/skills/git.md`

```bash
git checkout -b bugfix/TICKET-456-fix-description
```

### 2.2 Locate the Problem

Debugging strategies:
- [ ] Check console for errors
- [ ] Add logging/breakpoints
- [ ] Trace the data flow
- [ ] Review recent changes to affected area

### 2.3 Understand Root Cause

Before coding, answer:
- **What** is broken?
- **Why** did it break?
- **When** was it introduced?
- **Where** is the fix needed?

### 2.4 Implement the Fix

Follow the constitution: `.specify/memory/constitution.md`

Guidelines:
- [ ] Make the minimal change needed
- [ ] Don't refactor unrelated code
- [ ] Don't introduce new features
- [ ] Handle edge cases

### 2.5 Write a Regression Test

Reference: `.agent/skills/test.md`

```typescript
describe('Bug TICKET-456', () => {
  it('should not crash when input is empty', () => {
    // This test ensures the bug doesn't return
    const result = handleInput('');
    expect(result).toBe(defaultValue);
  });
});
```

**The test must fail before your fix and pass after.**

---

## Step 3: Verify ✅

### 3.1 Test the Fix

- [ ] Bug no longer reproduces
- [ ] Regression test passes
- [ ] All existing tests pass
- [ ] No new issues introduced

```bash
# Run all tests
npm test

# Run E2E if UI bug
npx playwright test
```

### 3.2 Test Related Functionality

Check that the fix doesn't break:
- [ ] Related features
- [ ] Edge cases
- [ ] Different user roles
- [ ] Different environments

### 3.3 Self-Review

Use the checklist: `.agent/skills/review-checklist.md`

Focus on:
- [ ] Security implications
- [ ] Performance impact
- [ ] Backward compatibility

---

## Step 4: Submit 📤

### 4.1 Commit with Reference

```bash
git add .
git commit -m "fix(scope): description

Fixes #456"
```

### 4.2 Push and Create PR

```bash
git push origin bugfix/TICKET-456-fix-description
```

PR should include:
- Clear title: `[TICKET-456] fix: Description`
- Root cause explanation
- What the fix does
- How to test
- Screenshots if UI

### 4.3 Link Everything

- [ ] Link PR to ticket
- [ ] Update ticket status
- [ ] Notify reporter (if appropriate)

---

## Step 5: Monitor 👁️

After merge:
- [ ] Verify fix in staging/production
- [ ] Check error monitoring for related issues
- [ ] Close the ticket
- [ ] Update documentation if needed

---

## 📊 Workflow Diagram

```
┌───────────┐     ┌───────────┐     ┌───────────┐
│ REPRODUCE │────▶│    FIX    │────▶│  VERIFY   │
└───────────┘     └───────────┘     └───────────┘
      │                 │                 │
      ▼                 ▼                 ▼
  Read report      Find root cause   Test fix
  Reproduce        Minimal change    Run tests
  Confirm bug      Write reg. test   Self-review
```

---

## ⚠️ Common Pitfalls

1. **Fixing symptoms, not causes** — Dig deeper
2. **Over-engineering the fix** — Keep it minimal
3. **Skipping the regression test** — Always add one
4. **Not checking related areas** — Test thoroughly
5. **Rushing the fix** — Take time to understand

---

*A proper bug fix prevents recurrence.*

