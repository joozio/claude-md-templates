# Project CLAUDE.md Template

**File location:** `/your-project/CLAUDE.md`

This file defines what the agent DOES in this specific project — capabilities, infrastructure, file structure, task rules. It's read alongside the global file, so don't repeat global rules here.

---

```markdown
# [Project Name] — What I Do

**Root:** `/path/to/project/` | **Context:** `[main context file if any]`

---

## Core: EXECUTE FIRST

Find a way. Do it. Present result. Ask only when blocked.

---

## Capabilities & Tools

[Map trigger phrases to tools/actions. This is the routing layer.
Without it, the agent improvises — sometimes wrong.]

| Trigger | Tool/Action |
|---------|-------------|
| "deploy" | SSH to production server |
| "send email" | Gmail SMTP via script |
| "run tests" | `npm test` or equivalent |
| "search web" | WebSearch tool |
| [Add your tools] | [What to use] |

---

## Infrastructure

[Specific details for this project only. Never in the global file.]

**Server:** `user@your-server.com`
**Deployment:** `[deployment command or path]`
**Database:** `[connection method]`
**Key paths:**

| What | Where |
|------|-------|
| Config | `config/` |
| Secrets | `[secrets location]` |
| Logs | `logs/` |
| [Add paths] | [Location] |

---

## Project Structure

```
[project-root]/
├── src/           # [description]
├── tests/         # [description]
├── config/        # [description]
└── [add yours]    # [description]
```

---

## Task Rules

[Specific rules for this project. Common patterns:]

**Before making changes:**
- Read the relevant files first, don't modify without reading
- Check `[relevant file]` before creating new ones to avoid duplication

**Testing:**
- Run tests after any code change: `[test command]`
- Don't mark a task done if tests fail

**Commits:**
- Use conventional commits: `feat:`, `fix:`, `chore:`, `docs:`
- Never commit secrets or credentials

**[Add your project-specific rules here]**

---

## Current State

[Optional but useful: current status, known issues, in-progress work.
Update this when context shifts significantly.]

- **Status:** [Active/Paused/In progress]
- **Known issues:** [Any current blockers]
- **In progress:** [What's being worked on]

---

## Credentials & Secrets

**All credentials in:** `[secrets directory]`
**Format:** Read with `cat [secrets file]` — never hardcode

[List what credentials exist, not the values themselves:]
- API key: `[secrets/api-key.md]`
- Database password: `[secrets/db.md]`
```

---

## Notes on Customization

**Infrastructure details belong here, not in the global file.** Server addresses, API endpoints, database connections — all project-specific.

**Task rules should reflect real recurring patterns.** If you've corrected the agent about the same thing twice, write a rule.

**The Capabilities table is important.** Without explicit tool routing, the agent guesses. For any tool you want the agent to use reliably, add a row.

**Update Current State regularly.** It takes 30 seconds and saves the agent from making wrong assumptions about project state at the start of sessions.
