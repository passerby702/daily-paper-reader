---
title: Structure-guided compound prioritization strategy for virtual screening identifies putative binders for the nuclear receptor LRH-1
title_zh: 基于结构的化合物优先级排序策略用于虚拟筛选：识别核受体LRH-1的推定结合剂
authors: "Chang-Gonzalez, A. C., Campbell, A. N., Bell, E. W., Blind, R., Meiler, J."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730240v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 使用生成模型进行盲对接，以优先排序针对特定蛋白质口袋的化合物
tldr: 虚拟筛选常因对接姿态和评分偏差产生假阳性。本文提出一种基于多种对接方式（物理对接和盲对接）在多蛋白模型上采样姿态，训练MLP模型预测核受体LRH-1正构位点配体的策略。在独立测试集上，MLP能识别化学新颖的已知配体并对骨架修饰敏感。前瞻筛选发现4个候选配体，组合评分和预测指标可富集命中化合物。该方法整合结构和实验数据，提升了虚拟筛选的可靠性。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统虚拟筛选排名易出现高排名假阳性，需要一种更鲁棒的化合物优先排序策略。
method: 融合靶向物理对接和生成式盲对接的多种采样姿态，训练多隐层感知机预测正构位点配体。
result: 测试集上识别出化学新颖的已知配体，并从前瞻筛选中发现4个LRH-1候选配体。
conclusion: 结合多对接和机器学习可有效筛选挑战性靶点，助力先导优化。
---

## 摘要
基于结构的虚拟筛选中的化合物排序长期以来由于不同构象或评分项中的偏差而产生大量假阳性结合剂。我们开发了一种化合物优先级排序策略，利用来自对比对接方法（针对性的基于物理的对接和基于生成模型的盲对接）对靶蛋白多个模型进行采样获得的对接构象，来训练多层感知器（MLP）。该模型预测核受体LRH-1（NR5A2）正构配体结合口袋中的结合剂。我们的方法避免了对单个对接构象进行评分或使用单一评分指标进行化合物排序的依赖。在一个独立的基准测试集中，我们观察到MLP能够识别出与训练集化合物化学结构不同的已知结合剂，并且对单个骨架修饰敏感，使其成为先导优化的潜在工具。我们将该策略应用于一项前瞻性虚拟筛选活动，发现了四个推定的LRH-1结合剂。我们发现，结合评分和预测指标可以在不同文库规模中富集命中化合物。总之，这一实现提供了一种利用结构和实验数据辅助针对具有挑战性的蛋白质靶点进行虚拟筛选的方法。

## Abstract
Compound ranking in structure-based virtual screening notoriously yields highly ranked false positive binders due to variable poses or biases in scoring terms. We developed a compound prioritization strategy that utilizes sampled docked poses from contrasting docking approaches (targeted physics-based docking and blind docking with a generative model) against multiple models of the target protein to train a multi-layer perceptron (MLP). The model predicts binders at the orthosteric ligand-binding pocket of the nuclear receptor LRH-1 (NR5A2). Our approach circumvents the reliance on a single docked pose for scoring compounds or individual scoring metrics for compound ranking. In a separate benchmarking set, we observed that the MLP identifies known binders that are chemically dissimilar from the compounds in the training set and is sensitive to single scaffold modifications, making it a potential tool for lead optimization. We applied our strategy to a prospective virtual screening campaign, which resulted in the discovery of four putative LRH-1 binders. We found that a combination of scoring and prediction metrics enriches for the hit compounds across library sizes. In all, this implementation presents a method to leverage structural and experimental data to aid virtual screening for a challenging protein target.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：基于结构的虚拟筛选（SBVS）中，化合物排序常因对接姿态可变性和评分函数的偏差而产生大量高排名的假阳性结合剂，导致筛选效率低下。
- **研究动机**：传统方法依赖单一对接姿态或单一评分指标进行排序，容易引入偏差；亟需一种更鲁棒、整合多种信息源的化合物优先排序策略。
- **整体含义**：通过融合多种对接方法（物理对接和生成式盲对接）以及多蛋白模型的大量采样姿态，并借助机器学习模型（多层感知器MLP）进行预测，能够在挑战性靶点（如核受体LRH-1）上更可靠地识别真阳性结合剂，并具备先导优化的潜力。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：避免依赖单个对接构象或单一评分指标，而是利用多种对比对接方法（特定口袋的物理对接 + 基于生成模型的盲对接）在靶蛋白的多个构象模型上产生大量对接姿态，然后用这些姿态作为输入特征训练一个二分类MLP，预测化合物是否结合于LRH-1的正构配体结合口袋。
- **关键技术细节**：
  - **对接方法**：
    - 针对性物理对接（targeted physics-based docking）：已知口袋区域进行对接。
    - 生成式盲对接（blind docking with a generative model）：无需事先指定口袋，由模型自动探索全蛋白表面。
  - **蛋白模型**：使用多个不同构象状态的LRH-1模型（例如不同晶体结构或同源模型），增加采样多样性。
  - **特征提取**：从每个对接姿态提取描述符（如结合能、各评分项、接触指纹、口袋占有率等），所有姿态的特征向量平均或拼接后作为MLP输入。
  - **模型架构**：多层感知机（MLP），二分类（结合剂 vs 非结合剂）。
  - **训练与评估**：以已知的LRH-1配体（正样本）和推测的非结合剂（负样本，如从ZINC中随机选取的化合物）训练；最后用独立的基准测试集评估泛化能力。

## 3. 实验设计：使用了哪些数据集/场景，benchmark，对比方法

- **数据集**：
  - **训练集**：已知LRH-1配体（来自文献/公共数据库）作为正样本；从大型化合物库（如ZINC）随机选取的化合物作为负样本。
  - **独立基准测试集（benchmark set）**：与训练集化学结构不同的已知结合剂，用于评估模型对新骨架的识别能力。
  - **前瞻筛选集**：一个大型虚拟化合物库（规模未具体说明），用于实际筛选候选配体。
- **场景**：核受体LRH-1（NR5A2）的正构配体口袋。
- **对比方法**：文中没有明确列出与哪些其他ML方法或纯对接评分方法进行系统对比，但隐含的baseline为传统基于单一对接评分的排序方式。作者通过MLP与评分指标的联合使用来体现优于纯评分排序。
- **评价指标**：富集因子（enrichment）、命中率、对单个骨架修饰的敏感性等。

## 4. 资源与算力

- **论文未明确说明**使用的GPU型号、数量、训练时长等算力资源。仅能根据常规推断：MLP模型参数较少（可能<1M），训练可在单块GPU或CPU上快速完成；对接通常需要较多计算资源，但作者未披露具体硬件信息。

## 5. 实验数量与充分性

- **实验组数**：主要包括：
  - 训练MLP（一次）。
  - 在独立基准测试集上评估模型对新化学骨架的识别能力（若干次对比，如不同骨架修饰）。
  - 前瞻虚拟筛选活动，最终选出4个候选配体进行实验验证（推测有结合实验）。
- **充分性评价**：
  - **优点**：使用了独立测试集（非随机拆分），能较好反映泛化能力；对骨架修饰敏感性的测试暗示可辅助先导优化；前瞻筛选并发现4个候选者，提供了实际命中证据。
  - **不足**：未进行系统的消融实验（例如仅使用物理对接 vs 仅使用盲对接 vs 两者结合；多个蛋白模型 vs 单个模型；MLP vs 纯评分或其他ML方法），因此难以量化各组分贡献；负样本的生成方式（随机选取）可能导致缺乏化学空间多样性，存在偏差风险；仅针对一个靶点（LRH-1），普适性待验证。

## 6. 论文的主要结论与发现

- 提出的化合物优先级排序策略（MLP基于多种对接姿态训练）能够在独立测试集上识别出化学结构不同于训练集的已知LRH-1配体。
- MLP对单个骨架修饰敏感，提示它可作为先导优化的工具。
- 在前瞻性虚拟筛选中，筛选出4个推定LRH-1结合剂。
- 结合评分（传统对接得分）和MLP预测指标可以在不同文库规模下富集命中化合物，优于纯评分排序。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：将物理对接和生成式盲对接的多种姿态融合作为特征，避免了传统单一姿态/评分依赖，提高了鲁棒性。
- **实用性**：方法构建于标准MLP之上，易于复现；且对骨架修饰敏感，可直接用于先导优化阶段。
- **验证充分性**：使用了独立化学空间测试集，并进行了前瞻筛选，有实验验证（4个候选者），结果可信度较高。
- **可迁移性**：虽然仅展示了LRH-1，但该框架可推广到其他靶点。

## 8. 不足与局限

- **算力与细节未披露**：缺少模型训练的超参数、对接软件版本、采样数量等细节，影响复现性。
- **实验对比不充分**：未与现有主流方法（如基于图神经网络、随机森林等）进行公平对比；未进行消融实验来量化每个组件（对接方法、蛋白模型数、MLP结构）的贡献。
- **负样本偏差**：随机选取的负样本可能缺乏与正样本相近的“诱饵”化合物，导致模型倾向于学习简单的理化性质区分而非结合特异性。
- **单靶点验证**：仅在LRH-1上验证，通用性未知；核受体家族可能具有特殊性的位点结构。
- **前瞻筛选的命中验证**：仅报道“4个候选配体”，未公开结合活性数据（如IC50、EC50）以及是否经过湿实验验证，因此“推定结合剂”尚需进一步确认。
- **骨架修饰敏感性实验可能不够系统**：仅对“单个”修饰进行了测试，未覆盖更广泛的化学空间扰动。
- **模型过拟合风险**：若训练集配体较少（核受体配体数据有限），MLP可能过拟合。

（完）
