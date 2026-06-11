---
title: "A Drug-Target Specificity Foundation Model for Off-target Prediction, Repurposing, and Generative Design"
title_zh: 用于脱靶预测、老药新用和生成式设计的药物-靶标特异性基础模型
authors: "Reddy, S. T."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.730844v1.full.pdf"
tags: ["query:pocket-lig"]
score: 9.0
evidence: 直接针对靶标特异性的配体生成设计，匹配生成结合蛋白质口袋的配体的需求
tldr: "药物-靶点识别特异性由实验或基于结构的方法决定，成本高且通量低。本文提出dtSFM基础模型，基于Transformer注意力与玻尔兹曼分布的数学同构，直接从序列计算结合热力学。模型在71万已知相互作用上训练，编码器实现药物/靶点检索95%/89%召回率，脱靶筛选排名前0.6%；解码器生成分子71%达到与已批准药相当的AlphaFold 3置信度。该模型将计算热力学引入药物发现各阶段，实验验证为下一步工作。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法预测药物-靶点特异性依赖三维结构或实验筛选，效率低且覆盖有限；需一种直接从序列高效预测结合亲和力的通用框架。
method: "利用Transformer注意力玻尔兹曼同构，构建dtSFM编码器-解码器架构，在714,747个药物-蛋白质相互作用数据上训练，无需结构输入。"
result: "编码器对已知靶点/药物检索召回率达95%/89%；脱靶筛选排名前0.6%；发现46个新候选分子；生成设计71%候选分子达到高置信度指标。"
conclusion: dtSFM实现了序列原生的小分子-靶点特异性预测，覆盖脱靶预测、重定位和生成设计，为药物发现提供高效计算工具，待湿实验验证。
---

## 摘要
分子识别——即小分子与哪种蛋白质结合以及选择性如何——决定了每种治疗药物的疗效、安全性和发现，然而结合特异性仍通过实验筛选或先预测三维结构的计算方法来确定。Transformer的softmax注意力在数学上同构于热平衡下支配分子结合的玻尔兹曼分布¹，这一恒等式确定了一种单一的序列原生架构：特异性基础模型（SFM），该模型直接从序列计算分子结合兼容性作为热力学量²。该框架最近在六个分子识别领域作为原型编码器实现³。本文报告了小分子药物-靶标蛋白SFM（dtSFM）作为首个将全尺寸编码器与生成式解码器配对的实例，该模型在公开可用的数据上训练，包含714,747个测量的药物-蛋白质相互作用，涵盖522,776种化合物和22,964种蛋白质。在整个过程中，我们使用AlphaFold 3⁴作为正交结构验证器来验证结合预测，该验证器与dtSFM不共享架构、训练数据或表示基础。通过这个单一的dtSFM模型，我们展示了药物发现的三种序列原生应用：脱靶预测、老药新用和生成式设计。dtSFM编码器分别以95%和89%的分布内前十召回率检索药物的靶标和靶标的药物。在药物→靶标方向上，它在蛋白质组规模上筛选脱靶，针对临床激酶抑制剂的已记录脱靶，排名中位数为4,910个基因中的第30位——即筛选的前0.6%——在化学蛋白质组学面板验证后⁵。在靶标→药物方向上，它针对三个免疫学靶标对完整的522,776种化合物库进行排名，识别出46个通过AlphaFold-3结构门控的新候选分子。dtSFM交叉注意力解码器为16个靶标生成新分子，其中1,200个设计候选分子中有850个（71%）与已批准药物的AlphaFold 3结构置信度匹配（iPTM ≥ 0.9且界面PAE ≤ 1.67 Å），最佳候选分子达到iPTM 0.95-0.99和界面PAE 0.79-1.37 Å。dtSFM将计算热力学引入分子识别塑造药物发现的每个阶段；湿实验验证是下一步的直接工作。

## Abstract
Molecular recognition - which small molecule binds which protein, and with what selectivity - governs the efficacy, safety, and discovery of every therapeutic, yet binding specificity is still determined by experimental screening or by computational methods that first predict three-dimensional structure. Transformer softmax attention is mathematically isomorphic to the Boltzmann distribution governing molecular binding at thermal equilibrium1, an identity that prescribes a single sequence-native architecture: the Specificity Foundation Model (SFM), which computes molecular binding compatibility as a thermodynamic quantity directly from sequence2. The framework was recently realized as prototype encoders across six molecular-recognition domains3. Here we report the small molecule drug-target protein SFM (dtSFM) as the first instance to pair a full-scale encoder with a generative decoder, trained on publicly available data consisting of 714,747 measured drug-protein interactions spanning 522,776 compounds and 22,964 proteins. Throughout, we verify binding predictions with AlphaFold 34 as an orthogonal structural verifier that shares no architecture, training data, or representational basis with dtSFM. From this single dtSFM model we demonstrate the three sequence-native applications of drug discovery: off-target prediction, repurposing, and generative design. The dtSFM encoder retrieves a drugs target, and a targets drug, at 95% and 89% recall-at-10 in distribution, respectively. In the drug[-&gt;]target direction it screens off-targets at proteome scale, ranking the documented off-targets of clinical kinase inhibitors at a median of 30th out of 4,910 genes - the top 0.6% of the screen - when validated against a chemoproteomic panel5. In the target[-&gt;]drug direction it ranks the full 522,776-compound library against three immunology targets, identifying 46 novel candidates that pass AlphaFold-3 structural gating. The dtSFM cross-attentive decoder generates novel molecules for 16 targets, 850 of 1,200 (71%) designed candidates match the AlphaFold 3 structural confidence of the approved drug (iPTM [&ge;] 0.9 and interface PAE [&le;] 1.67 [A]), with the best candidates reaching iPTM 0.95-0.99 and interface PAE 0.79-1.37 [A]. dtSFM brings computational thermodynamics to every stage where molecular recognition shapes drug discovery; experimental wet-lab validation is the immediate next step.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：药物-靶点特异性（即小分子与哪种蛋白质结合以及选择性）的预测是药物发现的核心，但传统方法依赖实验筛选或先预测三维结构的计算方法，成本高、通量低，难以覆盖大规模蛋白质组和化合物库。
- **整体含义**：本文提出一个名为dtSFM（药物-靶标特异性基础模型）的序列原生框架，利用Transformer注意力与玻尔兹曼分布的数学同构，直接从序列计算结合热力学，同时实现脱靶预测、老药新用和生成式设计三种关键应用，旨在为药物发现提供高效、统一的计算工具。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：Transformer的softmax注意力在数学上同构于热平衡下分子结合的玻尔兹曼分布，因此可以直接从序列计算分子结合兼容性作为热力学量，无需显式三维结构预测。
- **关键技术细节**：
  - 构建编码器-解码器架构，命名为dtSFM（特异性基础模型的药物-靶标实例）。
  - **编码器**：用于药物-靶标检索和筛选，输出结合概率或排名。
  - **交叉注意力解码器**：用于生成新分子，输入目标蛋白质序列，输出小分子结构。
  - 训练数据：公开可用的714,747个测量的药物-蛋白质相互作用，涵盖522,776种化合物和22,964种蛋白质。
- **公式/算法流程**（文字说明）：
  - 编码阶段：将药物和蛋白质序列分别编码，通过softmax注意力计算交叉注意力分数，模拟玻尔兹曼分布，输出结合兼容性分数。
  - 解码阶段：基于目标蛋白质序列，使用交叉注意力引导自回归生成新的小分子，每一步选择最可能的化学片段。

## 3. 实验设计：数据集、场景、基准与对比方法
- **数据集**：
  - 训练集：714,747个药物-蛋白质相互作用（来自公开数据库），包含522,776种化合物和22,964种蛋白质。
  - 测试/验证：使用AlphaFold 3作为正交结构验证器（与dtSFM无共享架构、训练数据或表示基础）。
- **实验场景**：
  1. **脱靶预测**（药物→靶标方向）：针对临床激酶抑制剂，在蛋白质组规模（4,910个基因）上筛选脱靶，并对照已知脱靶记录和化学蛋白质组学面板验证。
  2. **老药新用**（靶标→药物方向）：针对三个免疫学靶标，对完整522,776种化合物库进行排名，识别候选分子并通过AlphaFold-3结构门控筛选。
  3. **生成式设计**：为16个靶标生成新分子，评估生成分子的AlphaFold 3结构置信度。
- **基准与对比方法**：论文未明确列出与传统方法（如 docking、DL-based affinity prediction）的定量对比，但以AlphaFold 3的结构置信度作为正交验证的“金标准”，并与已批准药物的置信度进行匹配比较。

## 4. 资源与算力
- **未明确说明**：论文摘要中未提及训练使用的GPU型号、数量、训练时长等具体算力信息。仅指出模型在公开数据上训练，是“全尺寸编码器与生成式解码器”的首次配对。

## 5. 实验数量与充分性
- **实验数量**：
  - 编码器检索任务：分布内前十召回率（药物→靶标95%，靶标→药物89%）。
  - 脱靶筛选：针对临床激酶抑制剂，排名中位数在4,910个基因中为第30位（前0.6%）。
  - 老药新用：三个免疫学靶标，发现46个通过AlphaFold-3门控的候选分子。
  - 生成设计：16个靶标，生成1,200个候选分子，其中850个（71%）与已批准药的AlphaFold 3置信度匹配。
- **充分性评估**：
  - **优点**：覆盖了三种典型应用，验证指标多样化（召回率、排名百分位、结构置信度）。
  - **不足**：缺乏消融实验（如不同架构变体、数据量影响的讨论）；未与其他主流方法（如DeepDTA、GraphDTA、Docking）进行定量对比；脱靶筛选仅针对激酶抑制剂，泛化性未充分论证；老药新用仅测试三个靶标，样本量较小。

## 6. 论文的主要结论与发现
- dtSFM编码器能够以高召回率检索已知药物-靶标相互作用，且脱靶筛选排名前0.6%，显示了良好的特异性预测能力。
- 解码器生成的分子中有71%达到与已批准药物相当的AlphaFold 3结构置信度，最佳候选分子iPTM达0.95-0.99，界面PAE低至0.79-1.37 Å，证明生成设计质量高。
- 单一模型实现了脱靶预测、老药新用和生成式设计三种序列原生应用，无需结构输入，为药物发现提供高效计算框架。
- 论文强调湿实验验证是下一步直接工作。

## 7. 优点：方法或实验设计上的亮点
- **方法创新**：利用Transformer注意力与玻尔兹曼分布的数学同构，直接从序列计算结合热力学，跳过了昂贵的三维结构预测步骤，实现了序列原生、一统多用的基础模型。
- **架构完整**：首次将全尺寸编码器与生成式解码器配对，同时支持检索与生成任务。
- **正交验证**：使用与模型完全独立的AlphaFold 3作为结构验证器，增强了结果的可信度，避免了同源偏差。
- **覆盖药物发现关键环节**：在单个模型中整合脱靶预测、老药新用和生成式设计，展示了基础模型的通用性。
- **生成质量高**：71%的生成分子与已批准药物在AlphaFold 3结构置信度上匹配，表明具有良好的结合姿态与界面稳定性。

## 8. 不足与局限
- **缺乏湿实验验证**：所有结论均基于计算预测及AlphaFold 3结构验证，尚未进行实验结合亲和力或功能验证，是最大的局限。
- **对比方法不充分**：未与现有主流方法（如基于结构的docking、基于序列的深度学习模型）进行定量比较，难以评估dtSFM的相对优势。
- **训练数据偏差**：训练数据来源于公开数据库，可能存在数据噪声、测量误差、以及已知相互作用偏向常见靶标/药物，可能影响对孤儿靶点或新化学空间的泛化。
- **脱靶评估范围有限**：仅针对临床激酶抑制剂的已知脱靶进行评估，未测试其他药物类别，脱靶预测的全面性有待扩展。
- **无消融研究**：未探讨不同组件（如编码器深度、注意力头数、训练数据规模）对性能的影响，模型设计选择的合理性缺乏实证。
- **生成分子多样性未评估**：仅报告了与已批准药物的置信度匹配比例，未分析生成分子的化学多样性、新颖性、可合成性等关键指标。

（完）
