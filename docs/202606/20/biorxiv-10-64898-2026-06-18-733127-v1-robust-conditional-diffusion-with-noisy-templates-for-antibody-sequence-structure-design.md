---
title: Robust Conditional Diffusion with Noisy Templates for Antibody Sequence-Structure Design
title_zh: 基于噪声模板的鲁棒条件扩散用于抗体序列-结构设计
authors: "Liu, p., Zhang, J., Yan, C."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733127v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 抗体序列-结构设计的扩散模型
tldr: "抗体设计面临数据稀缺和搜索空间大的挑战，从数据库检索的CDR模板虽可缩小搜索范围但可能不准确。本文提出NT-ABDiff，一种抗噪声模板的鲁棒条件扩散模型，通过可靠性感知模板调制自适应融合多个候选模板，并采用混合质量模板进行条件扰动正则化训练。实验表明，在多种模板缺失或错误场景下，NT-ABDiff显著提升CDR-H3序列恢复率（AAR达39.50%）和结构精度（RMSD降至2.76Å），优于现有方法，且对不完美模板保持稳定。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基于模板的抗体设计将检索模板作为硬条件，但针对新抗原的模板稀疏且有噪声，导致负迁移。
method: 提出NT-ABDiff，采用可靠性感知模板调制自适应融合多模板，并用混合质量模板进行条件扰动正则化训练。
result: "在随机模板和训练集检索评估中，NT-ABDiff将AAR提升至39.47%和39.50%，RMSD降至2.915Å和2.76Å。"
conclusion: NT-ABDiff有效融合噪声模板，提升抗体序列结构设计鲁棒性和准确性。
---

## 摘要
抗体能特异性识别抗原，在治疗发现中发挥核心作用。针对给定抗原设计抗体仍具挑战性，因为抗原-抗体复合物数据有限，而互补决定区（CDR）的序列和构象空间庞大。从数据库或候选库中检索到的CDR模板可以缩小设计空间并提高可控性，但对于新抗原的检索往往稀疏且不完美；将检索到的模板视为硬条件可能会偏置去噪过程并导致负迁移。为解决这一问题，我们提出了基于噪声模板的鲁棒条件扩散用于抗体序列-结构设计（NT-ABDiff），这是一个联合扩散框架，将候选的仅CDR模板视为可选且可能不可靠的条件。NT-ABDiff使用可靠性感知模板调制来估计每个候选模板在上下文条件下的有用性，并在条件化过程中自适应地重新加权和融合多个模板。我们进一步使用混合质量和损坏的模板作为条件扰动正则化来训练模型，鼓励去噪器利用信息性模板，同时在模板无信息时保持稳定。在受控模板偏移和训练集检索评估下的实验表明，NT-ABDiff在强基线上提高了CDR-H3序列恢复和结构准确性，同时保持对缺失、错配和损坏模板的鲁棒性。在严格的随机模板CDR-H3评估中，NT-ABDiff将氨基酸恢复率（AAR）从30.03%提高到39.47%，并将RMSD从3.160Å降低到2.915Å；在训练集检索候选中，它实现了39.50%的AAR和2.76Å的RMSD。代码、处理后的数据划分、配置文件及评估脚本可在https://github.com/ShiDeng7rz/NT-ABDiff获取。

## Abstract
Antibodies specifically recognize antigens and play a central role in therapeutic discovery. Designing antibodies for a given antigen remains challenging because antigen-antibody complex data are limited, whereas the sequence and conformational spaces of complementarity-determining regions (CDRs) are large. Retrieved CDR templates from databases or candidate libraries can narrow the design space and improve controllability, but retrieval for novel antigens is often sparse and imperfect; treating retrieved templates as hard conditions can bias the denoising process and cause negative transfer. To address this problem, we propose Robust Conditional Diffusion with Noisy Templates for antibody sequence-structure design (NT-ABDiff), a joint diffusion framework that treats candidate CDR-only templates as optional and potentially unreliable conditions. NT-ABDiff uses reliability-aware template modulation to estimate the context-conditioned usefulness of each candidate and to adaptively reweight and fuse multiple templates during conditioning. We further train the model with mixed-quality and corrupted templates as conditional perturbation regularization, encouraging the denoiser to exploit informative templates while remaining stable when templates are uninformative. Experiments under controlled template shifts and a train-set retrieval evaluation show that NT-ABDiff improves CDR-H3 sequence recovery and structural accuracy over strong baselines, while retaining robustness to missing, mismatched, and corrupted templates. Under a stringent random-template CDR-H3 evaluation, NT-ABDiff improves amino-acid recovery (AAR) from 30.03% to 39.47% and reduces RMSD from 3.160 to 2.915A; with train-set retrieval candidates, it achieves 39.50% AAR and 2.76 {ring} A RMSD. Code, processed splits, {ring} configuration files, and evaluation scripts are available at https://github.com/ShiDeng7rz/NT-ABDiff.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：抗体设计（特别是CDR-H3环）面临数据稀缺和搜索空间巨大的挑战。从数据库中检索CDR模板虽可缩小设计空间，但针对新抗原的检索结果常常稀疏、弱匹配或不一致，若将检索模板作为硬条件注入去噪过程，会引入负迁移，导致生成质量下降。
- **整体含义**：现有方法要么丢弃模板（失去潜在有用信息），要么僵硬依赖模板（易受噪声干扰）。因此需要一种条件注入机制，能够根据模板与抗原-框架上下文的兼容性自适应地利用或抑制各候选模板，从而在检索失败时仍保持鲁棒性。

## 2. 论文提出的方法论

### 核心思想
- 提出**NT-ABDiff**，基于DiffAb扩散骨架的轻量级模板条件扩展，将候选CDR模板视为**可选且可能不可靠**的条件。
- 通过**可靠性感知模板调制**（可学习的逐模板门控）估算每个模板的上下文条件化有用性，在去噪过程中自适应地重新加权和融合多模板。
- 使用**混合质量模板（原生、同源样、随机）进行条件扰动正则化训练**，使模型学会在信息模板可用时加以利用，在无用模板时不受影响。

### 关键技术细节
1. **模板编码**：每个候选CDR序列模板（长度对齐，非CDR位置用[PAD]填充）通过参数化编码器 \(E_\Theta\) 映射为连续特征 \(Z^{(k)} \in \mathbb{R}^{L \times d_t}\)。
2. **可靠性门控模块**：
   - 对每个模板，将上下文特征 \(H_t\) 与模板特征拼接，通过浅层交互网络 \(\phi_\theta\) 逐位置提取特征，经CDR掩码均值池化，再由评分头 \(s_\theta\) 输出标量 \(\ell^{(k)}\)，经sigmoid得到门控分数 \(\alpha^{(k)} \in [0,1]\)。
   - 训练时使用straight-through estimator得到硬门控 \(\tilde{\alpha}^{(k)} \in \{0,1\}\)；推理时使用阈值 \(\tau = 0.4\)。
3. **可抑制的多模板交叉注意力融合**：
   - 每个模板经门控后得到 \(\tilde{Z}^{(k)}\)，与 \(H_t\) 做交叉注意力得到 \(A^{(k)}\)。
   - 根据硬门控计算归一化权重 \(w^{(k)}\)，加权平均得到融合消息 \(A\)。
   - 通过Post-Norm残差更新 \(H'_t = \mathrm{LN}(H_t + A)\) 和FFN得到最终增强表示 \(\hat{H}_t\)。
4. **训练目标**：
   - 扩散损失 \(\mathcal{L}_{\text{diff}}\)（旋转、位置、序列三部分，沿用DiffAb）。
   - 门控监督损失 \(\mathcal{L}_{\text{gate}}\)：对门控logits施加二元交叉熵，标签 \(y^{(k)}\) 根据构造方式（原生/同源样=1，随机=0）生成。
   - 总损失 \(\mathcal{L}_{\text{total}} = \mathcal{L}_{\text{diff}} + \lambda_{\text{gate}} \mathcal{L}_{\text{gate}}\)。

### 算法流程（文字说明）
1. 对于每个训练批次，构造混合质量模板集（1个原生、⌈ρK⌉个同源样、其余随机），随机打乱后编码。
2. 在每个扩散反向步骤 \(t\)，先用DiffAb的SE(3)-等变编码器计算上下文特征 \(H_t\)，再调用门控模块计算各模板的 \(\alpha^{(k)}\)，硬门控后经交叉注意力融合得到增强特征 \(\hat{H}_t\)。
3. 将时间嵌入与 \(\hat{H}_t\) 拼接，送入三个预测头（位置噪声、旋转更新、氨基酸后验）计算损失。
4. 门控模块同时输出logits，与构造标签计算BCE损失。

## 3. 实验设计

- **数据集**：SAbDab，分辨率<4.0Å，抗原为非蛋白，使用ANARCI（Chothia编号）。以50% CDR-H3序列同一性聚类划分训练/测试集，去除同源重叠。19个验证集。
- **评估场景**：
  - **联合H1/H2/H3共同设计**（Table 1）。
  - **CDR-H3单独设计**（更严格协议，Table 2），减少跨CDR重叠效应。
  - **训练集检索评估**（Table 3）：用MMseqs2以重链非H3上下文中检索候选模板（pident≥80，相同H3长度，去重，取top-4），测试迁移能力。
- **测试模板设置**：
  - **Tst-Rand**：所有模板为随机构造（公平比较）。
  - **Tst-Oracle**：包含一个原生模板（上界，不参与排名）。
  - **Tst-RealBank**：从训练集检索得到的真实候选。
- **对比方法**：DiffAb、DIFFFORCE、RAbD、AbMEGD。所有扩散基线使用相同候选数量(100)和相同精炼管道（OpenMM + Rosetta all-atom refinement）。
- **指标**：AAR（氨基酸恢复率）、RMSD（Cα偏差，框架对齐后）、IMPROVE%（设计CDR复合物能量优于原生的比例）。
- **消融实验**（Table 2）：
  - 移除门控（Trn-Mix w/o Gate）
  - 仅随机模板训练（Trn-RandOnly w/o Gate / +Gate）
  - 仅原生模板训练（Trn-TrueOnly*）
- **门控行为分析**（Fig. 4, Table 4）
- **模板数量敏感性分析**（Fig. 5）：K=2~10，训练固定K=8，测试变化。

## 4. 资源与算力

论文**未明确说明**使用的GPU型号、数量及训练时长。仅提及使用T=100扩散步、Adam优化器、批大小16、K=8模板、90k迭代训练。具体硬件资源未报告。

## 5. 实验数量与充分性

- **实验数量**：约5个主实验+3个消融+2个门控分析+1个敏感性分析，共10+组实验设计，覆盖联合设计、H3单独、检索、消融、门控、模板数量等维度。
- **充分性**：实验设计较为全面，考虑了多种模板质量场景（随机、混合、检索），进行了严格的聚类划分避免数据泄露，并做了多随机种子验证（报告中提及5种子变异性在补充材料）。消融实验隔离了门控、训练模板构造等关键组件。敏感性实验探索了K的影响。
- **公平性**：所有方法共享相同候选预算和精炼管道，Oracle设置不参与排名。但直接与RAbD等非扩散方法对比时，RMSD指标可能受精炼流程影响（RAbD本身基于Rosetta，可能更有利）。整体对比合理。

## 6. 论文的主要结论与发现

1. **NT-ABDiff在Tst-Rand随机模板下显著优于DiffAb等基线**：
   - 联合H1/H2/H3：H3 AAR 38.96（第二，接近AbMEGD 38.93），H3 RMSD 3.065（第二，优于所有扩散基线）。
   - H3单独：AAR从30.03%提升至39.47%，RMSD从3.160降至2.915Å。
2. **Oracle上界设置显示模型能利用信息模板**：H3 AAR达41.70%，RMSD达2.871Å。
3. **门控是必要的**：移除门控后性能显著下降（AAR 29.87%，RMSD 3.194），几乎回到DiffAb水平。
4. **混合质量模板训练比单一类型训练更优**：Trn-TrueOnly*（仅原生）甚至更差（20.29% AAR），Trn-RandOnly稍好但不如混合。
5. **训练集检索评估中，混合训练的模型直接迁移有效**：在Tst-RealBank上AAR达39.50%，RMSD达2.76Å，优于同场景训练的门控变体（31.76%）。
6. **门控行为分析**：在混合池中，门控将高分数分配给原生/同源模板，随机模板分数接近零；在随机池中，门控集中在小值附近（均值0.071），偶尔有高激活但不主导去噪。
7. **模板数量敏感性**：K=8效果最佳，测试时增加K性能先升后饱和。

## 7. 优点

- **问题动机清晰**：针对模板检索不可靠的实际场景，设计鲁棒条件机制，具有实践价值。
- **方法简洁有效**：在DiffAb骨架基础上仅修改条件路径，门控模块轻量且可解释。
- **实验设计严谨**：严格聚类划分，考虑多种模板质量（随机、混合、检索），消融充分，门控行为可视化。
- **公平比较**：统一候选数、精炼管道，Oracle不作为正式排名。
- **代码开源**：提供完整配置和脚本，可复现。
- **迁移性验证**：混合训练模型能直接迁移到检索真实候选，说明泛化能力。

## 8. 不足与局限

- **数据集偏差**：SAbDab偏向常见靶点，对稀有表位性能未知。
- **模板构造人为化**：训练时混合模板基于随机突变，可能与真实检索分布不完全一致（虽然后续用真实检索验证了部分泛化，但未做外部独立数据库端到端检索）。
- **未优化可开发性**：未考虑免疫原性、稳定性、可制造性等属性，设计产物仍需实验验证。
- **能量优化不足**：IMPROVE%指标不如DIFFFORCE和RAbD，表明NT-ABDiff不直接优化Rosetta能量。
- **仅评估DiffAb骨架**：模块可移植性未在其他生成骨架上验证。
- **硬件资源未报告**：复现所需算力不明。
- **双用途风险**：仅提及需遵循机构政策，未讨论具体缓解措施。

（完）
