---
title: Programming Biomolecular Interactions with All-Atom Generative Model
title_zh: 利用全原子生成模型编程生物分子相互作用
authors: "Kong, X., Chen, J., Zhang, Z., Li, G., Zhu, Q., Wei, L., Li, M., Shi, Y., Dai, W., Tan, W., Jiao, R., Wang, X., Zheng, J., Yu, Z., Wu, Q., Guo, Z., Zhang, L., Li, W., Huang, Q., Zhu, T., Huang, W., She, Y., Zhang, J., Liu, Y., Liu, K., Ma, J."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.12.711044v2.full.pdf"
tags: ["query:diff-gen"]
score: 9.0
evidence: 统一生成框架实现跨尺度可转移分子设计
tldr: 针对小分子、核酸和蛋白质等不同分子尺度设计策略分离的问题，本文提出AnewOmni，一个基于全原子生成模型的统一框架，训练于超过500万个生物分子复合物。该框架通过组装化学构件实现可转移的分子设计，并引入可编程图提示支持用户定义的化学、拓扑和几何导向生成，探索了非经典化学空间。
source: biorxiv
selection_source: fresh_fetch
motivation: 统一生成框架实现跨尺度可转移分子设计。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
生物分子相互作用是细胞生命的核心，涵盖从小分子到核酸和蛋白质等多种分子形态。然而，尽管分子识别共享物理化学原理，设计策略仍然相互分离。在此，我们提出 AnewOmni，一个在超过 500 万个生物分子复合物上训练的统一生成框架，通过原子级分辨率组装具有化学意义的构建模块，实现跨分子尺度的可迁移分子设计。我们进一步引入可编程图提示，支持用户在生成过程中自定义化学、拓扑和几何导向，探索超越经典结构的混合与非常规化学。我们证明，通过一个捕捉原子细节和结构先验的原子到块潜空间，跨分子形态的相互作用模式和物理约束的可迁移学习是可能的。该框架成功设计了靶向具有挑战性的 KRAS G12D switch II 口袋的小分子、肽和纳米抗体，以及在缺乏已知结合位点的情况下针对 PCSK9 的正构肽和变构小分子抑制剂，仅通过低通量验证即实现了 23%-75% 的成功率，绕过了特定模态的高通量筛选。AnewOmni 是首个成功实现从化学小实体到大生物制剂等全尺度功能分子设计的模型，它代表了迈向通用分子推理引擎的垫脚石，倡导建立生物分子相互作用的生成基础模型，以进入数据和人类直觉仍然有限的领域。

## Abstract
Biomolecular interactions lie at the core of cellular life, spanning diverse molecular modalities from small molecules to nucleic acids and proteins. Nevertheless, design strategies remain separated despite shared physicochemical principles of molecular recognition. Here we present AnewOmni, a unified generative framework trained on more than 5 million biomolecular complexes, that enables transferable molecular design across molecular scales by assembling chemically meaningful building blocks at atomic resolution. We further introduce programmable graph prompts to support user-defined chemical, topological, and geometric steering during generation, exploring hybrid and unconventional chemistries beyond canonical structures. We demonstrate that transferable learning of interaction patterns and physical constraints across molecular modalities is possible, via an atom-to-block latent space capturing both atomic details and structural priors. The framework successfully designed small molecules, peptides, and nanobodies targeting the challenging KRAS G12D switch II pocket, as well as orthosteric peptides and allosteric small-molecule inhibitors for PCSK9 in the absence of known binding site, achieving 23%-75% success with only low-throughput validation, bypassing modality-specific high-throughput screening. AnewOmni is the first to succeed in functional molecular design across all scales, from small chemical entities to large biologics, and represents a stepstone towards general molecular reasoning engines, advocating a generative foundation model for biomolecular interactions to enter regimes where data and human intuition remain limited.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **核心问题**：生物分子相互作用（小分子、核酸、蛋白质等）设计策略目前是相互割裂的，虽然分子识别遵循共享的物理化学原理，但针对不同分子尺度的设计方法各自独立，缺乏统一的建模框架。
- **整体含义**：本文提出 AnewOmni，一个在超过 500 万个生物分子复合物上训练的全原子生成模型，旨在通过组装化学构建块实现跨分子尺度的可转移设计。该工作首次成功实现了从小分子到大生物制剂的全尺度功能分子设计，被视为构建通用分子推理引擎的重要基石。

## 2. 方法论

- **核心思想**：将分子设计统一为“化学构建块的原子级组装”，通过捕捉原子细节和结构先验的潜空间，使不同分子模态的相互作用模式和物理约束可以相互迁移。
- **关键技术细节**：
  - **统一生成框架**：模型在大规模生物分子复合物数据集上训练，将分子表示为原子到块的潜空间（atom-to-block latent space），既保留原子精度，又融入化学意义的结构先验。
  - **可编程图提示**（programmable graph prompts）：允许用户在生成过程中自定义化学组成、拓扑连接与空间几何导向，从而探索非经典化学空间（如混合化学实体、非常规结构）。
  - **训练与生成流程**：通过组装化学构建块（如片段、骨架）生成目标分子，模型需要同时学习分子的构象、化学价键以及结合界面的几何互补性。

## 3. 实验设计

- **测试靶点**：
  - KRAS G12D switch II 口袋：挑战性癌蛋白靶点，已知难成药。
  - PCSK9：用于验证无已知结合位点时的从头设计能力（正构肽、变构小分子抑制剂）。
- **设计分子类型**：小分子、肽、纳米抗体，覆盖从化学小实体到大生物制剂的多个尺度。
- **评价指标**：低通量实验验证成功率（23%–75%），直接衡量生成分子的实际结合活性。
- **对比方法**：文中未提具体的对比模型或经典方法，但强调通过低通量验证绕过了传统模态特异性高通量筛选流程，暗示与新框架相比，传统手段在跨尺度设计上效率低下或不可行。

## 4. 资源与算力

- 摘要及已提供信息中 **未明确说明** 所使用的 GPU 型号、数量、训练时长等具体算力资源。完整论文可能包含补充材料中的相关说明。

## 5. 实验数量与充分性

- **实验组数**：针对两个具有明确生物学意义的靶点（KRAS, PCSK9），分别设计并测试了三种分子形态（小分子、肽、纳米抗体），至少构成了 6 组以上的设计-验证任务。
- **充分性与客观性**：
  - 实验覆盖了不同难度（有/无已知结合位点）和不同模态，具有一定代表性。
  - 采用低通量实验直接验证结合活性，避免了计算指标与实验脱节的风险，设计成功率以实验数据呈现，较为客观。
  - 但摘要未提及消融实验、基线方法对比或统计显著性检验，因此在方法间的公平对比和关键模块的贡献验证方面尚有不足。

## 6. 主要结论与发现

- **可转移学习成立**：跨分子模态的相互作用模式和物理约束可以通过统一的原子到块潜空间实现迁移。
- **全尺度设计能力**：AnewOmni 成功生成了针对 KRAS G12D 的小分子、肽、纳米抗体，以及针对 PCSK9 的正构肽和变构小分子抑制剂，证明了从化学小分子到大生物制剂的全覆盖。
- **高效验证**：仅通过低通量实验即获得 23%–75% 的成功率，表明生成质量较高，可大幅减少对传统高通量筛选的依赖。
- **前景展望**：该工作为通用分子推理引擎奠定了基础，倡导建立生物分子相互作用的生成基础模型，以探索数据与直觉匮乏的领域。

## 7. 优点

- **统一的跨尺度框架**：打破传统按分子类型分而治之的设计范式，首次实现覆盖小分子到生物大分子的统一生成模型。
- **可编程控制**：引入图提示机制，使用者可灵活指定化学、拓扑和几何约束，拓展到非常规化学空间，增强了实用性与可探索性。
- **实验验证扎实**：生成结果直接由低通量实验证实，成功率令人信服，展现了真实的药物设计潜力。
- **弱先验依赖**：能够在缺乏已知结合位点信息的情况下，针对 PCSK9 设计出正构和变构抑制剂，展示了模型的泛化与探索能力。

## 8. 不足与局限

- **算力与训练细节缺失**：摘要及文本未提供模型训练所需的具体计算资源，不利于复现和成本评估。
- **对比方法缺失**：未提供与现有分子生成模型、对接方法或特定模态设计工具的量化对比，难以定位该方法的相对优势幅度。
- **实验规模有限**：仅验证了两个靶点，且未报告消融实验、鲁棒性测试或失败案例分析，对模型内部机制的解读不够深入。
- **数据偏差风险**：基于 PDB 等大规模复合物训练，可能受限于可结晶结构的偏差，对内在无序区或膜蛋白等场景的适用性未知。
- **验证方式单一**：低通量验证虽然直接，但缺乏结合亲和力、选择性、药代动力学等后续指标，距离实际药物开发仍有距离。

（完）
