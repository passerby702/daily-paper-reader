---
title: "HTS-Oracle X: AI-Guided Prospective Discovery of Small Molecule Immune Checkpoint Binders"
title_zh: HTS-Oracle X：人工智能引导的小分子免疫检查点结合剂前瞻性发现
authors: "Abdel-Rahman, S., Gabr, M."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732853v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: AI平台发现免疫检查点小分子结合剂，针对蛋白口袋
tldr: "免疫检查点蛋白-蛋白相互作用的小分子发现受限于平坦表面和低筛选命中率。HTS-Oracle X通过双向交叉注意力融合ChemBERTa与RDKit描述符，在连续结合信号上训练，并利用不确定性量化进行前瞻性筛选。对CD28等靶点从10万化合物中选出150个，确认45个结合物（30%命中率），获得亚微摩尔级先导化合物。该平台为无酶活性免疫检查点靶点的小分子发现提供了可扩展的AI指导框架。"
source: biorxiv
selection_source: fresh_fetch
motivation: 针对免疫检查点蛋白-蛋白相互作用的小分子发现受限于平坦结合表面和超低筛选命中率。
method: 集成双向交叉注意力融合ChemBERTa SMILES与RDKit描述符，训练于连续生物物理信号，使用MCDropout不确定性量化。
result: "前瞻筛选100,160化合物，150个模型选择化合物确认45个结合物（30%命中率），富集因子234-408x，获得16个亚微摩尔先导，KD在233-345 nM。"
conclusion: HTS-Oracle X是可扩展的AI框架，用于非酶免疫检查点靶点的小分子发现。
---

## 摘要
使用小分子靶向免疫检查点蛋白-蛋白相互作用（PPI）仍受限于共刺激和共抑制受体的浅表、缺乏特征的结合表面，以及针对这些界面的传统高通量筛选固有的低命中率。在此，我们报告HTS-Oracle X，这是一个多模态深度学习平台，它整合了ChemBERTa SMILES嵌入与扩展RDKit描述符的双向交叉注意力融合，基于连续生物物理结合信号而非二元标签进行训练，并采用蒙特卡洛Dropout不确定性量化进行不确定性调整的化合物选择。在 scaffold 感知的交叉验证下，该平台对每个靶点使用45,760个Dianthus TRIC筛选的化合物进行训练，随后前瞻性地应用于针对CD28、TIM-3和VISTA的100,160个Enamine化合物库。从150个模型选择的化合物中，鉴定出45个剂量反应确认的结合剂（整体命中率30.0%），相对于实验确定的随机前瞻基线，富集因子达到234-408倍，并发现16个亚微摩尔级命中物。顶级命中物HX-CD28-1（KD = 233 nM）、HX-TIM3-1（KD = 249 nM）和HX-VISTA-1（KD = 345 nM）在免疫细胞和肿瘤共培养实验中展示了靶向功能性活性。HTS-Oracle X代表了一个可扩展的AI引导框架，用于针对非酶免疫检查点靶点的小分子发现。

## Abstract
Targeting immune checkpoint protein-protein interactions (PPIs) using small molecules remains limited by the shallow, featureless binding surfaces of co-stimulatory and co-inhibitory receptors and the characteristically low hit rates of conventional high-throughput screening against these interfaces. Here we report HTS-Oracle X, a multimodal deep learning platform that integrates bidirectional cross-attention fusion of ChemBERTa SMILES embeddings with extended RDKit descriptors, trains on continuous biophysical binding signals rather than binary labels, and employs Monte Carlo Dropout uncertainty quantification for uncertainty-adjusted compound selection. Trained on 45,760 Dianthus TRIC-screened compounds per target under scaffold-aware cross-validation, HTS-Oracle X was applied prospectively to a 100,160-compound Enamine library against CD28, TIM-3, and VISTA. From 150 model-selected compounds, 45 dose-response confirmed binders were identified (30.0% overall hit rate), yielding enrichment factors of 234-408x over experimentally established random prospective baselines and 16 sub-micromolar hits. The top hits, HX-CD28-1 (KD = 233 nM), HX-TIM3-1 (KD = 249 nM), and HX-VISTA-1 (KD = 345 nM), demonstrated on-target functional activity in immune cell and tumor co-culture assays. HTS-Oracle X represents a scalable AI-guided framework for small molecule discovery against non-enzymatic immune checkpoint targets.