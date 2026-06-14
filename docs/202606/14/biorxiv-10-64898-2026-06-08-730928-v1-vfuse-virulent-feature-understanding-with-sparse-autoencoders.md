---
title: "VFUSE: Virulent Feature Understanding with Sparse autoEncoders"
title_zh: VFUSE：利用稀疏自编码器理解毒力特征
authors: "Olson, M. L., Yu, M."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.730928v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 使用稀疏自编码器解释基于扩散的蛋白质生成模型
tldr: 生成模型可能无意识生成有害蛋白质，现有审计方法缺乏对内部危险特征的深入理解。本文提出VFUSE，通过训练稀疏自编码器（SAE）分析扩散变换器的激活，提取可解释的单语义特征。在RoseTTAFold3和RFDiffusion3上，SAE潜空间中的线性探针检测有害设计的AUROC达0.84，性能优于原始表示，且保留了特定危险特征。这项工作首次将SAE应用于蛋白质模型的可解释性审计，为生物安全提供了新工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 生成模型可能被滥用于合成有害蛋白质，需要可解释的审计方法检测危险特征。
method: 训练稀疏自编码器（SAE）于扩散变换器激活，提取单语义特征，并在潜空间拟合线性探针。
result: SAE潜空间中线性探针检测有害设计AUROC达0.84，优于原始表示（q<10⁻¹³），并发现具单语义性的危险特征。
conclusion: VFUSE实现了对蛋白质模型危险特征的可解释审计，在不牺牲性能前提下提升了透明度。
---

## 摘要
生成式模型在蛋白质设计等多个领域取得了显著进展，但这种能力也使得有毒蛋白质的不透明生成成为可能。在这项工作中，我们引入了VFUSE（利用稀疏自编码器理解毒力特征），这是一种可解释性机制方法，通过在扩散变换器激活上训练SAE来审计蛋白质模型中的危害感知特征。我们将VFUSE应用于RoseTTAFold3和RFDiffusion3，这两个流行的开源蛋白质折叠与合成模型。我们发现，对于某些模块，线性探针在SAE潜在空间上拟合时，对危险设计的检测效果显著优于原始模型表示：在不牺牲模型性能的情况下提高了可解释性。此外，我们从SAE中识别出单语义特征，这些特征仅在危险设计上激活，AUROC高达0.84（q < 10^-13）。

## Abstract
Generative models have shown remarkable progress in a variety of domains such as protein design, but such power enables the opaque generation of hazardous proteins. In this work, we introduce VFUSE (Virulent Feature Understanding with Sparse autoEncoders), a mechanistic interpretability approach that trains SAEs on diffusion-transformer activations to audit protein models for hazard-aware features. We apply VFUSE to RoseTTAFold3 and RFDiffusion3, popular open-weight models for protein folding and synthesis. We find that for certain blocks, linear probes detect hazardous designs significantly better when fit in the SAE latent space over the original model's representations: improving interpretability without sacrificing model performance. Furthermore, we identify monosemantic features from the SAE that fire only on hazardous designs at up to AUROC 0.84 (q < 10-13).