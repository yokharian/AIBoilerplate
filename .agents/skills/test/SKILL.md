---
name: test
description: Provides guidance on testing with Jest and Playwright. Use when writing tests, running test suites, or when the user asks about unit tests, integration tests, E2E tests, test coverage, or testing patterns.
---

# Testing Skill

> Here is how to run Jest and Playwright.

---

## 🧪 Testing Stack

| Type | Tool | Purpose |
|------|------|---------|
| Unit Tests | Jest | Functions, hooks, utilities |
| Integration Tests | Jest + Supertest | API endpoints |
| E2E Tests | Playwright | User flows in browser |

---

## 🃏 Jest (Unit & Integration)

### Commands

```bash
# Run all tests
npm test

# Run in watch mode
npm test -- --watch

# Run specific file
npm test -- path/to/file.test.ts

# Run with coverage
npm test -- --coverage

# Update snapshots
npm test -- -u
```

### File Naming

```
src/
├── utils/
│   ├── formatDate.ts
│   └── formatDate.test.ts    # Co-located test
└── __tests__/
    └── integration/
        └── api.test.ts       # Integration tests
```

### Test Structure

```typescript
describe('formatDate', () => {
  beforeEach(() => {
    // Setup before each test
  });

  afterEach(() => {
    // Cleanup after each test
  });

  it('should format date in US locale', () => {
    const result = formatDate(new Date('2024-01-15'));
    expect(result).toBe('January 15, 2024');
  });

  it('should handle invalid date', () => {
    expect(() => formatDate(null)).toThrow('Invalid date');
  });
});
```

### Mocking

```typescript
// Mock a module
jest.mock('../services/api');

// Mock implementation
import { fetchUser } from '../services/api';
const mockFetchUser = fetchUser as jest.MockedFunction<typeof fetchUser>;

mockFetchUser.mockResolvedValue({ id: '1', name: 'John' });

// Spy on a method
const spy = jest.spyOn(console, 'log');
expect(spy).toHaveBeenCalledWith('message');
```

### Testing React Components

```typescript
import { render, screen, fireEvent } from '@testing-library/react';
import { Button } from './Button';

describe('Button', () => {
  it('should call onClick when clicked', () => {
    const handleClick = jest.fn();
    render(<Button onClick={handleClick}>Click me</Button>);
    
    fireEvent.click(screen.getByText('Click me'));
    
    expect(handleClick).toHaveBeenCalledTimes(1);
  });
});
```

---

## 🎭 Playwright (E2E)

### Commands

```bash
# Run all E2E tests
npx playwright test

# Run in headed mode (see browser)
npx playwright test --headed

# Run specific test file
npx playwright test tests/login.spec.ts

# Debug mode
npx playwright test --debug

# Generate tests (codegen)
npx playwright codegen http://localhost:3000

# View test report
npx playwright show-report
```

### File Structure

```
tests/
├── login.spec.ts
├── checkout.spec.ts
└── fixtures/
    └── auth.ts
```

### Test Structure

```typescript
import { test, expect } from '@playwright/test';

test.describe('Login Flow', () => {
  test.beforeEach(async ({ page }) => {
    await page.goto('/login');
  });

  test('should login successfully with valid credentials', async ({ page }) => {
    await page.fill('[data-testid="email"]', 'user@example.com');
    await page.fill('[data-testid="password"]', 'password123');
    await page.click('[data-testid="submit"]');
    
    await expect(page).toHaveURL('/dashboard');
    await expect(page.locator('h1')).toContainText('Welcome');
  });

  test('should show error with invalid credentials', async ({ page }) => {
    await page.fill('[data-testid="email"]', 'wrong@example.com');
    await page.fill('[data-testid="password"]', 'wrongpassword');
    await page.click('[data-testid="submit"]');
    
    await expect(page.locator('[data-testid="error"]')).toBeVisible();
  });
});
```

### Page Object Model

```typescript
// pages/LoginPage.ts
export class LoginPage {
  constructor(private page: Page) {}

  async goto() {
    await this.page.goto('/login');
  }

  async login(email: string, password: string) {
    await this.page.fill('[data-testid="email"]', email);
    await this.page.fill('[data-testid="password"]', password);
    await this.page.click('[data-testid="submit"]');
  }
}

// Usage in test
test('should login', async ({ page }) => {
  const loginPage = new LoginPage(page);
  await loginPage.goto();
  await loginPage.login('user@example.com', 'password');
});
```

---

## ✅ Coverage Requirements

| Type | Target |
|------|--------|
| Statements | 80% |
| Branches | 75% |
| Functions | 80% |
| Lines | 80% |

---

## ⚠️ Testing Rules

1. **Test behavior, not implementation**
2. **One assertion focus per test**
3. **Use descriptive test names**
4. **Avoid testing third-party code**
5. **Keep tests independent**
6. **Clean up after tests**
7. **Use `data-testid` for E2E selectors**

---

*Write tests that give confidence, not just coverage.*

