---
title: "PFM: perturbed flow matching for structure-based drug design"
title_zh: PFM：用于基于结构的药物设计的扰动流匹配
authors: "Yu, Y., Xu, G., Xie, Z., Yang, Y., Jiang, Y., Zhou, X., Li, K."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.11.737913v1.full.pdf"
tags: ["query:pocket-lig"]
score: 9.0
evidence: 基于流匹配的蛋白质口袋配体设计方法
tldr: 基于扩散的分子生成方法虽然有效，但需要大量采样步骤，计算成本高，影响药物发现速度。本文提出扰动流匹配（PFM），采用Flow Matching框架，通过设计扰动条件概率路径整合口袋结合位点与原子类型坐标信息，显著减少采样步数。在CrossDocked2020数据集上，PFM生成分子具有竞争力，平均结合亲和力达到-7.12，且有效分子生成速度提升21.3倍。PFM在加速药物设计的同时保持高性能，具有进一步优化的潜力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1417, \"height\": 562}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1142, \"height\": 578}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1400, \"height\": 329}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1406, \"height\": 1413}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 467}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1411, \"height\": 887}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 394}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 470}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 357}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1277, \"height\": 300}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1164, \"height\": 457}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 768, \"height\": 354}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1160, \"height\": 301}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-11-737913-v1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1423, \"height\": 261}]"
motivation: 现有扩散模型采样步骤多、计算成本高，限制了药物发现效率，亟需更高效的分子生成方法。
method: 提出扰动流匹配（PFM），设计扰动条件概率路径，融合口袋位点与原子类型坐标信息，加速分子生成。
result: 在CrossDocked2020上，PFM平均结合亲和力-7.12，生成速度提升21.3倍，3D结构具有竞争力。
conclusion: PFM显著加速基于结构的药物设计中的分子生成，同时保持高结合亲和力，为快速药物发现提供新途径。
---

## 摘要
通过生成模型生成能与特定蛋白质靶点结合的3D分子，在基于结构的药物设计中展现出巨大潜力。最近，基于扩散的方法取得了有希望的结果，但它们对高采样步数的依赖可能因增加时间和计算成本而减缓药物发现进程。在这项工作中，我们提出了一种名为扰动流匹配（PFM）的新方法，通过利用流匹配框架显著减少了采样步数。PFM引入了一种独特的扰动条件概率路径设计，该设计整合了口袋结合位点信息和原子类型-坐标耦合信息，以增强分子生成性能。在CrossDocked2020数据集上的实验表明，PFM生成的分子具有具有竞争力的3D结构和针对蛋白质靶点的最新（SOTA）结合亲和力，平均值为-7.12。此外，PFM将有效分子的生成速度提升了21.3倍，并展现出进一步改进的潜力。代码可在https://github.com/kurisu92725/PFM获取。

## Abstract
Generating 3D molecules that bind to specific protein targets via generative models has shown great promise in structure-based drug design. Recently, diffusion-based methods have achieved promising results, but their reliance on high sampling steps poses risks of slowing the drug discovery process due to increased time and computational costs. In this work, we propose a novel method named Perturbed Flow Matching (PFM), which significantly reduces sampling steps by leveraging a Flow Matching framework. PFM introduces a unique perturbed conditional probability path design that incorporates pocket binding site information and atom type-coordinate coupled information to enhance molecular generation performance. Experiments on CrossDocked2020 dataset demonstrate that PFM generates molecules with competitive 3D structures and state-of-the-art (SOTA) binding affinities towards the protein targets, achieving an Avg. of -7.12. Additionally, PFM accelerates the generation of valid molecules by a factor of 21.3, while demonstrating potential for further improvement. The code is available at https://github.com/kurisu92725/PFM.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：基于结构的药物设计（SBDD）旨在生成与靶点蛋白结合位点高度亲和的三维配体分子。现有基于扩散的生成模型（如 TargetDiff、DecompDiff、IPDiff）虽然表现优异，但依赖大量采样步数（通常数百步），导致时间和计算成本高昂，限制了药物发现的效率。
- **研究动机**：探索一种能够显著减少采样步数、同时保持或提升分子生成质量的框架。流匹配（Flow Matching）作为一种基于确定性常微分方程（ODE）的生成模型，理论上可通过较少步数实现快速采样，但直接应用到 SBDD 中效果不佳。
- **整体含义**：本文提出**扰动流匹配（PFM）**，通过设计新颖的**扰动条件概率路径**，将蛋白口袋结合位点信息与原子类型‑坐标耦合信息融入基础路径，从而在保持流匹配高效采样的同时提升分子生成性能。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：在 Flow Matching 框架下，不直接使用简单的线性插值路径，而是构造**扰动条件概率路径**，使不同条件轨迹更具区分度，同时近似边缘分布以保持理论正确性。
- **关键技术细节**：
  1. **扰动条件概率路径设计**：
     - 对原子坐标和类型分别定义扰动的条件分布：
       \[
       p_t(M|M_0,M_1,P) = \mathcal{N}\big(\,[X,S]\,\big|\,[tX_1+(1-t)X_0+\xi t(1-t)\hat{X},\; tS_1+(1-t)S_0+\xi t(1-t)\hat{S}],\ \sigma^2 I\big)
       \]
     - 其中 \(\hat{X}=f(S_1,X_0,P)\) 和 \(\hat{S}=g(X_1,S_0,P)\) 由预训练的扰动预测网络生成，\(\xi\) 控制扰动幅度。
  2. **统一训练损失函数**：
     - 通过重参数化将流匹配与得分匹配损失统一为：
       \[
       L_{SF} = \mathbb{E}_{t,(M_0,M_1),p_t(M|...)}\big\|\big[\tilde{X}-X_1,\ \tilde{S}-S_1\big]\big\|_F^2
       \]
     - 并加入两项辅助损失：
       - 键长损失 \(L_B\)：监督生成的键长与真实键长的差异。
       - 冲突损失 \(L_C\)：惩罚配体原子侵入蛋白内部区域（用高斯表面描述蛋白边界）。
     - 总损失：
       \[
       L_{PFM} = L_{SF} + \mu L_B + \nu L_C
       \]
  3. **全原子多阶段等变网络**：
     - 动态构建三个 k‑近邻图：蛋白质内部、配体内部、蛋白质‑配体交互。
     - 每个网络层分两阶段更新：第一阶段在配体图内更新原子特征和坐标；第二阶段在交互图内考虑蛋白影响更新坐标。网络输出直接预测 \(\tilde{X}\) 和 \(\tilde{S}\)。
  4. **采样过程**：
     - 确定版（PFM）：使用 Euler 积分求解概率流 ODE。
     - 随机版（PFM‑SDE）：在 ODE 基础上添加扩散项，无需重新训练。

### 3. 实验设计

- **数据集**：CrossDocked2020，经过标准预处理（保留 RMSD<1Å 的高质量对接姿态、蛋白质序列相似性 30%），最终得到约 99,900 个训练复合物和 100 个测试蛋白质。
- **基准对比方法**：
  - 非扩散方法：LiGAN、AR、GraphBP、Pocket2Mol
  - 扩散方法：TargetDiff、DecompDiff、IPDiff
- **评价指标**：
  - **靶点结合性能**：Vina Score、Vina Min、Vina Dock 的均值和中位数，高亲和力比例，冲突比例，RMSD（%<2Å）。
  - **分子构象与性质**：键长分布的 Jensen‑Shannon 散度（JSD）、应变能（SE）、QED、SA、多样性、相似性、有效性、唯一性。

### 4. 资源与算力

- **训练资源**：单块 NVIDIA GeForce RTX 4090 GPU。
- **训练时长**：
  - 扰动预测网络 \(\hat{X}\) 与 \(\hat{S}\) 各约 4.2 小时。
  - PFM 主模型约 6.31 小时，在 62.5k 步左右收敛。
- **推理时间**：生成 10,000 个有效分子约需 3.13 小时（比 IPDiff 快 21.3 倍）。

### 5. 实验数量与充分性

- **实验组数**：包含完整主实验（表 1‑3）、消融实验（表 4‑5、表 8）、采样步数分析（图 4）、路径对比（表 4 的 BFM、BFM‑Ref、LPFM、RPFM）、损失函数项消融（表 5）、耦合方式与损失形式对比（表 7）、额外可视化（图 3、5、6）。
- **充分性与公平性**：
  - 消融实验系统验证了扰动路径、辅助损失、扰动系数等各组件的必要性。
  - 与多个现有方法的比较涵盖了主流非扩散和扩散模型，且指标全面。
  - 不足之处：仅使用一个数据集（CrossDocked2020），未在其他数据集（如 PDBbind）上验证泛化性。部分对比（如与 IPDiff 在先验知识上的差异）在讨论中提及但未做进一步控制。总体而言实验设计较严谨，结论可靠。

### 6. 论文的主要结论与发现

1. **结合亲和力 SOTA**：PFM 在 Vina Score 均值达 -7.12，显著优于除 IPDiff 外的所有方法，且与 IPDiff 相比在 Vina Score 上提升 10.9%。
2. **生成速度大幅提升**：生成有效分子速度比 IPDiff 快 21.3 倍，且可进一步减少采样步数而不明显降低质量。
3. **分子构象与性质具竞争力**：PFM‑SDE 在 5/8 的键长 JSD 上达到最优；PFM 在应变能、QED 等指标上表现良好，但 SA 分数较低（因扰动路径带来的 QED‑SA 权衡）。
4. **扰动路径的有效性**：消融表明，扰动路径比简单线性路径（BFM）和参考扰动路径（BFM‑Ref）均产生更优的分子，且不同扰动策略（LPFM、RPFM、PFM）均有效。
5. **辅助损失的作用**：键长损失 \(L_B\) 贡献最大，冲突损失 \(L_C\) 需与 \(L_B\) 联合使用才能带来收益。

### 7. 优点

- **创新性**：首次将流匹配框架引入 SBDD，并设计了专门的扰动条件概率路径，巧妙融合口袋信息与原子耦合信息。
- **高效性**：采样速度远超扩散模型，同时保持高性能，满足药物筛选对速度的要求。
- **灵活性**：统一确定性/随机采样的损失函数，采样方式可选 SDE/ODE 无需重新训练。
- **网络设计**：全原子多阶段等变网络动态更新，充分利用蛋白‑配体交互，且支持端到端训练。
- **实验充分**：大量消融实验验证了每个设计选择，结论有说服力。

### 8. 不足与局限

- **数据集单一**：仅使用 CrossDocked2020，未在 PDBbind、Binding MOAD 等其他数据集上验证泛化性，可能存在过拟合风险。
- **局部结构约束薄弱**：仅用键长损失捕捉局部结构，未对键角、二面角等更高阶几何进行约束，可能导致生成的分子构象稳定性仍有提升空间。
- **合成可及性（SA）较低**：PFM 生成的分子 SA 得分显著低于某些基线（如 Pocket2Mol、TargetDiff），尽管作者解释在可接受范围内，但限制了实际合成可行性。
- **扰动网络依赖预训练**：扰动预测网络需要额外训练，且其有效性依赖于预训练质量（文中通过消融对比 PFM vs. BFM‑Ref 证明了扰动优于直接使用 \(X_1\)，但未讨论预训练网络本身的不确定性）。
- **应用局限性**：文中提到未在大规模多模态生成任务上验证，且方法依赖于对配体原子数的先验采样，可能对非标准分子（如超大配体）适应性不足。
- **公平性细节**：未提及是否将所有对比方法的采样步数标准化（PFM 主实验使用 100 步，而扩散模型通常使用 1000 步），但该差异正是方法优势之一。

（完）
