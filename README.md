# skills

Agent skills by [Danish Naseer](https://danishnaseer.tech) — AI engineer building agentic systems.

Each folder in this repo is an installable [Agent Skill](https://agentskills.io/) compatible with Claude Code, OpenCode, Codex, Cursor, and 70+ other agents.

## Install (one command)

```shell
# pick skills and agents interactively
npx skills add danishnaseer00/skills
```

Or install a specific skill directly:

```shell
npx skills add danishnaseer00/skills --skill paranoid-researcher -g -y
npx skills add danishnaseer00/skills --skill brutally-honest  -g -y
```

- `-g` — install globally (`~/.claude/skills/`, etc.) instead of project-only
- `-y` — skip confirmation prompts
- `--skill <name>` — install one skill; omit it to be prompted

Try a skill without installing it:

```shell
npx skills use danishnaseer00/skills@paranoid-researcher
```

Update installed skills later with `npx skills update paranoid-researcher`.

## Available skills

| Skill | Description |
|-------|-------------|
| [`brutally-honest`](./brutally-honest/) | Kills sycophancy. Verdict-first answers, load-bearing claims labeled `[fact]`/`[inference]`/`[speculation]`, research-backed results, holds its verdict under pressure without new evidence, zero fabricated sources, zero consolation. Triggers on "be honest", "no sugarcoating", "critique this", feedback requests. |
| [`paranoid-researcher`](./paranoid-researcher/) | Researches a question until nothing can break the answer. Claim ledger with provenance, traces every load-bearing claim to its primary source, searches in the negative voice, audits its own bias, and stops on saturation rather than vibes. Triggers on "research this", "deep dive", "fact-check", "due diligence", "don't trust the first answer", "keep researching until you're sure". |

## Adding new skills

New skills land here as top-level folders. Each contains a `SKILL.md` with valid frontmatter (`name` + `description`) and optional routed files under `references/`. Anyone can install any of them with:

```shell
npx skills add danishnaseer00/skills --skill <skill-name>
```

## License

MIT
