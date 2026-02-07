# Phase 1: Ideation

## Objective

Transform a raw idea into a structured, validated design document ready for business analysis.

## Skills

| Order | Skill | Purpose |
|-------|-------|---------|
| 1 | brainstorming | Explore the idea space, validate assumptions, define scope |

## Workflow

### Step 1: Invoke Brainstorming

Delegate to `brainstorming` with the user's initial idea. The skill handles intent exploration, problem mapping, alternative generation, convergence, and documentation.

### Step 2: Save Design Document

Ensure the output is saved to:
```
docs/plans/{project-name}-design.md
```

### Step 3: Commit

```
git add docs/plans/
git commit -m "docs: add design document for {project-name}"
```

## Exit Criteria

- [ ] Design document exists in `docs/plans/`
- [ ] Document covers problem, audience, solution, MVP features
- [ ] Document committed to the repository
- [ ] User has reviewed and approved the direction
