---
title: Geometric Deep Learning Reveals Ligandable and Cryptic RNA Binding Small Molecule Pockets (SMARTPocket)
title_zh: 几何深度学习揭示RNA结合小分子的可配体与隐藏口袋（SMARTPocket）
authors: "Thakare, R. H., Taghavi, A., Wang, J., Childs-Disney, J. L., Li, C., Disney, M. D., Li, Y."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.732920v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 使用几何深度学习预测RNA小分子结合口袋
tldr: RNA是重要药物靶点，但识别小分子结合口袋是RNA药物发现的瓶颈。本文提出SMARTPocket，一种基于几何深度学习的框架，将RNA表示为全原子点云，并通过迁移学习从超11万蛋白质结合界面结构弥补数据不足。在多个基准测试中，SMARTPocket优于现有方法，能识别隐性口袋，并在SARS-CoV-2移码元件和RNA适配体上验证。该方法为结构驱动的RNA口袋识别和靶向药物发现提供了通用框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以从RNA三维结构中准确预测小分子结合口袋，制约RNA靶向药物开发。
method: 基于几何深度学习，将RNA构建为全原子点云，利用蛋白质结合界面的迁移学习预训练，实现口袋预测。
result: 在四个单链和三个扩展基准上超越现有方法，成功识别隐性口袋，并复现SARS-CoV-2和RNA适配体的实验结合位点。
conclusion: SMARTPocket为加速RNA靶向小分子药物发现提供了有效的结构预测工具。
---

## 摘要
RNA是重要的治疗靶点，然而识别可配体的小分子结合口袋仍是RNA靶向药物发现的主要障碍。本文介绍了SMARTPocket，一种直接从三维结构预测RNA-小分子结合口袋的原子级几何深度学习框架。SMARTPocket将RNA表示为全原子点云，并通过从超过110,000个蛋白质结合界面结构进行迁移学习，克服了实验阐明的RNA-配体复合物数量有限的问题。在四个已建立的单链基准和三个更广泛整理的基准上，SMARTPocket始终优于现有的RNA口袋预测器和通用生物分子建模方法。该模型在构象变化较小时可推广至apo RNA结构，识别隐藏的可配体口袋，并在SARS-CoV-2移码元件和进化结合小分子的RNA适配体中重现实验验证的结合位点。与盲目对接相比，SMARTPocket引导的对接进一步提高了近天然RNA-配体姿态恢复和计算效率。这些结果确立了SMARTPocket作为基于结构识别可配体RNA口袋和加速RNA靶向小分子发现的通用框架。

## Abstract
RNAs are important therapeutic targets, however identifying ligandable small-molecule binding pockets remains a major barrier to RNA-targeted drug discovery. Here, SMARTPocket, an atomic-level geometric deep learning framework for predicting RNA-small molecule binding pockets directly from three-dimensional structure is introduced. SMARTPocket represents RNA as full-atom point clouds and uses transfer learning from more than 110,000 protein binding interface structures to overcome the limited number of experimentally elucidated RNA-ligand complexes. Across four established single-chain benchmarks and three broader curated benchmarks, SMARTPocket consistently outperforms existing RNA pocket predictors and general biomolecular modeling approaches. The model generalizes to apo RNA structures when conformational changes are modest, identifies cryptic ligandable pockets, and recapitulates experimentally validated binding sites in the SARS-CoV-2 frameshifting element and an RNA aptamer evolved to bind small molecules. SMARTPocket-guided docking further improves near-native RNA-ligand pose recovery and computational efficiency compared with blind docking. These results establish SMARTPocket as a generalizable framework for structure-based identification of ligandable RNA pockets and for accelerating discovery of RNA-targeted small molecules.