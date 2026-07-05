---
title: "StructureSAFE: A structure-aware chemical language model for unified hit identification and lead optimization"
title_zh: StructureSAFE：一种用于统一命中识别和先导优化的结构感知化学语言模型
authors: "Yang, B., Xu, K., Xiang, C., Lee, B., Xu, Y., Li, T., Shi, Y., Sinitskiy, A., Li, J."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735128v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 基于蛋白质口袋结构的分子生成（结构感知化学语言模型实现靶向设计）
tldr: 现有基于结构的生成模型在化学合理性和结构利用之间存在权衡。本文提出StructureSAFE，通过预训练和微调将蛋白质结构与进化信息融入SAFE化学语言模型，统一了从头命中识别和先导优化任务。在MolGenBench基准上，该方法在多项指标上达到最优，尤其在化学合理性上显著优于无预训练的图模型。案例研究证实了其生成类药、可合成分子并复现关键结合相互作用的能力。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有结构生成模型在化学合理性和结构利用之间难以平衡，且无法统一处理命中识别和先导优化。
method: 将蛋白质结构和进化编码器与SAFE分子表示结合，通过预训练和微调训练方案实现统一框架。
result: 在MolGenBench上实现多项指标SOTA，化学合理性大幅优于无预训练的图模型。
conclusion: StructureSAFE为命中识别和先导优化提供了实用工具，可生成高质量候选分子增强药物发现流程。
---

## 摘要
基于结构的生成模型（SBGMs）通过实现靶点感知的分子设计，在加速药物发现方面具有巨大潜力。然而，现有方法面临基本挑战：三维图模型可以明确整合蛋白质结构信息，但由于训练数据有限，常常生成化学上不合理的分子；而化学语言模型（CLMs）生成化学合理的分子，但难以有效利用三维结构信息进行结构条件生成，并且由于SMILES字符串的性质，很难整合先导优化功能。在此，我们提出StructureSAFE，一种结构感知的化学语言模型，通过将蛋白质结构和进化编码器与SAFE分子表示相结合，采用预训练和微调训练方案，在统一框架内实现了从头命中识别和全面的先导优化子任务。在MolGenBench数据集上的全面基准测试表明，StructureSAFE在多个指标上达到了最先进的性能，特别是在化学合理性方面相对于缺乏预训练的图模型有显著改进。在严格构建的保留测试集上的评估进一步证实了其能够生成类药、可合成且具有竞争力的预测结合亲和力的分子，适用于未见过的靶点的命中识别和先导优化设置。针对四个治疗相关靶点的计算机模拟案例研究验证了其生成化学合理分子的能力，这些分子重现了已知高亲和力配体的关键结合相互作用，同时提出可能具有更好亲和力的新型相互作用，并探索了化学空间中先前未知的区域。综上所述，StructureSAFE作为一种多功能且实用的工具，能够在命中识别和先导优化活动中提供高质量的候选分子，以增强药物化学工作流程。

## Abstract
Structure-based generative models (SBGMs) hold great promises for accelerating drug discovery by enabling target-aware molecular design. However, existing approaches face fundamental challenges: three-dimensional graph-based models can explicitly incorporate protein structural information but often generate chemically implausible molecules due to limited training data, while chemical language models (CLMs) produce chemically plausible molecules but struggle to effectively leverage three-dimensional structural information for structure-conditioned generation and hard to incorporate lead optimization functionality due to the nature of SMILES string. Here, we present StructureSAFE, a structure-aware chemical language model that resolves this trade-off by integrating protein structural and evolutionary encoders with the SAFE molecular representation via pretraining and finetuning training scheme, enabling both de novo hit identification and a comprehensive suite of lead optimization subtasks within a unified framework. Comprehensive benchmarking on the MolGenBench dataset demonstrates that StructureSAFE achieves state-of-the-art (SOTA) performance across multiple metrics, with particularly pronounced improvements in chemical plausibility relative to graph-based models lacking pretraining. Evaluation on a rigorously constructed held-out test set further confirms its ability to generate drug-like, synthetically accessible molecules with competitive predicted binding affinities for previously unseen targets on both hit identification and lead optimization setting. In silico case studies across four therapeutically relevant targets validate its capacity to generate chemically plausible molecules that recapitulate key binding interactions of known high-affinity ligands while proposing novel interactions for potential better affinity and exploring previously unknown regions of chemical space. Taking together, StructureSAFE represents a versatile and practical tool to provide high-quality candidate molecules for augmenting medicinal chemistry workflows in both hit identification and lead optimization campaigns.