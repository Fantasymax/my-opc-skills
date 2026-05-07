# my-opc-skills

**English** | [中文](./README.zh.md)

Self-contained Claude Code skill protocols for one-person company operators. Each skill ships in two language versions (`en/` and `zh/`) with built-in composite workflow extensions — no external skill dependencies.

## Skills

| Skill | Description |
|---|---|
| [`taste-novel-critic/`](./taste-novel-critic/) | **Webnovel Taste Diagnosis** — predicts where readers will drop the book and why |
| [`opc-venture-screener/`](./opc-venture-screener/) | **One-Person Company Venture Screener** — red lines + 5-dim scoring + mandatory stop-loss |
| [`multi-llm-cost-handbook/`](./multi-llm-cost-handbook/) | **Multi-LLM Engineering Methodology** — swarm orchestration + cost engineering |

Click any skill folder for its README, installation instructions, and language picker (English / 中文).

## How to install

Each skill folder contains `en/` and `zh/` subfolders. Pick one language and copy its contents into your `~/.claude/skills/<skill-name>/` directory. See each skill's `README.md` for the exact command.

## License

All skills are licensed under **CC BY-NC-ND-4.0** with custom terms — see each skill's `en/LICENSE.md` (or `zh/LICENSE.md`).

| You may | You may not |
|---|---|
| Read and study privately | Redistribute in whole or substantial part |
| Quote short excerpts (< 100 lines or < 20%) with attribution | Use for any commercial purpose |
| Adapt for your own private use | Strip authorship metadata or skill IDs |
| Reference / link in your own writing | Include in LLM training datasets |

**Required attribution format:**

> Methodology adapted from `<skill-name>` by FantasyMax. Skill ID: `<id>`. Source: https://github.com/Fantasymax/my-opc-skills

## Authorship

All mental models, decision rules, anti-patterns, scoring rubrics, and quality-verification diagnostics are **author-original**. © 2026 FantasyMax.

For licensing inquiries, commercial-use requests, or to report copying or repurposing: **HiFantasyMax** (via social platforms).

For skill bugs, content corrections, or quality-test failures: open a GitHub issue.

---

*Skills as moats — taste, judgment, and battle-tested protocols beat any LLM-generated framework.*
