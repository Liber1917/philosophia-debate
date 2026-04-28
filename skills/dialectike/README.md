# dialectike - 哲思屋辩证法编排器

> 通用化的多智能体辩证法辩论系统核心Skill

## 概述

dialectike 是哲思屋的核心编排Skill，负责：
- 编排辩论流程（正题→反题→矛盾展开→综合）
- 管理证据池和可信度评估
- 维护Epoché悬置区
- 生成综合报告并持久化

## 目录结构

```
dialectike/
├── SKILL.md           # 核心Skill定义
├── README.md          # 本文档
└── prompts/
    ├── opening.md     # 开题阶段提示词
    ├── scribe.md      # 书记记录模板
    ├── evidence.md    # 证据管理模板
    ├── arguments.md   # 哲人交互模板
    └── persistence.md  # 持久化模板
```

## 快速开始

在WorkBuddy中加载此Skill，然后说"开始辩论"即可启动。

## 核心流程

```
用户输入辩题
       ↓
   PHASE_1: 开题
  （解析辩题，选择哲人，分配角色）
       ↓
   PHASE_2: 正题
  （正题方陈述，搜索证据）
       ↓
   PHASE_3: 反题
  （反题方反驳，交叉检验）
       ↓
   PHASE_4: 矛盾展开
  （追问方挖掘深层张力）
       ↓
   PHASE_5: 综合
  （提炼新认识，生成报告）
       ↓
   PHASE_6: 持久化
  （保存辩论记录）
```

## 设计原则

1. **真理优先于胜负**
2. **证据优于修辞**
3. **悬置优于独断**
4. **记录优于遗忘**

## 参考

- 架构设计文档：`../../docs/design/ARCHITECTURE.md`
- 学术论文：[iMAD (2024)](https://arxiv.org/abs/2511.11306), [MAD-Logic (ICLR 2026)](https://openreview.net/forum?id=rdE9qxGfIv)
