---
title: "EvoSeq-ML: Advancing Data-Centric Machine Learning with Evolutionary-Informed Protein Sequence Representation and Generation"
title_zh: EvoSeq-ML：利用进化启发的蛋白质序列表示与生成推进以数据为中心的机器学习
authors: "Mardikoraem, M., Pascual, N. S., Eaves, J. N., Chatterjee, S., Mahama, A., Finneran, P., Hausinger, R. P., Woldring, D. R."
date: 2026-06-27
pdf: "https://www.biorxiv.org/content/10.1101/2024.10.02.616302v2.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 基于数据中心机器学习的蛋白质序列生成
tldr: 蛋白质工程中数据质量对机器学习模型至关重要，但数据增强策略常被忽视。本文提出基于祖先序列重建（ASR）的数据增强方法，用于训练变分自编码器（VAE）和微调ESM2表示模型。在乙烯形成酶（EFE）系统上，ASR增强的VAE生成的变体热稳定性显著优于现代序列训练的变体，但催化活性有所下降。ASR富集序列在溶菌酶稳定性分类任务中也展现了竞争力。该工作表明ASR数据增强是稳定性导向的蛋白质序列生成的有前景策略，为数据中心机器学习提供了新思路。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有蛋白质工程机器学习过度依赖模型改进，忽视数据质量对稳定性的影响，亟需能反映进化多样性的数据增强策略。
method: 构建祖先与近祖先序列数据集，分别用于训练VAE生成稳定变体，以及微调ESM2执行稳定性分类任务。
result: VAE生成变体热稳定性提升但活性降至野生型以下；ASR微调在溶菌酶分类任务中表现与现有方法相当。
conclusion: ASR数据增强有效捕捉稳定性特征，是蛋白质稳定性优化的可行方法，未来需结合功能选择。
---

## 摘要
从蛋白质结构预测到新型蛋白质生成，机器学习的进步使得具有挑战性的蛋白质工程任务成为可能。虽然这些基于机器学习的蛋白质工程研究主要由模型架构改进驱动，但数据整理的影响尚未得到充分探索。鉴于标记序列数据日益丰富，以数据为中心的进展（例如通过整理高质量、领域特定的训练数据来优先改进蛋白质工程机器学习工具）正逐渐取代以模型为中心的进展。实施能够准确反映生物复杂性和多样性的数据集已被证明可以提高蛋白质工程机器学习工具的训练效率。在此，我们评估了一种基于祖先序列重建的数据增强策略，用于训练蛋白质工程中的生成模型和表示学习模型。以乙烯形成酶为模型系统，我们表明，与使用现代序列训练数据生成的变体相比，在祖先序列和近祖先序列数据集上训练的变分自编码器模型生成的变体具有更高的预测和实验测量的热稳定性。所有经过实验测试的祖先和机器学习生成的乙烯形成酶都产生了可检测的乙烯，尽管机器学习生成的变体相对于野生型乙烯形成酶活性降低，这表明该方法更强烈地捕获了稳定性相关特征而非催化优化。我们还评估了富含祖先序列的集合，用于在溶菌内毒素和溶菌酶C稳定性分类任务中微调ESM2表示，在选定的设置中，祖先表示与现代序列微调具有竞争力。总体而言，本研究支持将祖先序列重建数据增强作为面向稳定性的蛋白质序列生成的一种有前景的策略，并激励未来工作将祖先序列多样性与明确的功能选择相结合。

## Abstract
From protein structure prediction to novel protein generation, challenging protein engineering tasks have been made possible by advancements in machine learning (ML). While largely driven by ML architecture refinements, these advancements in ML-based protein engineering campaigns have left the impact of data curation underexplored. In light of the growing wealth of labeled sequence data, data-centric advances (e.g. prioritizing improvements in ML protein engineering tools through the curation of high-quality, domain-specific training data) are increasingly preferred over model-centric advancements. Implementing datasets that accurately reflect biological complexity and diversity has been shown to improve the efficiency of training protein engineering ML tools. Here, we evaluate an ancestral sequence reconstruction (ASR)-informed data augmentation strategy for training generative and representation-learning models in protein engineering. Using ethylene-forming enzyme (EFE) as a model system, we show that variational autoencoder models trained on ancestral and near-ancestral sequence datasets generate variants with improved predicted and experimentally measured thermostability relative to variants generated from modern-sequence training data. All experimentally tested ancestral and ML-generated EFEs produced detectable ethylene, although ML-generated variants showed reduced activity relative to wild-type EFE, indicating that the approach more strongly captured stability-associated features than catalytic optimization. We further evaluated ASR-enriched sequence sets for fine-tuning ESM2 representations in endolysin and lysozyme C stability-classification tasks, where ancestral representations were competitive with modern-sequence fine-tuning in selected settings. Overall, this work supports ASR-informed data augmentation as a promising strategy for stability-oriented protein sequence generation and motivates future work to couple ancestral sequence diversity with explicit functional selection.