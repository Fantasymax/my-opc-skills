# taste-novel-critic

**Webnovel Taste Diagnosis** — A diagnostic protocol for webnovels (or AI-generated long-form fiction). Predicts where readers will drop the book and why — not a writing tool, a critic's lens.

> [English](./README.md) (current) · [中文](./README.zh.md)

## Mental models (4)

- **M1 · Plastic Feel Detection** (塑料感识别)
- **M2 · Power Imbalance Trap** (权力失衡陷阱)
- **M3 · Motivation Black Hole** (动机黑洞)
- **M4 · Information Asymmetry Mishandling** (信息差操纵失手)

Plus: decision heuristics, expression DNA (style fingerprint), anti-patterns, fixed 4-dimension review order, 7 quality-verification diagnostics. Composite workflows (post-diagnosis rewrite guide / chapter self-review / outline restructuring) shipped as `references/composite-workflows.md`.

## Trigger phrases

- "I can't get past Chapter 3 of this novel — why?"
- "Why did this webnovel flop?"
- "Diagnose this AI-generated chapter"
- "这段我读不下去" / "这本网文为什么扑了"

## Installation

Pick **one** language. Both versions are functionally equivalent — Claude Code only reads `SKILL.md` once per skill.

### English version

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/taste-novel-critic/en ~/.claude/skills/taste-novel-critic
rm -rf tmp
```

### 中文版

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/taste-novel-critic/zh ~/.claude/skills/taste-novel-critic
rm -rf tmp
```

After installing, restart your Claude Code session for skill discovery.

## Quality verification

The skill ships with 7 diagnostic Q&As distinguishing expert answers from generic LLM answers. To verify:

1. Open a fresh Claude Code session
2. Use one of the trigger phrases above
3. Compare against the expert-answer patterns in `SKILL.md`'s `## Quality Verification` section
4. Pass standard: ≥ 80% match

## License

CC BY-NC-ND-4.0+ with custom terms. See [`en/LICENSE.md`](./en/LICENSE.md).

| Field | Value |
|---|---|
| Skill ID | `tnc-v1.0-20260507-yqcr` |
| Author | FantasyMax |
| Contact | **HiFantasyMax** (via social platforms) |
| First creation | 2026-05-07 |
