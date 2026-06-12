---
title: "MolDeBERTa: Foundational Model for Physicochemical and Substructure-Informed Molecular Representation Learning"
title_zh: MolDeBERTa：面向物理化学和子结构信息驱动的分子表示学习的基础模型
authors: "de Oliveira, G. B., Saeed, F."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.15.706011v2.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 基于深度学习的分子生成
tldr: "现有分子语言模型基于第一代Transformer架构，掩码语言建模忽视理化与结构信息。MolDeBERTa采用字节级BPE分词，并引入三种新型预训练目标注入理化性质和结构相似性归纳偏置。在9个MoleculeNet基准上，回归误差降低16%，分类ROC-AUC提升3.0点，推动了无监督分子编码器的数据效率与化学感知表示学习。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有分子语言模型缺乏对理化性质和结构相似性的归纳偏置。
method: 提出MolDeBERTa，采用字节级BPE分词并设计三种新型预训练目标。
result: "在MoleculeNet基准上，回归误差降低16%，分类ROC-AUC提升最高3.0点。"
conclusion: MolDeBERTa实现了数据高效的化学信息表示学习。
---

## 摘要
学习分子语言的基础模型对于加速材料和药物发现至关重要。这些自学习模型可以在大量未标记分子上进行训练，从而支持属性预测、分子设计（从头生成、优化）以及特定功能筛选等应用。然而，现有的分子语言模型基于第一代Transformer架构，并使用掩码语言建模（一种通用的词元级目标，对物理化学和结构分子属性不可知）进行预训练。本文引入MolDeBERTa，一种结构信息驱动的自监督分子编码器，采用字节级字节对编码（BPE）分词策略。MolDeBERTa在来自PubChem的多达1.23亿个SMILES分子上进行了预训练，代表了最大的公开可用SMILES语料库之一。为实现这一目标，我们提出了三种新颖的预训练目标，旨在将分子属性和结构相似性的强归纳偏置直接注入潜在空间，从而缩小语言化学表示与物理分子属性之间的差距。随后，我们系统地在三种架构规模、两种数据集规模和五种不同的预训练目标下研究了该模型。在9个下游MoleculeNet基准测试上评估时，MolDeBERTa优于现有的掩码语言模型，在回归误差上降低高达16%，在分类基准上ROC-AUC提升高达3.0点。MolDeBERTa在预训练数据和下游评估两方面推动了基于无监督编码器的基础模型规模化，实现了数据高效的化学信息表示学习。源代码可在https://github.com/pcdslab/MolDeBERTa和Hugging Face https://huggingface.co/collections/SaeedLab/moldeberta 公开获取。所有预训练数据集可在https://huggingface.co/datasets/SaeedLab/MolDeBERTa 获取。

## Abstract
Foundational models that learn the language of molecules are essential for accelerating the material and drug discovery. These self-learning models can be trained on a large number of unlabelled molecules, enabling applications like property prediction, molecule de-sign (de novo generation, optimization), and screening for specific functions. However, existing molecular language models are built upon first-generation transformer architectures and are pretrained using masked language modeling, a generic token-level objective that is agnostic to physicochemical and structural molecular properties. Here we introduce MolDe-BERTa, a structure-informed self-supervised molecular encoder that leverages a byte-level Byte-Pair Encoding (BPE) tokenization strategy. MolDeBERTa is pretrained on up to 123 million SMILES molecules from PubChem, representing one of the largest publicly available SMILES-based corpora. To achieve this, we introduce three novel pretraining objectives designed to inject strong inductive biases for molecular properties and structural similarity directly into the latent space, resulting in reduced gap between linguistic chemical representations and physical molecular properties. The model was then systematically investigated across three architectural scales, two dataset sizes, and five distinct pretraining objectives. MolDeBERTa when evaluated on 9 downstream MoleculeNet benchmarks outperformed existing masked language models, achieving up to a 16% reduction in regression error and improvements of up to 3.0 ROC-AUC points on classification benchmarks. MolDeBERTa advances unsupervised encoder-based foundational models at scale both for pretraining data and downstream evaluation, enabling data-efficient chemistry-informed representation learning. The source code is publicly available at https://github.com/pcdslab/MolDeBERTa, and Hugging Face at https://huggingface.co/collections/SaeedLab/moldeberta. All the pretraining datasets are available at https://huggingface.co/datasets/SaeedLab/MolDeBERTa