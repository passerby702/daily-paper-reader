---
title: "The Dayhoff Atlas: scaling sequence diversity for improved protein generation"
title_zh: Dayhoff图谱：扩展序列多样性以改进蛋白质生成
authors: "Yang, K. K., Alamdari, S., Lee, A., Kaymak-Loveless, K., Char, S., Brixi, G., Domingo-Enrich, C., Wang, C., Lyu, S., Fusi, N., Tenenholtz, N., Amini, A. P."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.1101/2025.07.21.665991v2.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 蛋白质序列生成深度模型与数据集
tldr: 蛋白质序列数据的组织是计算生物学的基础，但现有数据规模和多样性不足。Dayhoff Atlas整合了包含34亿天然序列的GigaRef和4600万从设计骨架预测的合成序列BackboneRef，并训练了融合单序列与进化相关序列的Dayhoff蛋白语言模型。该模型能预测突变效应、引导结构基序生成，且使用这些数据显著提高了生成蛋白的细胞表达率。作为开源资源，Dayhoff Atlas为蛋白质设计与生成提供了前所未有的数据多样性和模型能力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-07-21-665991-v2/fig-001.webp\", \"caption\": \"\", \"page\": 57, \"index\": 1, \"width\": 485, \"height\": 459}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-07-21-665991-v2/fig-002.webp\", \"caption\": \"\", \"page\": 58, \"index\": 2, \"width\": 485, \"height\": 308}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-07-21-665991-v2/fig-003.webp\", \"caption\": \"\", \"page\": 58, \"index\": 3, \"width\": 485, \"height\": 308}]"
motivation: 现有蛋白质生成模型受限于序列数据的规模和多样性，亟需更丰富的数据源以提升生成蛋白的质量和功能性。
method: 整合元基因组与UniRef100构建GigaRef（34亿序列），从24万个设计骨架生成BackboneRef（4600万合成序列），训练融合单序列与进化序列的Dayhoff模型家族。
result: Dayhoff模型可预测突变效应、支架结构基序，并引导家族内新蛋白生成；使用GigaRef和BackboneRef数据使生成蛋白的细胞表达率显著提高。
conclusion: 扩展蛋白质序列数据的规模、多样性与新颖性可提升生成蛋白的实用性能，Dayhoff Atlas的开源发布将推动蛋白质生物学与设计的发展。
---

## 摘要
现代生物学依赖于生物信息的组织，这一框架由Margaret Dayhoff于1965年在其《蛋白质序列与结构图谱》中开创。源自这一共同祖先的数据库支撑着计算方法，这些方法彻底改变了我们理解和设计蛋白质的能力。我们引入了Dayhoff图谱，这是一个集中收集蛋白质序列数据和生成式蛋白质语言模型的资源，作为人工智能时代蛋白质生物学的现代资源。我们将宏基因组序列与UniRef100结合并重新聚类，创建了GigaRef，包含33.4亿条蛋白质序列，分布于17亿个簇中，是迄今为止最大的天然蛋白质开放数据集。为了融合蛋白质结构的丰富性与序列空间的可扩展性，我们生成了基于结构的合成数据，产生了BackboneRef，这是一个首类数据集，包含从240,811个从头设计的骨架预测出的4600万条合成蛋白质序列。利用这些数据和进化序列比对，我们训练了Dayhoff系列蛋白质语言模型，包括首个大规模结合单一蛋白质和进化相关序列集合的模型。仅在氨基酸序列空间中运行，Dayhoff模型能够自然预测突变对适应度的影响、支撑结构基序，并指导特定家族内新蛋白质的生成。从Dayhoff图谱的宏基因组和基于结构的合成数据中学习，提高了生成蛋白质的细胞表达率，突显了扩展蛋白质序列数据规模、多样性和新颖性的实际价值。我们以宽松许可协议发布Dayhoff图谱，包括所有数据集、代码和模型，以继续将计算的力量应用于蛋白质生物学与设计。

## Abstract
Modern biology is powered by the organization of biological information, a framework pioneered in 1965 by Margaret Dayhoff's Atlas of Protein Sequence and Structure. Databases descended from this common ancestor power computational methods that have revolutionized our ability to understand and design proteins. We introduce the Dayhoff Atlas, a centralized collection of both protein sequence data and generative protein language models, as a modern-day resource for protein biology in the age of AI. We combined and reclustered metagenomic sequences with UniRef100 to create GigaRef, which includes 3.34 billion protein sequences across 1.70 billion clusters and provides the largest open dataset of natural proteins to date. To fuse the richness of protein structure with the scalability of sequence space, we generated structure-based synthetic data, producing BackboneRef, a first-in-class dataset of 46 million synthetic protein sequences predicted from 240,811 de novo designed backbones. Using these data and evolutionary sequence alignments, we trained the Dayhoff family of protein language models, including the first model that combines single proteins and sets of evolutionarily-related sequences at scale. Operating only in amino acid sequence space, the Dayhoff models can natively predict mutation effects on fitness, scaffold structural motifs, and perform guided generation of new proteins within a specific family. Learning from metagenomic and structure-based synthetic data from the Dayhoff Atlas increased the cellular expression rates of generated proteins, highlighting the real-world value of expanding the scale, diversity, and novelty of protein sequence data. We release the Dayhoff Atlas, including all datasets, code, and models, under a permissive license to continue to bring the power of computation to protein biology and design.