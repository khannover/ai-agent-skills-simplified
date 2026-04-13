# Skill: Shipping & Launch

**Use when:** Code is reviewed and you're preparing to deploy.

## When This Applies
- Merging to main / production branch
- Tagging a release
- Deploying to any environment

## Pre-Ship Checklist
- [ ] All tests pass on CI
- [ ] No secrets or credentials in the diff
- [ ] Feature flags set correctly for this environment
- [ ] Rollback plan exists (can you revert in < 5 minutes?)
- [ ] Monitoring/alerting covers the new code path
- [ ] Dependent services notified if API contract changed

## Deployment Process
1. **Merge** — squash or merge commit, clean history
2. **Watch** — monitor error rates and key metrics for 15 minutes post-deploy
3. **Verify** — smoke test the critical path in production
4. **Flag off** — if using feature flags, schedule flag removal

## Rollback Trigger (do this immediately if):
- Error rate increases > 1% above baseline
- P95 latency doubles
- Any data integrity issue detected

## Exit Criteria
- [ ] Deploy confirmed healthy (no alerts fired)
- [ ] Smoke test passed
- [ ] Ticket/issue marked done
