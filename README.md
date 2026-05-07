# my-opc-skills

**English** | [中文](./README.zh.md)

Three self-contained Claude Code skills for one-person company operators and AI engineering. Each skill is a methodology distilled into a Claude Code skill — author-original mental models, decision rules, and diagnostic Q&As.

## Repository Layout

```
my-opc-skills/
├── en/                  ← Install this for English Claude Code environment
│   ├── taste-novel-critic/
│   ├── opc-venture-screener/
│   └── multi-llm-cost-handbook/
└── zh/                  ← Install this for Chinese Claude Code environment
    ├── taste-novel-critic/
    ├── opc-venture-screener/
    └── multi-llm-cost-handbook/
```

Each language version is an independent set of skills with `SKILL.md` (the canonical filename Claude Code uses for discovery) and `LICENSE.md`. Pick **one** language to install — they are not meant to coexist in the same `.claude/skills/` directory.

---

## What's Inside

### 1. `taste-novel-critic` — Webnovel Taste Diagnosis

A taste-driven diagnostic protocol for webnovels (or AI-generated long-form fiction). Predicts where readers will drop the book and why — not a writing tool, a reviewer's lens. Four mental models, fixed four-dimension review order (Setting → Motivation → Antagonist → Execution).

**When to invoke:**
- "I can't get past Chapter 3 of this novel — why?"
- "Why did this webnovel flop?"
- "Diagnose this AI-generated chapter"

### 2. `opc-venture-screener` — One-Person Company Venture Screener

A decision protocol for solo founders. Red lines first → 5-dimensional scoring → mandatory stop-loss → resource allocation. Five mental models, fifteen hard red lines, ready-to-use scoring rubric. Specifically calibrated for the OPC mode: low-key high-margin, no real-name front-facing exposure, no game mechanics / self-built platforms / direct AI image generation.

**When to invoke:**
- "Should I pursue this idea?"
- "Score this venture for me"
- "What stop-loss conditions should I set?"

### 3. `multi-llm-cost-handbook` — Multi-LLM Engineering Handbook

Multi-LLM swarm orchestration and cost engineering methodology. **Roles ≠ Models** — define roles first, then pick model tiers. Token-verification gates, provider isolation ROI, schema-driven configuration. Deliberately does not recommend specific model names — teaches tier-and-judgment instead.

**When to invoke:**
- "Which model should I use for this AI agent?"
- "Pay-per-token or monthly subscription — which is cheaper?"
- "How do I avoid single-provider outage?"

---

## Installation

### Option 1 — Install all three skills (recommended)

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/en/* ~/.claude/skills/        # English version
# OR for Chinese: cp -r tmp/zh/* ~/.claude/skills/
rm -rf tmp
```

After installing, restart your Claude Code session for skill discovery to register the new skills.

### Option 2 — Install only one skill

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/en/taste-novel-critic ~/.claude/skills/    # pick the one you want
rm -rf tmp
```

### Per-project install

Replace `~/.claude/skills/` with `<your-project>/.claude/skills/` to scope skills to a single project.

---

## Verifying a Skill Works

Each skill ships with a `## Quality Verification` section in its `SKILL.md` containing 7–9 diagnostic Q&As.

1. Open a fresh Claude Code session
2. Use one of the trigger phrases listed above
3. Compare the response against the expert-answer patterns in the diagnostic section
4. Pass standard: ≥ 80% match to expert answers (not generic LLM answers)

If a skill scores below 80%, the SKILL.md likely needs stronger trigger signals — open a GitHub issue.

---

## License

All skills are licensed under **CC BY-NC-ND-4.0** with additional custom terms. See each skill's `LICENSE.md` for the full text.

| You may | You may not |
|---|---|
| Read and study privately | Redistribute in whole or substantial part |
| Quote short excerpts (< 100 lines or < 20%) with attribution | Use for any commercial purpose |
| Reference or link in your own writing | Create derivative works for redistribution |
| Adapt for your own private use | Strip authorship metadata or skill IDs |
| Discuss in mentorship or teaching contexts | Include in LLM training datasets |
| | Mimic > 50% of structure in competing skills |

**Required attribution format:**

> Methodology adapted from `<skill-name>` by FantasyMax. Skill ID: `<id>`. Source: https://github.com/Fantasymax/my-opc-skills

---

## Skill IDs

These are permanent fingerprints. Stripping or altering them violates the license.

| Skill | Fingerprint |
|---|---|
| taste-novel-critic | `tnc-v1.0-20260507-yqcr` |
| opc-venture-screener | `opcvs-v1.0-20260507-yqcr` |
| multi-llm-cost-handbook | `mllmh-v1.0-20260507-yqcr` |

---

## Authorship

The mental models, decision rules, anti-patterns, scoring rubrics, and expert-answer voices in these skills are **author-original**. © 2026 FantasyMax.

For licensing inquiries, commercial-use requests, or to report copying or repurposing: **HiFantasyMax** (via social platforms).

For skill bugs, content corrections, or quality-test failures: open a GitHub issue.

---

*Skills as moats — taste, judgment, and battle-tested protocols beat any LLM-generated framework.*
