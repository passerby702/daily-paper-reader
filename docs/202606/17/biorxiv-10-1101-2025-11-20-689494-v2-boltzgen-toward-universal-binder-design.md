---
title: "BoltzGen: Toward Universal Binder Design"
title_zh: BoltzGen：迈向通用结合体设计
authors: "Stark, H., Faltings, F., Choi, M., Xie, Y., Hur, E., O'Donnell, T. J., Bushuiev, A., Ucar, T., Passaro, S., Mao, W., Reveiz, M., Bushuiev, R., Portnoi, T., Pluskal, T., Sivic, J., Kreis, K., Vahdat, A., Ray, S., Goldstein, J. T., Savinov, A., Hambalek, J. A., Gupta, A., Taquiri-Diaz, D. A., Zhang, Y., Snyder, S. J., Hatstat, A. K., Arada, A., Kim, N. H., Fan, H., Tackie-Yarboi, E., Boselli, D., Schnaider, L., Liu, C. C., Li, G.-W., Hnisz, D., Sabatini, D. M., DeGrado, W. F., Wohlwend, J., Corso, G., Barzilay, R., Jaakkola, T."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.20.689494v2.full.pdf"
tags: ["query:pocket-lig"]
score: 9.0
evidence: 全原子生成模型，用于设计与生物分子靶点结合的配体，可控制结合位点
tldr: 设计结合特定生物分子的蛋白质和肽类结合剂是生物技术中的关键挑战。BoltzGen提出全原子生成模型，将设计过程与结构预测统一，实现最先进的折叠性能。在8个设计活动、26个靶标上实验验证，成功识别针对新颖靶标的纳米抗体。模型权重、数据和代码已开源。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以高效设计多样化的蛋白质和肽类结合剂，缺乏统一框架。
method: BoltzGen统一设计与结构预测，采用全原子生成模型，支持灵活的设计规范。
result: 在8个设计活动26个靶标上验证，成功生成针对新颖靶标的纳米抗体等。
conclusion: 开源模型、数据和代码，为生物分子设计提供通用工具。
---

## 摘要
我们提出BoltzGen，一种全原子生成模型，用于设计跨所有模态的蛋白质和肽段，以结合多种生物分子靶标。BoltzGen将关于靶标-结合体相互作用的强大结构推理能力构建到其生成设计过程中。这通过统一设计与结构预测实现，从而产生一个同时达到最先进折叠性能的单一模型。BoltzGen的生成过程可以通过一种灵活的设计规范语言进行控制，该语言涵盖共价键、结构约束、结合位点等。我们在八个不同的设计任务中实验验证了这些能力，涉及26个靶标的功能和亲和力读数。在我们的实验中，结合体模态从纳米抗体到二硫键连接的肽段，靶标从无序蛋白质到小分子。特别地，我们识别出对与已知结合结构蛋白质相似度较低的新靶标的纳米抗体结合体。我们发布模型权重、数据以及推理和训练代码，地址为：https://github.com/HannesStark/boltzgen

## Abstract
We introduce BoltzGen, an all-atom generative model for designing proteins and peptides across all modalities to bind a wide range of biomolecular targets. BoltzGen builds strong structural reasoning capabilities about target-binder interactions into its generative design process. This is achieved by unifying design and structure prediction, resulting in a single model that also reaches state-of-the-art folding performance. BoltzGen's generation process can be controlled with a flexible design specification language over covalent bonds, structure constraints, binding sites, and more. We experimentally validate these capabilities in eight diverse design campaigns with functional and affinity readouts across 26 targets. In our experiments, binder modalities span from nanobodies to disulfide-bonded peptides, and targets from disordered proteins to small molecules. In particular, we identify nanobody binders for novel targets with low similarity to proteins with already known bound structures. We release model weights, data, and both inference and training code at: https://github.com/HannesStark/boltzgen

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：设计和优化能够与特定生物分子（蛋白质、肽段、小分子等）特异性结合的蛋白质或肽段结合体，是生物技术（如药物设计、合成生物学）中的关键挑战。现有方法通常针对单一模态或特定靶标，缺乏通用、高效、可控的设计框架。
- **研究动机**：作者希望克服现有方法的限制，构建一个能够覆盖多种结合体模态（纳米抗体、二硫键连接肽等）和多种靶标（无序蛋白、小分子等）的统一设计工具，并同时具备优秀的结构推理能力。
- **整体含义**：BoltzGen 提出了一种**全原子生成模型**，将结合体设计与结构预测统一在一个模型中，不仅实现了最先进的折叠性能，还通过灵活的设计规范语言实现了对生成过程的可控性，从而迈向“通用结合体设计”。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将靶标-结合体相互作用的强大的结构推理能力直接构建到生成设计过程中。通过**统一设计与结构预测**，使模型在设计新序列的同时也能预测其折叠结构，从而提升结合体的可靠性。
- **关键技术细节**：
  - 使用**全原子生成模型**：模型在原子级别操作，能够精细控制原子间相互作用。
  - 引入**灵活的设计规范语言**：允许用户指定共价键、结构约束（如二硫键）、结合位点等设计规则，从而控制生成过程。
  - 模型同时达到**最先进的折叠性能**，即设计的序列经过结构预测验证后与目标结构高度一致。
- **公式或算法流程**（文本未提供具体公式或伪代码，仅描述概念）。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **数据集/场景**：在**8个不同的设计活动（design campaigns）** 中验证，覆盖**26个靶标**。使用功能和亲和力读数（functional and affinity readouts）作为评价标准。
- **结合体模态**：从纳米抗体到二硫键连接的肽段。
- **靶标类型**：从无序蛋白质到小分子。
- **特别案例**：识别出针对**新颖靶标**（与已知结合结构蛋白质相似度低）的纳米抗体结合体。
- **对比方法**：论文摘要中未提及与哪些基线方法进行了对比（如是否与 RFdiffusion、ProteinMPNN 等作比较）。实验部分需要查看全文才能获知。

## 4. 资源与算力（GPU 型号、数量、训练时长等）

- **未明确说明**：提供的摘要和元数据中未提及使用的 GPU 型号、数量、训练时长等算力信息。推断在完整论文的实验部分可能有描述。

## 5. 实验数量与充分性

- **实验数量**：8 个设计活动 × 26 个靶标，实验数量较多且多样性较高（涵盖不同模态和靶标类型）。
- **充分性**：实验覆盖了多种结合体类型和靶标，并包括功能性读数，但论文摘要未提及消融实验、超参数敏感性分析等。因此，实验的整体充分性需要依赖全文细节，从现有摘要看规模合理但缺少内部验证细节。
- **客观性与公平性**：未说明是否与现有方法进行严格对比，也未提及随机种子或重复次数。仅凭摘要无法完全判断公平性。

## 6. 论文的主要结论与发现

- BoltzGen 能够成功设计出针对多种靶标的结合体，包括对**新颖靶标**（与已知结构相似度低）的纳米抗体。
- 统一的**设计与结构预测框架**使得模型在折叠性能上也达到最先进水平。
- 通过控制设计规范语言，可以灵活生成满足特定结构约束（如二硫键、结合位点）的序列。
- 所有模型权重、数据及代码均已开源（https://github.com/HannesStark/boltzgen），为社区提供了可直接使用的通用设计工具。

## 7. 优点

- **全原子生成**：原子级别的精细控制使设计更接近真实物理化学约束。
- **统一设计与预测**：一个模型同时完成序列设计和结构验证，简化了流程并提高了可靠性。
- **灵活性高**：支持多种设计规范（共价键、结构约束、结合位点），可适应不同应用场景。
- **实验验证广泛**：涵盖 8 个设计活动、26 个靶标，结合体模态和靶标类型多样，证明其通用性。
- **开源与可复现**：权重、数据、代码全部公开，促进了领域发展。

## 8. 不足与局限

- **实验覆盖的局限性**：虽然靶标数较多，但论文摘要未提及在更大规模蛋白质组或跨物种测试上的表现，也未说明对非标准氨基酸或修饰是否支持。
- **偏差风险**：仅凭 26 个靶标难以全面评估模型在极其多样化的生物分子上的泛化能力。
- **应用限制**：设计规范语言虽然灵活，但用户需要提供明确的约束，对于自动探索未约束的复杂相互作用可能仍有挑战。
- **对比不明**：未在摘要中明确与哪些基线方法进行量化比较，因此难以判断其性能提升的显著性。
- **算力需求未公开**：可能影响其他团队复现或使用该模型的可行性。

（完）
