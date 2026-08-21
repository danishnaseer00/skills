# skills

Agent skills by [Danish Naseer](https://danishnaseer.tech) — AI engineer building agentic systems.

Each folder in this repo is an installable [Agent Skill](https://agentskills.io/) compatible with Claude Code, OpenCode, Codex, Cursor, and 70+ other agents.

## Install (one command)

```shell
npx skills add danishnaseer00/skills --skill brutally-honest -g -y
```

Omit flags for an interactive picker (choose skill + target agent).

- `-g` — install globally (`~/.claude/skills/`, etc.) instead of project-only
- `-y` — skip confirmation prompts

## Available skills

| Skill | Description |
|-------|-------------|
| [`brutally-honest`](./brutally-honest/) | Kills sycophancy. Verdict-first answers, every claim labeled `[fact]`/`[inference]`/`[speculation]`, research-backed results, zero fabricated sources, zero consolation. Triggers on "be honest", "no sugarcoating", "critique this", feedback requests. |

## Adding new skills

New skills land here as top-level folders. Each contains a `SKILL.md` with valid frontmatter (`name` + `description`) and optional routed files under `references/`. Anyone can install any of them with:

```shell
npx skills add danishnaseer00/skills --skill <skill-name>
```

## License

MIT
