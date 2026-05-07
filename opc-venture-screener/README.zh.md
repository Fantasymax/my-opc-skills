# opc-venture-screener

**一人公司 venture 筛选器** — 一人公司创始人的决策协议。**先扫红线 → 五维评分 → 强制停损 → 资源分配**。专为 OPC 模式定制：低调高利、不真实身份露出、不做游戏机制 / 自建平台 / AI 直接生图。

> [English](./README.md) · [中文](./README.zh.md)（当前）

## 心智模型（5 个）

- M1 · 不可逆红线优先级 > LTV
- M2 · HITL 周时间 = 隐性成本
- M3 · 单月毛利 vs 时间投入
- M4 · 亲手做过的事 = 最强地基
- M5 · 停损指标先于启动条件

加上：5 维评分卡、**15 条硬红线**、决策启发式、反模式 vs 通用 startup 评估对比。完整 OPC 工作流（机会发现 / 商业化路径 / 执行治理）作为 `references/composite-workflows.md` 提供。

## 触发场景

- 「我有个新点子能不能做」
- 「帮我评一下这个 idea」
- 「停损条件应该怎么设」
- 「这个 venture 该不该启动」

## 安装

挑**一种**语言。两个版本功能等价。

### 中文版

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/opc-venture-screener/zh ~/.claude/skills/opc-venture-screener
rm -rf tmp
```

### English version

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/opc-venture-screener/en ~/.claude/skills/opc-venture-screener
rm -rf tmp
```

安装后重启 Claude Code session。

## 质量验证

Skill 自带 8 道诊断题，区分 OPC 专属决策与通用 startup 评估。通过标准：≥ 80% 接近专家答。

## 许可

CC BY-NC-ND-4.0+ 含自定义加强条款。详见 [`zh/LICENSE.md`](./zh/LICENSE.md)。

| 字段 | 值 |
|---|---|
| Skill ID | `opcvs-v1.0-20260507-yqcr` |
| 作者 | FantasyMax（幻想主义麦克斯）|
| 联系 | **HiFantasyMax**（社交平台） |
| 创建日期 | 2026-05-07 |
