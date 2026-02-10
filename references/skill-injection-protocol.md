# Skill Injection Protocol

When delegating tasks to any agent (Task tool subagent or Agent Team teammate),
identify relevant skills and instruct the agent to read them.

IMPORTANT: Always instruct agents to read the full SKILL.md file. Never summarize
or paraphrase skill contents — this prevents information loss and interpretation bias.

## Protocol

Before dispatching any agent:

### Step 1: Define the task profile

Determine for the agent's task:
- **Technologies involved** (languages, frameworks, platforms)
- **Task type** (implementation, architecture, design, testing, marketing, deployment, etc.)
- **Project stack** from `.claude/saas-project/status.json` (`stack.frontend`, `stack.backend`)

### Step 2: Scan installed skills

```
FOR each directory in ~/.claude/skills/:
  READ SKILL.md frontmatter (name, description fields)
  EVALUATE: does this skill's purpose align with the agent's task?
  Match criteria (any of):
    - Skill name or description mentions a technology the task uses
    - Skill description matches the task type (e.g., testing skill for implementation tasks)
    - Skill is listed in the current phase's skill table AND is relevant to this specific subtask
  IF match → add to candidate list
```

### Step 3: Select and prioritize

From candidates, select the most relevant (max 4-5 per agent):
- Prioritize skills that directly match the task's primary technology or purpose
- Include methodology skills applicable during execution (e.g., a testing skill for an implementation task)
- Exclude skills the agent will not realistically use for its specific subtask
- If a skill is the SAME one the agent is executing, always include it

### Step 4: Identify relevant skill files

Skills may contain more than just SKILL.md. Many include reference files
(e.g., `references/`, examples, templates) that provide deeper guidance.

For each selected skill:
```
LIST files in ~/.claude/skills/{skill}/
IF the skill has reference files or subdirectories:
  EVALUATE which ones are relevant to the agent's specific task
  ADD relevant reference file paths to the reading list
```

Always include the skill's SKILL.md (entry point). Add reference files only
when they directly apply to the agent's task — not all references of every skill.

### Step 5: Instruct the agent to read the skills

For ALL agent types (subagents and teammates alike), include reading directives
in the agent's prompt. The agent must read the actual files — never pass summaries.

```
=== READ FIRST ===
Read: ~/.claude/skills/{skill-a}/SKILL.md
Read: ~/.claude/skills/{skill-a}/references/{relevant-file}.md
Read: ~/.claude/skills/{skill-b}/SKILL.md
=== END READ ===

=== TASK ===
[task details, context, requirements]
=== END TASK ===
```

## Notes

- If no relevant skills are found, dispatch without the READ FIRST block — not every task needs skills
- Run this protocol at delegation time, not at phase start (skills may be installed mid-phase)
- For parallel agents (frontend + backend), each agent gets different skills matching their domain
- Never summarize or paraphrase skill contents to agents — always instruct them to read the source files
- Include reference files only when directly relevant to the task — don't dump entire skill directories
