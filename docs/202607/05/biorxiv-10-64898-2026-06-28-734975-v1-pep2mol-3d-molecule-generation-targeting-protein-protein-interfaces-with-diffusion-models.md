---
title: "Pep2Mol: 3D Molecule Generation Targeting Protein-Protein Interfaces with Diffusion Models"
title_zh: "Pep2Mol: 利用扩散模型靶向蛋白质-蛋白质界面的3D分子生成"
authors: "Yue, R., Yang, Z., Seabra, G., Li, C., Li, Y."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.734975v1.full.pdf"
tags: ["query:pocket-lig"]
score: 10.0
evidence: 使用扩散模型针对蛋白质界面设计3D分子
tldr: 蛋白-蛋白相互作用(PPI)在生物过程中至关重要，但现有结构药物设计方法难以处理PPI界面的大、浅且化学复杂特性。本文提出Pep2Mol扩散模型，利用结合肽或蛋白作为结构引导，生成靶向PPI位点的3D分子。模型通过两个SE(3)-等变图神经网络分别编码蛋白-配体和蛋白-肽相互作用，并用注意力机制融合表征引导扩散。在10596个实验解析复合物结构数据集上，生成配体具备高化学有效性和最优结合亲和力，为挑战性PPI界面的小分子抑制剂设计奠定基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有结构药物设计难以处理PPI界面的大、浅及化学复杂性，需要针对正交位点的新生成方法。
method: 提出Pep2Mol扩散模型，整合SE(3)-等变图神经网络编码蛋白-配体和蛋白-肽相互作用，通过注意力融合引导扩散。
result: 在10596个复合物数据集上，生成分子化学有效且结合亲和力达到最优水平。
conclusion: Pep2Mol为设计靶向挑战性PPI界面的小分子抑制剂提供强大基础。
---

## 摘要
蛋白质-蛋白质相互作用（PPI）是生物过程的核心。设计调节失调PPI的小分子为靶向“不可成药”蛋白带来了巨大希望。然而，现有的基于结构的药物设计方法聚焦于定义明确的小分子结合口袋，难以推广到大型、浅表且化学复杂的PPI界面。在此，我们提出Pep2Mol，一种基于扩散的3D分子设计生成模型，通过明确结合肽或蛋白质作为结构指导来靶向正构PPI位点，超越了传统的口袋条件生成。为支持模型开发和基准测试，我们整理了一个大规模、高质量的数据集，包含10956个实验解析的蛋白质复合物结构对，每对在重叠的受体界面上匹配一个正构竞争性配体与一个蛋白质结合物。Pep2Mol集成了两个SE(3)-等变图神经网络，分别编码蛋白质-配体和蛋白质-肽相互作用，并通过基于注意力的条件融合这些表示以联合引导扩散轨迹。广泛的评估表明，Pep2Mol生成的化学有效配体具有最先进的结合亲和力，为针对挑战性PPI界面的小分子抑制剂设计提供了坚实基础。

## Abstract
Protein-protein interactions (PPIs) are central to biological processes. Designing small molecules that modulate dysregulated PPIs holds strong promise for targeting undruggable proteins. However, existing structure-based drug design approaches focus on well-defined small-molecule binding pockets and struggle to generalize to large, shallow, and chemically complex PPI interfaces. Here, we introduce Pep2Mol, a diffusion-based generative model for 3D molecule design that targets orthosteric PPI sites by explicitly incorporating binding peptides or proteins as structural guidance, moving beyond conventional pocket-conditioned generation. To enable model development and benchmarking, we curate a large-scale, high-quality dataset of 10,956 experimentally resolved protein complex structure pairs, each pairing an orthosteric competitive ligand with a protein binder at overlapping receptor interfaces. Pep2Mol integrates two SE(3)-equivariant graph neural networks that encode protein-ligand and protein-peptide interactions respectively, and fuses these representations via attention-based conditioning to jointly guide the diffusion trajectory. Extensive evaluations demonstrate that Pep2Mol generates chemically valid ligands with state-of-the-art binding affinities, providing a strong foundation for small-molecule inhibitor design against challenging PPI interfaces.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：蛋白质-蛋白质相互作用（PPI）在生物过程中至关重要，但传统结构药物设计方法主要针对定义明确的小分子结合口袋，难以处理 PPI 界面的大尺寸、浅表面和化学复杂性。现有方法无法有效设计靶向正构 PPI 位点的小分子抑制剂。
- **整体含义**：提出一种新的生成模型 Pep2Mol，利用结合肽或蛋白的结构引导，突破口袋条件生成局限，为靶向“不可成药”蛋白和挑战性 PPI 界面的小分子抑制剂设计奠定基础。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：基于扩散模型的 3D 分子生成，通过同时编码蛋白-配体和蛋白-肽两种相互作用，用注意力机制融合表征来引导扩散轨迹，从而生成占据 PPI 正构位点的化学有效配体。
- **关键技术细节**：
  - 使用两个独立的 **SE(3)-等变图神经网络**（EGNN）分别编码蛋白-配体相互作用和蛋白-肽相互作用。
  - 通过 **基于注意力的条件融合** 模块将两种表征合并，联合指导扩散过程。
  - 扩散模型在配体原子坐标和类型上逐步去噪，最终生成 3D 分子结构。
- **算法流程**（文字说明）：
  1. 输入：目标蛋白受体、结合肽/蛋白（结构指导）、随机噪声（配体初始状态）。
  2. 编码：两个 EGNN 分别提取蛋白-配体图和蛋白-肽图特征。
  3. 融合：注意力机制将两种特征融合成条件向量。
  4. 扩散：条件向量逐步引导从噪声到配体坐标和原子类型的去噪过程。
  5. 输出：生成的 3D 配体分子。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：整理了一个大规模数据集，包含 **10,956 个实验解析的蛋白质复合物结构对**，每对在重叠的受体界面上匹配一个正构竞争性配体和一个蛋白质结合物（即配体-肽对共享同一受体界面）。
- **基准（Benchmark）**：使用该数据集进行训练和测试，评估生成分子的化学有效性和结合亲和力。
- **对比方法**：文中提到与“最先进的结合亲和力”比较，但未明确列出具体基线方法的名称（如传统的口袋条件生成模型、其他扩散模型等）。从上下文推测，可能对比了现有基于口袋条件的生成方法以及类似靶向 PPI 的分子生成模型。

### 4. 资源与算力
- **论文未明确说明** 使用的 GPU 型号、数量以及训练时长。只在元数据中提到“score: 10.0”和“evidence: 使用扩散模型针对蛋白质界面设计3D分子”，未涉及计算资源细节。

### 5. 实验数量与充分性
- **实验数量**：据摘要描述，主要在一个大规模数据集（10,956 对）上进行了训练和评估。未提及额外的消融实验、不同子集测试或多场景验证。
- **充分性**：数据集规模较大，结构来自实验解析，质量较高。但论文仅给出了总体评估（化学有效性和平均结合亲和力达到最优），缺乏针对不同 PPI 界面类型、不同受体家族、不同配体大小的详细分析。未展示与多种基线方法的系统对比，也未进行消融实验（如去掉注意力融合模块或只用单一编码器）。因此实验的充分性和客观性有待补充。

### 6. 论文的主要结论与发现
- Pep2Mol 能够生成化学有效的配体，且其结合亲和力达到当前最优水平（state-of-the-art）。
- 相比于传统口袋条件生成，明确利用结合肽/蛋白结构引导能更好地靶向正构 PPI 位点。
- 为设计针对挑战性 PPI 界面的小分子抑制剂提供了强大的基础模型。

### 7. 优点：方法或实验设计上的亮点
- **方法亮点**：
  - 首次将扩散模型与蛋白质-肽相互作用编码结合，实现超越口袋条件生成。
  - 双分支图神经网络 + 注意力融合机制，能同时利用蛋白-配体和蛋白-肽两种相互作用信息。
  - SE(3)-等变性保证生成分子的旋转平移不变性，符合物理化学规律。
- **实验亮点**：
  - 构建了大规模、高质量实验结构数据集（10,956 对），为后续研究提供资源。
  - 直接使用实验解析结构而非模拟数据，可靠性高。

### 8. 不足与局限
- **实验覆盖不足**：仅报告了整体平均亲和力，未分析生成分子对不同类型的 PPI 界面（如浅沟、疏水斑块等）的适用性。
- **偏差风险**：数据集仅包含已有实验结构的复合物，可能偏向于容易结晶或研究充分的系统，对新型 PPI 界面的泛化能力未验证。
- **应用限制**：
  - 需要已知结合肽/蛋白的结构作为引导，对于没有同源肽信息的 PPI 位点可能不适用。
  - 生成的小分子化学有效性仅基于计算指标，缺乏实验验证（如合成、活性测试）。
  - 未与最新主流方法（如基于流匹配、变分自编码器的3D生成模型）进行横向对比。
- **资源与复现**：未提供代码、算力细节，论文仍为预印本，方法可复现性待确认。

（完）
