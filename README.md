# saas-pipeline

A [Claude Code skill](https://skills.sh/) that orchestrates 28 skills across 8 phases to take a SaaS project from idea to launch.

## What it does

`saas-pipeline` is a **coordinator** — it never executes work itself. Instead, it:

- Tracks your project's current phase in `.claude/saas-project/status.json`
- Routes you to the right skill based on where you are
- Manages transitions between phases with exit criteria
- Offers parallel execution with agent teams when possible

## The 8 Phases

| # | Phase | Skills | Key Output |
|---|-------|--------|------------|
| 1 | Idea | brainstorming | Design document |
| 2 | Business | business-model-canvas, startup-business-models | Canvas + pricing |
| 3 | Product | product-manager-toolkit, product-marketing-context | PRD + marketing context |
| 4 | Architecture | backend-architect, ui-ux-pro-max | Architecture + API contracts |
| 5 | Design | ui-ux-pro-max | Design system |
| 6 | Implementation | writing-plans, git-worktrees, TDD, code-review, verification + 6 more | Working, tested code |
| 7 | Deployment | docker-expert | Dockerfile + docker-compose |
| 8 | Marketing | landing-page-copywriter, email-sequence, marketing-ideas, CRO, remotion | Marketing assets |

## Install

```bash
npx skills add <repo-url>@saas-pipeline -g -y
```

## Usage

Invoke in any project:

```
/saas-pipeline
```

The coordinator will:
1. Initialize a new project (if none exists)
2. Show the dashboard with current progress
3. Suggest the next skill to run
4. Auto-install missing skills as needed

### Common commands

| Command | What happens |
|---------|-------------|
| `/saas-pipeline` | Auto-route to next action |
| `/saas-pipeline status` | Show visual dashboard |
| `/saas-pipeline go to phase 4` | Jump to a specific phase |
| `/saas-pipeline team` | Evaluate parallel execution options |

## Stack-agnostic

The skill reads your tech stack from your project's `CLAUDE.md` (`## Tech Stack` section). If no stack is defined, it asks before Phase 4 (Architecture).

It dynamically discovers stack-specific skills using `find-skills` — no hardcoded stack assumptions.

## Agent Teams

Three opportunities for parallel execution:

1. **Phases 4+5** — Architecture + Design in parallel (separate frontend/backend)
2. **Phase 6** — Frontend + Backend implementation in parallel (when API contracts exist)
3. **Phase 8** — All 5 marketing skills simultaneously (fully independent)

## Structure

```
saas-pipeline/
├── SKILL.md                          # Coordinator logic (router, state, phases)
└── references/
    ├── install-commands.md           # Skill install commands (loaded on demand)
    ├── phase-1-idea.md               # Ideation workflow
    ├── phase-2-business.md           # Business model workflow
    ├── phase-3-product.md            # Product definition workflow
    ├── phase-4-architecture.md       # Architecture workflow
    ├── phase-5-design.md             # Design system workflow
    ├── phase-6-implementation.md     # Implementation workflow
    ├── phase-7-deployment.md         # Deployment workflow
    └── phase-8-marketing.md          # Marketing workflow
```

## License

MIT
