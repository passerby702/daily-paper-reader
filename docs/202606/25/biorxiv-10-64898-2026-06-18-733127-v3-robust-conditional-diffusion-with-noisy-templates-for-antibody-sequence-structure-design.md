---
title: Robust Conditional Diffusion with Noisy Templates for Antibody Sequence-Structure Design
title_zh: 基于噪声模板的鲁棒条件扩散用于抗体序列-结构设计
authors: "Liu, P., Yan, C., Pan, M., Liu, X., Huang, S., Wu, Z., Zhang, J."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733127v3.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 鲁棒条件扩散用于抗体序列结构设计
tldr: "抗体设计面临CDR序列和构象空间大、复合物数据有限的问题，检索模板常不完美。提出NT-ABDiff鲁棒条件扩散模型，将候选模板视为噪声条件，通过可靠性感知模板调制自适应融合模板，并用条件扰动正则化训练增强鲁棒性。在CDR-H3设计上，随机模板下AAR从30.03%提升至39.47%，RMSD从3.160降至2.915Å；训练集检索下AAR达39.50%、RMSD为2.76Å。该方法有效利用模板信息并显著提升性能，对模板质量具有鲁棒性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有条件扩散模型将检索模板作为硬条件，因模板稀疏不完美导致负迁移，需要鲁棒方法。
method: 提出NT-ABDiff，使用可靠性感知模板调制自适应融合多个候选模板，并采用条件扰动正则化训练增强鲁棒性。
result: "在CDR-H3设计任务上，随机模板下AAR从30.03%提升至39.47%，RMSD从3.160降至2.915Å。"
conclusion: NT-ABDiff通过软条件机制有效利用模板信息，显著提升抗体设计性能且对模板质量鲁棒。
---

## 摘要
抗体能够特异性识别抗原，在治疗药物发现中扮演核心角色。针对特定抗原设计抗体仍然具有挑战性，因为抗原-抗体复合物数据有限，而互补决定区（CDR）的序列和构象空间很大。从数据库或候选库中检索到的CDR模板可以缩小设计空间并提高可控性，但对新型抗原的检索通常稀疏且不完美；将检索到的模板视为硬条件可能会使去噪过程产生偏差并导致负迁移。为解决这一问题，我们提出了基于噪声模板的鲁棒条件扩散用于抗体序列-结构设计（NT-ABDiff），这是一种联合扩散框架，将候选的仅CDR模板视为可选且可能不可靠的条件。NT-ABDiff使用可靠性感知的模板调制来估计每个候选模板在上下文条件下的有用性，并在条件化过程中自适应地重新加权和融合多个模板。我们进一步使用混合质量和损坏的模板作为条件扰动正则化来训练模型，鼓励去噪器利用信息丰富的模板，同时在模板无信息时保持稳定。在受控模板偏移和训练集检索评估下的实验表明，NT-ABDiff在CDR-H3序列恢复和结构准确性上优于强基线，同时对缺失、不匹配和损坏的模板保持鲁棒性。在严格的随机模板CDR-H3评估下，NT-ABDiff将氨基酸恢复率（AAR）从30.03%提高到39.47%，并将RMSD从3.160降低到2.915 [A]；使用训练集检索候选模板时，达到39.50%的AAR和2.76 [A]的RMSD。代码、处理后的数据拆分、配置文件和评估脚本可在 https://github.com/ShiDeng7rz/NT-ABDiff 获取。

## Abstract
Antibodies specifically recognize antigens and play a central role in therapeutic discovery. Designing antibodies for a given antigen remains challenging because antigen-antibody complex data are limited, whereas the sequence and conformational spaces of complementarity-determining regions (CDRs) are large. Retrieved CDR templates from databases or candidate libraries can narrow the design space and improve controllability, but retrieval for novel antigens is often sparse and imperfect; treating retrieved templates as hard conditions can bias the denoising process and cause negative transfer. To address this problem, we propose Robust Conditional Diffusion with Noisy Templates for antibody sequence-structure design (NT-ABDiff), a joint diffusion framework that treats candidate CDR-only templates as optional and potentially unreliable conditions. NT-ABDiff uses reliability-aware template modulation to estimate the context-conditioned usefulness of each candidate and to adaptively reweight and fuse multiple templates during conditioning. We further train the model with mixed-quality and corrupted templates as conditional perturbation regularization, encouraging the denoiser to exploit informative templates while remaining stable when templates are uninformative. Experiments under controlled template shifts and a train-set retrieval evaluation show that NT-ABDiff improves CDR-H3 sequence recovery and structural accuracy over strong baselines, while retaining robustness to missing, mismatched, and corrupted templates. Under a stringent random-template CDR-H3 evaluation, NT-ABDiff improves amino-acid recovery (AAR) from 30.03% to 39.47% and reduces RMSD from 3.160 to 2.915 [A] ; with train-set retrieval candidates, it achieves 39.50% AAR and 2.76 [A] RMSD. Code, processed splits, configuration files, and evaluation scripts are available at https://github.com/ShiDeng7rz/NT-ABDiff.