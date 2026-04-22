# AI Agent Skills — Simplified

**Zero-dependency, plain Markdown workflows that give any AI coding agent structured engineering discipline.**

No scripts. No plugins. No zips. Just `.md` files you drop into your repo.

---

## What Is This?

A set of Markdown skill files that teach AI agents (GitHub Copilot, Claude, Cursor, Codex, and others) *when* to do *what* during software development. Instead of letting agents jump straight to code, these files enforce a structured lifecycle:

```
  DEFINE ──→ PLAN ──→ BUILD ──→ VERIFY ──→ REVIEW ──→ SHIP
    │          │         │         │          │         │
 spec.md   plan.md   build.md   test.md   review.md  ship.md
```

Every phase has a skill file with a clear process, constraints, and exit criteria that must be met before moving to the next phase.

---

## The 6-Phase Lifecycle

| # | Phase | What happens | Skill file |
|---|---|---|---|
| 1 | **DEFINE** | Clarify requirements, write a spec | `skills/spec.md` |
| 2 | **PLAN** | Break the spec into ordered, atomic tasks | `skills/plan.md` |
| 3 | **BUILD** | Implement one slice at a time, test-first | `skills/build.md` |
| 4 | **VERIFY** | Prove it works with tests, debug if it doesn't | `skills/test.md` |
| 5 | **REVIEW** | Assess quality across 5 axes before merging | `skills/review.md` |
| 6 | **SHIP** | Deploy with a checklist, monitor, rollback plan | `skills/ship.md` |

---

## Routing Table

The agent reads `AGENTS.md` and maps your request to the right phase:

| User intent | Phase | Skill file |
|---|---|---|
| "I have an idea / I want to build X" | DEFINE | `skills/spec.md` |
| "How should we approach / break this down?" | PLAN | `skills/plan.md` |
| "Implement / build / code this" | BUILD | `skills/build.md` + `skills/test.md` |
| "Something is broken / debug this" | VERIFY | `skills/test.md` |
| "Review this / is this good?" | REVIEW | `skills/review.md` |
| "Deploy / ship / release this" | SHIP | `skills/ship.md` |
| "Refactor / simplify / clean up" | REVIEW | `skills/review.md` |
| "Design an API / interface" | DEFINE + BUILD | `skills/spec.md` then `skills/build.md` |

---

## Using With Different Agents

### GitHub Copilot
Already configured. Copilot automatically reads `.github/copilot-instructions.md`, which contains the routing logic and lifecycle rules.

### Claude / Claude Code
Already configured. Claude automatically reads `AGENTS.md` from the repo root.

### Cursor
Copy the contents of `AGENTS.md` into `.cursor/rules/` in your project:
```bash
mkdir -p .cursor/rules
cp AGENTS.md .cursor/rules/agent-skills.md
```

### Codex / Other Agents
Paste the contents of `AGENTS.md` as your system prompt or instruction file. The agent will follow the routing table and read skill files as needed.

---

## Adding a Custom Skill

1. Create a new file in `skills/`, e.g. `skills/docs.md`
2. Follow the same structure (When This Applies, Process, Exit Criteria)
3. Add a row to the routing table in both `AGENTS.md` and `.github/copilot-instructions.md`

Example row:
```
| "Write documentation / explain this" | DOCUMENT | `skills/docs.md` |
```

---

## File Structure

```
your-repo/
├── .github/
│   └── copilot-instructions.md   ← GitHub Copilot reads this automatically
├── AGENTS.md                      ← Claude Code / other agents read this
├── README.md                      ← You are here
└── skills/
    ├── spec.md                    ← DEFINE: Write specs before code
    ├── plan.md                    ← PLAN: Break work into atomic tasks
    ├── build.md                   ← BUILD: Implement incrementally, test-first
    ├── test.md                    ← VERIFY: Prove it works or debug why not
    ├── review.md                  ← REVIEW: Quality gate before merge
    └── ship.md                    ← SHIP: Deploy safely with rollback plan
```

---

## Why This Exists

AI agents are eager to write code immediately. That's fast, but it leads to:
- Code without specs (misbuilt features)
- No tests (silent regressions)
- Skipped reviews (security holes, bad patterns)
- Unstructured deploys (outages)

These skill files add guardrails — not by limiting what agents can do, but by telling them *when* to do it.

---

## License

MIT — use it anywhere, modify it freely.