---
title: Scaling SMILES-Based Chemical Language Models for Therapeutic Peptide Engineering
title_zh: 基于SMILES的治疗性肽工程化学语言模型的扩展
authors: "Feller, A. L., Secor, M., Swanson, S., Wilke, C. O., Deibler, K."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.06.697994v5.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 基于SMILES的化学语言模型用于治疗性肽生成
tldr: 治疗性肽兼具蛋白质特异性和小分子化学多样性，但现有蛋白模型受限于天然氨基酸，化学模型难以处理聚合物样序列。本文提出PeptideCLM-2，基于SMILES的化学语言模型，在超1亿分子上训练，原生表示复杂肽化学。基准测试表明在预测膜扩散、生物功能和半衰期等开发终点上优于先前方法。该工作填补了计算盲区，为治疗性肽工程提供了高效通用工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有蛋白和化学模型均无法有效处理治疗性肽序列，导致依赖静态描述符或定制化多嵌入流程，缺乏通用高效的计算方法。
method: 提出PeptideCLM-2，基于SMILES的化学语言模型，在超1亿分子上训练，原生表示复杂肽化学结构。
result: 在膜扩散、生物功能和半衰期等开发终点预测上，PeptideCLM-2显著优于先前方法。
conclusion: PeptideCLM-2桥接了蛋白与化学模型在治疗性肽上的盲区，为肽工程提供了可扩展的通用建模方案。
---

## 摘要
治疗性肽在药物发现中占据独特的中间地带，兼具蛋白质相互作用的高特异性和小分子的化学多样性，但当前它们处于计算盲区。现有基础模型无法有效处理它们：蛋白质模型局限于天然氨基酸，而化学模型难以处理大的类聚合物序列。这种脱节迫使该领域依赖静态化学描述符（无法捕捉细微化学细节）或针对特定数据集定制的复杂多嵌入流程。为弥合这一差距，我们提出了PeptideCLM-2，一套在超过1亿个分子上训练的化学语言模型，能够原生表征复杂的肽化学。这种建模方法扩展了用于治疗性肽的机器学习模型工具箱。基准测试结果显示，与先前方法相比，在预测开发终点（包括膜扩散、生物功能和半衰期）方面表现强劲。

## Abstract
Therapeutic peptides occupy a unique middle ground in drug discovery, offering the high specificity of protein interactions with the chemical diversity of small molecules, yet they currently fall in a computational blind spot. Existing foundation models cannot handle them effectively: protein models are restricted to natural amino acids, while chemical models struggle to process large, polymer-like sequences. This disconnect has forced the field to rely on static chemical descriptors that fail to capture subtle chemical details or on complex multi-embedding pipelines that are custom tailored to specific datasets. To bridge this gap, we present PeptideCLM-2, a suite of chemical language models trained on over 100 million molecules to natively represent complex peptide chemistry. This modeling approach expands the available toolkit of machine learning models for therapeutic peptides. Benchmarking results show strong performance versus prior methods for predicting development endpoints including membrane diffusion, biological function, and half life.