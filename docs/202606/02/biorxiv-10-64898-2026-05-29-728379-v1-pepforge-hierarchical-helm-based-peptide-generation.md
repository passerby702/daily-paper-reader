---
title: "PepForge: Hierarchical HELM-Based Peptide Generation"
title_zh: PepForge：基于层次化HELM的肽生成
authors: "Wang, Q., Suessmuth, R. D."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728379v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 深度学习用于肽生成
tldr: 修饰肽药物具有大环化等特殊连接，但其化学空间难以被计算生成方法覆盖。PepForge利用HELM符号表示修饰肽，采用布局-内容-连接(LCC)级联分解生成任务，在38万HELM肽上训练。该方法支持从头生成、掩码填充和多级约束生成，结合抗菌效力预测器大规模生成478万新肽，经筛选得到799个结构新颖的候选抗菌肽。代码和模型开源，允许用户自定义扩展单体和连接类型，为修饰肽药物设计提供了新平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 修饰肽的特殊连接结构使现有计算方法难以覆盖其化学空间，需要能处理复杂修饰的肽生成模型。
method: "提出PepForge，基于HELM符号和LCC级联（布局-内容-连接）分解生成任务，在383,817个HELM肽上训练。"
result: 生成478万新肽，经抗菌预测和安全性筛选获得799个结构新颖的候选抗菌肽，支持多级约束生成和自定义扩展。
conclusion: PepForge有效解锁修饰肽化学空间，提供开源工具和预训练模型，为修饰肽药物设计奠定基础。
---

## 摘要
携带特殊连接（如大环化及其他多种结构修饰）的肽构成了一类主要的肽治疗药物，然而其化学空间在很大程度上仍无法通过计算生成方法访问。本文提出PepForge，一个用于肽生成的深度学习平台，该平台利用大分子层次化编辑语言（HELM）标记，通过布局-内容-连接（LCC）级联将生成任务分解为模块布局、单体含量和特殊连接预测，从而获取修饰肽的化学空间。LCC级联在383,817个HELM肽上训练，涵盖425种单体和9种连接类型。除了从头生成，LCC级联还支持用于靶向骨架修饰的掩码填充和多级约束生成。单体库和连接类型集均支持用户自定义扩展，以探索更广阔的化学空间。预测模块与生成解耦，可接受任意评分头进行下游任务。作为示范，我们构建了一个抗菌效力集成预测器，在具有最小抑制浓度（MIC）值的11,026个肽上训练，并结合外部PeptiVerse预测器。在规模化应用中，我们生成了478万个新的HELM肽，并在效力和安全性筛选后获得799个结构新颖的候选抗菌肽（AMP）。所有代码、预训练模型以及用于交互式使用的网络界面均公开在https://github.com/wqx1999/PepForge上。

## Abstract
Peptides carrying special connections such as macrocyclizations and various other structural modifications constitute a major class among peptide therapeutics, yet their chemical space remains largely inaccessible to computational generation methods. Here we present PepForge, a deep learning platform for peptide generation that exploits Hierarchical Editing Language for Macromolecules (HELM) notation to access the chemical space of modified peptides, through a Layout-Content-Connection (LCC) cascade decomposing the generation task into block layout, monomer content, and special connection prediction. The LCC cascade is trained on 383,817 HELM peptides covering 425 monomers and nine connection types. Beyond de novo generation, the LCC cascade supports masked infilling for targeted scaffold modification and multi-level constrained generation. Both the monomer library and the connection-type set support user-defined extensions for exploring a broader chemical space. The prediction module is decoupled from generation and accepts arbitrary scoring heads for downstream tasks. As a demonstration, we built an antimicrobial potency ensemble predictor trained on 11,026 peptides with minimum inhibitory concentration (MIC) values, alongside the external PeptiVerse predictor. Applied at scale, we generated 4.78 million novel HELM peptides and obtained 799 structurally novel hit antimicrobial peptide (AMP) candidates after potency and safety filtering. All code, pre-trained models, and a web interface for interactive use are publicly available at https://github.com/wqx1999/PepForge.