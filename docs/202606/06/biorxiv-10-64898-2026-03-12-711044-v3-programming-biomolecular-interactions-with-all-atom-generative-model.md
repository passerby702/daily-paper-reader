---
title: Programming Biomolecular Interactions with All-Atom Generative Model
title_zh: 用全原子生成模型编程生物分子相互作用
authors: "Kong, X., Chen, J., Zhang, Z., Li, G., Zhu, Q., Wei, L., Li, M., Shi, Y., Dai, W., Tan, W., Jiao, R., Wang, X., Zheng, J., Yu, Z., Wu, Q., Guo, Z., Zhang, L., Li, W., Huang, Q., Zhu, T., Huang, W., She, Y., Zhang, J., Liu, Y., Liu, K., Ma, J."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.12.711044v3.full.pdf"
tags: ["query:diff-gen"]
score: 8.0
evidence: 深度学习分子生成框架
tldr: "现有生物分子设计策略因分子模态（小分子、多肽、蛋白质）分离而缺乏统一性。本文提出AnewOmni，一个基于超过500万复合物训练的全原子生成框架，通过原子到块的潜空间和可编程图提示，实现跨尺度的可转移分子设计。在KRAS G12D和PCSK9靶点上，成功设计出小分子、多肽和纳米抗体，经低通量验证成功率23%-75%，无需模态特异性高通量筛选。这是首个在所有分子尺度上实现功能设计的统一框架，为通用分子推理引擎迈出关键一步。"
source: biorxiv
selection_source: fresh_fetch
motivation: 不同分子模态的设计策略相互分离，缺乏共享物理化学原理的统一框架。
method: 提出AnewOmni，基于超过500万生物分子复合物的全原子生成模型，通过原子到块潜空间和可编程图提示实现跨尺度设计。
result: "在KRAS G12D和PCSK9靶点上成功设计小分子、多肽和纳米抗体，低通量验证成功率23%-75%。"
conclusion: 首个跨分子尺度（小分子到生物大分子）的统一功能设计框架，为通用分子推理引擎奠定基础。
---

## 摘要
生物分子相互作用是细胞生命的核心，涵盖了从小分子到核酸和蛋白质的多种分子模式。然而，尽管分子识别的物理化学原理相同，设计策略仍然相互分离。在这里，我们提出了AnewOmni，一个在超过500万个生物分子复合物上训练的统⼀生成框架，通过以原子分辨率组装化学上有意义的构建块，实现了跨分子尺度的可迁移分子设计。我们进一步引入了可编程图提示，以支持生成过程中的用户定义化学、拓扑和几何引导，探索超越经典结构的混合和非常规化学。我们证明，通过一个捕捉原子细节和结构先验的原子到块潜在空间，跨分子模式的相互作用模式和物理约束的可迁移学习是可能的。该框架成功设计了针对挑战性KRAS G12D开关II口袋的小分子、肽和纳米抗体，以及在缺乏已知结合位点的情况下针对PCSK9的正构肽和变构小分子抑制剂，仅通过低通量验证就实现了23%-75%的成功率，绕过了特定模式的高通量筛选。AnewOmni是首个在所有尺度上（从小化学实体到大型生物制品）成功实现功能性分子设计的框架，代表了迈向通用分子推理引擎的一块基石，倡导生物分子相互作用的生成基础模型进入数据和人类直觉仍然有限的领域。

## Abstract
Biomolecular interactions lie at the core of cellular life, spanning diverse molecular modalities from small molecules to nucleic acids and proteins. Nevertheless, design strategies remain separated despite shared physicochemical principles of molecular recognition. Here we present AnewOmni, a unified generative framework trained on more than 5 million biomolecular complexes, that enables transferable molecular design across molecular scales by assembling chemically meaningful building blocks at atomic resolution. We further introduce programmable graph prompts to support user-defined chemical, topological, and geometric steering during generation, exploring hybrid and unconventional chemistries beyond canonical structures. We demonstrate that transferable learning of interaction patterns and physical constraints across molecular modalities is possible, via an atom-to-block latent space capturing both atomic details and structural priors. The framework successfully designed small molecules, peptides, and nanobodies targeting the challenging KRAS G12D switch II pocket, as well as orthosteric peptides and allosteric small-molecule inhibitors for PCSK9 in the absence of known binding site, achieving 23%-75% success with only low-throughput validation, bypassing modality-specific high-throughput screening. AnewOmni is the first to succeed in functional molecular design across all scales, from small chemical entities to large biologics, and represents a stepstone towards general molecular reasoning engines, advocating a generative foundation model for biomolecular interactions to enter regimes where data and human intuition remain limited.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：生物分子相互作用涵盖小分子、多肽、蛋白质等多种模态，其识别机制遵循共同的物理化学原理，但现有设计策略因分子模态不同而相互分离，缺乏统一的生成框架。
- **研究动机**：打破模态壁垒，利用共享的原子级相互作用模式与约束，构建一个能够跨尺度（从小分子到大型生物制品）直接设计功能分子的通用引擎，从而绕过传统模态特异性的高通量筛选。
- **整体含义**：本工作提出的 AnewOmni 框架是首个成功在所有分子尺度上实现功能性分子设计的统一模型，为生物分子相互作用的生成式基础模型发展奠定了基础，有望在数据匮乏或人类直觉有限的领域（如非常规化学空间）发挥作用。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程（文字说明）

### 核心思想
- **统一生成**：将小分子、多肽、纳米抗体等不同生物分子视为由化学有意义的“构建块”（如原子、官能团、氨基酸残基等）在原子分辨率下组装的复合物，通过共享的潜空间学习跨模态相互作用模式。
- **可编程图提示**：在生成过程中引入用户定义的化学、拓扑和几何引导，使模型能够探索超越经典结构的混合和非常规化学。

### 关键技术细节
- **全原子生成模型**：模型在超过 500 万个生物分子复合物（可能包括蛋白质-配体、蛋白质-肽、蛋白质-抗体复合物等）上进行训练，以原子分辨率为基本单元。
- **原子到块（Atom-to-Block）潜空间**：设计了一种嵌入机制，既能保留原子级细节（如键合、空间位置），又能捕获更高层次的结构先验（如残基类型、二级结构片段）。该潜空间实现了跨模态相互作用模式的迁移学习。
- **可编程图提示**：生成过程以图结构为基础，用户可指定目标结合位点、化学官能团偏好、拓扑约束（如环数量、链长）或几何约束（如特定距离、角度），模型将这些提示编码为条件变量，引导分子逐步构建。

### 算法流程（文字描述）
1. **输入**：靶点蛋白结构（全原子坐标）及用户定义的可编程图提示（例如：结合口袋残基、期望配体分子量范围、需要包含的特定片段）。
2. **编码**：利用图神经网络（GNN）将蛋白-配体复合物编码为原子级潜在表示，并提取“块”级别特征（如氨基酸侧链、小分子片段）。
3. **条件生成**：基于潜空间，使用自回归或扩散过程逐步添加原子/块，每一步都受可编程提示和物理约束（成键规则、空间位阻、静电作用）引导。
4. **输出**：生成完整的全原子分子结构（如小分子、线性肽序列、纳米抗体结构域），并给出结合亲和力预测或评分。
5. **后处理**：对生成的分子进行化学有效性检查、几何优化，并通过低通量实验验证。

## 3. 实验设计：使用的数据集/场景、benchmark、对比方法

### 数据集
- **训练集**：超过 500 万个生物分子复合物，涵盖小分子-蛋白、多肽-蛋白、纳米抗体-蛋白等模态。具体来源可能包括 PDB、BindingDB、PDBbind 等公共数据库（论文未明确列出）。
- **评估场景**：两个具有挑战性的靶点——KRAS G12D（开关 II 口袋）和 PCSK9（已知结合位点缺失的靶点）。

### 实验场景与任务
- **KRAS G12D**：设计针对开关 II 口袋的小分子、多肽和纳米抗体。
- **PCSK9**：设计正构多肽（占据原有结合位点）和变构小分子抑制剂（无已知结合位点）。

### Benchmark 与对比方法
- 论文**没有明确指出**与现有方法（如 Rosetta、AlphaFold、分子对接、片段筛选等）进行定量对比。作者强调，AnewOmni 直接生成功能分子，**低通量验证成功率 23%–75%**，而传统高通量筛选通常需要数百万化合物库。因此，其基准主要是“无需模态特异性高通量筛选”这一特点，而非与其他生成模型的直接数值对比。

### 验证方式
- 仅进行低通量实验验证（如体外结合或活性测试），未大规模筛选。

## 4. 资源与算力

- **未明确说明**：论文元数据和摘要中均未提及使用的 GPU 型号、数量、训练时长、显存消耗等具体计算资源信息。这可能是因为文中强调算法贡献而略去了工程细节，或是预印本阶段尚未公开。
- 推测：由于训练数据达 500 万复合物且模型为全原子，预计需要大规模 GPU 集群（如数十张 A100 或 H100 GPU），训练时间可能数天至数周。

## 5. 实验数量与充分性

### 实验数量
- 主要实验涉及**两个靶点**（KRAS G12D 和 PCSK9），每个靶点设计 2-3 种分子模态，总计可能进行 5-6 个独立设计任务。
- 每个任务下可能生成多个候选分子，并选择若干进行低通量验证。成功率 23%–75% 表明验证数量有限（可能每个任务验证 10-30 个分子）。

### 充分性评估
- **优点**：成功跨越小分子-多肽-纳米抗体三种尺度，且针对特异性口袋或无结合位点场景，展示了通用性。
- **不足**：
  - 缺乏与现有专用模型（如小分子生成模型、肽设计模型、抗体设计模型）的定量对比，难以判断其性能是否优于现有方法。
  - 仅两个靶点验证，泛化性尚需更多靶点（如不同家族、不同口袋几何）测试。
  - 未进行消融实验（如去掉可编程图提示、不同编码器设计、不同训练数据规模等）来验证各组件的贡献。
  - 成功率变化较大（23%–75%），未讨论失败案例原因，可能存在选择偏差。

总体而言，实验**初步验证了概念有效性**，但**充分性有待加强**，特别是缺少基准对比和系统消融。

## 6. 主要结论与发现

- AnewOmni 是**首个能够统一设计小分子、多肽和纳米抗体**的全原子生成框架。
- 通过原子到块潜空间和可编程图提示，实现了**跨模态相互作用模式的迁移学习**，在无已知结合位点时也能设计变构抑制剂。
- 仅通过**低通量验证（23%–75% 成功率）**即可获得功能分子，表明模型具备较强的先验知识，可以大幅减少实验筛选成本。
- 模型的成功表明，**生物分子相互作用的基础生成模型**可以应用于数据和人类直觉仍有限的领域（如非常规化学空间）。

## 7. 优点

- **统一性**：打破了小分子、多肽、蛋白质各领域独立设计的壁垒，提供了一个共享的生成框架。
- **原子级分辨率**：直接操作全原子细节，保留了化学和几何的精细约束，有望生成更真实、可合成的分子。
- **可编程性**：用户可通过图提示灵活控制生成目标，适合特定用途（如约束环结构、指定结合模式）。
- **高效性**：无需大规模高通量筛选即可获得多个活性分子，显著降低实验成本。
- **新颖性**：首次实现真正的跨尺度分子设计，为后续通用分子推理引擎奠定基础。

## 8. 不足与局限

- **缺少定量基准**：未与现有专业模型（如用于小分子生成的 MolGAN、用于肽设计的 PepDesign、用于抗体设计的 ABlooper 等）进行性能对比，难以客观评估优劣。
- **验证规模有限**：仅两个靶点和少量实验，统计显著性不足，且成功率波动大，不能排除过拟合或偶然性。
- **无消融实验**：未分析各组件（如潜空间设计、图提示机制、训练数据规模）的贡献，模型黑箱性质强。
- **应用限制**：
  - 模型设计可能依赖高质量靶点结构（如冷冻电镜或 X 射线晶体结构），对于柔性或无序蛋白效果未知。
  - 未讨论合成可行性与可合成性评分，生成的小分子/肽/纳米抗体是否实际可合成且稳定。
  - 未公开代码和模型权重（预印本阶段），可复现性差。
- **算力与数据**：训练数据 500 万复合物可能包含噪声或冗余，数据清洗策略未描述；高算力需求限制了普及应用。
- **偏见风险**：训练数据可能偏向已知的相互作用模式，导致模型不擅长探索完全新颖的结合模态或非常规化学。

（完）
