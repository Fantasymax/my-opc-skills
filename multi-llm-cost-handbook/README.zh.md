# multi-llm-cost-handbook

**多模型工程方法论** — 多模型 swarm 编排 + 成本工程。**角色 ≠ 模型** — 先定义角色，再挑模型档位。Token 验证门禁、provider 隔离 ROI、schema-driven 配置。**故意不推荐具体模型名** — 讲档位 + 判断准则（具体模型推荐过期太快）。

> [English](./README.md) · [中文](./README.zh.md)（当前）

## 心智模型（6 个）

- M1 · 角色 ≠ 模型
- M2 · 按量计费 vs 包月临界点
- M3 · 输出验证门禁
- M4 · Provider 隔离 = 成本 + 容错
- M5 · Schema-Driven > 硬编码
- M6 · 双语 / 多模态产物对称

加上：8 角色 × N provider 档位映射、**15 条工程门禁清单**、成本权衡启发式、反模式、9 道质量验证诊断题。

## 触发场景

- 「这个 AI 项目该用什么模型」
- 「按量计费还是包月划算」
- 「怎么避免单一 provider 宕机」
- 「怎么验证 LLM 输出真不真」

## 安装

挑**一种**语言。两个版本功能等价。

### 中文版

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/multi-llm-cost-handbook/zh ~/.claude/skills/multi-llm-cost-handbook
rm -rf tmp
```

### English version

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/multi-llm-cost-handbook/en ~/.claude/skills/multi-llm-cost-handbook
rm -rf tmp
```

安装后重启 Claude Code session。

## 质量验证

Skill 自带 9 道诊断题，区分实战工程师协议与通用 SDK 教程。通过标准：≥ 80% 接近专家答。

## 许可

CC BY-NC-ND-4.0+ 含自定义加强条款。详见 [`zh/LICENSE.md`](./zh/LICENSE.md)。

| 字段 | 值 |
|---|---|
| Skill ID | `mllmh-v1.0-20260507-yqcr` |
| 作者 | FantasyMax（幻想主义麦克斯）|
| 联系 | **HiFantasyMax**（社交平台） |
| 创建日期 | 2026-05-07 |
