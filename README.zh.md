# my-opc-skills

[**English**](./README.md) · 中文（当前）

> FantasyMax 个人 Claude Code skills 公开版，蒸馏自 20+ 年跨领域实战经验：网文鉴赏、一人公司运营、多模型工程。

**© 2026 FantasyMax · 幻想主义麦克斯** · 联系：**HiFantasyMax** · License: **CC BY-NC-ND-4.0+** 含自定义条款（见每个 skill 的 `LICENSE.md`）

---

## 包含 3 个 Skill

每个 skill 自包含（`SKILL.md` 中文 + `SKILL.en.md` 英文 + `LICENSE.md`）：

### 1. [`taste-novel-critic/`](./taste-novel-critic/) · 网文品味诊断官
20 年网文老读者的品味诊断 — **不是写作工具，是评审视角**：预测读者会在哪里弃文、为什么。4 个心智模型（塑料感识别 / 权力失衡陷阱 / 动机黑洞 / 信息差操纵失手）+ 固定 4 维评论顺序（设定 → 诉求 → 对手 → 细节）。

**触发话术**：「这段我读不下去」/「这本网文为什么扑了」/「这段 AI 写的哪里不对」

### 2. [`opc-venture-screener/`](./opc-venture-screener/) · 一人公司 venture 筛选器
一人公司决策引擎。**红线优先 → 5 维评分 → stop-loss 必填 → 资源配置**。专属于"低调发大财、不露脸"模式。

**触发话术**：「我有个新点子能不能干」/「帮我评一下这个 idea」/「停损条件应该怎么设」

### 3. [`multi-llm-cost-handbook/`](./multi-llm-cost-handbook/) · 多模型工程血泪手册
多模型 swarm 编排 + 成本控制。**角色 ≠ 模型** — 先定义角色，再挑模型档位。Token 验证门禁 + provider 隔离 ROI + schema-driven 配置。**故意不推荐具体模型名**（那些会过期），讲档位 + 判断准则。

**触发话术**：「这个 AI 项目该用什么模型」/「按量还是包月划算」/「怎么避免单一 provider 宕机」

---

## 这些 Skill 与通用 skill 的区别

不是"通用最佳实践"，是**作者原创心智模型**，蒸馏自多年从业级别经验：

- 每个心智模型经过**三重验证**筛选：跨域复现 + 生成力 + 排他性
- 每个 skill 含 `## 质量验证` 板块，7-9 道诊断题区分**专家答**和**通用 LLM 答**
- 所有敏感原始数据已**脱敏为抽象方法论** — skill 不带任何专有数字、项目代号、访谈对象姓名、竞品数据

---

## 安装

### Claude Code（项目级）

```bash
cd <你的项目>/.claude/skills/
git clone https://github.com/Fantasymax/my-opc-skills.git
# 或挑选单个 skill：
git clone https://github.com/Fantasymax/my-opc-skills.git tmp
mv tmp/taste-novel-critic .
rm -rf tmp
```

### Claude Code（用户全局）

```bash
cd ~/.claude/skills/
git clone https://github.com/Fantasymax/my-opc-skills.git
```

clone 后重启 Claude Code session 让 skill discovery 重新扫描。

---

## 质量验证

每个 skill 在 `SKILL.md` 的 `## 质量验证` 板块都自带诊断题。验证步骤：

1. 开新 Claude Code session
2. 用上面的触发话术
3. 把回答跟 quality tests 里的"专家答"对比
4. 通过标准：≥ 80% 接近专家答

---

## License 摘要

所有 skill 走 **CC BY-NC-ND-4.0** + **自定义加强条款**（详见每个 `LICENSE.md`）：

| ✅ 可以 | ❌ 不可以 |
|---|---|
| 私下学习 | 整体或重大部分再分发 |
| 短引用（< 100 行 或 < 20%）+ 署名 | 任何商业用途 |
| 在自己的写作 / 帖子里引用 + 链接 | 衍生再分发 |
| 自己私用改编 | 移除署名 / Skill ID |
| 在 mentorship / 教学场景讨论 | 进 LLM 训练集 |
| | 仿制 > 50% 结构 |

**引用格式**：

> 方法论引自 FantasyMax 的 `<skill-name>`。Skill ID: `<id>`。来源：https://github.com/Fantasymax/my-opc-skills

---

## Skill ID 指纹（举证用）

这些 ID 是**永久指纹**。剥离或修改它们违反 license。

| Skill | Fingerprint |
|---|---|
| taste-novel-critic | `tnc-v1.0-20260507-yqcr` |
| opc-venture-screener | `opcvs-v1.0-20260507-yqcr` |
| multi-llm-cost-handbook | `mllmh-v1.0-20260507-yqcr` |

---

## 原创性声明

这些 skill 中的心智模型、决策规则、反模式和"专家答"声音是**作者原创**，蒸馏自 FantasyMax 的私人实战档案 — 跨网文鉴赏、一人公司运营、多模型工程。

---

## 联系

License 询问 / 商用咨询 / 举报盗用：**HiFantasyMax**（社交平台）

Skill bug / 内容修正 / 质量验证失败：在 GitHub 开 issue。

---

*Skills as moats — 品味、判断和实战伤疤打败任何 LLM 生成的框架。*
