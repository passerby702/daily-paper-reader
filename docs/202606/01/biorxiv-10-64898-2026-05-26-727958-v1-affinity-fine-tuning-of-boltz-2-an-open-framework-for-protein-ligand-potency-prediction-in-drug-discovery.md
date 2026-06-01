---
title: "Affinity Fine-Tuning of Boltz-2: An Open Framework for Protein-Ligand Potency Prediction in Drug Discovery"
title_zh: Boltz-2的亲和力微调：药物发现中蛋白质-配体效能预测的开放框架
authors: "Amini, S., Sciabola, S., Wang, Y."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727958v1.full.pdf"
tags: ["query:pocket-lig"]
score: 9.0
evidence: 开源框架，微调蛋白质-配体共折叠生成模型以预测结合亲和力，辅助配体设计
tldr: Boltz-2模型能准确预测蛋白-配体结合亲和力，但缺少公开微调方案，限制了先导化合物优化中的持续应用。为此，提出一个开放框架，仅调整亲和力预测组件，利用项目特定实验数据微调Boltz-2。在内部多靶标回顾与单靶标（多达1700个配体）研究中，微调后相关性显著提升，部分场景性能可比自由能微扰方法。该框架的发布使社区能针对自身靶点和数据定制模型，加速药物发现。
source: biorxiv
selection_source: fresh_fetch
motivation: Boltz-2虽性能优异，但无公开训练流程，难以融入需利用新实验数据迭代的先导优化项目。
method: 提出开放框架，固定Boltz-2主体，仅微调亲和力预测组件，用项目特异数据适配模型。
result: 在两项内部研究中，微调Boltz-2提升相关性，单靶标1700配体下性能接近自由能微扰方法。
conclusion: 开放框架让Boltz-2可定制化，成为先导优化中实用的亲和力预测工具，社区可依靶点适配。
---

## 摘要
Boltz-2通过利用共折叠的蛋白质-配体结构实现了准确的结合亲和力预测，但公开训练方案的缺失限制了其在活跃药物发现项目中的应用——在这些项目中，先导化合物优化阶段会不断产生新的实验测量值和同类配体系列。我们提出了一个用于Boltz-2亲和力微调的开放框架，表明仅用项目特定的实验数据调整亲和力预测组件，就能使模型在先导优化中显著提升实用性。我们在两项内部研究中评估了该方法：一项针对物理方法和机器学习基线的多靶点回顾性基准测试，另一项涉及多达1700个配体的大规模单靶点研究。在这两种情境下，微调后的Boltz-2相比现成模型提高了相关性，并在某些情况下达到了与自由能微扰（FEP）方法相当的性能。通过发布此框架，我们旨在使社区能够将Boltz-2适应于各自药物发现活动中的特定靶点和数据。代码可在以下地址获取：https://github.com/molecularinformatics/Boltz2_affinity

## Abstract
Boltz-2 has enabled accurate binding affinity prediction by leveraging co-folded protein-ligand structures, but the absence of a public training recipe has limited its use in active drug discovery projects, where new experimental measurements and congeneric ligand series continually arrive during lead optimization. We present an open framework for affinity fine-tuning of Boltz-2, showing that adapting only the affinity prediction components with project-specific experimental data can make the model substantially more useful for lead optimization. We evaluate the approach in two internal studies: a multi-target retrospective benchmark against physics-based and machine learning baselines, and a large single-target study with up to 1,700 ligands. In both settings, fine-tuned Boltz-2 improves correlation over the off-the-shelf model, and in some cases reaches performance competitive with free energy perturbation (FEP) methods. By releasing this framework, we aim to enable the community to adapt Boltz-2 to the specific targets and data of their own drug discovery campaigns. The code is available at: https://github.com/molecularinformatics/Boltz2_affinity

---

## 论文详细总结（自动生成）

由于无法直接访问论文全文，以下总结主要基于提供的摘要及元数据信息展开。若缺失部分细节（如方法实现、实验超参、算力等），将如实说明。

---

## 1. 论文核心问题与研究动机

- **背景**：Boltz-2 是一种利用“蛋白质‑配体共折叠结构”预测结合亲和力的生成模型，在公开基准上已展示出准确预测能力。
- **核心痛点**：该模型的训练流程和权重并未公开，研究人员难以针对自己的项目数据进行微调，导致其在先导化合物优化（lead optimization）等实际药物发现流程中的应用受阻。先导优化阶段会持续产生新实验测量及同类配体系列（congeneric series），需要模型能够“随数据增长而进化”。
- **整体目标**：提出一个开放、可复用的亲和力微调框架，只使用项目特定的实验数据对 Boltz-2 的亲和力预测组件进行适配，从而显著提升其在真实药物项目中的实用性，并将该框架开源，让社区可以针对自身靶点和数据定制模型。

---

## 2. 方法论

- **核心思想**：固定 Boltz-2 的主体部分（如结构生成模块），仅对“亲和力预测组件”进行参数更新（微调）。这种方式既保留了原模型对蛋白质‑配体相互作用的通用理解，又能快速适配特定靶点/化学系列的数据分布。
- **关键流程（推断）**：
  1. 获取项目特异性实验结合数据（如 IC₅₀、Kᵢ、ΔG 等）。
  2. 利用 Boltz-2 的预训练权重初始化模型，冻结绝大部分参数，仅开放与亲和力读出（affinity readout）相关的层。
  3. 在项目数据上进行监督微调（回归任务），优化预测亲和力与实验值之间的损失函数。
  4. 微调后的模型可直接用于同类配体的亲和力排序或筛选。
- **公式/算法细节**：摘要中未给出具体损失函数形式或架构细节，但可推测采用均方误差（MSE）或相关排序损失进行回归微调。完整技术细节需查阅论文全文或代码仓库。

---

## 3. 实验设计

- **数据集/场景**：
  - **多靶点回顾性研究**：跨多个靶标的回顾性基准测试，对比基于物理的方法和机器学习基线。
  - **单靶点大规模研究**：针对单个靶点，包含多达 1700 个配体的大规模内部数据集。
- **对比方法**：
  - 未微调的 Boltz-2（off‑the‑shelf，即原始模型）。
  - 基于物理的方法（如自由能微扰 FEP）。
  - 其他机器学习基线（具体模型名称未在摘要中列出，需阅原文）。
- **评估指标**：主要关注“相关性（correlation）”的提升，可能为皮尔逊/斯皮尔曼相关系数或预测排序准确率。

---

## 4. 资源与算力

- 摘要和提供的元数据中**未提及**使用的 GPU 型号、数量、微调耗时等计算资源信息。微调通常比从头训练轻量，但具体资源需求需参考论文正文或代码库说明。

---

## 5. 实验数量与充分性

- **实验组数**：
  - 至少包含两大类内部研究：多靶点回顾基准 + 单靶点大规模（1700 配体）研究。
  - 两组场景下均评估了原始模型与微调后模型的性能提升，并与其他方法比较。
- **充分性与客观性**：
  - 从描述看，涵盖了多靶点泛化和单靶点深度两个维度，设计较为合理。
  - 由于摘要并非全文，无法判断是否包含消融实验（如冻结策略对比、不同数据量下的表现）或统计显著性检验。若能公开所有数据集和评估协议，则有助于检验公平性。

---

## 6. 主要结论与发现

- 仅用项目特定实验数据微调亲和力预测模块，就能显著提升 Boltz-2 与实验值的相关性，增强其先导优化实用性。
- 多靶点回顾基准中，微调后的模型优于原始版本；单靶点大规模（多达 1700 配体）研究中，其性能可在某些情况下与计算代价高昂的自由能微扰方法（FEP）相媲美。
- 通过发布开放框架，研究人员可将 Boltz-2 适配至自有靶标和内部数据，从而加速药物发现。

---

## 7. 优点

- **实用性强**：解决了高端模型“黑箱”不可微调的问题，将前沿 ML 预测器融入实际工作流。
- **开源与可定制**：提供完整框架和代码，降低社区使用门槛，促进迭代优化。
- **成本‑性能平衡**：仅微调部分组件，相比 FEP 方法可能计算更轻量，同时保持有竞争力的亲和力排序能力。
- **实验贴近真实场景**：采用项目内部数据，考虑单靶点先导优化中的同类配体系列，验证了微调对分子系列变化的敏感性。

---

## 8. 不足与局限

- **信息缺失**：摘要未披露微调所需的最小数据量、缩放定律、数据质量敏感性等问题，可能在某些靶点数据极度稀缺时表现受限。
- **泛化边界不明**：框架虽能适配新靶点，但微调后的模型可能对靶点构象变化或全新化学型（scaffold）的预测能力下降，这需要用更多样的数据集验证。
- **对比公平性**：与 FEP 比较时，未提及是否使用了相同的计算预算、准备流程或人类干预程度，需进一步细节才能确认结论稳健性。
- **仅侧重亲和力**：药物发现中还需考虑选择性、ADMET 等多维性质，框架目前聚焦结合亲和力，可能需扩展至多属性预测。
- **代码库依赖**：实际可用性取决于代码库的文档、维护与授权，摘要中未讨论这些生态问题。

---

（完）
