# multi-llm-cost-handbook

**Multi-LLM Engineering Methodology** — Multi-LLM swarm orchestration + cost engineering. **Roles ≠ Models** — define roles first, then pick model tiers. Token-verification gates, provider isolation ROI, schema-driven configuration. Deliberately does **not** recommend specific model names — teaches tier-and-judgment instead (model recommendations expire fast).

> [English](./README.md) (current) · [中文](./README.zh.md)

## Mental models (6)

- M1 · Roles ≠ Models
- M2 · Pay-per-token vs Coding Plan Threshold
- M3 · Output Verification Gates
- M4 · Provider Isolation = Cost + Resilience
- M5 · Schema-Driven > Hardcode
- M6 · Bilingual / Multi-Modal Output Symmetry

Plus: 8-role × N-provider tier mapping, **15-rule engineering gate checklist**, cost trade-off heuristics, anti-patterns, 9 quality-verification diagnostics.

## Trigger phrases

- "Which model should I use for this AI agent?"
- "Pay-per-token or monthly subscription — which is cheaper?"
- "How do I avoid single-provider outage?"
- "How do I verify whether LLM output is real?"
- "这个 AI 项目该用什么模型"
- "按量计费还是包月划算"

## Installation

Pick **one** language. Both versions are functionally equivalent.

### English version

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/multi-llm-cost-handbook/en ~/.claude/skills/multi-llm-cost-handbook
rm -rf tmp
```

### 中文版

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/multi-llm-cost-handbook/zh ~/.claude/skills/multi-llm-cost-handbook
rm -rf tmp
```

After installing, restart your Claude Code session for skill discovery.

## Quality verification

The skill ships with 9 diagnostic Q&As distinguishing battle-tested engineering protocols from generic SDK tutorials. Pass standard: ≥ 80% match.

## License

CC BY-NC-ND-4.0+ with custom terms. See [`en/LICENSE.md`](./en/LICENSE.md).

| Field | Value |
|---|---|
| Skill ID | `mllmh-v1.0-20260507-yqcr` |
| Author | FantasyMax |
| Contact | **HiFantasyMax** (via social platforms) |
| First creation | 2026-05-07 |
