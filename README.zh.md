# my-opc-skills

[**English**](./README.md) | 中文

一人公司运营者的自包含 Claude Code skill 协议。每个 skill 都有中英两个语言版本（`en/` 和 `zh/`），含内置的复合工作流扩展 — 无外部 skill 依赖。

## Skills

| Skill | 简介 |
|---|---|
| [`taste-novel-critic/`](./taste-novel-critic/) | **网文品味诊断** — 预测读者会在哪里弃文以及为什么 |
| [`opc-venture-screener/`](./opc-venture-screener/) | **一人公司 venture 筛选器** — 红线 + 五维评分 + 强制停损 |
| [`multi-llm-cost-handbook/`](./multi-llm-cost-handbook/) | **多模型工程方法论** — swarm 编排 + 成本工程 |

点击任一 skill 文件夹查看 README、安装说明、语言版本选择（中文 / English）。

## 如何安装

每个 skill 文件夹下都有 `en/` 和 `zh/` 子文件夹。挑一种语言，把对应子文件夹的内容复制到你的 `~/.claude/skills/<skill-name>/` 目录。具体命令见每个 skill 的 `README.zh.md`。

## 许可

所有 skill 都使用 **CC BY-NC-ND-4.0** + 自定义加强条款 — 见每个 skill 的 `en/LICENSE.md`（或 `zh/LICENSE.md`）。

| 允许 | 禁止 |
|---|---|
| 私下学习 | 整体或重大部分再分发 |
| 短引用（< 100 行 或 < 20%）+ 署名 | 任何商业用途 |
| 私用改编 | 移除署名 / Skill ID |
| 在自己的写作或链接里引用 | 进 LLM 训练集 |

**引用格式：**

> 方法论引自 FantasyMax 的 `<skill-name>`，Skill ID: `<id>`，来源：https://github.com/Fantasymax/my-opc-skills

## 原创性声明

所有心智模型、决策规则、反模式、评分卡、质量验证诊断题都是**作者原创**。© 2026 FantasyMax（幻想主义麦克斯）。

许可咨询、商用授权、举报盗用：**HiFantasyMax**（社交平台）。

Skill 报错、内容修正、质量验证失败：在 GitHub 提 issue。

---

*Skills as moats — 品味、判断和实战验证的协议打败任何 LLM 生成的框架。*
