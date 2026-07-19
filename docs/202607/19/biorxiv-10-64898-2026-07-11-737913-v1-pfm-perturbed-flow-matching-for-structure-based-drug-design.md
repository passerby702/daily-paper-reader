---
title: "PFM: perturbed flow matching for structure-based drug design"
title_zh: PFM：基于结构药物设计的扰动流匹配
authors: "Yu, Y., Xu, G., Xie, Z., Yang, Y., Jiang, Y., Zhou, X., Li, K."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.11.737913v1.full.pdf"
tags: ["query:pocket-lig"]
score: 9.0
evidence: 基于扰动流匹配的3D分子生成方法，条件于蛋白口袋，用于结构药物设计
tldr: 现有基于扩散的分子生成模型采样步骤多，计算成本高。本文提出扰动流匹配（PFM）方法，利用流匹配框架大幅减少采样步数，并通过设计扰动条件概率路径整合口袋结合位点与原子类型-坐标耦合信息。在CrossDocked2020数据集上，PFM生成分子的结合亲和力平均达-7.12，达到最优水平，同时有效分子生成速度提升21.3倍，具备进一步优化潜力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1417, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1142, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1400, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1406, \"height\": 1413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1411, \"height\": 887, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1277, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1164, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 768, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1160, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1423, \"height\": 261, \"label\": \"Table\"}]"
motivation: 扩散模型采样步骤多导致药物发现缓慢，PFM通过流匹配减少步数以加速生成。
method: PFM设计扰动条件概率路径，融合口袋结合位点信息和原子类型-坐标耦合信息，在流匹配框架下生成分子。
result: 在CrossDocked2020上PFM结合亲和力平均-7.12，生成速度提升21.3倍，结构质量有竞争力。
conclusion: PFM显著加速分子生成并保持高亲和力，为结构药物设计提供高效新方案。
---

## 摘要
通过生成模型生成与特定蛋白质靶点结合的3D分子，在基于结构的药物设计中显示出巨大潜力。近年来，基于扩散的方法取得了有希望的结果，但由于其依赖高采样步数，增加了时间和计算成本，可能减缓药物发现过程。在这项工作中，我们提出了一种名为扰动流匹配（PFM）的新方法，通过利用流匹配框架显著减少了采样步数。PFM引入了一种独特的扰动条件概率路径设计，融合了口袋结合位点信息和原子类型-坐标耦合信息，以增强分子生成性能。在CrossDocked2020数据集上的实验表明，PFM生成了具有竞争性3D结构和最先进（SOTA）结合亲和力的分子，平均值为-7.12。此外，PFM将有效分子的生成速度提高了21.3倍，同时显示出进一步改进的潜力。代码可在https://github.com/kurisu92725/PFM获取。

## Abstract
Generating 3D molecules that bind to specific protein targets via generative models has shown great promise in structure-based drug design. Recently, diffusion-based methods have achieved promising results, but their reliance on high sampling steps poses risks of slowing the drug discovery process due to increased time and computational costs. In this work, we propose a novel method named Perturbed Flow Matching (PFM), which significantly reduces sampling steps by leveraging a Flow Matching framework. PFM introduces a unique perturbed conditional probability path design that incorporates pocket binding site information and atom type-coordinate coupled information to enhance molecular generation performance. Experiments on CrossDocked2020 dataset demonstrate that PFM generates molecules with competitive 3D structures and state-of-the-art (SOTA) binding affinities towards the protein targets, achieving an Avg. of -7.12. Additionally, PFM accelerates the generation of valid molecules by a factor of 21.3, while demonstrating potential for further improvement. The code is available at https://github.com/kurisu92725/PFM.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：在基于结构的药物设计（SBDD）中，现有基于扩散的生成模型虽然能生成高质量的3D分子，但依赖大量采样步骤，导致时间和计算成本高昂，可能减缓药物发现进程。
- **整体含义**：本文旨在通过引入流匹配（Flow Matching）框架，显著减少采样步数，同时保持或提升分子生成质量和结合亲和力，从而加速SBDD流程。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：提出扰动流匹配（Perturbed Flow Matching, PFM），在流匹配框架下设计一种新型的“扰动条件概率路径”，该路径整合了口袋结合位点信息以及原子类型-坐标耦合信息，从而提升分子生成性能。
- **关键技术细节**：
  - **条件概率路径设计**：在基本高斯路径上添加与时间t(1-t)成比例的扰动项，扰动项由预训练的预测器网络生成，分别对应坐标和原子类型。
  - **连续化处理**：将离散原子类型通过soft one-hot编码映射到logit空间，并在此空间定义流。
  - **网络架构**：提出全原子多阶段等变网络（Full-atom Multi-stage Equivariant Network），分两阶段（分子内、分子-蛋白）更新特征和坐标，保证SE(3)等变性。
  - **统一损失函数**：通过重参数化将流匹配损失和条件分数匹配损失统一为简单的MSE形式，并加入键长损失和冲突损失作为辅助项。
  - **扩展至随机过程**：在不重新训练的情况下，可将确定性流扩展为随机微分方程（PFM-SDE）采样。
- **算法流程**：训练时从预处理数据中采样分子和蛋白，计算扰动，采样中间状态，网络预测干净样本，计算统一损失优化。推理时通过欧拉步或Euler-Maruyama积分逐步生成。

## 3. 实验设计：数据集、Benchmark、对比方法
- **数据集**：CrossDocked2020，预处理后保留99,900个高质量复合物用于训练，100个新颖蛋白用于测试（与之前工作一致）。
- **Benchmark**：评估指标分为两类：
  - 靶点结合结果：Vina Score（平均/中位）、Vina Min、Vina Dock、High Affinity、冲突比率（CCA/CM）、RMSD%<2Å。
  - 分子构象和性质：JSD（键长分布）、应变能（SE）、QED、SA、多样性、相似性、有效性、独特性。
- **对比方法**：
  - 非扩散模型：LiGAN、GraphBP、AR、Pocket2Mol。
  - 扩散模型：TargetDiff、DecompDiff、IPDiff。

## 4. 资源与算力
- **训练硬件**：单张NVIDIA GeForce RTX 4090 GPU。
- **训练时长**：
  - 预测器网络（ˆX predictor和ˆS predictor）各约4.22小时。
  - PFM主模型约6.31小时（62.5k步收敛）。
- **推理时间**：生成10,000个有效分子，PFM需3.13小时，相比IPDiff（66.68小时）加速21.3倍。
- 论文明确说明了以上算力和时间。

## 5. 实验数量与充分性
- **实验数量**：
  - 表1-3：主要结果对比（靶点结合、分子构象性质、键长JSD、SE等）。
  - 表4：扰动路径消融（BFM、BFM-Ref、LPFM、RPFM、PFM等）。
  - 表5：损失函数消融（LSF、LB、LC组合）。
  - 表6：训练和推理时间对比。
  - 表7：损失函数和条件分布改进效果。
  - 表8：扰动系数ξ消融。
  - 图3-6：可视化分析和采样步数影响。
- **充分性与公平性**：
  - 消融实验覆盖了核心组件（路径、损失、系数、采样步数），逻辑清晰。
  - 对比方法采用原论文设置，评估口径统一（多数指标沿用前人工作）。
  - 但作者指出缺乏大规模多模态生成任务验证，且未在更多数据集上测试（仅CrossDocked2020）。

## 6. 论文的主要结论与发现
- PFM生成的分子在结合亲和力方面达到SOTA（平均Vina Score -7.12），比IPDiff提升10.9%。
- 生成速度提升21.3倍，且保持高有效性（95.12%）和独特性（100%）。
- 扰动条件概率路径显著优于基本流匹配路径（BFM），且不同扰动策略（如LPFM、RPFM）均有效。
- 统一损失函数（LSF + LB + LC）整体最优，其中LB（键长损失）贡献最大。
- PFM-SDE（随机版本）在键长分布JSD上表现更优（5/8种键类型SOTA），但亲和力略低于PFM。
- 在几何冲突、应变能等指标上，PFM也优于多数扩散模型。

## 7. 优点：方法或实验设计上的亮点
- **方法创新**：
  - 首次将流匹配框架用于SBDD任务。
  - 设计扰动条件概率路径，巧妙整合口袋信息和原子类型-坐标耦合。
  - 统一损失函数使得训练只需优化确定性流，采样时可自由切换至SDE，无需重训。
  - 全原子多阶段等变网络灵活处理分子内和分子间交互。
- **实验设计**：
  - 全面的评估指标（亲和力、几何、构象、性质），覆盖分子生成质量各方面。
  - 消融实验设计系统，验证每个组件贡献。
  - 速度对比突出实际优势（加速21.3倍）。
- **实用价值**：大幅降低时间成本，有利于高通量虚拟筛选。

## 8. 不足与局限
- **实验覆盖不足**：仅在CrossDocked2020一个数据集上验证，缺乏跨数据集的泛化性测试（如PDBbind等）。
- **扰动路径依赖**：扰动由预训练预测器生成，其有效性未在大规模多模态生成任务中验证。
- **分子性质权衡**：PFM的SA得分（0.51）相对较低，虽在可接受范围，但影响合成可行性；作者认为主要是扰动路径和LB损失导致的QED-SA权衡。
- **结构约束有限**：仅通过键长损失和冲突损失引入局部结构线索，未考虑键角、二面角等更复杂的几何约束。
- **原子类型处理**：将离散类型连续化到logit空间可能引入信息损失，且未严格处理自由度减少。
- **偏差风险**：亲和力评估依赖Vina评分，可能无法完全反映真实生物学活性。

（完）
