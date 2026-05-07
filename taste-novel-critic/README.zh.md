# taste-novel-critic

**网文品味诊断** — 网文（或 AI 生成的中长篇小说）品味诊断协议。预测读者会在哪里弃文、底层原因是什么 — **不是写作工具，是评审视角**。

> [English](./README.md) · [中文](./README.zh.md)（当前）

## 心智模型（4 个）

- **M1 · 塑料感识别** (Plastic Feel Detection)
- **M2 · 权力失衡陷阱** (Power Imbalance Trap)
- **M3 · 动机黑洞** (Motivation Black Hole)
- **M4 · 信息差操纵失手** (Information Asymmetry Mishandling)

加上：决策启发式、表达 DNA（风格指纹）、反模式、固定 4 维评论顺序、7 道质量验证诊断题。复合工作流（诊断后改写指引 / 章节 self-review / 大纲重构）作为 `references/composite-workflows.md` 提供。

## 触发场景

- 「这段我读不下去」
- 「这本网文为什么扑了」
- 「这段 AI 写的哪里不对」
- 「帮我看看这章读者会不会跑」

## 安装

挑**一种**语言。两个版本功能等价 — Claude Code 每个 skill 只读一份 `SKILL.md`。

### 中文版

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/taste-novel-critic/zh ~/.claude/skills/taste-novel-critic
rm -rf tmp
```

### English version

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/taste-novel-critic/en ~/.claude/skills/taste-novel-critic
rm -rf tmp
```

安装后重启 Claude Code session，让 skill discovery 重新扫描。

## 质量验证

Skill 自带 7 道诊断 Q&A，区分专家答和通用 LLM 答。验证步骤：

1. 开新的 Claude Code session
2. 用上面的触发场景之一
3. 把回答跟 `SKILL.md` 的 `## 质量验证` 板块的专家答对比
4. 通过标准：≥ 80% 接近专家答

## 许可

CC BY-NC-ND-4.0+ 含自定义加强条款。详见 [`zh/LICENSE.md`](./zh/LICENSE.md)。

| 字段 | 值 |
|---|---|
| Skill ID | `tnc-v1.0-20260507-yqcr` |
| 作者 | FantasyMax（幻想主义麦克斯）|
| 联系 | **HiFantasyMax**（社交平台） |
| 创建日期 | 2026-05-07 |
