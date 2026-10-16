# Pome coach skills

Skills that let your coding agent drive [Pome](https://pome.sh): register an agent, suggest and author tasks, verify a seed, and run the exam.

## Install

Install all six skills:

```bash
npx skills add pome-sh/skills --skill '*'
```

Connect the Pome control MCP when you use hosted skills or MCP tools:

```bash
claude mcp add --transport http pome https://mcp.pome.sh/mcp
```

The installation includes each skill's `references/` directory. For CLI-only use, start with `pome init` and `pome docs getting-started`.

## Route requests

| Skill | Use it for |
| --- | --- |
| [`pome`](https://github.com/pome-sh/skills/tree/main/skills/pome) | Select the correct Pome workflow. |
| [`pome-intake`](https://github.com/pome-sh/skills/tree/main/skills/pome-intake) | Register a managed agent and report twin coverage. |
| [`pome-suggest-tasks`](https://github.com/pome-sh/skills/tree/main/skills/pome-suggest-tasks) | Propose test tasks from a registered local agent. |
| [`pome-author-task`](https://github.com/pome-sh/skills/tree/main/skills/pome-author-task) | Write and validate a graded task. |
| [`pome-verify-seed`](https://github.com/pome-sh/skills/tree/main/skills/pome-verify-seed) | Check that a seed creates a valid and useful initial state. |
| [`pome-run-task`](https://github.com/pome-sh/skills/tree/main/skills/pome-run-task) | Run a verified task and report the result. |

What each skill does: [docs.pome.sh/docs/coach-skills](https://docs.pome.sh/docs/coach-skills).

## Issues and security

This repository is generated from Pome's private repository and synced one way, so pull requests are not accepted here. Open an issue to report a bug. Report a security problem privately through this repository's Security tab.
