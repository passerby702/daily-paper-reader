---
title: "miDGD: a multi-modal deep generative model predicts miRNA expression from bulk or single-cell mRNA expression"
title_zh: miDGD：一种多模态深度生成模型，从批量或单细胞mRNA表达预测miRNA表达
authors: "Zamani, F., Rasmussen, A. M., Schuster, V., Diekema, M. H., Krogh, A., Pedersen, J. S."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.727918v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 用于miRNA预测的多模态深度生成模型
tldr: miRNA在单细胞和多数bulk RNA-seq中难以直接测量。为此提出miDGD，一种基于深度生成解码器的多模态模型，通过共享潜在表示从mRNA表达预测miRNA丰度。模型在TCGA、GTEx及细胞系数据上训练，能重建组织特异及广谱miRNA，复现已知调控关系，在稀疏数据中表现稳健。相比现有方法，miDGD预测精度更高且泛化性更强，为无法直接测量miRNA的场景提供了有效框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有RNA-seq数据中miRNA表达通常缺失，亟需从mRNA表达准确预测miRNA的方法。
method: 提出miDGD深度生成解码器，学习mRNA与miRNA的共享潜在表示，直接从基因表达预测miRNA丰度。
result: 在TCGA、GTEx及单细胞数据上，miDGD重建了组织特异性和广谱miRNA，表现优于miRSCAPE等方法，跨数据集泛化能力强。
conclusion: miDGD作为深度生成模型，为无法直接测量miRNA表达的场景提供了可靠预测框架，有助于揭示转录后调控机制。
---

## 摘要
微小RNA（miRNA）是重要的转录后调控因子，然而在单细胞和大多数批量RNA-seq数据集中，它们的表达通常未被观测到。我们提出了miDGD，一种深度生成解码器模型，可直接从基因表达本身预测miRNA丰度。通过在来自TCGA、GTEx和人类细胞系的批量及单细胞数据集上训练，miDGD学习到了匹配的mRNA和miRNA谱的共享潜在表征，该表征将样本组织成反映组织和癌症类型的生物学上有意义的聚类。该模型重构了组织特异性和广泛表达的miRNA，重现了已知的miRNA-靶标关系，并在稀疏和单细胞数据中表现出稳健的性能。miDGD优于miRSCAPE和最近的miRNA活性推断方法，并具有改进的跨数据集泛化能力。这些结果建立了一种深度生成模型作为在直接测量不可用时预测miRNA表达的改进框架。

## Abstract
MicroRNAs (miRNAs) are important post-transcriptional regulators, yet their expression is typically unobserved in single-cell and most bulk RNA-seq datasets. We present miDGD, a deep generative decoder model that predicts miRNA abundance directly from gene expression alone. Trained on bulk and single-cell datasets from TCGA, GTEx, and human cell lines, miDGD learned a shared latent representation of matched mRNA and miRNA profiles that organized samples into biologically meaningful clusters reflecting tissue and cancer types. The model reconstructed both tissue-specific and broadly expressed miRNAs, recapitulated known miRNA-target relationships, and showed robust performance in sparse and single-cell data. miDGD outperformed miRSCAPE and recent miRNA activity inference methods, with improved cross-dataset generalization. These results establish a deep generative model as an improved framework for predicting miRNA expression when direct measurements are unavailable.