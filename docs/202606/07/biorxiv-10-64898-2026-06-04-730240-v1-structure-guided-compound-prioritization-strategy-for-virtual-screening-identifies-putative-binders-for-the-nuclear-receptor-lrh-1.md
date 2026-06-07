---
title: Structure-guided compound prioritization strategy for virtual screening identifies putative binders for the nuclear receptor LRH-1
title_zh: 基于结构的虚拟筛选化合物优先排序策略识别核受体LRH-1的潜在结合物
authors: "Chang-Gonzalez, A. C., Campbell, A. N., Bell, E. W., Blind, R., Meiler, J."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730240v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 使用生成模型盲对接优先排序LRH-1口袋的化合物
tldr: 结构虚拟筛选常因单次对接姿势和评分偏差产生高假阳性。本研究采用靶向物理对接与生成模型盲对接对多个蛋白模型采样，训练多层感知器预测核受体LRH-1正构位点结合物。该模型能识别化学结构不同的已知结合物，对单支架修饰敏感，前瞻筛选发现四个潜在结合物。该方法综合利用结构和实验数据，为挑战性靶点虚拟筛选提供新策略。
source: biorxiv
selection_source: fresh_fetch
motivation: 克服结构虚拟筛选中单次对接姿势和评分偏差导致的高假阳性问题。
method: 结合靶向物理对接与生成模型盲对接，对多个蛋白模型采样，训练多层感知器预测LRH-1正构位点结合物。
result: MLP识别训练集外化学结构不同的已知结合物，对单支架修饰敏感，前瞻筛选发现四个LRH-1潜在结合物。
conclusion: 结合评分与预测指标可有效富集命中化合物，为挑战性靶点虚拟筛选提供新策略。
---

## 摘要
基于结构的虚拟筛选中，由于评分项中的可变结合姿态或偏差，化合物排名通常会产生高排名的假阳性结合物。我们开发了一种化合物优先排序策略，利用从对比对接方法（靶向基于物理的对接和基于生成模型的盲对接）中采样的对接姿态，针对靶蛋白的多个模型训练多层感知器（MLP）。该模型预测核受体LRH-1（NR5A2）的正构配体结合口袋中的结合物。我们的方法避免了依赖单个对接姿态来评分化合物或依赖单个评分指标进行化合物排名。在独立的基准测试集中，我们观察到MLP能够识别出与训练集中化合物化学结构不同的已知结合物，并且对单个骨架修饰敏感，使其成为先导化合物优化的潜在工具。我们将该策略应用于一项前瞻性虚拟筛选活动，结果发现了四种推定的LRH-1结合物。我们发现，评分和预测指标的组合能够在不同文库规模中富集命中化合物。总之，该实现提供了一种利用结构和实验数据来辅助针对具有挑战性的蛋白质靶点进行虚拟筛选的方法。

## Abstract
Compound ranking in structure-based virtual screening notoriously yields highly ranked false positive binders due to variable poses or biases in scoring terms. We developed a compound prioritization strategy that utilizes sampled docked poses from contrasting docking approaches (targeted physics-based docking and blind docking with a generative model) against multiple models of the target protein to train a multi-layer perceptron (MLP). The model predicts binders at the orthosteric ligand-binding pocket of the nuclear receptor LRH-1 (NR5A2). Our approach circumvents the reliance on a single docked pose for scoring compounds or individual scoring metrics for compound ranking. In a separate benchmarking set, we observed that the MLP identifies known binders that are chemically dissimilar from the compounds in the training set and is sensitive to single scaffold modifications, making it a potential tool for lead optimization. We applied our strategy to a prospective virtual screening campaign, which resulted in the discovery of four putative LRH-1 binders. We found that a combination of scoring and prediction metrics enriches for the hit compounds across library sizes. In all, this implementation presents a method to leverage structural and experimental data to aid virtual screening for a challenging protein target.