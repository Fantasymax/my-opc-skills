# my-opc-skills

**English** (current) · [中文](./README.zh.md)

> Public release of FantasyMax's personal Claude Code skills, distilled from 20+ years of cross-domain experience: webnovel taste, one-person company operations, and multi-LLM engineering.

> 📖 Each skill ships with two language versions: `SKILL.md` (Chinese, primary) and `SKILL.en.md` (English). `LICENSE.md` is in English (legal canonical text).

**© 2026 FantasyMax · 幻想主义麦克斯** · Contact: **HiFantasyMax** · License: **CC BY-NC-ND-4.0+** with custom terms (see each skill's `LICENSE.md`)

---

## What's inside

Three skills, each self-contained (`SKILL.md` + `SKILL.en.md` + `LICENSE.md`):

### 1. [`taste-novel-critic/`](./taste-novel-critic/) · 网文品味诊断官
20-year webnovel reader's taste-driven critic. **Predicts where readers will drop off and why** — not a writing tool, a critic's view. 4 mental models, fixed 4-dimension review order (设定 → 诉求 → 对手 → 细节).

**Trigger phrases**: "这段我读不下去" / "这本网文为什么扑了" / "这段 AI 写的哪里不对"

### 2. [`opc-venture-screener/`](./opc-venture-screener/) · 一人公司 venture 筛选器
One-person company decision engine. **Red lines first → 5-dim scoring → mandatory stop-loss → resource allocation**. Specifically tuned for "low-key high-margin, no real-name exposure" mode.

**Trigger phrases**: "我有个新点子能不能干" / "帮我评一下这个 idea" / "停损条件应该怎么设"

### 3. [`multi-llm-cost-handbook/`](./multi-llm-cost-handbook/) · 多模型工程血泪手册
Multi-LLM swarm orchestration + cost engineering. **Roles ≠ Models** — define roles first, then pick model tiers. Token-verification gates, provider isolation ROI, schema-driven config. Deliberately does **not** recommend specific model names (those expire); teaches tier-and-judgment instead.

**Trigger phrases**: "这个 AI 项目该用什么模型" / "按量还是包月划算" / "怎么避免单一 provider 宕机"

---

## Why these are different from generic skills

These are not "general best practices" — they encode **author-original mental models** distilled from years of practitioner-level experience:

- Each mental model passes a **triple verification** standard: cross-domain reproduction + generative power + exclusivity
- Each skill includes a `## 质量验证` section with 7-9 diagnostic questions distinguishing **expert answers** from **generic LLM answers**
- All sensitive raw data has been **redacted into abstract methodology** — the skills carry no proprietary numbers, project codenames, real interviewee names, or competitor data

---

## Installation

### Claude Code (project-local)

```bash
cd <your-project>/.claude/skills/
git clone https://github.com/Fantasymax/my-opc-skills.git
# Or pick individual skills:
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
mv tmp/taste-novel-critic .
rm -rf tmp
```

### Claude Code (user-global)

```bash
cd ~/.claude/skills/
git clone https://github.com/Fantasymax/my-opc-skills.git
```

After cloning, restart your Claude Code session so skill discovery picks them up.

---

## Quality verification

Each skill ships with self-tests in its `SKILL.md`'s `## 质量验证` section. To verify a skill is working correctly:

1. Open a fresh Claude Code session
2. Use one of the trigger phrases above
3. Compare the response to the "expert answer" patterns in the quality tests
4. Pass standard: ≥ 80% match to expert answers (not generic LLM answers)

---

## License Summary

All skills are licensed under **CC BY-NC-ND-4.0** with **additional custom terms** (see each `LICENSE.md` for full text):

| ✅ You may | ❌ You may not |
|---|---|
| Read and study privately | Redistribute in whole or substantial part |
| Quote short excerpts (< 100 lines or < 20%) **with attribution** | Use for any commercial purpose |
| Reference / link in your own writing | Create derivative works for redistribution |
| Adapt for your own private use | Strip authorship metadata or skill IDs |
| Discuss in mentorship/teaching contexts | Include in LLM training datasets |
| | Mimic > 50% of structure in competing skills |

**Required attribution format**:

> Methodology adapted from `<skill-name>` by FantasyMax. Skill ID: `<id>`. Source: https://github.com/Fantasymax/my-opc-skills

---

## Skill IDs (for proof of authorship)

These IDs are permanent fingerprints. Stripping or altering them violates the license.

| Skill | Fingerprint |
|---|---|
| taste-novel-critic | `tnc-v1.0-20260507-yqcr` |
| opc-venture-screener | `opcvs-v1.0-20260507-yqcr` |
| multi-llm-cost-handbook | `mllmh-v1.0-20260507-yqcr` |

---

## Authorship

The mental models, decision rules, anti-patterns, and "expert answer" voices in these skills are **author-original**, distilled from FantasyMax's private practice archive across webnovel critique, one-person company operations, and multi-LLM engineering.

---

## Contact

For licensing inquiries, commercial use requests, or to report copying / repurposing: **HiFantasyMax** (via social platforms).

For skill bugs, content corrections, or quality test failures: open a GitHub issue.

---

*Building skills as moats — quality, taste, and battle-scars beat any LLM-generated framework.*
