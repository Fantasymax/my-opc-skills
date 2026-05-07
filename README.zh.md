# my-opc-skills

[**English**](./README.md) | 中文

幻想主义麦克斯（FantasyMax）的个人 Claude Code skills — 蒸馏自 20+ 年跨领域实战经验：网文鉴赏、一人公司运营、多模型工程。

每个 skill 提供两个语言版本：

- `SKILL.md`：中文，Claude Code skill discovery 的主入口
- `SKILL.en.md`：英文，国际读者的镜像文档

`LICENSE.md` 是法律文本，英文为唯一权威版本。

© 2026 幻想主义麦克斯 · 许可：CC BY-NC-ND-4.0+ 含自定义条款 · 联系：HiFantasyMax

---

## 包含内容

三个自包含的 skill：

### 1. [`taste-novel-critic`](./taste-novel-critic/) — 网文品味诊断官

20 年老读者的品味诊断 — 不是写作工具，而是评审视角。预测读者会在哪里弃文以及为什么。四个心智模型，固定四维诊断顺序（设定 → 诉求 → 对手 → 细节）。

**触发场景：**

- 「这段我读不下去」
- 「这本网文为什么扑了」
- 「这段 AI 写的哪里不对」

### 2. [`opc-venture-screener`](./opc-venture-screener/) — 一人公司 venture 筛选器

一人公司创始人的决策引擎。先扫红线 → 五维评分 → 强制写停损 → 资源分配。五个心智模型，十五条硬红线，开箱即用的评分卡。

**触发场景：**

- 「我有个新点子能不能做」
- 「帮我评一下这个 idea」
- 「停损条件应该怎么设」

### 3. [`multi-llm-cost-handbook`](./multi-llm-cost-handbook/) — 多模型工程血泪手册

多模型 swarm 编排 + 成本控制。**角色 ≠ 模型** — 先定义角色，再挑模型档位。Token 验证门禁、provider 隔离 ROI、schema-driven 配置。**故意不推荐具体模型名**（那些会过期），讲档位 + 判断准则。

**触发场景：**

- 「这个 AI 项目该用什么模型」
- 「按量计费还是包月划算」
- 「怎么避免单一 provider 宕机」

---

## 跟通用 skill 的区别

不是通用最佳实践，而是**作者原创的心智模型**，蒸馏自多年从业级实战经验：

- 每个心智模型都经过三重验证筛选：跨域复现 + 生成力 + 排他性
- 每个 skill 都自带 7-9 道诊断题，区分**专家答**和**通用 LLM 答**
- 所有敏感原始数据都已脱敏为抽象方法论 — skill 不带任何专有数字、项目代号、访谈对象姓名、竞品数据

---

## 安装

项目级：

```bash
cd <你的项目>/.claude/skills/
git clone https://github.com/Fantasymax/my-opc-skills.git
```

用户全局：

```bash
cd ~/.claude/skills/
git clone https://github.com/Fantasymax/my-opc-skills.git
```

clone 完成后重启 Claude Code session，让 skill discovery 重新扫描。

只装单个 skill：

```bash
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
mv tmp/taste-novel-critic .
rm -rf tmp
```

---

## 质量验证

每个 skill 在 `SKILL.md` 里都自带诊断题集。验证步骤：

1. 开新的 Claude Code session
2. 用上面的触发场景之一
3. 把回答跟诊断题里的专家答对比
4. 通过标准：≥ 80% 接近专家答（不是通用 LLM 答）

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

> 方法论引自幻想主义麦克斯（FantasyMax）的 `<skill-name>`，Skill ID: `<id>`，来源：https://github.com/Fantasymax/my-opc-skills

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

这些 skill 中的心智模型、决策规则、反模式和专家答声音都是**作者原创**，蒸馏自幻想主义麦克斯（FantasyMax）的私人实战档案 — 跨网文鉴赏、一人公司运营、多模型工程。

---

## 联系

许可咨询、商用授权、或举报盗用：**HiFantasyMax**（社交平台）。

Skill 报错、内容修正、质量验证失败：在 GitHub 提 issue。

---

*Skills as moats — 品味、判断和实战伤疤打败任何 LLM 生成的框架。*
