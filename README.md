# my-opc-skills

**English** | [中文](./README.zh.md)

Personal Claude Code skills authored by FantasyMax — practitioner know-how distilled from 20+ years across webnovel critique, one-person company operations, and multi-LLM engineering.

Each skill ships in two languages:
- `SKILL.md` — Chinese, primary canonical for Claude Code skill discovery
- `SKILL.en.md` — English, mirror documentation for international readers

`LICENSE.md` is the legal canonical text in English.

© 2026 FantasyMax · License: CC BY-NC-ND-4.0+ with custom terms · Contact: HiFantasyMax

---

## What's Inside

Three self-contained skills:

### 1. [`taste-novel-critic`](./taste-novel-critic/) — Webnovel Taste Diagnosis

A 20-year reader's taste-driven critic. Predicts where readers will drop off and why — not a writing tool, a critic's lens. Four mental models, fixed four-dimension review order (Setting → Motivation → Antagonist → Execution).

**When to invoke:**
- "I can't get past Chapter 3 of this novel — why?"
- "Why did this webnovel flop?"
- "Diagnose this AI-generated chapter"

### 2. [`opc-venture-screener`](./opc-venture-screener/) — One-Person Company Venture Screener

A decision engine for solo founders. Red lines first → 5-dimensional scoring → mandatory stop-loss → resource allocation. Five mental models, fifteen hard red lines, ready-to-use scoring rubric.

**When to invoke:**
- "Should I pursue this idea?"
- "Score this venture for me"
- "What stop-loss conditions should I set?"

### 3. [`multi-llm-cost-handbook`](./multi-llm-cost-handbook/) — Multi-LLM Engineering Handbook

Multi-LLM swarm orchestration and cost engineering. **Roles ≠ Models** — define roles first, then pick model tiers. Token-verification gates, provider isolation ROI, schema-driven configuration. Deliberately does not recommend specific model names — teaches tier-and-judgment instead.

**When to invoke:**
- "Which model should I use for this AI agent?"
- "Pay-per-token or monthly subscription — which is cheaper?"
- "How do I avoid single-provider outage?"

---

## Why These Are Different

These are not generic best practices. They encode author-original mental models distilled from years of practitioner-level experience:

- Each mental model passes a triple-verification standard: cross-domain reproduction, generative power, and exclusivity
- Each skill includes 7-9 diagnostic questions distinguishing expert answers from generic LLM answers
- All sensitive raw data is redacted into abstract methodology — no proprietary numbers, project codenames, real interviewee names, or competitor data

---

## Installation

Project-local:

```bash
cd <your-project>/.claude/skills/
git clone https://github.com/Fantasymax/my-opc-skills.git
```

User-global:

```bash
cd ~/.claude/skills/
git clone https://github.com/Fantasymax/my-opc-skills.git
```

After cloning, restart your Claude Code session for skill discovery to pick up the new skills.

To install only one skill:

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
mv tmp/taste-novel-critic .
rm -rf tmp
```

---

## Quality Verification

Each skill ships with diagnostic Q&As inside its `SKILL.md`. To verify a skill is working:

1. Open a fresh Claude Code session
2. Use one of the trigger phrases above
3. Compare the response against the expert-answer patterns in the diagnostic section
4. Pass standard: ≥ 80% match to expert answers (not generic LLM answers)

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

The mental models, decision rules, anti-patterns, and expert-answer voices in these skills are author-original, distilled from FantasyMax's private practice archive across webnovel critique, one-person company operations, and multi-LLM engineering.

---

## Contact

For licensing inquiries, commercial-use requests, or to report copying or repurposing: **HiFantasyMax** (via social platforms).

For skill bugs, content corrections, or quality-test failures: open a GitHub issue.

---

*Skills as moats — taste, judgment, and battle-scars beat any LLM-generated framework.*
