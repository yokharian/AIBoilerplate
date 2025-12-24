# Review Checklist

> Here is the list of things to check in a PR.

---

## 📋 PR Review Checklist

Use this checklist when reviewing Pull Requests.

---

## 🔍 Code Quality

- [ ] **Code is readable** — Clear naming, logical structure
- [ ] **No dead code** — Unused variables, imports, or functions removed
- [ ] **DRY principle** — No unnecessary duplication
- [ ] **Single responsibility** — Functions/classes do one thing well
- [ ] **Error handling** — Errors are caught and handled gracefully
- [ ] **No hardcoded values** — Magic numbers replaced with constants

---

## 📐 Architecture & Design

- [ ] **Follows existing patterns** — Consistent with codebase conventions
- [ ] **Appropriate abstraction level** — Not over or under-engineered
- [ ] **Dependencies justified** — New packages are necessary
- [ ] **No circular dependencies** — Clean import structure
- [ ] **Separation of concerns** — UI, logic, and data layers are separate

---

## 🔒 Security

- [ ] **No secrets in code** — API keys, passwords in env vars
- [ ] **Input validation** — User inputs are sanitized
- [ ] **SQL injection prevention** — Parameterized queries used
- [ ] **XSS prevention** — User content is escaped
- [ ] **Authentication checks** — Protected routes are secured
- [ ] **Authorization checks** — Users can only access their data

---

## 🧪 Testing

- [ ] **Tests included** — New code has corresponding tests
- [ ] **Tests pass** — All existing tests still pass
- [ ] **Edge cases covered** — Boundary conditions tested
- [ ] **Mocks are appropriate** — Not mocking too much or too little
- [ ] **Test names are descriptive** — Clear what's being tested

---

## 📝 Documentation

- [ ] **Code is self-documenting** — Complex logic explained
- [ ] **JSDoc for public APIs** — Functions have proper documentation
- [ ] **README updated** — If feature affects usage
- [ ] **CHANGELOG updated** — Notable changes recorded
- [ ] **Comments explain "why"** — Not just "what"

---

## ⚡ Performance

- [ ] **No N+1 queries** — Database calls are optimized
- [ ] **Appropriate caching** — Expensive operations cached
- [ ] **No memory leaks** — Event listeners cleaned up
- [ ] **Lazy loading used** — Large components/data loaded on demand
- [ ] **Bundle size considered** — New dependencies aren't huge

---

## ♿ Accessibility

- [ ] **Semantic HTML** — Correct elements used
- [ ] **ARIA labels** — Interactive elements are labeled
- [ ] **Keyboard navigation** — Can navigate without mouse
- [ ] **Color contrast** — Text is readable
- [ ] **Focus indicators** — Visible focus states

---

## 🎨 UI/UX (if applicable)

- [ ] **Matches design** — Implementation follows mockups
- [ ] **Responsive** — Works on mobile, tablet, desktop
- [ ] **Loading states** — User knows when something is loading
- [ ] **Error states** — Errors are shown clearly
- [ ] **Empty states** — Handles no-data scenarios

---

## 📦 Build & Deploy

- [ ] **No linting errors** — Code passes ESLint
- [ ] **No type errors** — TypeScript compiles cleanly
- [ ] **Build succeeds** — Production build works
- [ ] **No console logs** — Debug logs removed
- [ ] **Environment vars documented** — New vars added to .env.example

---

## 🏷️ PR Metadata

- [ ] **Descriptive title** — Clear what the PR does
- [ ] **Linked to issue** — References ticket number
- [ ] **Appropriate labels** — Tagged correctly
- [ ] **Reasonable size** — Not too large to review
- [ ] **Screenshots included** — For UI changes

---

## ✅ Approval Criteria

**Approve** when:
- All critical items are checked
- No security vulnerabilities
- Tests pass and coverage is adequate

**Request Changes** when:
- Security issues found
- Breaking changes without migration
- Major bugs in logic

**Comment** when:
- Minor suggestions (nitpicks)
- Questions about implementation
- Alternative approaches to consider

---

*A thorough review prevents bugs in production.*

