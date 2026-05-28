---
title: "FragDockRL: A Reinforcement Learning Method for Fragment-Based Ligand Design via Building Block Assembly and Tethered Docking"
title_zh: FragDockRL：一种基于构建块组装和拴系对接的片段配体设计强化学习方法
authors: "Hong, S. H., Kim, H., Kim, S., Kang, S."
date: 2026-05-13
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.12.670002v2.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 使用强化学习和系留对接的片段基配体设计方法
tldr: 计算分子设计在组合化学空间探索中常受合成约束限制。本文提出FragDockRL，结合基于合成子的虚拟合成与系留对接，利用强化学习基于对接评分奖励搜索配体分子。该方法在预先定义的核心结构指导下，从可合成砌块组装分子，并在特定靶标案例中展现了高效寻优能力。该框架为结构基的片段式配体设计提供了一种实用解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 使用强化学习和系留对接的片段基配体设计方法。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
在合成约束下高效探索组合化学空间仍是计算分子设计的核心挑战。本文提出FragDock分子设计框架，该框架结合基于构建块（BB）的虚拟合成与由预定义核心结构引导的拴系对接。FragDock通过已知化学反应从可合成构建块组装分子来定义结构化搜索空间，并利用限制核心结合姿态的拴系对接评估候选分子。在此框架内，我们引入FragDockRL，一种基于强化学习的搜索方法，使用基于对接分数的奖励和修正的深度Q网络（DQN）来指导逐步的分子增长。我们在CSF1R、FA10和VEGFR2三个蛋白靶标上评估了FragDockRL，采用训练周期分析和与一步反应、随机搜索、束搜索和蒙特卡洛树搜索的基准比较。FragDockRL在学习过程中逐步富集了具有有利对接分数的分子，并在所有三个靶标上生成了比随机搜索更多的通过截断值的独特分子，支持了学习引导优先级排序的益处。然而，最优搜索策略具有靶标依赖性：一步反应、FragDockRL和束搜索在不同情况下各显优势。代表性分子案例研究表明，所选化合物在保持参考配体结合姿态的同时，在外围区域引入了结构变化。反应模式使用了市售构建块和成熟的药物化学转化，支持了所选化合物的合成可行性。总体而言，FragDock为合成约束、结构引导的分子探索提供了灵活框架，而FragDockRL提供了一种学习引导的搜索模式，可在有限的生成预算下高效地优先筛选候选分子。

## Abstract
Efficient exploration of combinatorial chemical space under synthetic constraints remains a central challenge in computational molecular design.

Here, we present FragDock, a molecular design framework that combines building block (BB)-based virtual synthesis with tethered docking guided by a predefined core structure. FragDock defines a structured search space by assembling molecules from synthetically accessible BBs through known chemical reactions and evaluating candidates using tethered docking with a restrained core binding pose. Within this framework, we introduce FragDockRL, a reinforcement learning-based search method that uses docking-score-based rewards and a modified Deep Q-Network (DQN) to guide stepwise molecular growth.

We evaluated FragDockRL on three protein targets, CSF1R, FA10, and VEGFR2, using training-cycle analysis and benchmark comparisons with One-Step Reaction, Random Search, Beam Search, and Monte Carlo Tree Search. FragDockRL progressively enriched molecules with favorable docking scores during learning and generated more cutoff-passing unique molecules than Random Search across all three targets, supporting the benefit of learning-guided prioritization. However, the best-performing search strategy was target-dependent: One-Step Reaction, FragDockRL, and Beam Search each showed advantages in different cases.

Representative molecular case studies showed that selected compounds retained reference-like binding poses while introducing structural variation in peripheral regions. The reaction schemes used commercially available BBs and well-established medicinal chemistry transformations, supporting the synthetic plausibility of the selected compounds. Overall, FragDock provides a flexible framework for synthetically constrained, structure-guided molecular exploration, and FragDockRL offers a learning-guided search mode for productive candidate prioritization under limited generation budgets.