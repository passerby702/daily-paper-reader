---
title: Geometric Deep Learning Reveals Ligandable and Cryptic RNA Binding Small Molecule Pockets (SMARTPocket)
title_zh: 几何深度学习揭示可配体结合和隐性的RNA小分子结合口袋（SMARTPocket）
authors: "Thakare, R. H., Taghavi, A., Wang, J., Childs-Disney, J. L., Li, C., Disney, M. D., Li, Y."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.732920v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 几何深度学习预测RNA小分子结合口袋，为实现口袋特异性分子生成提供基础
tldr: RNA是重要药物靶点，但缺乏配体结合口袋识别方法。SMARTPocket基于原子级几何深度学习，从三维结构直接预测RNA小分子结合口袋，利用迁移学习从超过11万蛋白质结合界面结构克服数据限制。在多个基准测试中，它优于现有方法，能识别隐蔽口袋并复现实验验证位点，引导对接提升近原生姿态恢复和计算效率。该通用框架可加速RNA靶向小分子发现。
source: biorxiv
selection_source: fresh_fetch
motivation: RNA是重要治疗靶点，但缺乏有效识别其小分子配体结合口袋的计算方法，阻碍了RNA靶向药物发现。
method: 提出SMARTPocket，一种全原子点云几何深度学习框架，通过迁移学习从大量蛋白质界面结构预测RNA小分子结合口袋。
result: 在多个基准上超越现有方法，能识别隐蔽口袋，复现SARS-CoV-2移码元件和RNA适体的实验验证结合位点，并引导对接提升效率。
conclusion: SMARTPocket为基于结构的RNA配体口袋识别提供了通用框架，有望加速RNA靶向小分子药物发现。
---

## 摘要
RNA是重要的治疗靶点，然而识别可配体结合的小分子结合口袋仍然是RNA靶向药物发现的主要障碍。本文提出了SMARTPocket，一种直接从三维结构预测RNA-小分子结合口袋的原子级几何深度学习框架。SMARTPocket将RNA表示为全原子点云，并利用超过110,000个蛋白质结合界面结构的迁移学习，以克服实验解析的RNA-配体复合物数量有限的问题。在四个已建立的单链基准测试和三个更广泛整理的基准测试中，SMARTPocket始终优于现有的RNA口袋预测因子和通用生物分子建模方法。该模型在构象变化较小时可泛化至未结合配体的RNA结构，识别隐性可配体结合口袋，并重现了SARS-CoV-2移码元件和经进化以结合小分子的RNA适配体中的实验验证结合位点。与盲对接相比，SMARTPocket引导的对接进一步提高了近天然RNA-配体位姿恢复和计算效率。这些结果确立了SMARTPocket作为基于结构识别可配体结合RNA口袋并加速RNA靶向小分子发现的通用框架。

## Abstract
RNAs are important therapeutic targets, however identifying ligandable small-molecule binding pockets remains a major barrier to RNA-targeted drug discovery. Here, SMARTPocket, an atomic-level geometric deep learning framework for predicting RNA-small molecule binding pockets directly from three-dimensional structure is introduced. SMARTPocket represents RNA as full-atom point clouds and uses transfer learning from more than 110,000 protein binding interface structures to overcome the limited number of experimentally elucidated RNA-ligand complexes. Across four established single-chain benchmarks and three broader curated benchmarks, SMARTPocket consistently outperforms existing RNA pocket predictors and general biomolecular modeling approaches. The model generalizes to apo RNA structures when conformational changes are modest, identifies cryptic ligandable pockets, and recapitulates experimentally validated binding sites in the SARS-CoV-2 frameshifting element and an RNA aptamer evolved to bind small molecules. SMARTPocket-guided docking further improves near-native RNA-ligand pose recovery and computational efficiency compared with blind docking. These results establish SMARTPocket as a generalizable framework for structure-based identification of ligandable RNA pockets and for accelerating discovery of RNA-targeted small molecules.