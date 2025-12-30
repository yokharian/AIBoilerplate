---
name: git
description: Provides standard Git commands and conventions for version control. Use when working with Git branches, commits, pull requests, or when the user asks about Git, branch naming, commit messages, or version control operations.
---

# Git Skill

> Here are the standard Git commands we use.

---

## 🌿 Branch Naming

```
<type>/<ticket-id>-<short-description>
```

### Types

| Type | Usage |
|------|-------|
| `feature/` | New features |
| `bugfix/` | Bug fixes |
| `hotfix/` | Urgent production fixes |
| `refactor/` | Code refactoring |
| `docs/` | Documentation changes |
| `chore/` | Maintenance tasks |

### Examples

```bash
feature/ABC-123-user-authentication
bugfix/ABC-456-fix-login-redirect
hotfix/ABC-789-critical-security-patch
```

---

## 💬 Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation |
| `style` | Formatting, no code change |
| `refactor` | Code restructuring |
| `test` | Adding tests |
| `chore` | Maintenance |

### Examples

```bash
feat(auth): add OAuth2 Google login

Implements Google OAuth2 authentication flow with
automatic account creation for new users.

Closes #123
```

---

## 📋 Common Commands

### Starting Work

```bash
# Get latest from main
git checkout main
git pull origin main

# Create feature branch
git checkout -b feature/ABC-123-new-feature
```

### During Development

```bash
# Stage changes
git add .

# Commit with message
git commit -m "feat(scope): description"

# Push to remote
git push origin feature/ABC-123-new-feature
```

### Syncing with Main

```bash
# Fetch latest
git fetch origin

# Rebase onto main (preferred)
git rebase origin/main

# Or merge if conflicts are complex
git merge origin/main
```

### Resolving Conflicts

```bash
# After conflict markers appear
# 1. Edit files to resolve conflicts
# 2. Stage resolved files
git add <resolved-files>

# 3. Continue rebase
git rebase --continue

# Or if merging
git commit
```

### Undoing Mistakes

```bash
# Undo last commit (keep changes)
git reset --soft HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1

# Discard local changes to a file
git checkout -- <file>

# Stash changes temporarily
git stash
git stash pop
```

---

## 🔀 Pull Request Process

1. **Push your branch**
   ```bash
   git push origin feature/ABC-123-new-feature
   ```

2. **Create PR** via GitHub/GitLab UI

3. **PR Title Format**
   ```
   [ABC-123] feat: Add user authentication
   ```

4. **Request Review** from team members

5. **After Approval**
   ```bash
   # Squash and merge via UI
   # Or locally:
   git checkout main
   git merge --squash feature/ABC-123-new-feature
   git commit -m "feat(auth): add user authentication (#123)"
   git push origin main
   ```

6. **Clean Up**
   ```bash
   git branch -d feature/ABC-123-new-feature
   git push origin --delete feature/ABC-123-new-feature
   ```

---

## ⚠️ Rules

1. **Never force push to `main`**
2. **Always pull before pushing**
3. **Keep commits atomic and focused**
4. **Write meaningful commit messages**
5. **Rebase feature branches, don't merge main into them**

---

*Follow these conventions for a clean Git history.*

