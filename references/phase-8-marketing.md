# Phase 8: Marketing

## Contents
- [Objective](#objective)
- [Skills](#skills)
- [Prerequisites](#prerequisites)
- [Workflow](#workflow)
- [Team Opportunity](#team-opportunity)
- [Exit Criteria](#exit-criteria)

## Objective

Create all marketing assets: landing page, email sequences, strategy, CRO, and promotional video.

## Skills

All 5 are independent — run in any order or in parallel.

| Skill | Purpose |
|-------|---------|
| landing-page-copywriter | Landing page copy (PAS/AIDA) |
| email-sequence | Drip campaigns, onboarding, nurture |
| marketing-ideas | 140+ proven strategies and tactics |
| conversion-optimization-expert | CRO analysis, A/B test ideas |
| remotion-best-practices | Promotional video (React/Remotion) |

## Prerequisites

**Required:** `.claude/product-marketing-context.md` (created in Phase 3).

All marketing skills reference this file. If missing, go back to Phase 3 and run `product-marketing-context`.

## Workflow

Delegate to each skill with `.claude/product-marketing-context.md` as context. Each produces independent output.

Save all to:
```
docs/marketing/
  landing-page-copy.md
  email-sequences.md
  marketing-strategy.md
  cro-recommendations.md
  video/
```

Optional second pass: `conversion-optimization-expert` reviews `landing-page-copywriter` output.

## Team Opportunity

Best phase for parallel execution — all 5 skills are fully independent:
```
Agent A: landing-page-copywriter
Agent B: email-sequence
Agent C: marketing-ideas
Agent D: conversion-optimization-expert
Agent E: remotion-best-practices
```

No synchronization needed.

## Exit Criteria

- [ ] Landing page copy with headlines, value props, CTAs
- [ ] At least one email sequence (welcome/onboarding)
- [ ] Marketing strategy with prioritized tactics
- [ ] CRO recommendations documented
- [ ] Promotional video project created (optional)
- [ ] All outputs in `docs/marketing/`

## Notes

- Remotion requires React/TypeScript. If not using React, run as standalone project or skip
