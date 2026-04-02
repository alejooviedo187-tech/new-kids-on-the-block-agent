# New Kids on the Block Agent — CLAUDE.md

This repo contains a Salesforce expert agent system for Claude Code. Each agent is named after a New Kids on the Block band member and specializes in a Salesforce domain.

## Project Structure

```
.claude/
  agents/
    manager.agent.md   # Routes questions to the right specialist
    donnie.agent.md    # Salesforce Data Cloud / Data 360
    joey.agent.md      # Salesforce AI & Agentforce
    jordan.agent.md    # General CRM, Marketing Cloud, platform & integrations
    jon.agent.md       # Slack
    danny.agent.md     # Service Cloud
    nkotb-fans.agent.md  # NKOTB band history & trivia
```

## Agent Files

Each agent is defined as a Markdown file in `.claude/agents/` with frontmatter fields:

- `name` — agent identifier used for `@`-mentions
- `description` — one-line summary used for routing decisions
- `tools` — tools the agent has access to (e.g., `read`, `search`, `web`, `agent`)
- `model` — model to use (all agents use `sonnet`)
- `user-invocable` — whether users can invoke the agent directly with `@name`
- `agents` — (manager only) list of subagents the manager can delegate to

## Making Changes

- To modify an agent's persona, expertise, or boundaries, edit the markdown body of the relevant `.claude/agents/*.agent.md` file.
- To adjust routing logic, edit `manager.agent.md`.
- To add a new specialist, create a new `.agent.md` file and add the agent name to the `agents` list in `manager.agent.md`.
- Agent descriptions in frontmatter are used by the manager for routing — keep them accurate and specific.

## Conventions

- All agents use the `sonnet` model.
- Agent personas match the NKOTB band member's personality — preserve the character voice when editing.
- Agents should not speculate about platform capabilities or present beta features as GA.
