# Skill: Testing & Verification

**Use when:** Proving that something works (or debugging why it doesn't).

## When This Applies
- After implementing any slice
- When a bug is reported
- Before any review or merge

## Test Pyramid (target ratios)
- **Unit (80%)** — pure logic, no I/O, fast
- **Integration (15%)** — service boundaries, DB, API contracts
- **E2E (5%)** — critical user paths only

## Process (for new code)
1. Write test → watch it fail (red)
2. Write minimum code → make it pass (green)
3. Refactor → keep tests green

## Process (for debugging)
1. **Reproduce** — write a test that fails with the bug
2. **Localize** — narrow the failing scope (binary search the stack)
3. **Fix** — change the minimum code needed
4. **Guard** — the reproducing test is now a regression test

## Exit Criteria
- [ ] Tests exist for every behavior change
- [ ] All tests pass
- [ ] No `// TODO: test this` comments
- [ ] Bug fixes include a regression test
