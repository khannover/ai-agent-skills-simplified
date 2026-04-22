# Skill: Incremental Implementation

**Use when:** You're writing new code.

## When This Applies
- Any implementation task from the plan
- Adding a feature, endpoint, component, or module

## Process

1. **Pick one task** from the plan — the smallest unblocked slice
2. **Write the test first** — define what "working" means before coding (see `skills/test.md`)
3. **Implement just enough** to make the test pass
4. **Verify** — run tests, confirm the slice works end-to-end
5. **Commit** — one atomic commit per working slice
6. **Repeat** — pick the next task

## Constraints
- Do not implement multiple tasks at once
- Do not commit broken code
- Do not defer tests ("I'll add them after")
- Use feature flags for anything that touches production paths

## Exit Criteria (before moving to REVIEW)
- [ ] All planned tasks complete
- [ ] Tests pass for each slice
- [ ] No TODO comments left in critical paths
- [ ] Feature flag in place if feature is not fully ready
