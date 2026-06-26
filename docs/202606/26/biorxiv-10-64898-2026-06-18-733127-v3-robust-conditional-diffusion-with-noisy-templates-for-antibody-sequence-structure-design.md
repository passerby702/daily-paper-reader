---
title: Robust Conditional Diffusion with Noisy Templates for Antibody Sequence-Structure Design
title_zh: 带有噪声模板的鲁棒条件扩散用于抗体序列-结构设计
authors: "Liu, P., Yan, C., Pan, M., Liu, X., Huang, S., Wu, Z., Zhang, J."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733127v3.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 使用条件扩散模型进行抗体设计
tldr: 抗体设计面临抗原-抗体复合物数据有限、CDR序列结构空间大的挑战，检索模板虽能缩小设计空间但常不完美。为此提出NT-ABDiff，一种将候选CDR模板视为可选且不可靠条件的鲁棒条件扩散框架，通过可靠性感知模板调制自适应重加权融合多模板，并用混合质量与损坏模板进行条件扰动正则化训练。实验表明，在模板偏移和训练集检索下，NT-ABDiff显著提升CDR-H3序列恢复率和结构精度，对缺失、错配、损坏模板保持鲁棒。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有抗体设计方法依赖检索的CDR模板，但针对新抗原的模板稀疏且不可靠，硬性条件化会导致偏差和负迁移。
method: 提出NT-ABDiff，采用噪声模板条件扩散，通过可靠性感知模板调制估计模板有用性并自适应重加权，同时用混合质量模板进行条件扰动正则化训练。
result: "在随机模板评估中，氨基酸恢复率从30.03%升至39.47%，RMSD从3.160降至2.915Å；训练集检索下达39.50%恢复率和2.76Å RMSD。"
conclusion: NT-ABDiff通过鲁棒性条件扩散有效缓解模板不可靠问题，在抗体序列-结构联合设计上优于强基线，且对模板质量变化稳定。
---

## 摘要
抗体能够特异性识别抗原，在治疗发现中发挥核心作用。针对给定抗原设计抗体仍然具有挑战性，因为抗原-抗体复合物数据有限，而互补决定区（CDR）的序列和构象空间很大。从数据库或候选库中检索到的CDR模板可以缩小设计空间并提高可控性，但对于新型抗原的检索通常是稀疏且不完美的；将检索到的模板视为硬条件可能会使去噪过程产生偏差并导致负迁移。为了解决这个问题，我们提出了带有噪声模板的鲁棒条件扩散用于抗体序列-结构设计（NT-ABDiff），这是一个联合扩散框架，将候选的仅CDR模板视为可选且可能不可靠的条件。NT-ABDiff使用可靠性感知模板调制来估计每个候选模板在上下文条件下的有用性，并在条件化过程中自适应地重新加权和融合多个模板。我们进一步使用混合质量和损坏的模板作为条件扰动正则化来训练模型，鼓励去噪器利用信息性模板，同时在模板无信息时保持稳定。在受控模板偏移和训练集检索评估下的实验表明，NT-ABDiff在强基线上提高了CDR-H3序列恢复和结构准确性，同时保持了对缺失、不匹配和损坏模板的鲁棒性。在严格的随机模板CDR-H3评估中，NT-ABDiff将氨基酸恢复率（AAR）从30.03%提高到39.47%，并将RMSD从3.160降低到2.915 [Å]；使用训练集检索候选时，它实现了39.50%的AAR和2.76 [Å]的RMSD。代码、处理后的分割、配置文件和评估脚本可在 https://github.com/ShiDeng7rz/NT-ABDiff 获取。

## Abstract
Antibodies specifically recognize antigens and play a central role in therapeutic discovery. Designing antibodies for a given antigen remains challenging because antigen-antibody complex data are limited, whereas the sequence and conformational spaces of complementarity-determining regions (CDRs) are large. Retrieved CDR templates from databases or candidate libraries can narrow the design space and improve controllability, but retrieval for novel antigens is often sparse and imperfect; treating retrieved templates as hard conditions can bias the denoising process and cause negative transfer. To address this problem, we propose Robust Conditional Diffusion with Noisy Templates for antibody sequence-structure design (NT-ABDiff), a joint diffusion framework that treats candidate CDR-only templates as optional and potentially unreliable conditions. NT-ABDiff uses reliability-aware template modulation to estimate the context-conditioned usefulness of each candidate and to adaptively reweight and fuse multiple templates during conditioning. We further train the model with mixed-quality and corrupted templates as conditional perturbation regularization, encouraging the denoiser to exploit informative templates while remaining stable when templates are uninformative. Experiments under controlled template shifts and a train-set retrieval evaluation show that NT-ABDiff improves CDR-H3 sequence recovery and structural accuracy over strong baselines, while retaining robustness to missing, mismatched, and corrupted templates. Under a stringent random-template CDR-H3 evaluation, NT-ABDiff improves amino-acid recovery (AAR) from 30.03% to 39.47% and reduces RMSD from 3.160 to 2.915 [A]; with train-set retrieval candidates, it achieves 39.50% AAR and 2.76 [A] RMSD. Code, processed splits, configuration files, and evaluation scripts are available at https://github.com/ShiDeng7rz/NT-ABDiff.