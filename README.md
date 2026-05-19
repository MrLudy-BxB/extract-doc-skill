# Extract Doc Skill

Turn docs, specs, workbooks, or source files into a clean installable AI-agent skill.

## Use This Repo

1. Clone this repo.
2. Open it with your AI coding agent.
3. Tell the agent to read `AGENT_KICKSTART.md`.
4. Give the agent your source docs, links, files, workbook, or API spec.
5. Ask the agent to create the skill.

That is the whole user workflow.

## What You Give The Agent

Examples:

- A docs URL.
- A GitHub docs folder.
- An OpenAPI spec.
- A PDF, Markdown file, or workbook.
- A folder of source docs.

## What The Agent Produces

The agent will create a project under:

```text
projects/<project-id>/
```

The final skill will be under:

```text
projects/<project-id>/skill/<skill-name>/
```

If you ask for a repo-local published copy, the agent can also copy it to:

```text
published-skills/skills/<skill-name>/
```

## For AI Agents

Start here:

```text
AGENT_KICKSTART.md
```

`AGENTS.md` is the short agent entrypoint. `AGENT_KICKSTART.md` has the full workflow.

## Engine Blueprint

Read `ENGINE.md` to understand the core thinking, architecture, and techniques behind this engine.
