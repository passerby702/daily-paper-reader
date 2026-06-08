---
title: Structure-guided compound prioritization strategy for virtual screening identifies putative binders for the nuclear receptor LRH-1
title_zh: 基于结构的虚拟筛选化合物优先排序策略发现核受体LRH-1的推定结合剂
authors: "Chang-Gonzalez, A. C., Campbell, A. N., Bell, E. W., Blind, R., Meiler, J."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730240v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 使用生成模型盲对接的结构引导化合物优先排序
tldr: 虚拟筛选常因单一对接姿势或评分偏差产生高排名假阳性。本研究结合靶向物理对接和生成模型盲对接，对LRH-1多蛋白模型采样姿势，训练MLP预测正构口袋结合物。在基准集上识别出与训练集化学结构不同的已知结合物，并对单个骨架修饰敏感。前瞻性筛选发现四个推定结合物，结合评分与预测指标可提升富集率。
source: biorxiv
selection_source: fresh_fetch
motivation: 克服结构虚拟筛选高假阳性问题，为核受体LRH-1开发可靠的化合物优先排序方法。
method: 利用多种对接方法（靶向物理对接和生成模型盲对接）对多个蛋白模型采样姿势，训练MLP分类器。
result: 基准测试识别出化学多样性结合物，向前瞻性筛选发现四个推定LRH-1结合物。
conclusion: 结合多姿势评分与MLP预测可减少假阳性，为挑战性靶点提供实用虚拟筛选策略。
---

## 摘要
在基于结构的虚拟筛选中，由于评分项中的可变姿势或偏差，化合物排序通常会产生高度排序的假阳性结合剂。我们开发了一种化合物优先排序策略，该策略利用从不同的对接方法（基于物理的靶向对接和基于生成模型的盲对接）对目标蛋白的多个模型采样的对接姿势来训练多层感知器（MLP）。该模型预测核受体LRH-1（NR5A2）的orthosteric配体结合口袋中的结合剂。我们的方法避免了对单个对接姿势进行评分或使用单个评分指标进行化合物排序的依赖。在一个独立的基准测试集中，我们观察到MLP能够识别出与训练集中化合物化学结构不同的已知结合剂，并且对单个骨架修饰敏感，使其成为先导化合物优化的潜在工具。我们将该策略应用于前瞻性虚拟筛选活动，发现了四个推定的LRH-1结合剂。我们发现，评分和预测指标的组合能够富集跨越不同文库大小的命中化合物。总之，该实现提供了一种利用结构数据和实验数据来辅助针对具有挑战性的蛋白质靶标进行虚拟筛选的方法。

## Abstract
Compound ranking in structure-based virtual screening notoriously yields highly ranked false positive binders due to variable poses or biases in scoring terms. We developed a compound prioritization strategy that utilizes sampled docked poses from contrasting docking approaches (targeted physics-based docking and blind docking with a generative model) against multiple models of the target protein to train a multi-layer perceptron (MLP). The model predicts binders at the orthosteric ligand-binding pocket of the nuclear receptor LRH-1 (NR5A2). Our approach circumvents the reliance on a single docked pose for scoring compounds or individual scoring metrics for compound ranking. In a separate benchmarking set, we observed that the MLP identifies known binders that are chemically dissimilar from the compounds in the training set and is sensitive to single scaffold modifications, making it a potential tool for lead optimization. We applied our strategy to a prospective virtual screening campaign, which resulted in the discovery of four putative LRH-1 binders. We found that a combination of scoring and prediction metrics enriches for the hit compounds across library sizes. In all, this implementation presents a method to leverage structural and experimental data to aid virtual screening for a challenging protein target.