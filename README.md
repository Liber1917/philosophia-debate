# 哲思屋（Philosophia）

> 用古希腊的辩论形式，通过多方哲学视角的交锋，逼近真理

## 项目愿景

哲思屋是一个**通用化的多智能体辩证法辩论系统**，不是为辩论而辩论，而是通过辩论**逼近真理**。

对应古希腊辩证法（διαλεκτική）的原初含义——通过问答对话揭露矛盾，最终在更高层次达成新的认识。

## 核心特性

| 特性 | 说明 |
|------|------|
| **多视角辩论** | 整合 10+ 位哲学家的视角，不同思维框架在同一议题上交锋 |
| **热插拔架构** | 每位哲人为独立 GitHub 仓库 Skill，通过 `philosopher-registry.json` 声明式注册，即加即用 |
| **证据驱动** | 各方主动搜索事实支撑，论证基于可查证的信息 |
| **悬置存疑** | 无法判定的论点不强行定论，暂时悬置 |
| **书记记录** | 辩论过程完整记录，形成可查阅的知识库 |
| **持续蒸馏** | 不断添加新的哲学视角，丰富辩论多样性 |

## 哲人天团

当前已注册 **11 位哲人**（其中 10 位已启用），每位对应一个独立的 GitHub 仓库作为 Skill 源。

| 哲人 | 仓库 | 视角领域 | 状态 |
|------|------|---------|:----:|
| 🔵 **黑格尔** | [hegel-perspective-skill](https://github.com/Liber1917/hegel-perspective-skill) | 辩证法 / 精神现象学 / 逻辑学 | ✅ |
| 🔴 **马克思** | [karl-marx-skill](https://github.com/Liber1917/karl-marx-skill) | 历史唯物主义 / 阶级批判 / 剩余价值 | ✅ |
| 🟣 **拉康** | [lacan-perspective-skill](https://github.com/Liber1917/lacan-perspective-skill) | 精神分析 / 无意识 / 大他者 / 对象 a | ✅ |
| 🟢 **维特根斯坦** | [witgenstein-perspective-skill](https://github.com/Liber1917/witgenstein-perspective-skill) | 语言游戏 / 家族相似性 / 规则悖论 | ✅ |
| 🟡 **齐泽克** | [zizek-perspective-skill](https://github.com/Liber1917/zizek-perspective-skill) | 意识形态批判 / 崇高客体 / 视差 | ✅ |
| 🔶 **列宁** | [lenin-perspective-skill](https://github.com/Liber1917/lenin-perspective-skill) | 革命理论 / 帝国主义 / 民主集中制 | ✅ |
| 🟤 **福柯** | [foucault-perspective-skill](https://github.com/Liber1917/foucault-perspective-skill) | 权力分析 / 谱系学 / 生命政治 | ✅ |
| ⚪ **葛兰西** | [gramsci-perspective-skill](https://github.com/Liber1917/gramsci-perspective-skill) | 霸权理论 / 阵地战 / 有机知识分子 | ✅ |
| 🔷 **德勒兹 & 加塔利** | [deleuze-guattari-perspective-skill](https://github.com/Liber1917/deleuze-guattari-perspective-skill) | 根茎 / 欲望机器 / 逃逸线 | ✅ |
| 🌾 **詹姆斯·C·斯科特** | [scott-perspective-skill](https://github.com/Liber1917/scott-perspective-skill) | 日常抵抗 / 隐蔽文本 / 道德经济 | ✅ |
| 🟠 **奈格里 & 哈特** | [negri-hardt-perspective-skill](https://github.com/Liber1917/negri-hardt-perspective-skill) | 帝国 / 诸众 / 共有 / 出走 | ✅ |
| 🔘 **柏拉图** | 待创建 | 理念论 / 洞穴寓言 | ❌ 待蒸馏 |

### 待蒸馏哲人

- [ ] **亚里士多德** — 形而上学 / 四因说 / 实践智慧
- [ ] **尼采** — 权力意志 / 价值重估 / 永恒轮回
- [ ] **阿多诺** — 否定辩证法 / 文化工业 / 非同一性
- [ ] **阿伦特** — 极权主义 / 行动 / 公共领域

## 系统架构

```
用户输入议题
       ↓
   编排层（Orchestrator — dialectike SKILL）
  ┌──────────────────────────────────────┐
  │ • 读取 philosopher-registry.json      │
  │ • 从远程（GitHub raw）加载已启用哲人   │
  │ • 管理并行辩论流程                      │
  │ • 控制轮次（正题 → 反题 → 综合）       │
  └──────────────────────────────────────┘
       ↓
┌──────────────────────────────────────────────┐
│           哲人 Agent（远程 SKILL）             │
│  黑格尔 ← 马克思 ← 拉康 ← 维特根斯坦 ← 齐泽克 │
│  列宁  ← 福柯   ← 葛兰西 ← 德勒兹&加塔利     │
│  斯科特 ← 奈格里&哈特 ← (更多待加入)         │
└──────────────────────────────────────────────┘
       ↓
   书记 Agent（Scribe）
  ┌────────────────────────────┐
  │ • 实时辩论记录             │
  │ • 管理证据池               │
  │ • 维护悬置区               │
  │ • 提炼新认识               │
  └────────────────────────────┘
       ↓
   持久化到 dialectike-records/
```

## 辩论流程

```
正题（Thesis）      → 正方提出核心主张
    ↓
反题（Antithesis）  → 反方揭示内在矛盾
    ↓
矛盾展开            → 多方追问，挖掘深层张力
    ↓
综合（Synthesis）   → 提炼新认识（这是目的）
```

每次辩论包含三轮（Round 1-3），围绕议题的不同维度展开递进式交锋。

## 辩论记录

| 日期 | 议题 | 参与哲人 |
|------|------|---------|
| 2026-04-29 | [技术与劳动解放与异化](dialectike-records/2026-04-29-technology-liberation-alienation/) | 黑格尔 / 马克思 / 拉康 |
| 2026-05-16 | [谱系学追问](dialectike-records/2026-05-16_round1-genealogy.md)（Round 1） | 福柯 / 马克思 / 斯科特 |
| 2026-05-16 | [宏观结构争论](dialectike-records/2026-05-16_round2-macro-structure.md)（Round 2） | 列宁 / 葛兰西 / 奈格里&哈特 |
| 2026-05-16 | [主体与语言](dialectike-records/2026-05-16_round3-subject-language.md)（Round 3） | 拉康 / 维特根斯坦 / 德勒兹&加塔利 / 齐泽克 |

## 证据系统

每个论点都需要可查证的证据支撑：

```markdown
> 根据[来源]，某数据/事实陈述

📎 证据标注：
   - 来源：出版物/报告链接
   - 可信度：⭐⭐⭐⭐⭐
```

### 悬置机制

遇到无法判定的论点时，采用现象学的"悬置"（Epoché）方法：

```markdown
⚠️ 悬置项：[争议命题]
原因：涉及[领域]问题，现有证据无法判定
```

## 项目结构

```
philosophia-debate/
├── philosopher-registry.json    # 核心配置：哲人注册中心
├── skills/
│   └── dialectike/              # 辩证法编排核心 Skill
│       ├── SKILL.md             # 编排器提示词
│       └── prompts/             # 各阶段提示词（开场/论证/证据/记录）
├── dialectike-records/          # 辩论记录存储
│   └── YYYY-MM-DD-{topic}/
│       ├── debate.md            # 辩论正文
│       ├── epoche.md            # 悬置项记录
│       ├── evidence.json        # 证据池
│       └── synthesis.md         # 综合认识
├── docs/
│   └── design/
│       └── ARCHITECTURE.md      # 详细架构设计
├── README.md
└── LICENSE
```

> **说明**：哲人 Skill 本身不存储在本地 `skills/` 目录中。它们作为独立的 GitHub 仓库远程托管，由 `philosopher-registry.json` 通过 raw URL 热插拔加载。本地仅保留辩论编排器（`dialectike`）。

## 技术栈

| 组件 | 技术选择 |
|------|---------|
| 核心框架 | WorkBuddy Agent Framework |
| 哲人 Skill | 独立 GitHub 仓库（raw SKILL.md 热插拔） |
| 搜索能力 | Web Search（并行检索） |
| 持久化 | Markdown + JSON |
| 版本控制 | Git + GitHub |

## 设计原则

1. **真理优先于胜负** — 辩论的目的是逼近真理，不是分出胜负
2. **证据优于修辞** — 论证必须建立在可查证的事实基础上
3. **悬置优于独断** — 承认认知的边界，保持开放性
4. **记录优于遗忘** — 每一次辩论都是知识的积累

## 快速开始

### 前置条件

- 安装 [WorkBuddy](https://www.codebuddy.cn/)
- 确保 WorkBuddy 具备 Web Search 能力

### 发起辩论

```bash
# 克隆仓库
git clone https://github.com/Liber1917/philosophia-debate.git
cd philosophia-debate

# 在 WorkBuddy 中加载 dialectike Skill
# 输入辩题，编排器会自动从远程加载所有已启用的哲人
```

### 添加新哲人

1. 创建一个新的 GitHub 仓库 `<哲人名>-perspective-skill`
2. 编写 `SKILL.md`，定义该哲人的视角立场、论证风格和核心概念
3. 在 `philosopher-registry.json` 中添加条目
4. 在 `_meta.autoDiscover.defaultPhilosophers` 中追加仓库名

## 参与贡献

欢迎提交 Issue 或 Pull Request！特别欢迎以下贡献：

- 🌱 蒸馏新的哲学家视角 Skill
- 🐛 修复问题或改进文档
- 💡 提出新的功能设计
- 📖 补充辩论案例

## 参考资源

### 学术论文
- [iMAD: Efficient Multi-Agent Debate for LLMs (2024)](https://arxiv.org/abs/2511.11306)
- [MAD-Logic: Multi-Agent Debate for Reasoning (ICLR 2026)](https://openreview.net/forum?id=rdE9qxGfIv)
- [Multi-LLM Debate: Framework, Principals, and Interventions (NeurIPS 2024)](https://proceedings.neurips.cc/paper_files/paper/2024/file/32e07a110c6c6acf1afbf2bf82b614ad-Paper-Conference.pdf)

### 开源项目
- [Skytliang/Multi-Agents-Debate](https://github.com/Skytliang/Multi-Agents-Debate)

### 哲学方法论
- 古希腊辩证法：苏格拉底对话法、柏拉图对话录
- 黑格尔辩证法：正题-反题-合题
- 胡塞尔现象学：Epoché（悬置）

## 许可证

本项目采用 MIT 许可证。详见 [LICENSE](LICENSE) 文件。

---

*"真正的智慧不在于知道多少，而在于承认还有多少不知道。" — 苏格拉底*
