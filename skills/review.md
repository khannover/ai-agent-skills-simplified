# Skill: Code Review & Quality Gate

**Use when:** Code is written and you want to assess quality before merging.

## When This Applies
- Before opening a PR
- When asked to review existing code
- After refactoring

## Five Review Axes

Review on each axis in order:

1. **Correctness** — Does it do what the spec says? Does it handle edge cases?
2. **Tests** — Do tests cover the behavior, not just the happy path?
3. **Readability** — Would a new engineer understand this in 5 minutes?
4. **Security** — Any user input that isn't validated? Any secrets in code?
5. **Performance** — Any obvious N+1s, unbounded loops, or missing indexes?

## Severity Labels (use in comments)
- `Nit:` — Style, preference. Non-blocking.
- `Optional:` — Good idea but not required to merge.
- `Required:` — Must fix before merge.
- `Blocking:` — Fundamental problem, needs redesign.

## Change Size
- Ideal PR: ~100 lines changed
- If diff is >400 lines: suggest splitting before reviewing

## Exit Criteria (before SHIP)
- [ ] No `Required:` or `Blocking:` issues open
- [ ] Security axis reviewed
- [ ] Tests reviewed (not just "tests exist")
