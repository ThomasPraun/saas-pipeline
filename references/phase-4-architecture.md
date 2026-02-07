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
| 1 | ux-flow-designer | User flow diagrams, screen maps, HTML wireframes |
| 2 | find-skills | Discover stack-specific skills |
| 3 | backend-architect | API design, data models, infrastructure |
| 4 | ui-ux-pro-max | UI architecture, component hierarchy |

## Prerequisites

Stack must be defined before starting. Read `## Tech Stack` from project's `CLAUDE.md`. If absent, ask the user. Update `status.json` with chosen stack.

## Workflow

### Step 1: UX Flows

Delegate to `ux-flow-designer` with PRD from phase 3. Produces user flow diagrams, screen maps, and HTML wireframes.

Save to `docs/architecture/ux-flows/`.

### Step 2: Stack-Specific Skill Discovery

```
FOR each technology in stack:
  RUN: npx skills find {technology}
  PRESENT results, OFFER install
```

### Step 3: Backend Architecture

Delegate to `backend-architect` with context from phases 1-3, UX flows from Step 1, and backend stack.

Save to `docs/architecture/backend-architecture.md`.

### Step 4: UI Architecture

Delegate to `ui-ux-pro-max` with PRD, UX flows from Step 1, API contracts from Step 3, and frontend stack.

Save to `docs/architecture/ui-architecture.md`.

### Step 5: API Contract Alignment

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

- [ ] User flow diagrams and screen maps created
- [ ] Backend architecture documented
- [ ] UI architecture documented
- [ ] API contracts defined and aligned
- [ ] Stack-specific skills discovered and installed
- [ ] All documents in `docs/architecture/`

## Notes

- API contracts are the critical handoff for Phase 6 parallel implementation
- Consider billing/metering requirements from Phase 2
