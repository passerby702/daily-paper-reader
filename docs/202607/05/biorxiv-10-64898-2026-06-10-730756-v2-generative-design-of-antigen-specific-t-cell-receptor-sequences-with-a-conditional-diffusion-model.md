---
title: Generative design of antigen-specific T-cell receptor sequences with a conditional diffusion model
title_zh: 基于条件扩散模型的抗原特异性T细胞受体序列的生成式设计
authors: "Zhang, Y., Liang, W., Xu, S., Witney, M., Su, X., Andrews, M. C., Rossjohn, J., Purcell, A. W., Wang, F., Song, J."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.730756v2.full.pdf"
tags: ["query:diff-gen"]
score: 9.0
evidence: 用于抗原特异性TCR序列生成的条件扩散模型
tldr: T细胞受体（TCR）免疫疗法潜力巨大，但现有计算设计方法条件引导弱、灵活性差且缺乏功能验证。为此提出了TCRDiff条件扩散框架，基于大规模TCR库和TCR-pMHC识别数据，生成抗原特异性CDR3β序列。扩散过程结合界面几何特征，生成的TCR-pMHC复合物结构更合理。在MAGE-A3癌抗原上的体外验证表明，TCRDiff设计的TCR能高效识别靶点且脱靶反应低。该工作建立了经实验验证的计算范式，加速了TCR免疫疗法开发。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有计算方法条件引导弱、灵活性有限且缺乏严格功能验证，亟需生成抗原特异性TCR序列的新范式。
method: 提出TCRDiff条件扩散模型，利用预训练知识从TCR库学习，以pMHC和TCR可变基因条件生成CDR3β序列，并整合界面几何特征优化结构。
result: 生成的序列与天然结合TCR高度相似，结构合理性优于序列扩散或结构建模方法。体外实验验证对MAGE-A3抗原高效识别且脱靶低。
conclusion: TCRDiff建立了经验证的计算范式，可加速TCR免疫疗法开发，在癌症、自身免疫和感染病治疗中具有应用潜力。
---

## 摘要
基于T细胞受体（TCR）的免疫疗法在治疗癌症、自身免疫性疾病和传染病方面具有巨大潜力，其中抗原特异性TCR识别对于适应性免疫反应至关重要。利用人工智能工程化或从头生成TCR互补决定区3（CDR3）环，为设计抗原特异性TCR提供了一种强大的替代方案，避免了繁琐的实验筛选。然而，当前的计算机模拟方法受到条件引导弱、灵活性有限以及缺乏严格功能验证的制约。为解决这些局限性，我们引入了TCRDiff，这是一个生成式扩散框架，用于设计以肽-MHC（pMHC）靶点和种系编码的TCR可变基因为条件的抗原特异性TCR。通过利用大量T细胞库和TCR-pMHC识别数据的预训练知识，TCRDiff通过去噪扩散过程生成与天然结合TCR高度相似的CDR3β序列。此外，纳入界面几何特征生成的TCR-pMHC复合物，在结构合理性上优于仅依赖基于序列的扩散或基于结构的建模的方法。作为概念验证，我们在一个系统流程中部署TCRDiff，设计针对临床验证的癌症抗原的候选TCR。体外激活实验验证了TCRDiff生成的TCR能够有效识别MAGE-A3表位，且脱靶反应性极小。因此，TCRDiff建立了一个强大且经过验证的计算范式，以加速基于TCR的免疫疗法的发展。

## Abstract
T cell receptor (TCR)-based immunotherapy holds immense potential for treating cancers, autoimmunity, and infectious diseases, where antigen-specific TCR recognition is crucial for adaptive immune responses. Engineering or de novo generation of the complementarity-determining region 3 (CDR3) loops of TCRs using artificial intelligence offers a powerful alternative to designing antigen-specific TCRs rather than laborious experimental screening. However, current in silico approaches are constrained by weak conditional guidance, limited flexibility, and a lack of rigorous functional validation. To address these limitations, we introduce TCRDiff, a generative diffusion framework for designing antigen-specific TCRs conditioned on peptide-MHC (pMHC) targets and germline-encoded TCR variable genes. By leveraging pre-trained knowledge from massive T-cell repertoires and TCR-pMHC recognition data, TCRDiff generates CDR3{beta} sequences that closely resemble native-binding TCRs via a denoising diffusion process. Furthermore, incorporating interface geometry features generated TCR-pMHC complexes with superior structural plausibility than models relying solely on sequence-based diffusion or structure-based modeling. As a proof of concept, we deployed TCRDiff in a systematic pipeline to design candidate TCRs against a clinically validated cancer antigen. In vitro activation assays validated that TCRDiff-generated TCRs efficiently recognize the MAGE-A3 epitope with minimal off-target reactivity. Thus, TCRDiff establishes a powerful, validated computational paradigm to accelerate the development of TCR-based immunotherapies.

---

## 论文详细总结（自动生成）

# 论文结构化中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：T细胞受体（TCR）在癌症、自身免疫和感染性疾病免疫治疗中至关重要。现有实验筛选方法（如MHC四聚体测序、微流控技术等）耗时费力，且难以高效探索巨大的TCR序列空间；而已有的计算生成方法（如Seq2Seq、VAE）存在条件引导弱、灵活性差、缺乏严格功能验证等局限。
- **目标**：开发一个能够以pMHC靶点和TCR种系可变基因为条件、**从头生成抗原特异性TCR CDR3β序列**的生成式模型，并通过体外实验验证其功能性。

## 2. 方法论

### 核心思想
- 采用**离散条件扩散模型**，在去噪过程中利用pMHC条件信息和TCR周围序列（CDR1/2、V基因）迭代生成CDR3β氨基酸。
- 结合预训练的TCR语言模型（基于Diffusion Transformer, DiT）和pMHC结合模型（基于PairFormer架构），通过PairFormer适配器融合条件信息。
- 可选集成**结构指导**（TCRDiff+）：将ProteinMPNN基于结构的logits叠加到扩散步骤中，以提升结构合理性。

### 关键技术细节
- **前向扩散**：逐步掩码CDR3序列，直至完全随机。
- **反向去噪**：在每一步预测掩码位置的概率分布，采用确定性解码（argmax）或随机解码（Gumbel噪声采样）。
- **条件嵌入**：pMHC通过预训练的肽-MHC结合模型获得表示，再经由PairFormer适配器与TCR表示交互。
- **损失函数**：简化为重加权的交叉熵损失（相当于掩码语言模型损失），采用线性或常数权重策略。
- **迭代生成**：从完全掩码开始，每个时间步保留置信度高的token，重新掩码置信度低的token，逐步生成完整序列。

## 3. 实验设计

### 使用数据集
- **预训练TCR库**：来自Observed TCR Space、10X Genomics、泛疾病人类CD8+CD4+ T细胞图谱等，共约247万人类TCR和31.5万小鼠TCR。
- **TCR-pMHC反应对**：IEDB、VDJdb、PIRD、McPAS等数据库收集，共135,244个训练对（含配对TRA-TRB、单链记录），验证集1,817个。
- **负样本**：随机打乱（3倍正样本） + 健康库采样（2倍正样本）。
- **IMMREP23测试集**：598个阳性TCR-pMHC对，覆盖20个pMHC靶点，用于独立评估。
- **STCRDab结构测试集**：34个2022年后释放的TCR-pMHC复合物晶体结构，用于评估结构合理性。

### Benchmark与对比方法
- **TCR-pMHC结合预测**：对比NetTCR v2.2、STAPLER、pMTnet-omni、TULIP、TAPIR等。
- **序列生成**：对比GRATCR、TCR-Translate、ProteinMPNN。
- **消融实验**：逐步加入预训练、子采样、PairFormer架构，评估AUPR、AAR等指标。

### 评估指标
- 结合预测：AUPR、AUC0.1
- 生成一致性：Amino Acid Recovery (AAR)、Levenshtein距离、BLOSUM分数、序列一致性
- 结构合理性：ipTM（界面模板建模得分）、pLDDT、PAE、iRMSD（与实验结构对比）

## 4. 资源与算力

- 文中**未明确说明**使用的GPU型号、数量及训练时长。
- 仅提到使用AdamW优化器，学习率1e-4到2e-4，训练80-200个epoch，采用早停策略。算力规格未披露。

## 5. 实验数量与充分性

- **大量消融实验**：包括预训练、子采样、PairFormer、不同解码策略（确定性/随机）、不同条件输入（无条件、加CDR1/2、加pMHC）等。
- **多数据集验证**：内部验证集、IMMREP23独立测试集、STCRDab结构测试集。
- **跨物种/跨MHC类别**：人/小鼠、MHC-I/II均有评估。
- **结构生成对比**：与ProteinMPNN在34个结构上进行AAR、ipTM、iRMSD对比。
- **体外功能验证**：针对MAGE-A3抗原设计5个候选TCR，用J76-NFAT报告细胞系进行Luciferase和CD69激活实验，同时检测对Titin脱靶肽的反应。
- **实验充分性评价**：实验设计较为全面，涵盖了结合预测、序列生成、结构评估、体外功能验证四个层次。但**缺少体内动物实验**，且仅验证了一个抗原靶点（MAGE-A3），泛化性仍有限。

## 6. 主要结论与发现

1. **TCRDiff在TCR-pMHC结合预测上达到最优**：在IMMREP23上平均AUPR达0.515，优于TULIP（0.422）等；AUC0.1也领先。
2. **条件扩散生成CDR3序列高度一致**：在验证集上AAR达0.635，在IMMREP23上AAR达0.597；生成序列多样性高（87.9%唯一），且能准确恢复已知CDR3β基序（如GILGFVFTL的R-S-S-Y）。
3. **融合结构信息（TCRDiff+）进一步提升结构合理性**：在STCRDab测试集上，CDR3β AAR达0.692（单独TCRDiff为0.635），ipTM达0.826，iRMSD与实验结构高度相关（r=-0.69）。
4. **体外实验验证了功能性**：所设计5个候选TCR中有4个（TCR2-5）能特异性识别MAGE-A3表位，且脱靶激活（对Titin肽）极低，而野生型MAG-IC3 TCR出现强脱靶反应。

## 7. 优点

- **方法创新性**：首次将离散条件扩散模型应用于抗原特异性TCR CDR3从头生成，具备灵活的条件控制和迭代精炼能力。
- **强大的通用性**：跨物种（人/小鼠）、跨MHC类（I/II）、跨肽类型（病毒、肿瘤、新抗原）表现稳健。
- **结构-序列协同**：TCRDiff+巧妙结合结构设计（ProteinMPNN）和序列扩散，弥补了纯序列方法在结构合理性上的不足。
- **实验验证严谨**：不仅进行了全面的计算评估，还完成了体外细胞功能实验，直接证明了生成TCR的功能活性与特异性。

## 8. 不足与局限

- **数据偏差**：训练数据偏向常见病毒表位和已知肿瘤抗原，对新抗原和稀有MHC亚型泛化性受限。
- **缺乏算力细节**：未报告GPU规格和训练耗时，可复现性参考信息不足。
- **体外验证范围小**：仅针对一个抗原（MAGE-A3）在J76报告细胞系上验证，缺少原代T细胞实验和体内肿瘤模型评估。
- **生成范围有限**：当前仅生成CDR3αβ序列，未扩展至CDR1/CDR2，且未考虑TCR交叉反应性与力学性质（如catch-bond）。
- **结构依赖风险**：TCRDiff+依赖ProteinMPNN生成的结构模板，若模板质量差（如非天然对接结构），可能引入偏差。
- **未进行多轮迭代学习**：未利用实验反馈进行主动学习或强化学习优化。

（完）
