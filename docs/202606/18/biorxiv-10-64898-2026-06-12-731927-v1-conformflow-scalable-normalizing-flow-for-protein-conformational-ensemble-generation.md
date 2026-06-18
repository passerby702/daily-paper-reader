---
title: "ConformFlow: scalable normalizing flow for protein conformational ensemble generation"
title_zh: ConformFlow：面向蛋白质构象整体生成的可扩展归一化流
authors: "Liu, Y., Lin, G., Chen, M."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731927v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 可扩展归一化流用于蛋白质构象系综生成
tldr: 蛋白质构象采样是分子动力学模拟的瓶颈，生成模型提供了替代方案。本文提出ConformFlow，首个可扩展的归一化流框架，结合连续骨架潜在表示与序列感知Transformer耦合网络，实现精确似然训练和单步采样。在多种蛋白质上，生成的构象集成与MD模拟高度一致，且泛化到未知蛋白质，采样速度显著优于扩散模型。该工作为高效可控的构象集成生成建立了新范式。
source: biorxiv
selection_source: fresh_fetch
motivation: 分子动力学模拟计算成本高昂，现有扩散模型采样慢，亟需更高效可扩展的生成方法。
method: ConformFlow结合连续骨架潜在表示和RealNVP归一化流，参数化为序列感知Transformer耦合网络，支持精确似然训练和单步采样。
result: 在多种蛋白质上，生成构象集成与MD模拟吻合，泛化到未知蛋白质，采样速度远快于扩散基线。
conclusion: ConformFlow作为归一化流框架，提供了高效可控的蛋白质构象集成生成替代方案。
---

## 摘要
分子动力学（MD）模拟仍然是描述蛋白质构象景观的标准工具，但其高昂的计算成本限制了大规模和长时间尺度的应用。最近的生成模型，特别是基于扩散的方法，通过学习跨不同蛋白质系统的平衡构象分布，提供了有前景的替代方案。我们提出了ConformFlow，这是首个面向序列条件蛋白质构象整体生成的可扩展归一化流框架。ConformFlow将连续主链潜在表示与由序列感知Transformer耦合网络参数化的RealNVP风格流相结合，实现了精确似然训练、单步采样以及对灵活几何约束的即插即用条件化。在多种蛋白质系统中，ConformFlow生成的构象整体与参考MD模拟高度一致，能够泛化到训练数据之外的蛋白质，并且比基于扩散的基线方法实现了显著更快的采样。这些结果确立了ConformFlow作为蛋白质构象整体生成的一种高效且可控的替代方案。

## Abstract
Molecular dynamics (MD) simulations remain the standard tool for characterizing protein conformational landscapes, but their high computational cost limits large-scale and long-timescale applications. Recent generative models, especially diffusion-based approaches, provide promising alternatives by learning equilibrium conformational distributions across diverse protein systems. We present \textbf{ConformFlow}, the first scalable normalizing-flow framework for sequence-conditioned protein conformational ensemble generation. ConformFlow combines a continuous backbone latent representation with a RealNVP-style flow parameterized by sequence-aware Transformer coupling networks, enabling exact likelihood training, single-step sampling, and plug-and-play conditioning on flexible geometric constraints. Across diverse protein systems, ConformFlow generates ensembles that agree well with reference MD simulations, generalizes to proteins beyond its training data, and achieves substantially faster sampling than diffusion-based baselines. These results establish ConformFlow as an efficient and controllable alternative for protein conformational ensemble generation.