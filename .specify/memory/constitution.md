# Constitution

> I am the Law (Tech Stack & Rules). **Never ignore me.**

---

## 🏗️ Tech Stack

> ⚠️ **IMPORTANT**: The following tech stack is just an example. **You must delete these examples and replace them with your actual tech stack before continuing.**

### Frontend
- **Framework**: React 18+ with TypeScript
- **Styling**: Tailwind CSS
- **State Management**: Zustand or React Query
- **Build Tool**: Vite

### Backend
- **Runtime**: Node.js 20+ LTS
- **Framework**: Express.js or Fastify
- **Database**: PostgreSQL with Prisma ORM
- **Cache**: Redis

### Infrastructure
- **Cloud**: AWS
- **Container**: Docker
- **CI/CD**: GitHub Actions
- **Monitoring**: DataDog or CloudWatch

---

## 📏 Coding Standards

> ⚠️ **IMPORTANT**: The following coding standards are just examples. **You must delete these examples and replace them with your actual coding standards before continuing.**

### General Rules

1. **TypeScript Everywhere** — No plain JavaScript in production code
2. **Strict Mode** — `"strict": true` in all tsconfig files
3. **ESLint + Prettier** — Code must pass linting before commit
4. **No `any`** — Use proper types or `unknown` if truly dynamic

### Naming Conventions

| Type | Convention | Example |
|------|------------|---------|
| Files (Components) | PascalCase | `UserProfile.tsx` |
| Files (Utils) | camelCase | `formatDate.ts` |
| Variables | camelCase | `userName` |
| Constants | SCREAMING_SNAKE | `MAX_RETRY_COUNT` |
| Types/Interfaces | PascalCase | `UserProfile` |
| CSS Classes | kebab-case | `user-profile-card` |

### File Structure

```
src/
├── components/     # React components
├── hooks/          # Custom React hooks
├── utils/          # Pure utility functions
├── services/       # API calls and external services
├── types/          # TypeScript type definitions
├── constants/      # Application constants
└── __tests__/      # Test files
```

---

## 🚫 Forbidden Patterns

1. **No `console.log` in production** — Use proper logging library
2. **No hardcoded secrets** — Use environment variables
3. **No `// @ts-ignore`** — Fix the type issue properly
4. **No inline styles** — Use Tailwind or CSS modules
5. **No `var`** — Use `const` or `let`
6. **No nested callbacks** — Use async/await
7. **No magic numbers** — Use named constants

---

## ✅ Required Patterns

1. **Error Boundaries** — Wrap components that can fail
2. **Loading States** — Always show loading indicators
3. **Error States** — Always handle and display errors gracefully
4. **Input Validation** — Validate all user inputs
5. **Accessibility** — Use semantic HTML and ARIA labels
6. **Responsive Design** — Mobile-first approach

---

## 🔒 Security Rules

1. **Sanitize all inputs** — Prevent XSS and SQL injection
2. **Use parameterized queries** — Never concatenate SQL strings
3. **HTTPS only** — No HTTP in production
4. **JWT expiration** — Tokens expire in 24 hours max
5. **Rate limiting** — Implement on all public APIs
6. **CORS configuration** — Whitelist allowed origins only

---

## 📝 Documentation Requirements

1. **JSDoc for public functions** — Describe params and return types
2. **README per major feature** — Explain purpose and usage
3. **API documentation** — OpenAPI/Swagger spec for all endpoints
4. **Changelog** — Keep CHANGELOG.md updated

---

## 🧪 Testing Requirements

| Type | Coverage Target | Tool |
|------|-----------------|------|
| Unit Tests | 80% | Jest |
| Integration Tests | Critical paths | Supertest |
| E2E Tests | Happy paths | Playwright |

---

*This constitution is non-negotiable. All code must comply.*
