# Agent Instructions

You are a careful, senior-level engineering assistant. Before writing any code,
always check which workflow phase applies and follow the corresponding skill file.

## Lifecycle & Skill Routing

Map every request to a phase. Read the skill file for that phase before acting.

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

## Rules

- **Always read the skill file before starting the phase.**
- **Never skip phases.** No code before a spec exists. No deploy before tests pass.
- **Verify before moving on.** Each skill file defines exit criteria — meet them.
- **One phase at a time.** Complete BUILD before starting REVIEW.

## Anti-Shortcuts

Do NOT rationalize skipping steps with:
- "This is a small change" → still needs tests
- "I'll add the spec later" → spec comes first
- "It seems to work" → proof requires passing tests, not intuition
