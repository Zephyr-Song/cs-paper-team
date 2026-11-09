---
name: cs-paper-reading
display_name: CS 论文分工解读规范
description: Shared protocol for the CS Paper Reading Team. Defines evidence-grading tags ([E]/[C]/[I]/[NR]), the four-specialist division of labor, and the final report skeleton. Use whenever the team reads a computer-science paper, or when any specialist needs the grading rules or report structure. 当团队精读计算机论文、或任一成员需要证据分级规则 / 报告骨架时触发。
version: 1.0.0
tags: [cs-paper, evidence-audit, collaborative-team, reproducibility]
keywords: [论文解读, 证据分级, 分工协作, 可信度, 计算机论文]
---

# CS 论文分工解读规范

本规范供「CS 论文解读团」主理人与四位专家共用。

## 证据分级（强制）
每个关键断言后必须带标记，禁止混为一谈：

| 标记 | 含义 | 写法 |
|------|------|------|
| `[E]` | 论文有明确实证支撑 | 数字 + 出处（§4.2 / Table 3 / Fig. 5） |
| `[C]` | 作者的声称，但证据不足或仅口头断言 | 标注"作者声称，未见对应实验" |
| `[I]` | 你的推断（推断链要说出来） | "据此推断……，依据是……" |
| `[NR]` | 论文未报告 | 明确写"未报告"，禁止用常识补齐 |

**铁律：任何数字都必须能在原文找到出处，找不到就标 `[NR]`。绝不允许估算、补齐、编造。**

## 四维分工
| 专家 | 只看什么 | 不看什么 |
|------|---------|---------|
| 沈析构（方法） | 机制、数学直觉、创新点、复杂度、边界 | 实验真假、复现成本 |
| 严证衡（证据） | 结论—证据对齐、baseline、消融、显著性 | 方法机理拆解、复现成本 |
| 程复现（复现） | 数据/算力/代码、最小验证实验、坑点 | 方法拆解、实验真假 |
| 文溯源（文献） | 与已有工作真实差异、可引用点、后续 | 方法拆解、实验审计 |

## 高频陷阱（全员须知）
1. 把 Abstract 当结果（摘要数字常是最好看的 setting）
2. 把 ablation 掉点当因果证明（掉点≠是这个机制起作用）
3. 弱 baseline 上的大幅提升一文不值
4. 作者没报告的 setting 往往就是失败处
5. 在 7B 模型上的结论 ≠ 在 70B 上成立
6. 多阶段 pipeline 可能只是已知组件的工程串联

## 最终报告骨架（主理人汇编）
见 `references/report-template.md`。主理人负责：结论前置（BLUF）→ 四维度分章 → 总体可信度评分（高/中/低 + 理由）→「如果我要用这篇论文」。
