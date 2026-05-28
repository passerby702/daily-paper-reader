---
title: Integrating Diffusion and Liquid AI Models for Predicting Peptide Affinity from mRNA Display Selections
title_zh: 整合扩散模型与液态人工智能模型预测mRNA展示选择中的肽亲和力
authors: "Leaf, C. M., Qi, P., Gandhi, Y. P., Jalali-Yazdi, F., Ong, J. N., Takahashi, T. T., Kalia, R., Roberts, R. W."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.723033v1.full.pdf"
tags: ["query:pocket-lig"]
score: 9.0
evidence: 去噪扩散模型扩展针对Bcl-xL靶标的功能肽序列，并预测亲和力
tldr: mRNA展示可筛选海量多肽，但序列空间探索受限且缺乏亲和力预测方法。本研究结合去噪扩散隐式模型（DDIM）与封闭式连续（CfC）神经网络，先利用DDIM扩增功能序列，再通过CfC网络基于序列预测结合自由能。结果显示模型准确预测实验及生成肽的亲和力，并鉴定出5个皮摩尔级高亲和力肽，为定向进化数据驱动的肽配体计算机辅助设计提供了统一高效框架。
source: biorxiv
selection_source: fresh_fetch
motivation: mRNA展示等定向进化技术产生大量多肽，但实验探索序列有限，且缺乏精确预测结合自由能的手段。
method: 使用DDIM模型扩增功能肽序列，再训练CfC神经网络以序列-结合自由能对预测ΔG°值。
result: CfC模型准确预测实验与生成肽的亲和力排名及自由能，发现5个具有个位数皮摩尔亲和力的DDIM生成肽。
conclusion: 结合DDIM和CfC网络可从定量数据中扩展并精准预测高亲和力肽，加速配体发现流程。
---

## 摘要
体外选择和定向进化技术如mRNA展示，能探索大型文库（≥10^14个变体）并产生针对各种靶标的数千至数百万个功能多肽配体。使用展示衍生的深度测序数据训练的降噪扩散隐式机器学习模型（DDIMs）可大幅扩展这些功能序列，超越实验可及范围。然而，仍需方法预测肽的性质，如结合自由能（ΔG°）。在此，我们应用机器学习方法预测实验和DDIM生成的多肽配体对目标靶标——致癌蛋白Bcl-xL的结合自由能。为此，我们使用包含15,700个多肽配体的数据集训练了一个闭式连续（CfC）神经网络，其中序列及其对应的结合自由能（ΔG°）作为输入。选择该模型是因为它能表示不规则系列。得到的CfC模型准确预测了实验和DDIM生成肽的排序（在误差范围内）及结合自由能（ΔG°），并识别出五个具有个位数皮摩尔亲和力的DDIM生成肽。结合训练的DDIM和CfC模型，提供了一条统一途径，扩展了实验配体发现的范围，预测实验和生成配体的分子性质，并凸显了大型定量数据集在计算机上精确预测高亲和力候选肽的实用性。

声明：对mRNA展示文库的高通量测序分析能够产生新型多肽配体，并扩展功能序列的范围，超越实验可及。使用序列及其相应的自由能训练的闭式连续神经网络，准确预测实验和机器学习生成肽的结合自由能，从而能够利用定向进化数据定量预测肽的性质。

## Abstract
In vitro selection and directed evolution technologies such as mRNA display, explore large libraries ([&ge;]1014 variants) and generate thousands to millions of functional polypeptide ligands to a variety of targets. Denoising diffusion implicit machine learning models (DDIMs) trained using display-derived deep sequencing data can greatly expand these functional sequences beyond what is accessible experimentally. However, methods are needed to predict peptide properties such as binding free energies ({Delta}G{degrees}). Here, we applied machine learning methods to predict binding free energies of both experimental and DDIM-generated peptide ligands against a target of interest, the oncogenic protein Bcl-xL. To do this, we trained a Closed-form Continuous (CfC) neural network using a dataset of 15,700 peptide ligands where pairs of sequences and their corresponding binding free energies ({Delta}G{degrees}) were used as inputs. This type of model was chosen due to its ability to represent irregular series. The resulting CfC model accurately predicts the rank order, within error, and binding free energies ({Delta}G{degrees}) for both experimental and DDIM-generated peptides, identifying five DDIM-generated peptides with single-digit picomolar affinities. Combining trained DDIM and CfC models offers a unified route to expand the scope of experimental ligand discovery, predict the molecular properties of both experimental and generated ligands, and highlights the utility of large quantitative datasets for making accurate in silico predictions of high-affinity peptide candidates.

StatementHigh-throughput sequencing analysis of mRNA display libraries enables generating novel peptide ligands and expands the scope of functional sequences beyond what is accessible experimentally. Closed-form Continuous neural networks trained using sequences and their corresponding free energies accurately predict the binding free energies of both experimental and machine learning-generated peptides, enabling a route to quantitatively predict peptide properties using directed evolution data.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景与问题**：  
  mRNA 展示等体外选择技术可筛选数目庞大的随机肽库（≥10^14变体），产生大量针对目标蛋白质的功能肽配体。然而，实验能够探索的序列空间极为有限，且缺乏统一的计算方法直接根据序列预测结合自由能（ΔG°），这限制了从海量富集数据中高效发现高亲和力候选肽的能力。
- **整体含义**：  
  论文提出了一种将**生成模型**与**预测模型**串联的计算框架：先用**去噪扩散隐式模型（DDIM）** 对实验获得的有限功能序列进行扩展，生成超出实验可及范围的新型肽；再通过**闭式连续（CfC）神经网络**以序列‑结合自由能对为输入，定量预测肽的结合自由能。该框架旨在从大规模定量测序数据中加速高亲和力配体的计算机发现，并展示定向进化数据驱动配体设计的潜力。

### 2. 论文提出的方法论

- **核心思想**：  
  分为两个相互配合的阶段：  
  1. **序列生成与扩展**：利用 DDIM 从 mRNA 展示的深度测序数据中学习功能肽的分布，生成大量新颖且保留功能特征的肽序列。  
  2. **亲和力预测**：训练 CfC 神经网络，直接将肽序列映射到其结合自由能 ΔG°，从而对实验所得肽和 DDIM 生成肽进行定量排序和识别。

- **关键技术细节**：
  - **去噪扩散隐式模型 (DDIM)**  
    - 以深度测序获得的肽序列作为训练数据，学习功能肽的潜在概率分布。  
    - 通过迭代去噪过程生成新序列，可超越实验文库的覆盖范围。  
  - **闭式连续 (CfC) 神经网络**  
    - 选择 CfC 的理由是它能有效建模**不规则序列**（irregular series）。  
    - 输入为肽序列及其对应的实验结合自由能（ΔG°）构成的配对数据集（共 15,700 条肽）。  
    - 网络输出为预测的 ΔG° 值，实现对亲和力的连续值回归。

- **算法流程（文字描述）**：  
  1. 从 mRNA 展示高通量测序数据中获取丰度信息及对应肽序列，通过定量分析得到一批肽的 ΔG° 值。  
  2. 用这些序列训练 DDIM，学习肽序列的生成分布；采样生成大量新肽。  
  3. 将实验测定的序列‑ΔG° 对作为训练集，训练 CfC 网络。  
  4. 对实验保留的测试肽以及 DDIM 生成肽，用 CfC 预测 ΔG°，并与实验测定值比较，评估排序和数值准确性。  
  5. 筛选预测为皮摩尔级亲和力的生成肽进行实验验证。

### 3. 实验设计

- **数据集与场景**：  
  - 靶标：**致癌蛋白 Bcl‑xL**。  
  - 训练 CfC 的数据集包含 **15,700 个肽配体**，每个配体有确切的序列和实验测定的结合自由能 ΔG°。  
  - 评价对象包括：  
    - 实验获得的肽（含训练中未见过的子集）。  
    - DDIM 生成的全新肽。

- **Benchmark 与对比方法**：  
  - 主要基准是实验测定的 ΔG° 值及亲和力排序。  
  - 文中未提及对比其他机器学习模型（如常规 RNN、CNN、Transformer 等），但强调了 CfC 模型对不规则序列的建模优势。  
  - 通过预测排序准确性（误差范围内）和自由能数值偏差来评估模型性能。

### 4. 资源与算力

- **文中提及情况**：  
  提供的元数据、摘要和简介中**未披露**所用 GPU 型号、数量、训练时长等算力信息。DDIM 和 CfC 的训练计算资源需求未明确说明。

### 5. 实验数量与充分性

- **实验组数**：  
  - 主要验证实验包括：  
    1. 对实验肽的 ΔG° 预测与其实际排序和数值的对比。  
    2. 对 DDIM 生成肽的预测排序，并挑选 5 个预测为个位数皮摩尔亲和力的候选进行实验验证。  
  - 此外，可能涉及消融或参数敏感性分析（未明确说明）。

- **充分性与公平性**：  
  - 训练集规模较大（15,700 条带定量自由能的序列），有助于模型学习序列‑亲和力的映射。  
  - 对外部生成序列的预测验证了模型的泛化能力。  
  - 欠缺与其他基线模型的比较，且未详细报告交叉验证、误差统计（如 RMSE、相关性系数）及超参数消融实验，因此**实验的对比充分度有限**。  
  - 仅在一个靶标（Bcl‑xL）上测试，泛化性尚未评估。

### 6. 论文的主要结论与发现

- CfC 模型能够**准确预测**实验肽的结合自由能和相对排序（在误差范围内）。  
- 对 DDIM 生成的超出实验范围的全新肽，CfC 预测结果同样准确，并成功**鉴定出 5 个具有个位数皮摩尔亲和力**（单数字 pM）的高亲和力肽。  
- 结合 DDIM 和 CfC 构成了一条**统一的计算机辅助流程**，能够扩展功能序列空间并定量预测亲和力，显著加速高亲和力配体的发现。  
- 大规模定量数据集（序列‑ΔG° 对）对于训练精准预测模型至关重要。

### 7. 优点

- **方法亮点**：  
  - 将扩散生成模型与连续时间序列专用网络结合，首先生成多肽，再精确预测自由能，形成完整闭环。  
  - 使用 CfC 处理序列这种非规则采样问题，理论上比传统 RNN 更灵活。  
  - 直接从实验定量数据学习，无需依赖结构信息，更贴近定向进化实际输出。  
- **实验结果亮点**：  
  - 在真实高价值靶标 Bcl‑xL 上验证，得到皮摩尔级候选肽，展示了实际应用潜力。  
  - 对生成肽的预测和实验验证证明了模型的泛化能力。

### 8. 不足与局限

- **实验覆盖不足**：  
  - 仅在一个靶标（Bcl‑xL）上评估，未进行多样性的靶点测试。  
  - 缺乏与传统机器学习基线（如基于序列的词向量+回归器）的系统性对比。  
  - 未报告详细的误差度量（相关系数、平均绝对误差等）和统计显著性检验。  
- **偏差风险**：  
  - 训练数据来源于同一实验平台的测量，存在系统偏差，可能影响模型在实际筛选不同条件下的适应性。  
  - 仅使用序列和自由能，忽略了肽构象、靶标动态等信息，复杂结合机制可能未被捕捉。  
- **应用限制**：  
  - 计算成本未披露，可能限制大规模推广。  
  - 尚未解决肽的稳定性、细胞渗透性、选择性等药物开发中必须考虑的性质。  

（完）
