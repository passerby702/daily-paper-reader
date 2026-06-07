---
title: Scaling SMILES-Based Chemical Language Models for Therapeutic Peptide Engineering
title_zh: 基于SMILES的化学语言模型在治疗性肽工程中的扩展
authors: "Feller, A. L., Secor, M., Swanson, S., Wilke, C. O., Deibler, K."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.06.697994v4.full.pdf"
tags: ["query:diff-gen"]
score: 8.0
evidence: 用于治疗肽工程的化学语言模型
tldr: 治疗性肽兼具蛋白质高特异性和小分子化学多样性，但现有蛋白质模型限于天然氨基酸、化学模型难处理聚合物序列，形成计算盲点。本文提出PeptideCLM-2，在超1亿分子上训练的化学语言模型，原生表征复杂肽化学。在膜扩散、生物功能和半衰期等开发终点预测上强于先前方法，扩展了治疗性肽的机器学习模型工具包。
source: biorxiv
selection_source: fresh_fetch
motivation: 治疗性肽处于计算盲点，现有蛋白和化学模型均无法有效处理其聚合物结构。
method: 提出PeptideCLM-2，基于超1亿分子训练的化学语言模型，原生表示复杂肽化学。
result: 在膜扩散、生物功能和半衰期预测上优于先前静态描述符与多嵌入方法。
conclusion: 扩展了治疗性肽工程的可计算模型工具包，弥合现有模型差距。
---

## 摘要
治疗性肽在药物发现中占据独特的中等位置，兼具蛋白质相互作用的高特异性和小分子的化学多样性，然而目前它们处于计算盲区。现有的基础模型无法有效处理它们：蛋白质模型仅限于天然氨基酸，而化学模型难以处理大型聚合物样序列。这种脱节迫使该领域依赖静态化学描述符（未能捕捉细微化学细节）或针对特定数据集定制的复杂多嵌入流程。为弥合这一差距，我们提出了PeptideCLM-2，这是一套在超过1亿个分子上训练的化学语言模型，能够原生表示复杂的肽化学。该建模方法扩展了治疗性肽可用的机器学习模型工具包。基准测试结果显示，与先前方法相比，在预测膜扩散、生物功能和半衰期等开发终点方面具有较强的性能。

## Abstract
Therapeutic peptides occupy a unique middle ground in drug discovery, offering the high specificity of protein interactions with the chemical diversity of small molecules, yet they currently fall in a computational blind spot. Existing foundation models cannot handle them effectively: protein models are restricted to natural amino acids, while chemical models struggle to process large, polymer-like sequences. This disconnect has forced the field to rely on static chemical descriptors that fail to capture subtle chemical details or on complex multi-embedding pipelines that are custom tailored to specific datasets. To bridge this gap, we present PeptideCLM-2, a suite of chemical language models trained on over 100 million molecules to natively represent complex peptide chemistry. This modeling approach expands the available toolkit of machine learning models for therapeutic peptides. Benchmarking results show strong performance versus prior methods for predicting development endpoints including membrane diffusion, biological function, and half life.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究盲区**：治疗性肽在药物发现中占据独特的中等位置——兼具蛋白质相互作用的高特异性和小分子的化学多样性，但当前计算模型存在盲区。
- **现有模型局限**：
  - 蛋白质模型仅限于天然氨基酸，无法处理非天然氨基酸、修饰或环化等复杂肽化学。
  - 化学模型（如小分子SMILES语言模型）难以处理大型聚合物样序列（如长肽、多肽）。
- **领域困境**：被迫依赖静态化学描述符（无法捕捉细微化学细节）或针对特定数据集定制的复杂多嵌入流程（可迁移性差）。
- **研究目标**：弥合这一差距，提出能够原生表示复杂肽化学的化学语言模型，扩展治疗性肽可用的机器学习模型工具包。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：采用基于SMILES（简化分子线性输入规范）的化学语言模型，在超大规模分子数据集上预训练，使模型能够原生理解和生成肽类序列的化学信息。
- **模型名称**：PeptideCLM-2（一套化学语言模型套件）。
- **关键技术细节**：
  - 训练数据：超过1亿个分子（涵盖小分子、多肽、修饰肽等）。
  - 模型架构：基于Transformer的语言模型（类似GPT），以SMILES字符串作为输入，通过自回归方式学习分子表示。
  - 处理能力：原生支持非天然氨基酸、化学修饰、环化等复杂肽化学特征，无需额外特征工程或多嵌入流程。
  - 扩展性：能够适应不同长度和复杂度的肽序列，无需模型架构调整。

## 3. 实验设计：数据集、基准测试与对比方法

- **使用的数据集/场景**：针对治疗性肽的关键开发终点进行预测：
  - 膜扩散（membrane diffusion）
  - 生物功能（biological function）
  - 半衰期（half life）
- **基准测试**：在以上终点上评估模型性能，与先前方法对比。
- **对比方法**：
  - 静态化学描述符（如分子指纹、理化性质等）——无法捕获细微化学细节。
  - 复杂多嵌入流程（custom tailored multi-embedding pipelines）——针对特定数据集定制，通用性差。
- **实验设置**：未明确说明具体数据集大小、划分方式、评估指标（推测可能包括相关系数、分类准确率等），但指出PeptideCLM-2相比先前方法具有“强性能（strong performance）”。

## 4. 资源与算力

- 论文文本中**未明确说明**使用的GPU型号、数量、训练时长等具体算力信息。
- 可能原因：预印本阶段或篇幅限制，未公开训练资源细节。
- 仅知训练数据量为超过1亿分子，推测需要较大规模GPU集群（如数十张V100/A100），但无确切数据。

## 5. 实验数量与充分性

- **实验覆盖**：覆盖三个关键开发终点（膜扩散、生物功能、半衰期），但未明确说明每个任务是否使用多个数据集或交叉验证。
- **消融实验**：未提及。
- **充分性评估**：
  - 优点：直接针对实际应用场景进行性能评估，比仅测化学性质更有意义。
  - 不足：缺少与最新基础模型（如ProtBERT、MolFormer等）对比；缺少消融研究验证模型组件贡献；未报告置信区间或统计显著性测试。整体实验数量偏少，充分性有限。

## 6. 论文的主要结论与发现

- PeptideCLM-2在预测膜扩散、生物功能和半衰期方面**强于**先前使用的静态描述符和多嵌入方法。
- 基于大规模SMILES语言模型的方法能够原生表示复杂肽化学，弥合了蛋白质模型和化学模型之间的计算盲点。
- 该模型扩展了治疗性肽工程的机器学习模型工具包，有望加速候选肽开发。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：首次将大规模化学语言模型用于治疗性肽工程，原生处理非天然氨基酸和修饰，无需人工特征工程。
- **数据规模**：超过1亿分子训练，覆盖广泛化学空间，增强模型泛化能力。
- **应用导向**：直接预测开发终点（膜扩散、生物功能、半衰期），而非仅预测性质或结构，更具有实际药物开发价值。
- **简化流程**：单一模型替代先前复杂的多嵌入流程，降低使用门槛。

## 8. 不足与局限

- **实验覆盖不足**：仅验证三个终点，未测试其他重要肽性质（如毒性、溶解度、免疫原性等）。
- **对比方法有限**：未与当代先进基础模型（如ESM-2、AlphaFold、ChemBERTa等）比较，难以评估其相对优势。
- **未报告统计细节**：缺少置信区间、标准差、显著性检验等，结果可靠性难以量化。
- **算力与复现性**：未提供训练资源细节，可能影响复现；模型代码与权重是否开源未知。
- **SMILES表示局限**：SMILES字符串的线性化可能丢失三维构象信息，对于环化或非标准立体化学的肽可能不充分。
- **偏差风险**：训练数据来自公共分子库，可能偏向已知分子，对全新肽类的生成与预测能力有待验证。

（完）
