---
title: Generative design of antigen-specific T-cell receptor sequences with a conditional diffusion model
title_zh: 基于条件扩散模型的抗原特异性T细胞受体序列生成设计
authors: "Zhang, Y., Liang, W., Xu, S., Witney, M., Rossjohn, J., Su, X., Purcell, A. W., Wang, F., Song, J."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.730756v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 基于扩散模型的T细胞受体序列生成
tldr: T细胞受体(TCR)的抗原特异性识别对肿瘤和感染性疾病的免疫治疗至关重要。现有计算方法在条件引导、灵活性和功能验证方面存在局限。本文提出TCRDiff，一种基于条件扩散模型的生成框架，能够设计针对特定肽-MHC(pMHC)靶点且与给定胚系可变基因匹配的TCR CDR3β序列。通过利用海量T细胞库和TCR-pMHC识别数据的预训练知识，TCRDiff通过去噪扩散过程生成高保真的结合TCR序列，并借助界面几何特征提升生成复合物的结构合理性。体外激活实验验证了TCRDiff生成的TCR能够特异性识别MAGE-A3表位，且脱靶交叉反应性极低。该工作为加速基于TCR的免疫治疗开发提供了有效的计算范式。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有计算设计抗原特异性TCR的方法受限于弱条件引导、灵活性不足及缺乏严格功能验证。
method: 提出TCRDiff，一种以pMHC靶点和胚系可变基因为条件的扩散模型，从大量TCR组库数据中学习并生成CDR3β序列。
result: 生成的TCR在体外激活实验中特异性识别MAGE-A3表位，且脱靶交叉反应性极低，结合位点结构合理性更高。
conclusion: TCRDiff为加速基于TCR的免疫疗法开发提供了经过验证的强效计算范式。
---

## 摘要
基于T细胞受体（TCR）的免疫疗法在治疗癌症和传染病方面具有巨大潜力，其中高度抗原特异性的TCR识别对于针对肿瘤和病原体的适应性免疫至关重要。通过人工智能对TCR的互补决定区3（CDR3）环进行工程改造或从头生成，为设计反应性TCR提供了一种强有力的替代方案，而非繁琐的实验筛选。然而，当前的计算方法受限于弱条件引导、灵活性不足以及缺乏严格的功能验证。为解决这些局限性，我们引入了TCRDiff，一种生成式扩散框架，用于设计以肽-MHC（pMHC）靶点和种系编码可变基因为条件的抗原特异性TCR。通过利用来自大规模T细胞库和TCR-pMHC识别数据的预训练知识，TCRDiff通过去噪扩散过程生成与天然结合TCR具有最先进保真度的CDR3β序列。此外，整合界面几何特征生成的TCR-pMHC复合物具有优越的结构合理性。作为概念验证，我们将TCRDiff部署在一个系统管道中，以设计用于免疫疗法的候选TCR。体外激活实验验证了TCRDiff生成的TCR能够特异性识别MAGE-A3表位，并具有最小化的脱靶交叉反应性。总之，TCRDiff建立了一种强大且经过验证的计算范式，可加速基于TCR的免疫疗法的发展。

## Abstract
T cell receptor (TCR)-based immunotherapy holds immense potential for treating cancers and infectious diseases, where highly antigen-specific TCR recognition is crucial for adaptive immunity against tumors and pathogens. Engineering or de novo generation of the complementarity-determining region 3 (CDR3) loops of TCRs using artificial intelligence offers a powerful alternative to designing reactive TCRs rather than laborious experimental screening. However, current in silico approaches are constrained by weak conditional guidance, limited flexibility, and a lack of rigorous functional validation. To address these limitations, we introduce TCRDiff, a generative diffusion framework for designing antigen-specific TCRs conditioned on peptide-MHC (pMHC) targets and germline-encoded variable genes. By leveraging pre-trained knowledge from massive T-cell repertoires and TCR-pMHC recognition data, TCRDiff generates CDR3{beta} sequences with state-of-the-art fidelity to native binding TCRs through a denoising diffusion process. Furthermore, incorporating the interface geometry features generated TCR-pMHC complexes with superior structural plausibility. As a proof of concept, we deployed TCRDiff in a systematic pipeline to design candidate TCRs for immunotherapy. In vitro activation assays validated that TCRDiff-generated TCRs specifically recognize the MAGE-A3 epitope with minimized off-target cross-reactivity. Together, TCRDiff establishes a powerful, validated computational paradigm to accelerate the development of TCR-based immunotherapies.