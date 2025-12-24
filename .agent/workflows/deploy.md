# Deploy Workflow

> Step 1: Lint. Step 2: Build. Step 3: Ship.

---

## 📋 Overview

This workflow guides you through deploying code to production safely.

---

## Step 1: Lint 🔍

### 1.1 Run Linting

```bash
# ESLint
npm run lint

# Fix auto-fixable issues
npm run lint:fix
```

### 1.2 Run Type Checking

```bash
# TypeScript
npx tsc --noEmit
```

### 1.3 Run Formatting

```bash
# Prettier
npm run format

# Check formatting
npm run format:check
```

### 1.4 Verify All Checks Pass

- [ ] No ESLint errors
- [ ] No TypeScript errors
- [ ] Code is formatted
- [ ] No console.log statements

---

## Step 2: Build 🔨

### 2.1 Run Tests

Reference: `.agent/skills/test.md`

```bash
# Unit & Integration tests
npm test

# E2E tests
npx playwright test

# With coverage
npm test -- --coverage
```

All tests must pass before proceeding.

### 2.2 Create Production Build

```bash
# Build the application
npm run build
```

### 2.3 Verify Build

```bash
# Preview production build locally
npm run preview
```

Check:
- [ ] Build completes without errors
- [ ] Application loads correctly
- [ ] All features work as expected
- [ ] No console errors in browser

### 2.4 Check Bundle Size

```bash
# Analyze bundle
npm run build -- --analyze
```

Ensure:
- [ ] No unexpected size increases
- [ ] Large dependencies are code-split
- [ ] Assets are optimized

---

## Step 3: Ship 🚀

### 3.1 Pre-Deployment Checklist

- [ ] All tests pass
- [ ] Build succeeds
- [ ] Environment variables are set
- [ ] Database migrations are ready
- [ ] Team is notified
- [ ] Rollback plan is ready

### 3.2 Deploy to Staging

```bash
# Deploy to staging environment
npm run deploy:staging
```

### 3.3 Verify on Staging

- [ ] Application loads
- [ ] Critical flows work
- [ ] Integrations function
- [ ] Performance is acceptable

### 3.4 Deploy to Production

```bash
# Deploy to production
npm run deploy:production
```

### 3.5 Post-Deployment Verification

- [ ] Application is accessible
- [ ] Health checks pass
- [ ] Key metrics are normal
- [ ] No spike in errors

---

## 🔄 Rollback Procedure

If issues are detected:

### Immediate Rollback

```bash
# Revert to previous deployment
npm run rollback:production
```

### Or Manual Rollback

```bash
# Identify last good commit
git log --oneline

# Deploy specific version
npm run deploy:production -- --version=<commit-sha>
```

### Post-Rollback

1. Notify the team
2. Investigate the issue
3. Create a hotfix if needed
4. Update incident log

---

## 📊 Deployment Checklist

### Before Deployment

| Check | Status |
|-------|--------|
| Linting passes | ⬜ |
| Types check | ⬜ |
| Tests pass | ⬜ |
| Build succeeds | ⬜ |
| Staging verified | ⬜ |
| Team notified | ⬜ |

### After Deployment

| Check | Status |
|-------|--------|
| App loads | ⬜ |
| Health checks pass | ⬜ |
| Critical flows work | ⬜ |
| Error rates normal | ⬜ |
| Performance normal | ⬜ |

---

## 📊 Workflow Diagram

```
┌─────────┐     ┌─────────┐     ┌─────────┐
│  LINT   │────▶│  BUILD  │────▶│  SHIP   │
└─────────┘     └─────────┘     └─────────┘
     │               │               │
     ▼               ▼               ▼
 ESLint          Run tests      Deploy staging
 TypeScript      Build prod     Verify
 Prettier        Check size     Deploy prod
                                Monitor
```

---

## ⚠️ Deployment Rules

1. **Never deploy on Fridays** (unless critical)
2. **Always deploy to staging first**
3. **Have a rollback plan ready**
4. **Monitor for 30 minutes after deploy**
5. **One person deploys at a time**
6. **Document any manual steps**

---

## 🔧 Environment Variables

Ensure these are set in production:

```bash
NODE_ENV=production
DATABASE_URL=<production-db-url>
API_KEY=<production-api-key>
# ... other env vars
```

Reference `.env.example` for required variables.

---

*Deploy with confidence, but always be ready to rollback.*

