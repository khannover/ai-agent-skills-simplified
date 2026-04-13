# Skill: Spec-Driven Development

**Use when:** Starting anything new, or when requirements are unclear.

## When This Applies
- New feature, new endpoint, new component
- Vague request ("build me a login page")
- Any work that will take more than ~30 minutes

## Process

1. **Clarify the goal** — one sentence: what problem does this solve for whom?
2. **Define success** — what does "done" look like? (user-visible behavior)
3. **Write the spec** — a short `SPEC.md` with:
   - Objective (1–2 sentences)
   - Key behaviors (bullet list, user-facing)
   - Out of scope (explicit)
   - Open questions (anything unresolved)
4. **Get confirmation** — don't write code until the spec is agreed on

## Exit Criteria (before moving to PLAN)
- [ ] Spec doc exists
- [ ] Objective is one clear sentence
- [ ] "Out of scope" is written down
- [ ] No open questions blocking implementation

## Anti-Rationalization
| Excuse | Response |
|---|---|
| "The requirement is obvious" | Write it down anyway — obvious things get misbuilt |
| "It's just a small feature" | Small features with no spec drift the most |
