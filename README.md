# 哲思屋（Philosophia）

> 用古希腊的辩论形式，通过多方哲学视角的交锋，逼近真理

## 项目愿景

哲思屋是一个**通用化的多智能体辩证法辩论系统**，它不是为辩论而辩论，而是通过辩论**逼近真理**。

这对应古希腊辩证法（διαλεκτική）的原初含义——通过问答对话揭露矛盾，最终在更高层次达成新的认识。

## 核心特性

| 特性 | 说明 |
|------|------|
| 🎭 **多视角辩论** | 整合多位哲学家的视角，让不同的思维框架在同一议题上交锋 |
| 📚 **证据驱动** | 各方主动搜索事实支撑，让论证建立在可查证的基础上 |
| ⚖️ **悬置存疑** | 无法判定的论点不强行定论，暂时悬置，保持认识的开放性 |
| 📖 **书记记录** | 辩论过程完整记录，形成可查阅的知识库 |
| 🔄 **持续蒸馏** | 不断添加新的哲学视角，丰富辩论的多样性 |

## 系统架构

```
用户输入议题
       ↓
   编排层（Orchestrator）
  ┌────────────────────────────┐
  │ • 注入搜索能力             │
  │ • 管理并行检索             │
  │ • 控制辩论流程             │
  └────────────────────────────┘
       ↓
┌─────────────────────────────────────────────┐
│             哲人Agent（Philosopher）          │
│  柏拉图 ↔ 黑格尔 ↔ 马克思 ↔ 亚里士多德...  │
└─────────────────────────────────────────────┘
       ↓
   书记Agent（Scribe）
  ┌────────────────────────────┐
  │ • 实时记录                 │
  │ • 管理证据池               │
  │ • 维护悬置区              │
  │ • 提炼新认识              │
  └────────────────────────────┘
       ↓
   持久化到 dialectike-records/
```

## 已集成的哲学家

- [x] **黑格尔**（hegel-perspective）— 辩证法大师
- [x] **马克思**（karl-marx）— 历史唯物主义批判
- [ ] **柏拉图**（plato-perspective）— 理想国对话录
- [ ] **亚里士多德**（aristotle-perspective）— 形而上学
- [ ] **苏格拉底**（socrates-perspective）— 产婆术追问
- [ ] **尼采**（nietzsche-perspective）— 价值重估

## 工作原理

### 辩论流程

```
正题（Thesis）      → 正题方提出观点
    ↓
反题（Antithesis）  → 反题方揭示矛盾
    ↓
矛盾展开            → 多方追问，挖掘深层张力
    ↓
综合（Synthesis）   → 提炼新认识（这是目的）
```

### 证据系统

每个论点都需要可查证的证据支撑：

```markdown
> 根据[IFR世界机器人报告2025]，2025年全球制造业自动化率达32%

📎 证据标注：
   - 来源：IFR World Robotics 2025
   - 可信度：⭐⭐⭐⭐⭐
```

### 悬置机制

当遇到无法判定的论点时，采用现象学的"悬置"（Epoché）方法：

```markdown
⚠️ 悬置项：AI是否具有"目的因"
原因：涉及形而上学问题，现有证据无法判定
```

## 技术栈

| 组件 | 技术选择 |
|------|---------|
| 核心框架 | WorkBuddy Agent Framework |
| 哲人Skill | 女娲(Nuwa)方法论蒸馏 |
| 搜索能力 | Web Search（并行检索） |
| 持久化 | Markdown + JSON |
| 版本控制 | Git + GitHub |

## 快速开始

### 安装哲人Skill

```bash
# 克隆仓库
git clone https://github.com/Liber1917/philosophia-debate.git
cd philosophia-debate

# 查看已集成的Skill
ls skills/
```

### 发起辩论

在WorkBuddy中加载dialectike-skill，输入辩题即可开始辩论。

## 项目结构

```
philosophia-debate/
├── docs/
│   ├── design/
│   │   └── ARCHITECTURE.md    # 详细架构设计文档
│   └── plans/                  # 实现计划
├── skills/
│   ├── dialectike/            # 辩证法编排核心
│   ├── hegel-perspective/     # 黑格尔视角
│   ├── karl-marx/            # 马克思视角
│   └── ...                    # 更多哲学家待添加
├── dialectike-records/        # 辩论记录存储
├── README.md
└── LICENSE
```

## 设计原则

1. **真理优先于胜负**：辩论的目的是逼近真理，不是分出胜负
2. **证据优于修辞**：空洞的言辞不如扎实的证据
3. **悬置优于独断**：承认认知的边界，保持开放
4. **记录优于遗忘**：每一次辩论都是知识的积累

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

## 参与贡献

欢迎提交Issue或Pull Request！特别欢迎以下贡献：

- 🌱 蒸馏新的哲学家视角Skill
- 🐛 修复问题或改进文档
- 💡 提出新的功能设计
- 📖 补充辩论案例

## 许可证

本项目采用 MIT 许可证。详见 [LICENSE](LICENSE) 文件。

---

*"真正的智慧不在于知道多少，而在于承认还有多少不知道。" — 苏格拉底*
