# claude-md-templates

A curated collection of CLAUDE.md templates for AI agent instructions. Based on principles from [How I Structure CLAUDE.md After 1000+ Sessions](https://thoughts.jock.pl/p/how-i-structure-claude-md-after-1000-sessions).

## What is CLAUDE.md?

CLAUDE.md is a system instruction file that defines how an AI agent should behave within a specific context. It's the bridge between generic agent capabilities and your specific needs, preferences, and constraints.

The power of CLAUDE.md is **principles over rules**. Agents generalize principles effectively; exhaustive rule lists create conflicts and miss edge cases.

## The Two-File System

The recommended approach uses two files:

### Global: `~/.claude/CLAUDE.md`
Defines agent identity, core principles, and universal behaviors. Loaded for every session.

**Typical sections:**
- Working With [Human Name]
- Decision Rules (tiebreakers)
- Core Behaviors (non-negotiables)
- Self-Extension (how agent improves autonomously)

### Project: `/project/CLAUDE.md`
Execution specifics for a particular codebase or initiative. Loaded when working in that context.

**Typical sections:**
- Project-specific behaviors
- Key paths and architecture
- Automation patterns
- Content standards

## Templates in This Repo

### 1. **global-template.md**
A starter global CLAUDE.md. Covers personal context, decision rules, and self-improvement loops. ~80 lines.

**Best for:** First-time CLAUDE.md users establishing baseline agent instructions.

### 2. **project-template.md**
A starter project-level CLAUDE.md. Covers codebase navigation, local execution patterns, and project-specific rules.

**Best for:** Setting up consistent agent behavior for a specific project or team.

### 3. **advanced-global.md**
Extended global template with sections for:
- Memory systems
- Security/compliance policies
- Model selection heuristics
- Custom skills framework

**Best for:** Complex operations with multiple agents, data sensitivity, or custom tooling.

### 4. **project-commerce.md**
Real-world example for e-commerce projects. Includes:
- Store/inventory patterns
- Order handling rules
- Payment/customer data security
- Deployment safeguards

**Best for:** Learning how CLAUDE.md applies to product/commerce work.

## Getting Started

1. **Start with the global template:**
   ```
   cp global-template.md ~/.claude/CLAUDE.md
   ```

2. **Customize for your context:**
   - Replace `[Name]` placeholders
   - Add your core decision rules
   - Define what "done" means for you
   - List tools you use frequently

3. **Create project-specific files as needed:**
   ```
   cp project-template.md /path/to/project/CLAUDE.md
   ```

4. **Share and iterate:**
   - Version control your CLAUDE.md files
   - Test instructions with your agent
   - Refine based on what works

## Key Principles

These principles appear across all templates:

1. **Action over asking** – Agent takes reversible actions without permission
2. **Concise over verbose** – Brief, direct communication
3. **Principles over rules** – Guidelines that generalize beat exhaustive checklists
4. **Execute first, refine later** – Ship working solutions, not perfect plans
5. **Auto-learning** – Agent records preferences and improves over time

## Examples from the Wild

- **Pawel's global file**: Focus on ADHD accommodations, decision rules, personal communication style
- **Pawel's project file** (Wiz): Automation patterns, content standards, key paths, behavior rules
- **Commerce project**: Security constraints, financial operation guards, customer data handling

## Best Practices

### DO ✅
- Keep global file lean (~60-100 lines)
- Use principles as tiebreakers, not exhaustive rules
- Include references to external docs (e.g., content standards, memory system)
- Update when you discover new preferences or patterns
- Version control your files

### DON'T ❌
- Write exhaustive rule lists that conflict
- Duplicate context between global and project files
- Add instructions for one-off exceptions
- Let the file grow without pruning
- Assume the agent will follow implicit rules

## Customization Guide

### For Managers/Leaders
Focus on decision authority and escalation thresholds.

### For Builders/Engineers
Emphasize execution patterns, testing, and reversibility.

### For Content Creators
Define voice, editorial standards, and publishing guardrails.

### For Data-Sensitive Work
Add sections on security, compliance, and data handling.

## Contributing

Found a pattern that works? Send a PR:

1. Create a new template (e.g., `project-saas.md`)
2. Include a brief description of the context
3. Keep it under 150 lines
4. Add it to this README under "Templates"

## Related

See also: [claude-skills](https://github.com/joozio/claude-skills) — drop-in skill collection for Claude Code

## Resources

- Blog post: [How I Structure CLAUDE.md After 1000+ Sessions](https://thoughts.jock.pl/p/how-i-structure-claude-md-after-1000-sessions)
- Original inspiration: Anthropic's agent documentation
- Community: Share your CLAUDE.md patterns and lessons

---

**Why this matters:** A good CLAUDE.md is the difference between an agent that takes random actions and one that aligns with your goals, constraints, and communication style. It's also a forcing function to clarify what you actually want.

---

Built by [Pawel Jozefiak](https://thoughts.jock.pl). I write about AI agents, automation, and building in public at **[Digital Thoughts](https://thoughts.jock.pl)** (1,000+ subscribers).

Read more: [How I Structure CLAUDE.md](https://thoughts.jock.pl/p/how-i-structure-claudemd)

Go deeper: [Claude Code Workshop](https://wiz.jock.pl/store/claude-code-workshop) ($29) · [Agent Memory System Kit](https://wiz.jock.pl/store/agent-memory-system) ($39)

[Subscribe to the newsletter](https://thoughts.jock.pl/subscribe) | [More projects](https://github.com/joozio) | [@joozio](https://x.com/joozio)
