# cs-paper-team · CS 论文解读团

> WorkBuddy 专家团（Team 型）。由一名主理人 + 四位专家**分工协作**精读计算机论文：从方法机理、实验证据、系统复现、领域文献四个维度拆解，并给出**可信度分级**的最终报告。

- **团队名**：CS 论文解读团（CS Paper Reading Team）
- **主理人**：论衡（Lun Heng）· CS 论文解读总编
- **形态**：专家团（Team 型），分类 `02-Engineering`
- **适用**：计算机全领域论文（系统 / ML / 网络 / 数据库 / PL / HCI …）

## 团队成员（各管一块）

| 成员 | 花名 | 负责维度 |
|------|------|---------|
| `cs-paper-team-lead` | 论衡 | 建团队、拆解任务、汇编最终报告 |
| `method-analyst` | 沈析构 | **方法机理**：算法/架构拆解、创新点真伪、复杂度与边界 |
| `evidence-auditor` | 严证衡 | **实验证据**：结论—证据对齐、baseline 公平性、消融/显著性审计 |
| `repro-engineer` | 程复现 | **系统复现**：算力/数据/代码盘点、最小验证实验、坑点 |
| `lit-surveyor` | 文溯源 | **领域文献**：与已有工作真实差异、可引用点、后续空间 |

## 它怎么工作（SOP）

1. **建团队**：主理人建立本次解读团队。
2. **定位**：主理人抽取标题/摘要/图表，产出全局上下文包（不下结论）。
3. **四专家并行**：把论文派给四位专家，各自独立分析。
4. **交叉校验 + 汇编**：主理人收齐四份产出，做一致性检查并整合。
5. **最终报告**：结论前置（BLUF）→ 四维度分章 → 总体可信度评分 →「如果我要用这篇论文」。

预设三种编排：全量精读（默认）/ 方法+证据聚焦 / 复现+文献聚焦。

## 核心差异化：证据分级（防幻觉）

所有断言带标记：`[E]` 实证 / `[C]` 作者声称但证据不足 / `[I]` 推断 / `[NR]` 未报告。
数字必须标原文出处（§/Table/Fig），找不到标 `[NR]`，**绝不编造**。

## 试试这样问我

1. 帮我用专家团精读这篇 CS 论文（附 PDF / 链接 / arXiv ID），四人分工出完整解读与可信度评估
2. 这篇论文的方法到底新在哪？实验是否真支撑结论？从方法和证据两路帮我拆解
3. 这篇能复现吗？它和哪几篇工作真正相关？给我复现路径和文献定位

## 安装到 WorkBuddy

专家团必须放在 WorkBuddy 的专家目录下才会被加载：

```bash
# 1. 克隆到专家目录
git clone https://github.com/Zephyr-Song/cs-paper-team.git \
  "$WORKBUDDY_CONFIG_DIR/plugins/marketplaces/my-experts/plugins/cs-paper-team"

# 2. 注册（使其出现在专家中心）
python3 scripts/register_expert.py \
  "$WORKBUDDY_CONFIG_DIR/plugins/marketplaces/my-experts/plugins/cs-paper-team"
```

> `scripts/` 指 WorkBuddy 内置的 `expert-manager` 技能目录；注册脚本会校验并把专家写入 `marketplace.json`。

## 头像

`avatars/` 下为程序化生成的占位头像（非 AI 绘图），统一蓝紫色调。如需替换，要求：PNG/JPG、512×512 px、单张 ≤ 500KB。

## 目录结构

```
cs-paper-team/
├── .codebuddy-plugin/plugin.json
├── agents/
│   ├── cs-paper-team-team-lead.md     # 主理人：SOP + 成员清单 + 路由
│   ├── method-analyst.md              # 方法机理拆解
│   ├── evidence-auditor.md            # 实验证据审计
│   ├── repro-engineer.md              # 系统复现评估
│   └── lit-surveyor.md                # 领域文献定位
├── skills/cs-paper-reading/           # 共享规范：证据分级 + 报告骨架
│   ├── SKILL.md
│   └── references/report-template.md
├── avatars/*.png
├── settings.json
├── LICENSE
└── README.md
```

## License

MIT
