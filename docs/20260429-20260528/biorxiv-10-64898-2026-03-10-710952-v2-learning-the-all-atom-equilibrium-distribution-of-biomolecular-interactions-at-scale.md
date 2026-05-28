---
title: Learning the All-Atom Equilibrium Distribution of Biomolecular Interactions at Scale
authors: "Wang, Y., Xu, Y., Li, W., Yu, H., Tan, W., Li, S., Huang, Q., Chen, N., Wu, X., Wu, Q., Liu, K."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.10.710952v2.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 用于采样蛋白-配体相互作用平衡分布的生成框架
tldr: 虽然AlphaFold等模型在静态结构预测上取得突破，但准确捕捉全原子平衡分布仍是挑战，主要因分子动力学模拟成本高。AnewSampling采用商空间生成框架与超1500万构象的大规模蛋白-配体轨迹数据，实现全原子高保真采样。在ATLAS基准上一致超越先前方法，并与真实MD统计对齐；在CDK2系统中成功恢复配体与侧链的耦合运动。这有望在密集型模拟前快速探索构象景观，阐明基本生物物理机制，加速功能性生物分子设计。
source: biorxiv
selection_source: fresh_fetch
motivation: 捕捉全原子平衡分布对于理解生物分子功能至关重要，但MD模拟成本过高，现有生成方法无法高保真复现。
method: 提出AnewSampling，基于商空间生成框架，利用自整理的1500万构象蛋白-配体轨迹数据库。
result: 在ATLAS基准上显著超越先前方法，并与真实MD紧密对齐；在CDK2中克服采样难点，恢复耦合运动。
conclusion: AnewSampling实现了全原子平衡分布高保真采样，可加速构象探索和功能分子设计。
---

## 摘要
生物分子功能由动态构象系综而非静态结构所控制。虽然 AlphaFold 等模型彻底改变了静态结构预测，但由于分子动力学（MD）的高计算成本，准确捕捉全原子生物分子相互作用的平衡分布仍是一个重大挑战。我们提出了 AnewSampling，这是一个可迁移的生成式基础框架，旨在高保真地采样全原子平衡分布，是首个在原子水平上忠实重现 MD 的模型。它采用商空间生成框架以确保数学一致性，并利用了迄今为止最大的自建蛋白质-配体轨迹数据库，包含超过 1500 万个构象。统计上，AnewSampling 在 ATLAS 单体基准上始终优于所有先前的生成方法，并且 AnewSampling 的全原子能力使其在评估蛋白质-配体动力学中的原子生物分子相互作用时，能够与真实 MD 实现接近的统计对齐。此外，AnewSampling 成功恢复了 CDK2 系统中配体与侧链的耦合运动，克服了传统 MD 固有的主要采样障碍。AnewSampling 能够在密集模拟前快速探索构象景观，阐明基本生物物理机制，并加速更广泛的功能生物分子设计。

## 速览
**TLDR**：生物分子功能由其动态构象系综决定，但全原子平衡分布采样因分子动力学模拟计算成本过高而受限。AnewSampling模型采用商空间生成框架，基于全球最大的蛋白-配体轨迹数据库训练，首次在原子水平上高保真复现MD。模型在ATLAS单体基准上显著优于所有现有生成方法，并成功捕捉CDK2系统中配体与侧链的耦合运动。该工作为在深入模拟前快速探索构象景观、揭示生物物理机制及加速功能分子设计奠定了基础。 \
**Motivation**：准确捕捉全原子生物分子互作平衡分布需高昂的分子动力学计算，亟需高效生成模型。 \
**Method**：提出AnewSampling框架，采用商空间生成方法确保数学一致性，利用自建的包含超1500万构象的蛋白-配体轨迹库训练。 \
**Result**：在ATLAS基准上超越所有生成方法，在蛋白-配体动力学中与MD统计高度一致，并首次恢复CDK2体系中的耦合运动。 \
**Conclusion**：AnewSampling可快速勘探构象系综，克服传统MD采样瓶颈，加速功能生物分子设计与生物物理机制解析。

---

## Abstract
Biomolecular functions are governed by dynamic conformational ensembles rather than static structures. While models like AlphaFold have revolutionized static structure prediction, accurately capturing the equilibrium distribution of all-atom biomolecular interactions remains a significant challenge due to the high computational cost of molecular dynamics (MD). We present AnewSampling, a transferable generative foundation framework designed for the high-fidelity sampling of all-atom equilibrium distributions, which is the first model to faithfully reproduce MD at the all-atom level. It uses a quotient-space generative framework to ensure mathematical consistency and leverages the largest self-curated database of protein-ligand trajectories to date, with over 15 million conformations. Statistically, AnewSampling consistently outperforms all prior generative methods on the ATLAS monomer benchmark, and the all-atom capabilities of AnewSampling enable close statistical alignment with ground-truth MD for evaluating atomic biomolecular interactions in protein-ligand dynamics. Furthermore, AnewSampling successfully recovers coupled ligand and side-chain motions in CDK2 systems, overcoming a major sampling hurdle inherent to conventional MD. AnewSampling enables rapid exploration of conformational landscapes prior to intensive simulations, elucidating fundamental biophysical mechanisms and accelerating the broader design of functional biomolecules.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**  
  生物分子功能由动态构象系综而非单一静态结构决定。尽管 AlphaFold 等模型在静态结构预测上取得突破，但准确捕捉全原子水平生物分子相互作用的平衡分布仍是巨大挑战，主要原因是分子动力学（MD）模拟的高昂计算成本。

- **整体含义**  
  该工作旨在提供一个可高效替代昂贵 MD 模拟的生成式基础框架，使其能够在原子水平上高保真地采样构象平衡分布，从而在深入模拟之前快速探索构象景观、阐明生物物理机制，并加速功能分子设计。

### 2. 论文提出的方法论

- **核心思想**  
  构建一个可迁移的生成式框架 AnewSampling，直接从数据中学习全原子平衡分布，实现高保真构象采样，首次在原子层级忠实复现 MD 统计结果。

- **关键技术与框架**  
  - **商空间生成框架（quotient‑space generative framework）**：确保生成过程在数学上与物理平衡分布的一致性。  
  - **大规模自建数据库**：利用至今最大的蛋白质‑配体轨迹数据集，包含超过 1500 万个构象，用于训练模型。

- **算法流程**（基于摘要推断）  
  通过商空间生成模型对构象系综进行建模，以大量 MD 轨迹中的构象为训练目标，学习从简单分布到复杂全原子构象的映射，生成符合真实平衡分布的样本。

### 3. 实验设计

- **数据集/场景**  
  - 自建蛋白质‑配体轨迹数据库（>1500 万构象），用于训练。  
  - **ATLAS 单体基准**：用于评估模型在蛋白质单体构象采样上的表现。  
  - **CDK2 系统**：用于验证蛋白质‑配体相互作用中配体与侧链的耦合运动恢复能力。

- **对比方法**  
  与所有先前生成式方法（具体名称在摘要中未列出）进行比较，AnewSampling 在 ATLAS 基准上一致优于这些方法。

### 4. 资源与算力

- 摘要中**未明确提及** GPU 型号、数量、训练时长等具体资源与算力信息。

### 5. 实验数量与充分性

- **实验量概览**  
  - 至少包含 ATLAS 单体基准上的多方法对比实验。  
  - 在蛋白质‑配体动力学评估中与真实 MD 进行统计对齐实验。  
  - 在 CDK2 系统上验证耦合运动恢复能力。  
  由于仅有摘要，无法获知更详细的消融实验或敏感性分析是否开展。

- **充分性评价**  
  从描述看，实验覆盖了单体构象采样和复合物动态耦合两个关键场景，并与真实 MD 统计对齐，在一定程度上支撑了方法的有效性与泛化性。但缺少具体的消融研究或不同体系规模的系统性验证细节，无法完全判断实验的全面性和公平性。

### 6. 论文的主要结论与发现

- AnewSampling 是**首个在原子水平上忠实重现 MD 的模型**，在 ATLAS 单体基准上显著超越所有先前生成方法。  
- 蛋白质‑配体动力学评估中，AnewSampling 的全原子能力使其与真实 MD 的统计分布高度一致。  
- 成功恢复 CDK2 系统中**配体与侧链的耦合运动**，克服了传统 MD 在此类体系中遇到的采样障碍。  
- 模型能够**在密集模拟前快速探索构象景观**，为阐明生物物理机制和加速功能性生物分子设计奠定基础。

### 7. 优点

- **方法创新**：引入商空间生成框架，数学上保障生成分布与物理平衡分布一致性。  
- **数据规模**：使用含超 1500 万构象的大规模轨迹数据库，增强模型的表征能力和泛化性。  
- **全原子高保真**：在原子层级复现 MD 统计，填补了现有生成模型在全原子精度上的不足。  
- **实例验证突出**：在 CDK2 上成功捕捉到传统 MD 难以采样的耦合运动，展示了对困难体系的优势。

### 8. 不足与局限

- **算力信息缺失**：未提供训练所需 GPU 资源、时间等细节，难以评估实用成本和可复现性。  
- **实验详细度有限**：仅从摘要看，缺少消融实验、不同体系尺寸或类型的系统比较，结论的稳健性和适用范围尚待全文验证。  
- **应用边界未知**：聚焦于蛋白质‑配体系统，是否适用于更大生物组装体或其他非蛋白质体系尚不明确。  
- **与真实 MD 的偏差**：虽称“高保真”，但对精细动力学、非平衡过程的采样质量未能量化，可能存在隐藏偏差。

（完）
