# attack-protection

A checklist skill for AI coding agents. It makes the agent write, or review, code that resists eight attacks: XSS, exposed API routes, exposed API keys, an open database, SQL injection, missing rate limits, prompt injection and hallucinated packages. Before finishing, the agent walks the eight checks against the code it touched and reports each one as OK, FIXED or RISK, with file and line.

## Install

For Claude Code, copy the skill folders into your personal skills directory:

```bash
git clone https://github.com/orenatobr/attack-protection.git
mkdir -p ~/.claude/skills
cp -R attack-protection/skills/* ~/.claude/skills/
```

Start a new Claude Code session. Skills load from the `description` in each `SKILL.md`, so they trigger on their own and can also be called by name.

Other agents: each skill is a folder with a `SKILL.md` (YAML frontmatter plus Markdown). Tools that read the Agent Skills format can load `skills/` as it is. For the rest, paste the body of the `SKILL.md` into the agent's instruction file.

## Usage

Invoke `/attack-protection`, optionally with a file, diff or path to audit. It also triggers on its own when the agent writes code that handles user input, HTML, API routes, secrets, databases, LLM calls or dependencies.

## Requirements

Nothing beyond an agent that loads skills.

## Related skills

Pairs well with `programming-best-practices`, which points to it for secret handling in logs.

## What is in this repo

| Path | Purpose |
|------|---------|
| `skills/attack-protection/` | The `attack-protection` skill. |
| `CHANGELOG.md` | Notable changes, in Keep a Changelog format. |
| `AGENTS.md` | Rules for AI agents that edit this repo. |

## Contributing

`main` is protected: changes land through a pull request with one approval. See [AGENTS.md](AGENTS.md) for the conventions.

## License

MIT, see [LICENSE](LICENSE).
