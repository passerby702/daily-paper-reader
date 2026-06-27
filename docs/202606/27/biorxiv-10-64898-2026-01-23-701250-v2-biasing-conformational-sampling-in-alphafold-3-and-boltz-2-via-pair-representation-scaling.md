---
title: Biasing Conformational Sampling in AlphaFold 3 and Boltz-2 via Pair Representation Scaling
title_zh: 通过成对表示缩放偏置AlphaFold 3和Boltz-2中的构象采样
authors: "Suzuki, S., Amagasa, T."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.23.701250v2.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: "利用扩散模型（AlphaFold 3, Boltz-2）进行3D构象采样"
tldr: 深度学习方法通常只返回单一构象，缺乏对替代功能状态的控制。本文提出pair representation缩放，在推理时对潜层pair表示乘以标量，无需重训练或辅助模型。在86个双态蛋白上，该缩放拓宽了AlphaFold 3和Boltz-2的构象集合，恢复默认推理缺失的替代状态，效果接近基于比对的方法。这是一种可解释、低成本的构象采样控制手段。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有深度学习方法通常只预测单一构象，缺乏对蛋白质替代功能状态的控制。
method: 在Pairformer模块前将潜层pair表示乘以一个全局标量，偏置扩散模型的构象采样。
result: 在86个双态蛋白上，缩放拓宽构象集合，有效恢复默认推理无法采样的替代状态。
conclusion: Pair representation缩放是一种可解释、低成本的构象采样控制方法。
---

## 摘要
深度学习已彻底改变蛋白质结构预测，但大多数系统仅返回单一优势构象，对替代功能状态的控制很少。我们引入了成对表示缩放，这是一种推理时方法，通过在Pairformer主干之前将潜在成对表示乘以单个标量（无需重新训练、辅助模型或二次前向传播），偏置基于扩散的结构预测器中的构象采样。在跨越结构域运动和膜转运蛋白的86个双态蛋白质上，缩放拓宽了AlphaFold 3和Boltz-2的构象集成，并恢复了默认推理遗漏的替代状态，在AlphaFold 3中效果最为显著，其增益甚至扩展到训练截止后提交的目标。它接近基于比对的采样方法的替代状态恢复能力，即使没有多序列比对，这种益处仍然存在。预测的距离分布表明，缩放将编码的双态分布向实验观察到的替代状态移动，这是一种定向调控而非任意扰动。成对表示缩放为深度学习结构预测器的构象集成提供了一个可解释、低成本的操控手段。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWDeep learning has transformed protein structure prediction, yet most systems return a single dominant conformation with little control over alternative functional states. We introduce pair representation scaling, an inference-time method that biases conformational sampling in diffusion-based structure predictors by multiplying the latent pair representation by a single scalar before the Pairformer trunk, without retraining, an auxiliary model, or a second forward pass. On 86 two-state proteins spanning domain motions and membrane transporters, scaling broadens the conformational ensembles of both AlphaFold 3 and Boltz-2 and recovers alternative states that default inference misses, most strongly in AlphaFold 3, where the gains extend even to targets deposited after the training cutoff. It approaches the alternative-state recovery of alignment-based sampling methods, and the benefit persists even without a multiple sequence alignment. The predicted distance distributions show that scaling shifts the encoded two-state distribution toward the experimentally observed alternative state, a directed modulation rather than arbitrary perturbation. Pair representation scaling is an interpretable, low-cost handle on the conformational ensembles of deep learning structure predictors.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=62 SRC="FIGDIR/small/701250v2_ufig1.gif" ALT="Figure 1">
View larger version (17K):
org.highwire.dtl.DTLVardef@126be3forg.highwire.dtl.DTLVardef@945b50org.highwire.dtl.DTLVardef@1f7066aorg.highwire.dtl.DTLVardef@c61b2e_HPS_FORMAT_FIGEXP  M_FIG C_FIG Pair representation scalingA query sequence and its multiple sequence alignment enter the Pairformer trunk, where the latent pair representation z is rescaled by a single global scalar to (1 + {beta}) z and the diffusion module then generates a structure. The alignment and the trained weights are unchanged, and the same operation applies in AlphaFold 3 and Boltz-2. The scalar {beta} is a single explicit handle: sweeping it broadens the sampled ensemble toward alternative states, and its effect can be read out directly inside the network.