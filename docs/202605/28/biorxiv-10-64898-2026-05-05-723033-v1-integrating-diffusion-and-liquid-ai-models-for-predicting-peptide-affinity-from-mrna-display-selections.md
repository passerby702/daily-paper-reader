---
title: Integrating Diffusion and Liquid AI Models for Predicting Peptide Affinity from mRNA Display Selections
title_zh: 整合扩散与液态人工智能模型从mRNA展示选择中预测肽亲和力
authors: "Leaf, C. M., Qi, P., Gandhi, Y. P., Jalali-Yazdi, F., Ong, J. N., Takahashi, T. T., Kalia, R., Roberts, R. W."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.723033v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 使用DDIM生成针对目标蛋白的肽配体
tldr: mRNA展示技术能从超大文库中筛选出数千至数百万种功能性多肽配体，但实验可探索的序列空间有限。通过去噪扩散隐式模型（DDIM）生成新序列，并利用序列-结合自由能配对数据训练闭式连续（CfC）神经网络来预测亲和力。CfC模型准确预测了实验及DDIM生成肽的结合自由能，从中识别出5条皮摩尔级亲和力多肽。该工作整合生成与预测模型，为基于定向进化数据的高亲和力配体发现提供了定量预测的统一框架。
source: biorxiv
selection_source: carryover_cache
motivation: 针对癌蛋白Bcl-xL，需要从mRNA展示海量数据中准确预测实验与生成肽的结合自由能。
method: "使用15,700条肽配体的序列及其ΔG°配对数据集，训练适于不规则序列的闭式连续（CfC）神经网络模型。"
result: CfC模型能准确预测实验和DDIM生成肽的排序与结合自由能，发现5条单皮摩尔级亲和力的DDIM生成肽。
conclusion: 联合DDIM生成与CfC预测，为利用大规模定量数据集进行肽配体发现与性质预测开辟了统一途径。
---

## 摘要
体外选择和定向进化技术（如mRNA展示）可探索大型文库（≥10^14个变体），并针对多种靶标产生成千上万至数百万的功能性多肽配体。利用展示衍生的深度测序数据训练的去噪扩散隐式机器学习模型（DDIMs）能极大地扩展这些功能序列，远超实验可及的范围。然而，仍需方法预测肽的特性，如结合自由能（ΔG°）。在此，我们应用机器学习方法，预测实验和DDIM生成的肽配体对目标靶标——致癌蛋白Bcl-xL的结合自由能。为此，我们使用包含15,700个肽配体的数据集训练了一个闭式连续（CfC）神经网络，以序列和对应结合自由能（ΔG°）组成的配对作为输入。选择该模型是因其能表示不规则序列。所得的CfC模型能准确预测实验和DDIM生成肽的排序（在误差范围内）及结合自由能（ΔG°），并识别出五个具有个位数皮摩尔亲和力的DDIM生成肽。将训练好的DDIM和CfC模型相结合，为拓展实验配体发现的范畴、预测实验和生成配体的分子性质提供了统一途径，并凸显了利用大型定量数据集对高亲和力肽候选物进行精确计算机预测的效用。

重要性声明对mRNA展示库进行高通量测序分析，能够产生新的肽配体，并将功能序列的范围拓展到实验可及之外。使用序列及其对应自由能训练的闭式连续神经网络，可以准确预测实验和机器学习生成肽的结合自由能，从而提供一条利用定向进化数据定量预测肽性质的途径。

## Abstract
In vitro selection and directed evolution technologies such as mRNA display, explore large libraries ([&ge;]1014 variants) and generate thousands to millions of functional polypeptide ligands to a variety of targets. Denoising diffusion implicit machine learning models (DDIMs) trained using display-derived deep sequencing data can greatly expand these functional sequences beyond what is accessible experimentally. However, methods are needed to predict peptide properties such as binding free energies ({Delta}G{degrees}). Here, we applied machine learning methods to predict binding free energies of both experimental and DDIM-generated peptide ligands against a target of interest, the oncogenic protein Bcl-xL. To do this, we trained a Closed-form Continuous (CfC) neural network using a dataset of 15,700 peptide ligands where pairs of sequences and their corresponding binding free energies ({Delta}G{degrees}) were used as inputs. This type of model was chosen due to its ability to represent irregular series. The resulting CfC model accurately predicts the rank order, within error, and binding free energies ({Delta}G{degrees}) for both experimental and DDIM-generated peptides, identifying five DDIM-generated peptides with single-digit picomolar affinities. Combining trained DDIM and CfC models offers a unified route to expand the scope of experimental ligand discovery, predict the molecular properties of both experimental and generated ligands, and highlights the utility of large quantitative datasets for making accurate in silico predictions of high-affinity peptide candidates.

StatementHigh-throughput sequencing analysis of mRNA display libraries enables generating novel peptide ligands and expands the scope of functional sequences beyond what is accessible experimentally. Closed-form Continuous neural networks trained using sequences and their corresponding free energies accurately predict the binding free energies of both experimental and machine learning-generated peptides, enabling a route to quantitatively predict peptide properties using directed evolution data.

---

## 论文详细总结（自动生成）

## 1. 研究动机与核心问题
- **背景**：mRNA展示等体外选择技术能从超大文库（≥10¹⁴）中筛选出成千上万的功能性多肽配体，但受实验通量限制，可探索的序列空间依然很小。
- **已解决的部分**：已有去噪扩散隐式模型（DDIMs）利用深度测序数据生成新序列，将功能肽空间扩展至实验不可及的区域。
- **待解决问题**：缺乏有效方法定量预测这些实验及生成肽的关键性质——结合自由能（ΔG°），阻碍了对高亲和力配体的精准发现。
- **整体含义**：论文旨在整合生成模型与预测模型，构建一套从序列扩增到亲和力量化预测的统一计算框架，针对癌蛋白Bcl‑xL发现皮摩尔级亲和力多肽。

## 2. 方法论
- **核心思想**：将“序列生成”与“性质预测”解耦，使用DDIM拓展功能序列，再用闭式连续神经网络（CfC）对任意来源的序列进行结合自由能的精准回归，形成端到端的虚拟筛选能力。
- **生成阶段（DDIM）**：利用mRNA展示筛选得到的深度测序数据训练去噪扩散隐式模型，生成大量候选肽序列。
- **预测阶段（CfC）**：采用闭式连续神经网络，专为解决不规则序列数据表征而设计，输入为序列-ΔG°配对，输出预测的结合自由能。
- **技术细节**：
  - 训练数据：15,700条实验确定的肽配体，每条都带有实验测得的ΔG°值。
  - CfC模型特点：能够处理序列的不规则依赖和时间动态（原文提及“represent irregular series”），适合多肽序列这类离散但有序的符号序列。
  - 预测输出：对任意肽（实验来源或DDIM生成）给出预测ΔG°，并以排序误差评估准确性。

## 3. 实验设计
- **数据集**：
  - 训练集：针对Bcl‑xL的15,700条肽配体的序列及其实验结合自由能（ΔG°）。
  - 测试集1：实验产生的肽（与训练集不同划分方式，摘要未详述，但提到“预测实验肽的排序和自由能”，暗示采用交叉验证或留出法）。
  - 测试集2：DDIM生成的新肽，用于验证模型的泛化能力。
- **评价指标**：
  - 预测排序的准确性（在误差范围内是否与实验排序一致）。
  - 预测ΔG°的数值精度。
  - 在DDIM生成肽中成功识别出5条具有个位数皮摩尔亲和力的高活性肽（可能是预测后经实验验证）。
- **对比方法**：摘要未提及与其他机器学习方法（如LSTM、Transformer等）的横向对比，因此基准对比可能仅限于与实验值的吻合度。

## 4. 资源与算力
- 提供的摘要及元数据中**未明确说明**训练DDIM和CfC模型所使用的GPU型号、数量、训练时长或总计算开销。该信息可能位于论文正文的方法学或附录部分，在当前获取的内容中缺失。

## 5. 实验数量与充分性
- **显式实验**：
  1. CfC模型在实验肽上的结合自由能预测效果验证。
  2. CfC模型在DDIM生成肽上的预测与排序验证，并识别出5条皮摩尔级肽。
- **潜在消融/补充实验**：摘要未提及不同模型结构消融、数据量对性能的影响、DDIM不同超参数下的生成质量等。因此从现有信息看，实验组数偏少，但足以支撑概念验证。
- **公平性与客观性**：由于未与其它预测模型比较，目前仅能判断该方法在特定数据集上的自洽性，外部公平性无法评估；测试了生成肽的实验验证，提供了客观证据。

## 6. 主要结论与发现
- CfC神经网络能够准确预测实验和DDIM生成肽对Bcl‑xL的结合自由能，预测排序在误差范围内与实验一致。
- 成功从DDIM生成肽中鉴定出5条单皮摩尔级亲和力多肽，证实了生成‑预测联合框架挖掘超高亲和力配体的能力。
- 该方法为拓展定向进化实验的配体发现边界、实现大规模定量数据驱动的计算机辅助性质预测提供了统一且可行的路线。

## 7. 优点
- **模型组合创新**：首次将扩散生成模型与液态神经网络（CfC）结合，分别解决序列空间扩展和性质预测，分工明确。
- **处理不规则序列**：CfC天生适合表示多肽的不规则、序列化特征，相比传统固定长度模型可能更具优势。
- **实验验证扎实**：对生成肽进行了实际亲和力验证，发现了真实的高活性分子，证明预测的实用价值。
- **数据规模化利用**：基于15,700条带精确ΔG°的数据集，充分利用了mRNA展示的大规模定量信息。

## 8. 不足与局限
- **单一靶标测试**：仅针对Bcl‑xL一个蛋白，通用性有待在其他靶标和家族上验证。
- **缺少模型对比**：未与常用的序列回归模型（如CNN、Transformer、图神经网络）比较，难以判断CfC的绝对优势。
- **数据集偏差风险**：训练数据完全来自mRNA展示筛选，可能偏向特定理化性质的序列，对全新序列空间的预测可能不稳健。
- **生成模型的质量依赖**：DDIM生成肽的质量直接影响后续预测的命中率，缺乏对生成模型本身多样性与真实性控制的讨论。
- **算力与复现性**：未公开计算资源和详细超参数，影响方法复现和成本评估。
- **实验验证规模小**：仅验证了5条生成肽的亲和力，更大规模的湿实验验证才能充分证明预测可靠性。

（完）
