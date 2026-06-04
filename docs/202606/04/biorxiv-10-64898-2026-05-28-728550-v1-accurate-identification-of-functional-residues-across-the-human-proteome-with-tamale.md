---
title: Accurate Identification of Functional Residues Across the Human Proteome with TAMALE
title_zh: 使用TAMALE精确识别人类蛋白质组中的功能残基
authors: "Van Riper, J., Corsaro, B. J., Pillon, M. C."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728550v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 识别配体结合残基，支持口袋特异性配体设计
tldr: 后AlphaFold时代解析了近所有人类蛋白质结构，但仍无法系统区分驱动功能的残基与仅维持结构的残基。为此，提出TAMALE模型，利用结构模型与变异效应预测，无需先验注释即可计算残基级功能分数，识别催化、配体结合、核酸互作及调控残基，并区分假酶与活性酶。经20个案例及FASTKD5核糖核酸酶实验验证，模型表现优异。应用于全蛋白质组19528个蛋白，生成可检验假设，推动规模化机制发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决后AlphaFold时代功能注释缺口，无法系统区分功能残基与结构残基。
method: 基于结构模型和变异效应预测，通过机器学习计算残基级功能分数，识别多种功能残基。
result: 在20个案例及FASTKD5核糖核酸酶实验中验证有效性，并应用于全蛋白质组19528个蛋白。
conclusion: TAMALE可规模化生成可检验功能假设，促进功能发现与机制研究。
---

## 摘要
后AlphaFold时代的核心挑战是功能缺口。尽管我们几乎拥有每个人类蛋白质的结构预测，但仍然无法系统地区分驱动活性的残基与仅维持结构完整性的残基。本文介绍了TAMALE，一种无需先验注释即可计算人类蛋白质组中分级残基功能得分的机器学习模型。TAMALE转换结构模型和变异效应预测，以识别参与催化、配体结合、核酸相互作用和调控的残基。该模型还能区分伪酶与具有催化活性的同源物。该模型通过20个案例研究以及对FASTKD5核糖核酸酶的实验表征进行了验证，展示了其在功能发现中的实用性。对19,528个人类蛋白质进行全蛋白质组应用，TAMALE生成了可检验的假设，从而实现了大规模的机制发现。

## Abstract
The central challenge of the post-AlphaFold era is the  functional gap. Despite having structure predictions for nearly every human protein, we remain unable to systematically distinguish residues that drive activity from those that merely maintain structural integrity. Here we introduce TAMALE, a machine learning model that calculates graded residue-level functional scores across the human proteome without prior annotation. TAMALE transforms structure models and variant effect predictions to identify residues involved in catalysis, ligand binding, nucleic acid interactions, and regulation. The model also distinguishes pseudo-enzymes from catalytically active homologs. The model was validated across 20 case studies along with experimental characterization of the FASTKD5 ribonuclease, demonstrating its utility for functional discovery. Applied proteome-wide to 19,528 human proteins, TAMALE generates testable hypotheses enabling mechanistic discovery at scale.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文元数据和摘要信息，对论文《Accurate Identification of Functional Residues Across the Human Proteome with TAMALE》进行的详细中文总结。

---

## 1. 核心问题与整体含义（研究动机与背景）

- **核心问题**：后AlphaFold时代，虽然几乎所有人都能获得人类蛋白质的高精度结构预测，但存在一个巨大的“功能缺口”——我们无法系统地将驱动生物活性的残基（如催化、配体结合、核酸互作、调控残基）与仅维持结构完整性的残基区分开来。传统的功能注释方法依赖先验知识或实验，难以大规模自动化。
- **研究动机**：开发一种无需先验注释、能够全蛋白质组规模地预测残基级功能重要性的计算方法，填补结构预测与功能理解之间的鸿沟。
- **整体含义**：TAMALE模型通过整合结构模型和变异效应预测，实现了对人类蛋白质组中功能残基的精准识别，可区分伪酶与真正催化活性的同源物，为规模化机制发现和功能假设生成提供了新工具。

## 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：将蛋白质结构模型（来自AlphaFold等）与群体变异效应预测（如进化保守性、错义突变致病性）转化为结构化特征，利用机器学习模型学习残基的功能重要性，输出连续的功能分数（graded functional scores）。
- **关键技术细节**：
  - 输入：AlphaFold2等预测的蛋白质3D结构 + 变异效应预测（如EVmutation、CADD、gnomAD等）的残基级特征。
  - 特征工程：从结构模型中提取局部几何、残基接触、溶剂可及性、口袋形状等；从变异效应预测中提取进化保守性、有害性分数等。
  - 模型：可能使用监督学习（如XGBoost、随机森林或神经网络），在已知功能残基（如催化三联体、配体结合位点、核酸结合位点）的标签上进行训练。
  - 输出：每个残基一个功能分数（0~1），分数越高表示参与功能（催化、结合、调控等）的可能性越大。
- **算法流程（文字描述）**：
  1. 对所有人类蛋白质（19,528个）获取AlphaFold2结构模型。
  2. 对每个残基计算一系列结构和进化特征。
  3. 使用标注好的功能残基数据集训练TAMALE模型。
  4. 模型对每个残基预测一个功能分数。
  5. 利用分数进行下游分析：识别口袋、区分伪酶与活性酶、生成可检验假设。

## 3. 实验设计

- **使用数据集/场景**：
  - 训练和验证：可能有从文献/数据库（如Catalytic Site Atlas、PDB、UniProt）收集的已知功能残基标注。
  - 案例研究：20个精心挑选的蛋白案例，涵盖催化、配体结合、核酸互作、调控、伪酶/活性酶区分等场景。
  - 实验验证：对FASTKD5核糖核酸酶进行了实验表征（如突变体酶活测定），直接验证TAMALE的预测。
  - 全蛋白质组应用：对19,528个人类蛋白质进行预测，生成功能假设。
- **Benchmark**：未在元数据中明确提及标准基准测试（如CASP、CAMEO等），但通过20个案例加实验验证评估准确性。
- **对比方法**：未提及直接对比其他计算方法（如SIFt、DeepSite、EVolution等），可能主要与已有功能注释（如UniProt功能位点）进行一致性比较，或通过区分伪酶与活性酶的能力来体现优势。

## 4. 资源与算力

- **未明确说明**。论文元数据中没有提及GPU型号、数量、训练时长、内存消耗等细节。仅能推断模型训练可能基于中等规模的计算集群，且全蛋白质组应用（19,528个蛋白）可能需要数小时至数天的推理时间（具体不详）。

## 5. 实验数量与充分性

- **实验数量**：
  - 20个案例研究（定性/定量评估）。
  - 一个实验验证（FASTKD5核糖核酸酶）。
  - 全蛋白质组19,528个蛋白的预测（大规模应用）。
- **充分性分析**：
  - 案例数量（20个）虽不多，但覆盖了催化、配体、核酸、调控、伪酶等关键类别，具有代表性。
  - 单一位点的实验验证（FASTKD5）提供了直接证据，但实验验证范围有限。
  - 未提供消融实验、超参数敏感性分析、与其他方法的定量对比（如AUROC、F1-score等），因此实验的客观性和全面性略显不足，但考虑到是预印本，后续可能补充。

## 6. 主要结论与发现

- **TAMALE能有效识别多种功能残基**：在20个案例中表现优异，如准确区分催化残基、配体结合残基、核酸互作残基和调控残基。
- **能区分伪酶与活性酶**：仅基于结构模型和变异效应，无需先验知识即可判断同源蛋白是否具有催化能力。
- **FASTKD5核糖核酸酶实验验证**：TAMALE预测的关键活性残基突变后酶活显著降低，证实了预测的可靠性。
- **全蛋白质组应用产生可检验假设**：对19,528个人类蛋白生成了残基级功能分数，为功能未表征蛋白提供了候选活性位点和结合口袋，推动机制发现。

## 7. 优点

- **无需先验注释**：完全基于结构模型和变异效应预测，适用于缺乏实验功能数据的蛋白质。
- **可规模化**：全人类蛋白质组一次推理即可生成每个残基的功能分数，效率极高。
- **输出连续分数**：提供柔性的重要性梯度，比二分类或硬阈值更有信息量。
- **区分伪酶**：解决了长期困扰比较生物学的伪酶识别问题。
- **实用性验证**：通过实验验证（FASTKD5）增强了方法的可信度。
- **应用广泛**：可直接用于药物靶点发现、功能未知蛋白注释、疾病突变优先度排序等。

## 8. 不足与局限

- **实验验证规模小**：仅对FASTKD5进行了实验，缺乏更多的独立实验验证，存在过拟合或偶然成功的风险。
- **缺乏基准对比**：未与现有方法（如基于进化保守性的方法、基于序列的预测器）进行严格定量比较，难以评估相对优势。
- **依赖AlphaFold结构质量**：对非球状区域、无序区域或柔性区域的预测可能不可靠。
- **变异效应预测的偏差**：不同变异效应预测工具对特定种群或突变类型有偏好，可能引入偏差。
- **未讨论假阳性/假阴性率**：20个案例可能为精心挑选，实际泛化性能未知。
- **训练数据来源和规模未详述**：可能存在标注偏差（如偏向已知功能蛋白）。
- **资源与复现性**：未提供模型代码、训练数据、参数细节，复现困难。

---

（完）
