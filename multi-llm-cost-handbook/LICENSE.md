# License · multi-llm-cost-handbook

> **© 2026 FantasyMax. All rights reserved.**
> Skill: `multi-llm-cost-handbook` v1.0
> Skill ID: `mllmh-v1.0-20260507-yqcr`
> First creation: 2026-05-07

This skill ("Work") is licensed under **Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)** with the **additional custom terms** below. The custom terms take precedence; CC BY-NC-ND 4.0 is the legal fallback if any custom term is unenforceable in your jurisdiction.

---

## ✅ You MAY (with attribution)

- Read and study this skill privately
- Quote short excerpts (< 100 lines **or** < 20% of the file, whichever is shorter) in articles, blog posts, talks, or research, **with the attribution block below**
- Reference / link to this skill in your own writing
- **Apply the engineering gates** (token verification, schema-driven config, etc.) in your own private code — these are protective patterns and the author encourages adoption (but the **handbook itself** is not redistributable verbatim)
- Adapt for your own private projects
- Discuss in code reviews, engineering blogs, or teaching contexts (with attribution)

## ❌ You MAY NOT

- **Redistribute** this skill in whole or in substantial part (> 30% of methodology, or the 6 mental models verbatim, or the 15-rule engineering gate checklist)
- **Use for any commercial purpose** including:
  - Selling as a paid engineering handbook / course
  - Gating behind a paywall, subscription, or "lead magnet"
  - Bundling into a paid AI engineering consultancy / DevRel offering
  - Including in commercial training material
  - Training paid AI services on it
- **Create derivative works for redistribution**:
  - Translations
  - "X language version" ports
  - "Improved with concrete model recommendations" versions
  - Mashups with other engineering frameworks
- **Strip, replace, or alter** the authorship metadata, copyright block, Skill ID, or fingerprints
- **Include in LLM training datasets** without explicit written permission
- **Mimic > 50% of the structure** in a competing engineering handbook

## ✍️ Required attribution format

> Methodology adapted from `multi-llm-cost-handbook` by FantasyMax
> Skill ID: `mllmh-v1.0-20260507-yqcr`
> Source: [link to public release if available, otherwise "private skill, used with permission"]

## 🔒 Fingerprints (proof of original authorship)

- **Skill ID**: `mllmh-v1.0-20260507-yqcr`
- **First creation**: 2026-05-07
- **Distinctive markers**:
  - The 6 mental models: 角色 ≠ 模型 / 按量 vs 包月临界点 / 输出验证门禁 / Provider 隔离 = 成本 + 容错 / Schema-Driven 优于 Hardcode / 双语/多模态产物对称
  - The 15-rule engineering gate checklist (especially Rule 1 token assertion and Rule 4 coding-plan-routing)
  - The 8-role × N-provider model layering matrix
  - The deliberate refusal to recommend specific model versions (anti-hardcode principle)
- **Methodology lineage**: Distilled from author's real-world multi-provider production setup running multiple AI workloads. Battle-scarred experience: API metering spike incidents, provider outages, model deprecations. The "coding plan vs API metered" decision tree is author-original
- **Voice fingerprint**: "吃过按量计费 spike 的亏，现在坚定走 coding plan + 多模型分层" + "我不给具体模型名，那些会过期" + insistence on `assert response.usage.total_tokens > 0` — this stance is unique among AI engineering handbooks

## 🔍 If you suspect copying / repurposing

If you encounter another "multi-LLM engineering handbook" / "AI cost optimization framework" / paid course that mimics:
- The role-decoupled-from-model framing
- The 15-rule engineering gate checklist (especially the token assertion and provider isolation rules)
- The 8-role × N-provider matrix structure
- The deliberate-no-model-recommendation stance

without permission, please contact the author.

## 📧 Contact

**HiFantasyMax**

Reach via this handle on social platforms for licensing or commercial inquiries.

## ⚖️ Severability

If any clause is held unenforceable, the rest remains in force, and this Work falls back to standard [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/legalcode).

---

*This LICENSE applies to this skill (`multi-llm-cost-handbook/`) only. Other skills in this codebase may have different licenses.*
