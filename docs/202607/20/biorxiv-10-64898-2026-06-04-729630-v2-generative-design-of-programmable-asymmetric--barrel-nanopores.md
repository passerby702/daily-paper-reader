---
title: Generative design of programmable asymmetric β-barrel nanopores
title_zh: 可编程非对称β桶纳米孔的生成式设计
authors: "Philomin, A., Sonigra, R., Majumder, S., Lin, H.-J., Li, Y., Xue, F., Kibler, R. D., Baldus, C., Trapido, E., Medeiros, A., Coventry, B., Bera, A., Kang, A., Mendoza, J., Kumar, M., Yang, Y., Baker, D."
date: 2026-07-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.729630v2.full.pdf"
tags: ["query:diff-gen"]
score: 8.0
evidence: 生成式AI框架设计蛋白质纳米孔，直接与分子生成相关
tldr: 蛋白质纳米孔在分子传感等领域重要，但可编程设计困难。本文提出生成式AI框架，设计跨膜β桶纳米孔，训练于蒸馏集。实验表征48个设计，直径0.7-1.5 nm，晶体结构匹配模型。方法实现可定制纳米孔，用于离子传感、DNA易位等，突破传统设计局限。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-04-729630-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1661, \"height\": 1826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-04-729630-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1642, \"height\": 2228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-04-729630-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1686, \"height\": 1118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-04-729630-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1684, \"height\": 1826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-04-729630-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1700, \"height\": 1230, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-04-729630-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1550, \"height\": 724, \"label\": \"Table\"}]"
motivation: 现有纳米孔设计方法局限于均匀管腔结构，难以实现可编程功能，且高度依赖于工。
method: 采用生成式AI框架，包含主链和序列设计模型，并在精选蒸馏集上训练。
result: 设计了48种跨膜β桶纳米孔，直径0.7-1.5 nm，晶体结构与设计模型高度一致。
conclusion: 该方法可生成可定制的纳米孔，应用于离子传感、DNA易位和跨膜传输，实现功能可编程。
---

## 摘要
蛋白质纳米孔是分子传感、测序和分离的有力工具，但设计具有可编程功能的孔仍然具有挑战性。天然同源寡聚体跨膜β桶常用于这些应用，但其均匀的管腔限制了空间分辨率和分析物区分能力。尽管可以使用基于能量的方法设计单体TMB，但这些方法仍高度依赖人工，且局限于结构设计而非功能。在此，我们提出一个用于TMB设计的生成式AI框架，其骨干和序列设计模型基于一个精选的蒸馏集进行训练。我们表征了48种设计，直径范围为0.7-1.5纳米，具有多样化的管腔化学性质和疏水厚度。晶体结构与设计模型高度吻合。我们证明，我们的方法可生成用于离子传感、DNA易位以及跨聚合物膜运输的可定制纳米孔。

## Abstract
Protein nanopores are powerful tools for molecular sensing, sequencing, and separation, but designing pores with programmable function remains challenging. Native homo-oligomeric transmembrane {beta} barrels (TMBs) are used for these applications, but their uniform lumens limit spatial resolution and analyte discrimination. Although monomeric TMBs can be designed using energy-based methods, these approaches remain highly manual and limited to structural design rather than function. Here, we present a generative AI framework for TMB design, with backbone and sequence design models trained on a curated distillation set. We characterized 48 designs spanning 0.7-1.5 nm in diameter, diverse lumen chemistries, and hydrophobic thicknesses. Crystal structures closely match the design models. We demonstrate that our method produces customizable nanopores for ion sensing, DNA translocation, and transport across polymer membranes.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

蛋白质纳米孔在单分子传感、DNA/RNA测序和分子分离等领域具有广泛应用。然而，天然纳米孔（如 α-溶血素、MspA 等）通常具有对称的管腔结构，限制了空间分辨率和分析物区分能力；而单体细菌孔如 OmpF 虽有一定不对称性，但受进化“包袱”影响（如柔性 loop 导致的噪声和自发门控），且难以在不破坏孔结构的前提下进行重工程化。传统从头设计方法（如基于 Rosetta 的能量方法）虽然可以构建跨膜 β 桶（TMB），但高度依赖人工经验，主要关注结构设计而非功能可编程性。

本文旨在解决 **TMB 可编程功能设计的瓶颈**，提出一个端到端的生成式 AI 框架，能够生成具有可调疏水厚度、多样管腔化学性质和几何不对称性的 TMB 纳米孔，并实现离子传感、DNA 易位以及跨聚合物膜运输等功能。

### 2. 论文提出的方法论：核心思想、关键技术细节

核心思想：通过**两阶段生成式 AI 管线**实现 TMB 的从头设计——先由扩散模型生成主链，再由消息传递神经网络设计序列。

**关键技术细节：**

- **蒸馏集构建**：从 “Is It A Barrel” 数据库出发，选择长度 <600 氨基酸的序列，利用 AlphaFold 数据库（AFDB）或 AlphaFold2 预测结构，经 pLDDT (>75)、二级结构、主链氢键和几何特征过滤，最终获得 117,447 个高置信度单体 TMB 结构（远超 OPM 数据库中的 699 个实验结构）。
- **主链生成模型（TMB_RFD2）**：在 RFDiffusion2 基础上微调。通过引入 1D 残基级二级结构特征、2D 残基-残基邻接矩阵（编码 β 链配对）以及额外的 1D 二进制输入（指示甘氨酸扭转和 β 凸起的位置），使模型能够生成更符合天然 TMB 特征的骨架。训练时采用选择性掩码防止泄露链长信息。
- **序列设计模型（TMB_MPNN）**：在 ProteinMPNN 基础上改进。将感受野从 32 个最近邻增大到 96 个，使残基能感知桶对面残基；并在 TMB 蒸馏集上微调，纠正 ProteinMPNN 在埋藏区域过度使用脂肪族残基的偏差。进一步引入**疏水厚度感知变体**，通过 token 化埋藏跨膜区和界面区，实现可调节疏水厚度。
- **功能基序脚手架**：利用 RFDiffusion2 的基序脚手架训练协议，随机采样面向孔内部的链段，在管腔中引入功能基序（如 His₃ 铜结合位点）。
- **计算筛选**：使用 AlphaFold3 或 RosettaFold3 作为结构预测 oracle，过滤出高 pLDDT 和低 Cα RMSD 的设计。

（公式/算法流程本文未给出具体数学公式，上述为文字描述。）

### 3. 实验设计：使用的数据集、基准和对比方法

**数据集**：
- **蒸馏集**：来自 "Is It A Barrel" 数据库的 485,000 个预测结构，经筛选得到 117,447 个高置信度 TMB。用于训练 TMB_RFD2 和 TMB_MPNN。
- **PDB 结构**：699 个实验 TMB 结构（OPM 数据库）用于对比和初始训练。
- **AlphaFold 数据库（AFDB）**提供预测结构来源。

**基准**：
- 主链生成：对比 Parametric-guided diffusion、原始 RFDiffusion2（RFD2）、未经条件化的 NC_TMB_RFD2 以及条件化的 TMB_RFD2，评估几何过滤通过率、甘氨酸扭转和 β 凸起数量。
- 序列设计：对比 ProteinMPNN、96NN_MPNN 和 TMB_MPNN，评估在已知工作骨架上的氨基酸组成偏差、AlphaFold 预测质量以及大肠杆菌表达率。

**实验场景**：
- 体外表达和折叠：在大肠杆菌中表达、纯化、重折叠，通过 SEC 评估折叠质量。
- 电生理学：在 DPhPC 脂质双层中用 Orbit 16 TC 平台测量单通道电导及门控行为。
- 离子选择性：对 10 链和 12 链孔测量不同阳离子/阴离子溶液的电导。
- 晶体结构：解析 2 个 10 链设计的 X 射线晶体结构（分辨率未明确给出，但 RMSD <1.2 Å）。
- 功能验证：铜离子感应（His₃ 基序）、DNA 易位（22 胸腺嘧啶重复和酶驱动质粒易位）、聚合物膜整合（PBd-b-PEO 膜）及 JIBE 平台测试。

**对比方法**：
- 与前期能量法设计（如 Berhanu 2024, Vorobieva 2021）对比表达成功率、SEC 质量和功能成功率。
- 与自然孔 R10.4 对比 DNA 易位信号（状态转移概率热图）。

### 4. 资源与算力

**论文未明确说明使用的 GPU 型号、数量及训练时长**。仅提及训练使用了 TMB_RFD2 和 TMB_MPNN 模型，但未列出具体计算资源投入。因此，无法在此方面提供详细信息。

### 5. 实验数量与充分性

**实验数量**：
- **主链生成**：针对不同链数（10/12/14/16，及少量 18）各生成 100 个主链，并统计通过几何过滤的比例。
- **序列设计**：共测试了 48 个设计进行详细表征，包括 10-16 链。具体数字：42 个 10 链、47 个 12 链、91 个 14 链、101 个 16 链设计用于 SEC 测试（表1）。
- **功能验证**：铜离子传感（1 个主要设计 + 1 个敲除对照）、DNA 易位（2 个 14 链设计）、聚合物膜整合（2 个设计对比，其中 1 个为前期方法设计）、JIBE 测试（2 个设计对比）。
- **晶体结构**：2 个 10 链设计的晶体解析。
- **突变实验**：在未表达的 NC_TMB_RFD2 设计中引入脯氨酸突变（显示可恢复功能）。

**充分性**：
- 实验覆盖了从主链生成 → 序列设计 → 体外表达 → 结构验证 → 多种功能验证的完整管线，较为全面。
- 消融实验：对比了有无条件化（NC vs TMB_RFD2）、不同感受野（96NN vs TMB_MPNN）、有无脯氨酸突变等，控制变量较好。
- **客观性**：所有成功率均基于实际实验（表达、SEC、电生理），并非纯计算指标。但功能实验样本量有限（如 DNA 易位仅 1-2 个孔），可能不足以泛化。
- **公平性**：与前期能量法设计的对比直接点出优劣（如 TMB12_3 无法插入聚合物膜而本工作设计可插入），但未在完全一致的实验条件下对比所有设计（如相同缓冲液、相同电压），略有不足。

### 6. 论文的主要结论与发现

1. **TMB_RFD2** 可通过指定链数、残基数、甘氨酸扭转和 β 凸起位置生成结构多样的骨架，且晶体结构与设计模型高度吻合（RMSD ~0.7-1.2 Å），验证了设计精度。
2. **TMB_MPNN** 能生成更接近天然 TMB 氨基酸组成的序列，显著提高大肠杆菌表达率（60-80% vs NC_TMB_RFD2 的 20-40%），且改善了折叠质量（SEC 峰清晰、聚集减少）。
3. 设计出的 TMB 孔径范围 0.7-1.5 nm，具有不对称离子传输行为，且离子电导不遵循体相迁移率趋势，表明可通过管腔化学和几何控制选择性。
4. 成功在管腔中脚手架化 His₃ 铜结合基序，实现铜特异性门控（敲除对照无响应），证明了分子感应的可编程性。
5. 14 链设计 TMB_N14_des1 可观察到酶驱动的 DNA 易位信号，虽噪声较高但状态转移概率与 R10.4 孔类似，首次展示无可溶结构域的非对称纳米孔实现酶促 DNA 穿行。
6. 通过延长疏水厚度（~32 Å）设计，TMB_N10_des5 能在聚合物膜（PBd-b-PEO）和 C18 单甘油酯双层（JIBE）中形成稳定通道，而传统短设计（TMB12_3）不能。
7. 脯氨酸在顺式 β 凸起处的引入是改善折叠和功能的关键因素之一。

### 7. 优点

- **创新性**：首次将生成式 AI（扩散模型+消息传递网络）端到端地应用于 TMB 纳米孔设计，突破了传统能量法的手动限制。
- **数据构建**：构建了超大规模的高置信度 TMB 蒸馏集（11.7 万结构），为深度学习提供关键训练数据。
- **条件可控性**：主链生成可指定甘氨酸扭转、β 凸起等天然特征；序列设计可调节疏水厚度，适应不同膜环境。
- **实验验证充分**：从结构（晶体）到功能（电生理、离子传感、DNA 易位、聚合物膜）多维度证明方法有效性。
- **可编程性**：通过基序脚手架实现功能模块化添加（如金属结合），展示了从结构到功能的定制能力。
- **应用潜力**：聚合物膜兼容性为工业过滤和传感提供新平台；DNA 易位展示测序可能。

### 8. 不足与局限

- **大桶设计稳定性**：链数 ≥ 16 的设计 SEC 峰不清晰、聚集多，电导噪声大，表明大桶稳定性不足。作者提及其有螺旋结构域的设计噪声也高，未来需优化。
- **功能实验样本量有限**：DNA 易位仅测试了 2 个 14 链设计，且信号噪声高于商业孔 R10.4，远未达到实际测序所需分辨率；铜传感仅 1 个主要设计 + 1 个敲除，缺乏多位点改变复现。
- **计算资源未披露**：无法评估方法的可复现性和资源需求。
- **表达依赖大肠杆菌**：所有设计在 E. coli 中表达为包涵体后重折叠，效率较低且可能丢失膜环境信息；未测试真核表达系统。
- **孔的自发门控**：部分设计即使在无天然 loop 时仍显示随机门控，提示对膜动态和骨架柔性的考虑仍不充分（作者也承认这一点）。
- **对比不够全面**：与前期能量法设计的比较仅在表达成功率、SEC 质量和聚合物膜插入上，未在相同条件下系统对比所有电导特性或单分子传感能力。
- **缺乏分子动力学验证**：设计过程中未使用 MD 模拟来优化或评估孔在膜中的动态行为，可能限制对门控和选择性的理解。

（完）
