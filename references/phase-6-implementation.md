# Phase 6: Implementation

## Contents
- [Objective](#objective)
- [Skills](#skills)
- [Workflow](#workflow) (Steps 1-6)
- [Team Opportunity](#team-opportunity)
- [Exit Criteria](#exit-criteria)

## Objective

Build the product following TDD, code review, and verification practices.

## Skills

| Order | Skill | Purpose |
|-------|-------|---------|
| 1 | writing-plans | Break architecture into implementation plan |
| 2 | using-git-worktrees | Create isolated workspace |
| 3a | executing-plans | Execute with review checkpoints |
| 3b | subagent-driven-development | Alternative: parallel execution |
| 4 | test-driven-development | Tests before code |
| 5 | systematic-debugging | Structured debugging |
| 6 | requesting-code-review | Package changes for review |
| 7 | receiving-code-review | Process feedback with rigor |
| 8 | verification-before-completion | Verify before claiming done |
| 9 | finishing-a-development-branch | Merge, PR, or cleanup |

## Workflow

### Step 1: Write Implementation Plan

Delegate to `writing-plans` with architecture docs, design system, and PRD.

### Step 2: Set Up Workspace

Delegate to `using-git-worktrees` for isolated feature branch.

### Step 3: Execute

Choose one:
- **`executing-plans`** — step by step with review checkpoints (solo work)
- **`subagent-driven-development`** — parallel execution (independent tasks)

During execution, apply continuously:
- `test-driven-development` — before writing any implementation code
- `systematic-debugging` — when tests fail or unexpected behavior occurs

### Step 4: Code Review

1. `requesting-code-review` — package changes, document what and why
2. `receiving-code-review` — verify suggestions before applying

If issues found: fix → re-test → re-review.

### Step 5: Verify

Delegate to `verification-before-completion`. Do not proceed until it passes.

### Step 6: Finish Branch

Delegate to `finishing-a-development-branch`.

## Team Opportunity

Frontend + Backend in parallel when API contracts exist:
```
Agent A: Frontend → implement UI against contracts (mock responses)
Agent B: Backend → implement API endpoints matching contracts
Sync: integration testing after both complete
```

Each agent follows the same inner loop:
```
writing-plans → git-worktrees → executing-plans
  + TDD + debugging (during)
  → code-review → verification → finish-branch (after)
```

## Exit Criteria

- [ ] All planned features implemented
- [ ] All tests pass (unit, integration)
- [ ] Code review completed and approved
- [ ] Verification confirms all acceptance criteria
- [ ] Branch merged or PR created

## Notes

- Never skip TDD — catches design issues early
- If implementation reveals architecture issues, go back to Phase 4
