# CLAUDE.md (Project Template)

Project-specific instructions for `/project/` codebase.

---

## Context

**Project**: [Name]  
**Purpose**: [What is this project?]  
**Key stakeholders**: [Who uses this?]

---

## Execution Rules

- **Reversible actions**: Take autonomously (edit files, run tests, create branches)
- **Irreversible actions**: Confirm first (delete, force-push, deploy to production)
- **When stuck**: Try alternatives, exhaust options, then ask

---

## Key Paths

| What | Path |
|------|------|
| Source code | `src/` |
| Tests | `tests/` |
| Config | `.env.local`, `config/` |
| Docs | `docs/` |
| CI/CD | `.github/workflows/` |
| Secrets | See `global/secrets/` in parent context |

---

## Code Standards

- **Language**: [Python/TypeScript/Go/etc.]
- **Style guide**: [Linter config file / link]
- **Testing**: [Test framework, coverage threshold]
- **Commits**: [Conventional commits / specific format]
- **PRs**: [Squash/rebase? Require approvals?]

---

## Common Tasks

### Running tests
```bash
[command]
```

### Building
```bash
[command]
```

### Deploying
```bash
[command]
```

### Checking code quality
```bash
[command]
```

---

## Gotchas & Constraints

1. [Known limitation or risk]
2. [Tool/service that's flaky]
3. [Permission/access constraint]

---

## When Uncertain

1. Check existing code patterns
2. Read recent commits for context
3. Run tests to validate changes
4. Ask if you've exhausted alternatives

---

_See global CLAUDE.md for general principles. This file is project-specific._
