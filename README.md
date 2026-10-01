# Agent skills

Reusable [Agent Skills](https://agentskills.io/) for software engineering and productivity. Browse the [skill catalog](SKILLS.md) to find a skill.

| Directory | Skills |
|---|---|
| [`skills/engineering/`](skills/engineering/) | Planning, research, software design, implementation, testing, and code review. |
| [`skills/productivity/`](skills/productivity/) | Decision-making, agent instructions, writing, and model routing. |

## Install

### Requirements

- [Node.js](https://nodejs.org/) and npm.
- Git, with access to this Azure Repos repository. For a private repository, configure Git authentication for Azure DevOps before installing.
- A supported coding agent, such as OpenCode, GitHub Copilot, Codex, or Claude Code.

### Choose your agent

Use the command for your agent below, then select the skills you want from the CLI's list. Each command installs globally for your user account, making the skills available across projects.

**Keep the `--agent` parameter** to target your chosen agent explicitly and avoid additional installation attempts for agents such as PromptScript, which supports project-level installation only.

#### GitHub Copilot

Agent parameter: **`--agent github-copilot`**

```bash
npx skills@latest add grauzone-git/agent-skills --global --agent github-copilot
```

#### OpenCode

Agent parameter: **`--agent opencode`**

```bash
npx skills@latest add grauzone-git/agent-skills --global --agent opencode
```

#### OpenAI Codex

Agent parameter: **`--agent codex`**

```bash
npx skills@latest add grauzone-git/agent-skills --global --agent codex
```

#### Claude Code

Agent parameter: **`--agent claude-code`**

```bash
npx skills@latest add grauzone-git/agent-skills --global --agent claude-code
```

### Install for one project

Run your agent's command from the target project directory, remove `--global`, and choose **Project** when the CLI asks for the installation scope. Keep `--agent` unchanged.

### Install a specific skill

Add `--skill <name>` to select a skill directly. Add `--yes` to skip prompts. For example, this installs `research` for OpenCode in the current project:

```bash
npx skills@latest add grauzone-git/agent-skills --skill research --agent opencode --yes
```

Replace `research` with a skill name from the [catalog](SKILLS.md) and `opencode` with your agent's identifier above. Add `--global` for a user-level installation.

## Update or remove skills

Run these commands from the project where you installed the skills:

```bash
npx skills@latest update
npx skills@latest remove
```

The CLI guides you through choosing which installed skills to update or remove. Add `--global` to target a user-level installation.

## About skills

Each skill is a directory containing a `SKILL.md` file and, when needed, supporting files. Review a skill before installing it. Skills provide instructions to an AI agent and may reference tools or actions in your environment.

## References

- [Skill catalog](SKILLS.md)
- [Agent Skills specification](https://agentskills.io/specification)
- [Skills CLI](https://github.com/vercel-labs/skills)
- [Supported agents](https://github.com/vercel-labs/skills#supported-agents)
