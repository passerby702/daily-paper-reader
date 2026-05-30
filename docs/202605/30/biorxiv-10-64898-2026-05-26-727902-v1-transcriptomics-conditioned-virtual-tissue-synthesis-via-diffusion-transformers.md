---
title: Transcriptomics-Conditioned Virtual Tissue Synthesis via Diffusion Transformers
title_zh: 基于转录组学条件的虚拟组织合成：扩散变换器方法
authors: "Vlachas, P., Nonchev, K., Koelzer, V., Ratsch, G."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727902v1.full.pdf"
tags: ["query:diff-gen"]
score: 9.0
evidence: 扩散变换器从转录组学多模态图像合成
tldr: "空间转录组学将H&E组织形态与空间基因表达耦合，但生成模型鲜有利用该耦合合成组织图像。STMDiT扩散变压器通过自适应层归一化和交叉注意力，融合基因表达与形态嵌入生成病理切片。在黑色素瘤队列上，基因条件将FID从330.7降至252.9，AUC从0.229升至0.267；使用伪标签训练后零样本迁移至TCGA SKCM，FID达690.0（改善57点），实现分布外合成。代码已开源，为计算病理学假设检验提供虚拟组织模拟工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 空间转录组学蕴含基因-形态耦合，但缺乏利用转录组谱合成组织图像的生成模型，限制了虚拟组织模拟。
method: STMDiT扩散变压器集成冷冻CancerFoundation编码器，通过自适应层归一化和逐块交叉注意力，以基因表达和形态嵌入为双条件，采用双分类器自由引导训练。
result: "基因条件将FID从330.7降至252.9，AUC从0.229升至0.267（达真实切片上限82%）；伪标签训练使零样本OOD FID达690.0，改善57点。"
conclusion: "基因表达条件产生形态可辨的组织图像，支持虚拟组织模拟和假设检验，并通过伪标签拓展至无空间转录组数据的H&E队列。"
---

## 摘要
空间转录组学将苏木精-伊红（H&E）染色的组织形态与空间解析的基因表达（GE）相结合。然而，利用这种耦合关系从转录组谱合成组织图像的生成模型仍然稀少。我们提出了STMDiT（空间转录组学与形态学扩散变换器），这是一种扩散变换器，联合以形态嵌入和转录组谱为条件合成H&E组织病理切片。基于PixCell（Yellapragada等人，2025），我们通过自适应层归一化和逐块交叉注意力整合来自冻结的CancerFoundation编码器（Theus等人，2024）的基因表达，并在双重无分类器引导和独立模态丢弃下进行训练。在10x TuPro Visium黑色素瘤队列中，基因表达条件相较于无基因表达的PixCell-B基线提升了图像质量（最佳FID为252.9对比330.7）和转录组保真度（最佳AUC为0.267对比0.229，达到真实瓷砖上限的82%）。使用DeepSpot的预测转录组伪标签（PTPL）训练可独特地零样本迁移至TCGA SKCM，一个分布外（OOD）仅含H&E的黑色素瘤队列：PTPL-XAttn-PMA-B达到FID=690.0，较无基因表达基线（747.1）下降57点，模型内基因表达消融效应为ΔOOD=+309.5，从而实现了超越原生空间转录组覆盖范围的虚拟组织合成。我们的结果表明，基因表达条件产生了形态上可区分的组织图像，并支持用于计算病理学假设检验的虚拟组织模拟。代码可用性：https://github.com/ratschlab/stmdit

## Abstract
Spatial transcriptomics couples hematoxylin and eosin (H&E) tissue morphology with spatially resolved gene expression (GE). However, generative models that exploit this coupling to synthesize tissue images from transcriptomic profiles remain scarce. We present STMDiT (Spatial Transcriptomics and Morphology Diffusion Transformer), a diffusion transformer that synthesizes H&E histopathology patches conditioned jointly on morphological embeddings and transcriptomic profiles. Building on PixCell (Yellapragada et al., 2025), we integrate gene expression from a frozen CancerFoundation encoder (Theus et al., 2024) through adaptive layer normalization and per-block cross-attention, and we train under dual classifier-free guidance with independent modality dropout. On the 10x TuPro Visium melanoma cohort, GE conditioning improves both image quality over the no-GE PixCell-B baseline (best FID = 252.9 vs 330.7) and transcriptomic fidelity (best AUC = 0.267 vs 0.229, reaching 82% of the real-tile ceiling). Training with DeepSpot's predicted-transcriptomics pseudo-labels (PTPL) uniquely transfers zero-shot to TCGA SKCM, an out-of-distribution (OOD) H&E-only melanoma cohort: PTPL-XAttn-PMA-B reaches FID = 690.0, a 57-point improvement over the no-GE baseline (747.1), with a within-model GE-ablation effect of {Delta}OOD = +309.5, enabling virtual tissue synthesis beyond native spatial-transcriptomics coverage. Our results indicate that gene-expression conditioning produces morphologically distinct tissue images and supports virtual tissue simulation for hypothesis testing in computational pathology. Code availability: https://github.com/ratschlab/stmdit

---

## 论文详细总结（自动生成）

# 论文详细总结：基于转录组学条件的虚拟组织合成（扩散变换器方法）

## 1. 论文核心问题与整体含义
*   **研究背景**：空间转录组学技术（如10x Visium）能够将组织切片的苏木精-伊红（H&E）染色形态与空间解析的基因表达（GE）进行配对。这种天然耦合关系蕴含着“基因型—组织形态”的深层联系。
*   **核心问题**：当前生成模型极少利用这种耦合关系，从转录组谱直接合成出逼真、可区分的组织病理图像，导致无法实现“虚拟组织模拟”来辅助计算病理学研究（如假设检验、数据增强）。
*   **整体含义**：该工作旨在填补空白，通过扩散变换器实现**转录组条件**下的组织图像合成，并证明基因表达条件不仅能改善合成质量，还能让模型泛化到仅含H&E图像的外部队列，实现零样本虚拟组织合成。

## 2. 方法论
### 核心思想
基于扩散变换器架构，设计**双条件生成机制**：同时以组织形态嵌入（H&E图像本身或形态特征）和空间转录组谱（基因表达）作为条件，引导H&E病理补丁的合成。

### 关键技术细节
*   **基础架构**：建立在 **PixCell**（Yellapragada 等人, 2025）扩散变换器之上，命名为 **STMDiT**（Spatial Transcriptomics and Morphology Diffusion Transformer）。
*   **基因表达编码器**：采用一个**冻结的（frozen）CancerFoundation编码器**（Theus 等人, 2024），将基因表达谱转化为高维嵌入，不参与反向传播。
*   **条件融合方式**：通过 **自适应层归一化（Adaptive Layer Normalization）** 和 **逐块交叉注意力（Per-block Cross-Attention）** 将基因表达嵌入注入到扩散变换器的各个块中，与形态嵌入实现深度融合。
*   **训练策略**：
    *   **双重无分类器引导（Dual Classifier-Free Guidance）**：在训练和采样时分别对形态条件和基因条件进行独立调节和丢弃，增强条件可控性。
    *   **独立模态丢弃（Independent Modality Dropout）**：训练中随机丢弃形态或基因条件，迫使模型在单条件或无条件情况下也能生成，支撑无分类器引导。
*   **伪标签拓展**：对于无空间转录组数据的纯H&E队列，使用 **DeepSpot** 预测的转录组伪标签（Predicted-Transcriptomics Pseudo-Labels, PTPL）进行训练，实现分布外泛化。

## 3. 实验设计
### 数据集与场景
*   **主训练/评估队列**：**10x TuPro Visium 黑色素瘤队列**（包含配对H&E图像与空间基因表达）。
*   **零样本分布外（OOD）泛化队列**：**TCGA SKCM**（仅含H&E染色的黑色素瘤全切片图像，无原始空间转录组数据）。
*   **benchmark基准**：以**无基因表达条件的 PixCell-B** 作为基线（无GE条件仅形态合成）。
*   **对比方法**：自身方法的多个变体，如加入基因表达条件的模型、使用伪标签训练的模型等，通过消融实验对比。

### 评估指标
*   **图像质量**：Fréchet Inception Distance（FID），越低越好。
*   **转录组保真度**：曲线下面积（AUC），衡量合成图像与真实基因表达谱的关联一致性（以真实瓷砖的AUC为上限）。

## 4. 资源与算力
*   论文提供的元数据与摘要中**未明确说明**所使用的GPU型号、数量、训练总时长以及训练数据的具体规模（如表征补丁数量）。相关算力资源信息需查阅原文完整版。

## 5. 实验数量与充分性
*   **主要实验组数**：从摘要可辨识至少4组关键实验对比：
    1.  无基因条件基线（PixCell-B） vs 基因条件模型（FID、AUC对比）。
    2.  基因条件模型 vs 真实瓷砖上限（AUC达到上限的82%）。
    3.  使用伪标签（PTPL）训练的模型进行零样本OOD迁移，对比无GE基线。
    4.  在OOD条件下的基因表达消融实验（计算ΔOOD效应）。
*   **充分性评价**：实验设计覆盖了**内部队列对比**、**外部OOD泛化**、**消融验证**三个关键维度，且与无GE基线公平比较，通过FID和AUC双指标评估生成质量和条件保真度，具备较好的客观性和充分性。但实验目前集中在黑色素瘤单一癌种，跨癌种泛化未验证。

## 6. 主要结论与发现
*   **基因条件显著提升质量**：在10x Visium黑色素瘤队列上，基因表达条件将FID从基线的330.7降至252.9，改善明显。
*   **转录组保真度接近上限**：基因条件模型AUC达到0.267，相比于无GE基线的0.229，已经达到真实瓷砖上限的82%，证明合成图像能准确反映基因表达模式。
*   **伪标签实现零样本组织合成突破**：通过PTPL训练，模型成功零样本迁移到TCGA SKCM队列，FID达690.0，较无GE基线（747.1）优化57点。体内基因表达消融实验显示，移除基因条件后FID劣化高达309.5点，强有力证实了基因条件对OOD合成的关键作用。
*   **形态可区分性**：基因表达条件产生的组织图像在形态上可被区分，为虚拟组织模拟和计算病理假设检验提供了工具。

## 7. 优点
*   **新颖的条件融合机制**：将冻结的CancerFoundation编码器与自适应层归一化、逐块交叉注意力相结合，高效利用转录组先验，避免了大规模微调编码器的资源消耗。
*   **鲁棒的训练策略**：双重无分类器引导和独立模态丢弃增强了模型在不同条件下（仅形态、仅基因或双条件）的生成灵活性和控制力。
*   **开创性OOD泛化能力**：利用DeepSpot伪标签，使模型突破了原生空间转录组数据的覆盖限制，能够在常规H&E队列上进行虚拟组织合成，极大拓展了应用范围。
*   **开源与可复现**：代码已在GitHub公开，便于后续研究验证与拓展。

## 8. 不足与局限
*   **癌种单一**：所有实验仅基于黑色素瘤（Visium和SKCM），模型对其他组织类型或癌种的泛化能力未知。
*   **伪标签依赖性**：OOD泛化能力依赖于DeepSpot预测表达谱的准确性，若伪标签偏差较大，可能限制合成组织的生物学可解释性。
*   **缺少人类偏好评估**：评估仅依赖FID和AUC等自动指标，未报告病理学家对合成图像真实性的盲法评分或图灵测试。
*   **潜在偏差风险**：训练数据来自特定平台（10x Visium），合成图像可能带有平台相关的技术伪影，影响下游分析的公平性。
*   **应用限制**：虽支持虚拟组织模拟，但其在真实假设检验（如基因扰动驱动形态变化）中的因果推断能力尚未直接验证，仍停留在关联生成层面。

（完）
