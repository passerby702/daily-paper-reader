---
title: Programming Biomolecular Interactions with All-Atom Generative Model
title_zh: 使用全原子生成模型编程生物分子相互作用
authors: "Kong, X., Chen, J., Zhang, Z., Li, G., Zhu, Q., Wei, L., Li, M., Shi, Y., Dai, W., Tan, W., Jiao, R., Wang, X., Zheng, J., Yu, Z., Wu, Q., Guo, Z., Zhang, L., Li, W., Huang, Q., Zhu, T., Huang, W., She, Y., Zhang, J., Liu, Y., Liu, K., Ma, J."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.12.711044v3.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 全原子生成模型可编程生物分子相互作用，适用于配体设计
tldr: "生物分子相互作用设计目前各模态策略分离，缺乏统一框架。AnewOmni提出基于全原子生成模型，在500多万复合物上训练，通过可编程图提示实现化学、拓扑、几何可控生成。在KRAS G12D和PCSK9靶点上，成功设计小分子、肽和纳米抗体，低通量验证成功率23%-75%。该工作是首个跨尺度功能分子设计模型，为通用分子推理引擎奠定基础。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有设计方法针对单一分子类型，缺乏共享物理化学原理的统一跨模态框架。
method: 提出AnewOmni，在500万生物分子复合物上训练的原子分辨率生成模型，通过可编程图提示支持化学、拓扑、几何引导。
result: "在KRAS G12D和PCSK9靶点上成功设计小分子、肽和纳米抗体，低通量验证成功率23%-75%。"
conclusion: 首个跨尺度统一分子设计框架，展示了生成模型在数据与人类直觉有限领域的潜力。
---

## 摘要
生物分子相互作用是细胞生命活动的核心，涵盖从小分子到核酸和蛋白质等多种分子模式。然而，尽管分子识别具有共同的物理化学原理，设计策略仍然彼此分离。在这里，我们提出AnewOmni，一个统一的生成框架，在超过500万个生物分子复合物上训练，通过在原子分辨率下组装具有化学意义的构建模块，实现跨分子尺度的可迁移分子设计。我们进一步引入了可编程图提示，以支持生成过程中用户定义的化学、拓扑和几何引导，探索超越经典结构的杂化和非常规化学。我们证明，通过一个原子到块的潜在空间，同时捕获原子细节和结构先验，跨分子模式的相互作用模式和物理约束的可迁移学习是可能的。该框架成功设计了针对具有挑战性的KRAS G12D switch II口袋的小分子、肽和纳米抗体，以及在缺乏已知结合位点的情况下针对PCSK9的正构肽和变构小分子抑制剂，仅通过低通量验证就实现了23%-75%的成功率，绕过了模态特异性的高通量筛选。AnewOmni是首个在所有尺度上成功实现功能性分子设计的框架，从小化学实体到大型生物制剂，并代表了迈向通用分子推理引擎的基石，倡导将生物分子相互作用的生成式基础模型引入数据和人类直觉仍然有限的领域。

## Abstract
Biomolecular interactions lie at the core of cellular life, spanning diverse molecular modalities from small molecules to nucleic acids and proteins. Nevertheless, design strategies remain separated despite shared physicochemical principles of molecular recognition. Here we present AnewOmni, a unified generative framework trained on more than 5 million biomolecular complexes, that enables transferable molecular design across molecular scales by assembling chemically meaningful building blocks at atomic resolution. We further introduce programmable graph prompts to support user-defined chemical, topological, and geometric steering during generation, exploring hybrid and unconventional chemistries beyond canonical structures. We demonstrate that transferable learning of interaction patterns and physical constraints across molecular modalities is possible, via an atom-to-block latent space capturing both atomic details and structural priors. The framework successfully designed small molecules, peptides, and nanobodies targeting the challenging KRAS G12D switch II pocket, as well as orthosteric peptides and allosteric small-molecule inhibitors for PCSK9 in the absence of known binding site, achieving 23%-75% success with only low-throughput validation, bypassing modality-specific high-throughput screening. AnewOmni is the first to succeed in functional molecular design across all scales, from small chemical entities to large biologics, and represents a stepstone towards general molecular reasoning engines, advocating a generative foundation model for biomolecular interactions to enter regimes where data and human intuition remain limited.