---
title: Robust Conditional Diffusion with Noisy Templates for Antibody Sequence-Structure Design
title_zh: 基于噪声模板的鲁棒条件扩散用于抗体序列-结构设计
authors: "Liu, p., Zhang, J., Yan, C., Pan, M., Liu, X., Huang, S., Wu, Z."
date: 2026-06-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733127v2.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 抗体序列-结构设计的条件扩散模型
tldr: "抗体设计需从数据库中检索CDR模板，但新抗原的模板常稀疏且不可靠，硬条件会导致负迁移。本文提出NT-ABDiff，一种鲁棒条件扩散模型，通过可靠性感知模板调制自适应融合多候选模板，并利用混合质量模板训练进行条件扰动正则化，使模型在利用有用信息的同时对噪声模板保持稳定。在受控模板偏移和检索评估中，NT-ABDiff在CDR-H3设计上显著提升氨基酸恢复率（AAR从30.03%升至39.47%）并降低结构误差（RMSD从3.160Å降至2.915Å），展现了优越的鲁棒性和准确性。该工作为抗体序列-结构联合设计提供了可靠且实用的条件扩散方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有抗体设计依赖可靠CDR模板，但新抗原模板稀疏且质量差，硬条件导致负迁移，需设计对噪声模板鲁棒的扩散模型。
method: 提出NT-ABDiff，采用可靠性感知模板调制自适应重加权融合多模板，并用混合质量模板训练作为条件扰动正则化，增强模型对噪声的稳定性。
result: "在随机模板下，AAR从30.03%提至39.47%，RMSD从3.160Å降至2.915Å；检索评估下AAR达39.50%，RMSD 2.76Å，超越强基线。"
conclusion: NT-ABDiff通过鲁棒条件扩散有效利用噪声模板，提升了抗体设计在模板不可靠时的泛化性和鲁棒性。
---

## 摘要
抗体能够特异性识别抗原，在治疗发现中发挥核心作用。针对给定抗原设计抗体仍然具有挑战性，因为抗原-抗体复合物数据有限，而互补决定区（CDR）的序列和构象空间很大。从数据库或候选库中检索到的CDR模板可以缩小设计空间并提高可控性，但对于新抗原的检索通常是稀疏且不完美的；将检索到的模板视为硬条件可能会使去噪过程产生偏差并导致负迁移。为了解决这个问题，我们提出了一种基于噪声模板的鲁棒条件扩散方法用于抗体序列-结构设计（NT-ABDiff），这是一个联合扩散框架，将仅包含CDR的候选模板视为可选且可能不可靠的条件。NT-ABDiff使用可靠性感知的模板调制来估计每个候选模板在上下文条件下的有用性，并在条件化过程中自适应地重新加权和融合多个模板。我们进一步使用混合质量和损坏的模板作为条件扰动正则化来训练模型，鼓励去噪器利用信息丰富的模板，同时在模板无信息时保持稳定。在受控模板偏移和训练集检索评估下的实验表明，NT-ABDiff在CDR-H3序列恢复和结构准确性上优于强基线，同时保持对缺失、不匹配和损坏模板的鲁棒性。在严格的随机模板CDR-H3评估中，NT-ABDiff将氨基酸恢复率（AAR）从30.03%提高到39.47%，并将RMSD从3.160降至2.915Å；使用训练集检索候选时，实现了39.50%的AAR和2.76Å的RMSD。代码、处理后的分割文件、配置文件及评估脚本可在https://github.com/ShiDeng7rz/NT-ABDiff获取。

## Abstract
Antibodies specifically recognize antigens and play a central role in therapeutic discovery. Designing antibodies for a given antigen remains challenging because antigen-antibody complex data are limited, whereas the sequence and conformational spaces of complementarity-determining regions (CDRs) are large. Retrieved CDR templates from databases or candidate libraries can narrow the design space and improve controllability, but retrieval for novel antigens is often sparse and imperfect; treating retrieved templates as hard conditions can bias the denoising process and cause negative transfer. To address this problem, we propose Robust Conditional Diffusion with Noisy Templates for antibody sequence-structure design (NT-ABDiff), a joint diffusion framework that treats candidate CDR-only templates as optional and potentially unreliable conditions. NT-ABDiff uses reliability-aware template modulation to estimate the context-conditioned usefulness of each candidate and to adaptively reweight and fuse multiple templates during conditioning. We further train the model with mixed-quality and corrupted templates as conditional perturbation regularization, encouraging the denoiser to exploit informative templates while remaining stable when templates are uninformative. Experiments under controlled template shifts and a train-set retrieval evaluation show that NT-ABDiff improves CDR-H3 sequence recovery and structural accuracy over strong baselines, while retaining robustness to missing, mismatched, and corrupted templates. Under a stringent random-template CDR-H3 evaluation, NT-ABDiff improves amino-acid recovery (AAR) from 30.03% to 39.47% and reduces RMSD from 3.160 to 2.915A; with train-set retrieval candidates, it achieves 39.50% AAR and 2.76 {ring} A RMSD. Code, processed splits, {ring} configuration files, and evaluation scripts are available at https://github.com/ShiDeng7rz/NT-ABDiff.