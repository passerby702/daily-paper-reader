---
title: "MORPHE: Bridging Image Generation and Spatial Omics for Tissue Synthesis"
title_zh: MORPHE：连接图像生成与空间组学实现组织合成
authors: "Feng, Y., Robers, Z., Rasheed, L., Miao, Y., Wen, S., Lee, K., Sohigian, J., Brbic, M., Hickey, J. W."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.03.709377v2.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 扩散模型用于图像与空间组学的多模态生成
tldr: 空间组学技术受限于成本、覆盖和维度，MORPHE框架通过图引导概率嵌入将细胞身份与空间关系映射至RGB-like潜在空间，结合扩散模型实现单细胞分辨率的组织生成。该方法在肠道与脑数据上可扩展至百万细胞，支持外推、内插和跨组织填补，在2D和3D上修复实验限制，为空间组学数据提供新思路。
source: biorxiv
selection_source: fresh_fetch
motivation: 空间组学数据成本高、覆盖不全且存在实验伪影，亟需计算方法扩展或重建组织上下文。
method: MORPHE利用图引导概率嵌入将细胞空间映射为RGB-like潜在表示，结合扩散模型学习生成。
result: 在肠道和脑数据集上，MORPHE实现外推、内插和跨组织填补，支持2D/3D单细胞级重构。
conclusion: MORPHE作为新型组织生成算法，可有效应对空间组学数据的限制与挑战。
---

## 摘要
空间分辨组学技术以单细胞分辨率揭示组织结构，但受限于检测成本、空间覆盖不完全、仅二维成像以及实验伪影。这些因素促使我们需要计算机模拟方法，以重建或扩展当前空间测量所提供的组织上下文。我们提出MORPHE（结构化空间高维嵌入建模），这是一种人工智能框架，学习直接从空间组学数据中合成具有生物真实性的组织结构。MORPHE引入了一种基于图的概率嵌入，将离散的细胞身份及其空间关系映射到与扩散建模兼容的连续RGB类潜在空间中。这种表示桥梁使得空间细胞图谱能够利用大型预训练图像生成模型，同时在解码时保留生物学可解释性。通过将细胞建模为生成的基本单元，并学习它们的身份和空间关系如何共同产生大规模组织结构，MORPHE能够以单细胞分辨率生成和重建组织结构。我们将该方法应用于来自肠道的单细胞蛋白质组学大规模数据集和来自脑的单细胞转录组学数据集，展示了其对数百万个细胞的计算可扩展性。我们在这些数据集上使用MORPHE来进行超出实验限制视野的外推绘制、填补缺失或实验损伤的组织区域，以及进行跨组织插补，将分离的组织区域连接成单个连续的样本（二维和三维）。MORPHE代表了一类新的组织生成算法，将有助于解决当前单细胞空间组学数据集的局限性和挑战。

## Abstract
Spatially resolved omics technologies reveal tissue organization at single-cell resolution but remain limited by the cost of the assays, incomplete spatial coverage, 2D-only imaging, and experimental artifacts. These factors motivate the need for in silico methods that can reconstruct or extend tissue context beyond what current spatial measurements provide. We present MORPHE (MOdeling of stRuctured sPatial High-dimensional Embeddings), an AI framework that learns to synthesize biologically faithful tissue architecture directly from spatial-omics data. MORPHE introduces a graph-informed probabilistic embedding that maps discrete cell identities and their spatial relationships into a continuous RGB-like latent space compatible with diffusion modeling. This representational bridge enables spatial cellular maps to leverage large pre-trained image-generative models while preserving biological interpretability upon decoding. By modeling cells as the fundamental units of generation and learning how their identities and spatial relationships collectively give rise to large-scale tissue structure, MORPHE enables generation and reconstruction of tissue architecture at single-cell resolution. We applied the method across large-scale single-cell proteomic datasets from the intestine and single-cell transcriptomic datasets from the brain, showing computational scalability acrosss millions of cells. We used MORPHE on these datasets to outpaint beyond experimentally restricted fields of view, inpaint missing or experimentally damaged tissue regions, and perform cross-tissue imputation, connecting separated tissue regions into a single contiguous sample in both 2D and 3D. MORPHE represents a new class of tissue generation algorithms that will help solve current limitations and challenges with single-cell spatial-omics datasets.