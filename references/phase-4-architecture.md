# Phase 4: Technical Architecture

## Contents
- [Objective](#objective)
- [Skills](#skills)
- [Prerequisites](#prerequisites)
- [Workflow](#workflow)
- [Team Opportunity](#team-opportunity)
- [Exit Criteria](#exit-criteria)

## Objective

Define technical architecture, API contracts, and data models. Ensure stack-specific skills are available.

## Skills

| Order | Skill | Purpose |
|-------|-------|---------|
| 1 | find-skills | Discover stack-specific skills |
| 2 | backend-architect | API design, data models, infrastructure |
| 3 | ui-ux-pro-max | UI architecture, component hierarchy |

## Prerequisites

Stack must be defined before starting. Read `## Tech Stack` from project's `CLAUDE.md`. If absent, ask the user. Update `status.json` with chosen stack.

## Workflow

### Step 1: Stack-Specific Skill Discovery

```
FOR each technology in stack:
  RUN: npx skills find {technology}
  PRESENT results, OFFER install
```

### Step 2: Backend Architecture

Delegate to `backend-architect` with context from phases 1-3 and backend stack.

Save to `docs/architecture/backend-architecture.md`.

### Step 3: UI Architecture

Delegate to `ui-ux-pro-max` with PRD, API contracts from Step 2, and frontend stack.

Save to `docs/architecture/ui-architecture.md`.

### Step 4: API Contract Alignment

Verify backend contracts align with UI data needs. Resolve mismatches.

Save final contracts to `docs/architecture/api-contracts.md`.

## Team Opportunity

Phases 4+5 can run in parallel if separate frontend/backend stack:
```
Agent A: backend-architect → backend architecture
Agent B: ui-ux-pro-max → UI architecture + design system (phase 5)
Sync: API contract alignment after both complete
```

## Exit Criteria

- [ ] Backend architecture documented
- [ ] UI architecture documented
- [ ] API contracts defined and aligned
- [ ] Stack-specific skills discovered and installed
- [ ] All documents in `docs/architecture/`

## Notes

- API contracts are the critical handoff for Phase 6 parallel implementation
- Consider billing/metering requirements from Phase 2
