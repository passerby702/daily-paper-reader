---
title: "MoE-Bind: Guiding De Novo Protein Binder Generation with Sparse Experts"
title_zh: MoE-Bind：利用稀疏专家指导从头蛋白质结合物生成
authors: "Sarkar, D., Sarkar, C."
date: 2026-06-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.13.732043v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 基于稀疏专家混合的从头蛋白质结合剂生成
tldr: 现有蛋白结合体生成依赖结构信息，计算量大。本文提出MoE-Bind，首次将稀疏专家架构用于序列生成，结合多头潜注意力和MoE前馈网络。在无需结构信息的条件下，激活不到一半参数，性能匹配或超越密集基线，训练和推理计算大幅降低。路由分析显示专家在氨基酸和生化层面具有可解释的专门化。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有序列生成模型结构密集且需结构计算，效率低，亟需稀疏架构提升蛋白结合体生成的效率和可解释性。
method: 将多头潜注意力和稀疏MoE前馈网络结合，构建自回归蛋白结合体生成器MoE-Bind。
result: 在Docking Benchmark 5.0上，激活参数不到一半，性能与密集基线相当，计算量显著降低。
conclusion: 稀疏架构设计可替代规模扩展，实现快速、无结构、可解释的蛋白结合体生成。
---

## 摘要
从头蛋白质结合物设计一直以基于结构的方法为主，这些方法需要已知的三维目标构象，并且每次设计消耗大量计算和生成时间，限制了其在大规模结合物探索中的通量和可及性。仅基于序列的生成模型有望提供更快、更轻量的替代方案，但现有系统仍然保持全密集结构，并且在推理中频繁重新引入结构计算，削弱了它们原本旨在提供的核心优势。与此同时，在更广泛的自然语言建模社区中，Transformer已从全密集设计转向稀疏混合专家架构，这种架构将模型容量与每个token的计算量解耦，而这一转变尚未影响到仅基于序列的蛋白质结合物生成。我们提出了MoE-Bind，这是一种自回归蛋白质结合物生成器，在该领域首次将多头潜注意力与稀疏混合专家前馈网络相结合，并在两个独立的结构预测器Boltz-2和AlphaFold2-Multimer上进行了评估。尽管激活的每token参数少于计算匹配的密集基线的一半，MoE-Bind在无泄漏的Docking Benchmark 5.0评估上的全长受体条件结合物生成中达到或超过了基线性能，无需肽特异性训练即可迁移到短肽设计，并大幅减少了训练和推理计算量。对生成结合物的路由分析揭示了在单个氨基酸和生化基团水平上的可解释专家专业化，这是一种在自然语言MoE模型中尚未报道的结构化专家-标记对齐。这些结果表明，稀疏架构设计而非规模，能够实现快速、无结构且可解释的蛋白质结合物生成。

## Abstract
De novo protein binder design has been dominated by structure-based pipelines that require known three-dimensional target conformations and consume substantial compute and generation time per design, limiting their throughput and accessibility for routine large-scale binder exploration. Sequence-only generative models promise a faster and lighter alternative, yet existing systems remain uniformly dense and frequently reintroduce structural computation at inference, undermining the core advantages they were intended to deliver. Across the broader language modelling community, transformers have meanwhile transitioned from fully dense designs to sparse Mixture-of-Experts architectures that decouple capacity from per-token compute, a shift that has yet to reach sequence-only protein binder generation. We present MoE-Bind, an autoregressive protein binder generator that, for the first time in this domain, combines Multi-head Latent Attention with a sparse Mixture-of-Experts feed-forward network and is evaluated under two independent structure predictors, Boltz-2 and AlphaFold2-Multimer. Despite activating less than half the per-token parameters of compute-matched dense baselines, MoE-Bind matches or exceeds them on full-length receptor-conditioned binder generation on a leakage-free Docking Benchmark 5.0 evaluation, transfers without peptide-specific training to short-peptide design, and reduces training and inference compute by a large margin. Routing analysis on generated binders reveals interpretable expert specialization at both the individual amino acid and biochemical group level, a structured expert-token alignment not previously reported for natural-language MoE models. These results show that sparse architectural design, rather than scale, can deliver fast, structure-free, and interpretable protein binder generation.