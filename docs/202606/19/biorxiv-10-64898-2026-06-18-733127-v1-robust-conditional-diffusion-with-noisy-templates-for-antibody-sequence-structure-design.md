---
title: Robust Conditional Diffusion with Noisy Templates for Antibody Sequence-Structure Design
title_zh: 基于噪声模板的鲁棒条件扩散用于抗体序列-结构设计
authors: "Liu, p., Zhang, J., Yan, C."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733127v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 用于抗体序列-结构设计的扩散模型
tldr: "抗体设计中检索模板常因数据稀疏而不完美，直接作为硬条件会引入偏差。提出NT-ABDiff，一种鲁棒条件扩散框架，将候选CDR模板视为可选且不可靠条件，通过可靠性感知模板调制自适应融合多模板，并利用混合质量模板训练。在模板偏移和检索评估中，相比强基线，CDR-H3序列恢复率提升至39.47%，RMSD降至2.915Å，且对缺失、错配模板保持鲁棒。该方法有效结合模板信息与生成模型，提升了抗体设计的准确性和鲁棒性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有条件扩散将检索模板作为硬条件，但新型抗原模板稀疏有噪声，导致负迁移。
method: 提出NT-ABDiff，用可靠性感知模板调制估计模板有用性，自适应重加权融合多模板，并加入条件扰动正则化训练。
result: "随机模板下AAR从30.03%升至39.47%，RMSD从3.160降至2.915Å；检索模板下AAR达39.50%，RMSD为2.76Å。"
conclusion: NT-ABDiff提升了抗体序列结构设计的鲁棒性与准确性，有效应对模板噪声。
---

## 摘要
抗体能够特异性识别抗原，在治疗发现中发挥核心作用。针对给定抗原设计抗体仍具挑战性，因为抗原-抗体复合物数据有限，而互补决定区（CDR）的序列和构象空间巨大。从数据库或候选库中检索到的CDR模板可以缩小设计空间并提高可控性，但对于新型抗原的检索通常稀疏且不完美；将检索到的模板视为硬条件可能会使去噪过程产生偏差，导致负迁移。为解决此问题，我们提出基于噪声模板的鲁棒条件扩散用于抗体序列-结构设计（NT-ABDiff），这是一个联合扩散框架，将仅包含候选CDR的模板视为可选且可能不可靠的条件。NT-ABDiff利用可靠性感知的模板调制来估计每个候选者在上下文条件下的有用性，并在条件化过程中自适应地重新加权和融合多个模板。我们进一步使用混合质量和损坏的模板作为条件扰动正则化来训练模型，鼓励去噪器利用信息丰富的模板，同时在模板无信息时保持稳定。在受控模板偏移和训练集检索评估下的实验表明，NT-ABDiff在CDR-H3序列恢复和结构准确性上优于强基线，同时对缺失、不匹配和损坏的模板保持鲁棒性。在严格的随机模板CDR-H3评估中，NT-ABDiff将氨基酸恢复率（AAR）从30.03%提高到39.47%，并将RMSD从3.160降低到2.915Å；使用训练集检索候选者时，实现了39.50%的AAR和2.76Å的RMSD。代码、处理后的分割、配置文件以及评估脚本可在https://github.com/ShiDeng7rz/NT-ABDiff获取。

## Abstract
Antibodies specifically recognize antigens and play a central role in therapeutic discovery. Designing antibodies for a given antigen remains challenging because antigen-antibody complex data are limited, whereas the sequence and conformational spaces of complementarity-determining regions (CDRs) are large. Retrieved CDR templates from databases or candidate libraries can narrow the design space and improve controllability, but retrieval for novel antigens is often sparse and imperfect; treating retrieved templates as hard conditions can bias the denoising process and cause negative transfer. To address this problem, we propose Robust Conditional Diffusion with Noisy Templates for antibody sequence-structure design (NT-ABDiff), a joint diffusion framework that treats candidate CDR-only templates as optional and potentially unreliable conditions. NT-ABDiff uses reliability-aware template modulation to estimate the context-conditioned usefulness of each candidate and to adaptively reweight and fuse multiple templates during conditioning. We further train the model with mixed-quality and corrupted templates as conditional perturbation regularization, encouraging the denoiser to exploit informative templates while remaining stable when templates are uninformative. Experiments under controlled template shifts and a train-set retrieval evaluation show that NT-ABDiff improves CDR-H3 sequence recovery and structural accuracy over strong baselines, while retaining robustness to missing, mismatched, and corrupted templates. Under a stringent random-template CDR-H3 evaluation, NT-ABDiff improves amino-acid recovery (AAR) from 30.03% to 39.47% and reduces RMSD from 3.160 to 2.915A; with train-set retrieval candidates, it achieves 39.50% AAR and 2.76 {ring} A RMSD. Code, processed splits, {ring} configuration files, and evaluation scripts are available at https://github.com/ShiDeng7rz/NT-ABDiff.