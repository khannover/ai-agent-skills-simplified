# AI Agent Skills — Simplified

A zero-dependency, plain-Markdown system that gives any AI coding agent structured engineering workflows. No scripts, no zips, no plugins — just Markdown files that any agent can read.

## How It Works

Every engineering task follows a lifecycle. The `AGENTS.md` file routes user intent to the correct phase and skill file. Each skill file defines **when it applies**, a **process to follow**, and **exit criteria** that must be met before moving on.

### Lifecycle

```
DEFINE  →  PLAN  →  BUILD  →  VERIFY  →  REVIEW  →  SHIP
  │          │        │          │          │          │
spec.md   plan.md  build.md   test.md   review.md  ship.md
                   + test.md
```

### Routing Table

| User intent | Phase | Skill file |
|---|---|---|
| "I have an idea / I want to build X" | DEFINE | `skills/spec.md` |
| "How should we approach / break this down?" | PLAN | `skills/plan.md` |
| "Implement / build / code this" | BUILD | `skills/build.md` + `skills/test.md` |
| "Something is broken / debug this" | VERIFY | `skills/test.md` |
| "Review this / is this good?" | REVIEW | `skills/review.md` |
| "Deploy / ship / release this" | SHIP | `skills/ship.md` |
| "Refactor / simplify / clean up" | REVIEW | `skills/review.md` |
| "Design an API / interface" | BUILD | `skills/spec.md` then `skills/build.md` |

## Repository Structure

```
├── AGENTS.md                      ← Routing brain (Claude, Codex, others)
├── .github/
│   └── copilot-instructions.md    ← Same content, auto-loaded by GitHub Copilot
├── skills/
│   ├── spec.md                    ← Spec-Driven Development
│   ├── plan.md                    ← Planning & Task Breakdown
│   ├── build.md                   ← Incremental Implementation
│   ├── test.md                    ← Testing & Verification
│   ├── review.md                  ← Code Review & Quality Gate
│   └── ship.md                    ← Shipping & Launch
└── README.md                      ← This file
```

## Using with AI Agents

| Agent | How it reads the skills |
|---|---|
| **GitHub Copilot** | Automatically reads `.github/copilot-instructions.md` |
| **Claude / Claude Code** | Reads `AGENTS.md` at the repository root |
| **Cursor** | Copy `AGENTS.md` content into `.cursor/rules/` |
| **Codex / others** | Paste `AGENTS.md` content into your system prompt |

No configuration needed for Copilot or Claude — they pick up the files automatically.

## Adding Custom Skills

1. Create a new file: `skills/your-skill.md`
2. Follow the same structure as existing skills:
   - **"Use when"** — one-line summary of when this skill applies
   - **"When This Applies"** — bullet list of trigger conditions
   - **"Process"** — numbered steps to follow
   - **"Exit Criteria"** — checklist that must pass before moving on
3. Add a row to the routing table in `AGENTS.md` (and `.github/copilot-instructions.md`)

## About the Skill Files

Each file in `skills/` is a standalone workflow that an AI agent reads and follows. The key sections are:

- **When This Applies** — tells the agent whether this skill is relevant to the current task
- **Process** — step-by-step instructions the agent follows
- **Exit Criteria** — a checklist the agent must satisfy before moving to the next phase

The agent reads `AGENTS.md` first to determine which skill file to load, then follows that skill's process from start to finish.

## License

This project is open source. Use it however you like.