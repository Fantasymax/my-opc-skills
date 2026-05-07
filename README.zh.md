# my-opc-skills

[**English**](./README.md) | 中文

三个自包含的 Claude Code skills，专为一人公司运营者和 AI 工程师打造。每个 skill 都是一套方法论协议，含原创心智模型、决策规则、诊断题集。

## 仓库结构

```
my-opc-skills/
├── en/                  ← 英文 Claude Code 环境装这套
│   ├── taste-novel-critic/
│   ├── opc-venture-screener/
│   └── multi-llm-cost-handbook/
└── zh/                  ← 中文 Claude Code 环境装这套
    ├── taste-novel-critic/
    ├── opc-venture-screener/
    └── multi-llm-cost-handbook/
```

每种语言版本都是独立的 skill 集合，含 `SKILL.md`（Claude Code 识别 skill 的标准文件名）和 `LICENSE.md`。**只装一种语言**，两种不应同时存在于同一个 `.claude/skills/` 目录。

---

## 包含内容

### 1. `taste-novel-critic` — 网文品味诊断官

网文（或 AI 生成的中长篇小说）品味诊断协议。**不评分文笔**，而是**预测读者会在哪里弃文、底层原因是什么**。四个心智模型，固定四维诊断顺序（设定 → 诉求 → 对手 → 细节）。

**触发场景：**

- 「这段我读不下去」
- 「这本网文为什么扑了」
- 「这段 AI 写的哪里不对」

### 2. `opc-venture-screener` — 一人公司 venture 筛选器

一人公司创始人的决策协议。**先扫红线 → 五维评分 → 强制写停损 → 资源分配**。五个心智模型，十五条硬红线，开箱即用的评分卡。专为 OPC 模式定制：低调高利、不真实身份露出、不做游戏机制 / 自建平台 / AI 直接生图。

**触发场景：**

- 「我有个新点子能不能做」
- 「帮我评一下这个 idea」
- 「停损条件应该怎么设」

### 3. `multi-llm-cost-handbook` — 多模型工程方法论

多模型 swarm 编排 + 成本控制方法论。**角色 ≠ 模型** — 先定义角色，再挑模型档位。Token 验证门禁、provider 隔离 ROI、schema-driven 配置。**故意不推荐具体模型名**（那些会过期），讲档位 + 判断准则。

**触发场景：**

- 「这个 AI 项目该用什么模型」
- 「按量计费还是包月划算」
- 「怎么避免单一 provider 宕机」

---

## 安装

### 方式一 — 安装全部 3 个 skill（推荐）

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/zh/* ~/.claude/skills/        # 中文版本
# 或安装英文版：cp -r tmp/en/* ~/.claude/skills/
rm -rf tmp
```

安装后重启 Claude Code session，让 skill discovery 重新扫描。

### 方式二 — 只装其中一个 skill

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
cp -r tmp/zh/taste-novel-critic ~/.claude/skills/    # 挑你想要的
rm -rf tmp
```

### 项目级安装

把 `~/.claude/skills/` 替换为 `<你的项目>/.claude/skills/`，让 skill 仅对该项目生效。

---

## 验证 skill 是否生效

每个 skill 在 `SKILL.md` 里都有 `## 质量验证` 板块，含 7–9 道诊断题。

1. 开新的 Claude Code session
2. 用上面的触发场景之一
3. 把回答跟诊断题里的"专家答"对比
4. 通过标准：≥ 80% 接近专家答（不是通用 LLM 答）

如果通过率不到 80%，可能是 SKILL.md 的触发信号不够强 — 提 GitHub issue。

---

## 许可

所有 skill 都使用 **CC BY-NC-ND-4.0** + 自定义加强条款。完整条款见每个 skill 的 `LICENSE.md`。

| 允许 | 禁止 |
|---|---|
| 私下学习与研究 | 整体或重大部分再分发 |
| 短引用（< 100 行 或 < 20%）+ 署名 | 任何商业用途 |
| 在自己的写作或链接里引用 | 衍生再分发 |
| 私用改编 | 移除署名 / Skill ID |
| 在导师或教学场景讨论 | 进 LLM 训练集 |
| | 仿制 > 50% 的结构 |

**引用格式：**

> 方法论引自 FantasyMax 的 `<skill-name>`，Skill ID: `<id>`，来源：https://github.com/Fantasymax/my-opc-skills

---

## Skill 指纹

下列 ID 是永久指纹。剥离或修改它们等同于违反许可。

| Skill | 指纹 |
|---|---|
| taste-novel-critic | `tnc-v1.0-20260507-yqcr` |
| opc-venture-screener | `opcvs-v1.0-20260507-yqcr` |
| multi-llm-cost-handbook | `mllmh-v1.0-20260507-yqcr` |

---

## 原创性声明

这些 skill 中的心智模型、决策规则、反模式、评分卡、专家答声音都是**作者原创**。© 2026 FantasyMax。

许可咨询、商用授权、举报盗用：**HiFantasyMax**（社交平台）。

Skill 报错、内容修正、质量验证失败：在 GitHub 提 issue。

---

*Skills as moats — 品味、判断和实战验证的协议打败任何 LLM 生成的框架。*
