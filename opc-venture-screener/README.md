# opc-venture-screener

**One-Person Company Venture Screener** — A decision protocol for solo founders. Red lines first → 5-dimensional scoring → mandatory stop-loss → resource allocation. Specifically calibrated for the OPC mode: low-key high-margin, no real-name front-facing exposure, no game mechanics / self-built platforms / direct AI image generation.

> [English](./README.md) (current) · [中文](./README.zh.md)

## Mental models (5)

- M1 · Irreversible Red Lines > LTV
- M2 · HITL Weekly Hours = Hidden Cost
- M3 · Monthly Gross Profit vs Time Investment
- M4 · Hands-on Past Experience = Strongest Foundation
- M5 · Stop-loss Indicators Precede Launch Conditions

Plus: 5-dimension scoring rubric, **15 hard red lines**, decision heuristics, anti-patterns vs generic startup evaluation. Complete OPC workflow (opportunity discovery / commercialization path / execution governance) shipped as `references/composite-workflows.md`.

## Trigger phrases

- "Should I pursue this idea?"
- "Score this venture for me"
- "What stop-loss conditions should I set?"
- "我有个新点子能不能做"
- "帮我评一下这个 idea"

## Installation

Pick **one** language. Both versions are functionally equivalent.

### English version

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/opc-venture-screener/en ~/.claude/skills/opc-venture-screener
rm -rf tmp
```

### 中文版

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/opc-venture-screener/zh ~/.claude/skills/opc-venture-screener
rm -rf tmp
```

After installing, restart your Claude Code session for skill discovery.

## Quality verification

The skill ships with 8 diagnostic Q&As distinguishing OPC-specific decisions from generic startup evaluation. Pass standard: ≥ 80% match.

## License

CC BY-NC-ND-4.0+ with custom terms. See [`en/LICENSE.md`](./en/LICENSE.md).

| Field | Value |
|---|---|
| Skill ID | `opcvs-v1.0-20260507-yqcr` |
| Author | FantasyMax |
| Contact | **HiFantasyMax** (via social platforms) |
| First creation | 2026-05-07 |
