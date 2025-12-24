# Database Skill

> Here is how to run SQL and migrations.

---

## 🗄️ Database: PostgreSQL + Prisma

We use **PostgreSQL** as our primary database and **Prisma** as the ORM.

---

## 📋 Common Commands

### Prisma CLI

```bash
# Generate Prisma Client after schema changes
npx prisma generate

# Create a new migration
npx prisma migrate dev --name <migration-name>

# Apply migrations in production
npx prisma migrate deploy

# Reset database (DEV ONLY - drops all data)
npx prisma migrate reset

# Open Prisma Studio (GUI)
npx prisma studio

# Format schema file
npx prisma format

# Validate schema
npx prisma validate
```

---

## 📝 Schema Conventions

### Naming

| Element | Convention | Example |
|---------|------------|---------|
| Models | PascalCase, singular | `User`, `BlogPost` |
| Fields | camelCase | `firstName`, `createdAt` |
| Relations | camelCase | `author`, `posts` |
| Enums | PascalCase | `UserRole`, `OrderStatus` |

### Required Fields

Every model should have:

```prisma
model Example {
  id        String   @id @default(cuid())
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
  
  // ... other fields
}
```

---

## 🔄 Migration Workflow

### 1. Modify Schema

Edit `prisma/schema.prisma`:

```prisma
model User {
  id        String   @id @default(cuid())
  email     String   @unique
  name      String?
  posts     Post[]
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
}
```

### 2. Create Migration

```bash
npx prisma migrate dev --name add_user_table
```

### 3. Verify Migration

Check `prisma/migrations/` for the generated SQL.

### 4. Commit Both

```bash
git add prisma/schema.prisma prisma/migrations/
git commit -m "feat(db): add user table"
```

---

## 🔍 Query Patterns

### Basic CRUD

```typescript
// Create
const user = await prisma.user.create({
  data: { email: 'user@example.com', name: 'John' }
});

// Read
const user = await prisma.user.findUnique({
  where: { id: 'user-id' }
});

// Update
const user = await prisma.user.update({
  where: { id: 'user-id' },
  data: { name: 'Jane' }
});

// Delete
await prisma.user.delete({
  where: { id: 'user-id' }
});
```

### With Relations

```typescript
// Include related data
const userWithPosts = await prisma.user.findUnique({
  where: { id: 'user-id' },
  include: { posts: true }
});

// Nested create
const user = await prisma.user.create({
  data: {
    email: 'user@example.com',
    posts: {
      create: [{ title: 'First Post' }]
    }
  }
});
```

### Transactions

```typescript
const [user, post] = await prisma.$transaction([
  prisma.user.create({ data: { email: 'user@example.com' } }),
  prisma.post.create({ data: { title: 'Post', authorId: 'id' } })
]);
```

---

## ⚠️ Rules

1. **Never run `migrate reset` in production**
2. **Always review generated SQL before applying**
3. **Use transactions for multi-step operations**
4. **Index frequently queried fields**
5. **Use `@unique` for natural keys**
6. **Soft delete when data retention is required**

---

## 🔧 Environment Setup

```bash
# .env
DATABASE_URL="postgresql://user:password@localhost:5432/mydb?schema=public"
```

---

*Follow these patterns for consistent database operations.*

