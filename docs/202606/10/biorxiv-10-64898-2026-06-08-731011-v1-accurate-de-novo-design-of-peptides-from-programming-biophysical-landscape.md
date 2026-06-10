---
title: Accurate de novo design of peptides from programming biophysical landscape
title_zh: 通过编程生物物理景观实现肽的精确从头设计
authors: "Li, M., Liu, Y., Zhong, J., Shi, X., Zheng, J., Wang, K., Cui, Y., Cheng, C., Li, S., Kong, X., Xv, M., Zhu, C., Lan, X., Yang, H., Chang, K., An, Z., Wan, S., Yang, X., Shen, Q., Xu, H. E., Wang, Z., Liu, L., Zhuang, Y., Ma, J., Zhang, J."
date: 2026-06-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.731011v1.full.pdf"
tags: ["query:diff-gen"]
score: 8.0
evidence: 使用生成式深度学习从头设计肽类
tldr: "多肽设计因生物物理建模难和数据稀缺而面临挑战。NeoPep生成式深度学习框架整合500万+肽-蛋白复合物，学习生物物理景观实现精确从头设计。在10个靶标上命中率达12.5-66.7%，结构再设计达到原子级精度，效力提升43.3倍。该框架将生物物理原则转化为可编程多肽功能，为生物工程和医学提供通用平台。"
source: biorxiv
selection_source: fresh_fetch
motivation: 从头设计功能多肽因生物物理建模困难和数据稀缺而极具挑战，现有方法难以精准编程肽-蛋白相互作用。
method: 提出NeoPep框架，整合实验、模拟和结构集合数据，学习肽功能生物物理景观，支持从头协同设计及结构或序列再设计。
result: "在10个靶标上生成有效多肽，命中率12.5-66.7%；结构再设计获得原子级精度（Cα RMSD<2.0Å），效力提升43.3倍。"
conclusion: NeoPep建立通用框架，将生物物理原理转化为精确多肽功能，有望推动基础研究、生物工程和医学应用。
---

## 摘要
肽几乎调控每一个细胞过程，并作为生物工程和治疗学中的变革性模态出现。然而，功能性肽的从头设计仍然具有挑战性，因为肽-蛋白质相互作用受微妙且动态的生物物理学支配，难以建模，且实验数据集稀少。这里我们提出NeoPep，一个生成式深度学习框架，它编码生物物理原理以精确从头设计功能性肽。通过整合跨越实验测定、序列模拟和结构集合的超过500万个肽-蛋白质复合物，NeoPep学习控制肽功能的复杂生物物理景观，并实现其可编程控制。在针对10个多样且具有挑战性靶点的前瞻性应用中，NeoPep生成了有效的肽结合物、激动剂和拮抗剂，命中率为12.5-66.7%，即使在缺乏明确结合位点或结构信息的情况下。除了从头共设计，NeoPep支持独立的结构或序列再设计，轻松区分微妙的上下文差异。在结构再设计模式下，它生成具有原子级构象精度（Cα RMSD < 2.0 Å，与我们解析的冷冻电镜结构相比）的高选择性肽。这种结构精度避免了实验结构测定的需要，进一步加速迭代序列再设计，从而产生效力43.3倍的提升。这些发现建立了一个将生物物理原理转化为可行肽功能的通用框架，对基础研究、生物工程和医学具有广泛意义。

## Abstract
Peptides regulate virtually every cellular process and emerge as transformative modalities in bioengineering and therapeutics. However, the de novo design of functional peptides remains challenging, as peptide--protein interactions are governed by delicate and dynamic biophysics that are difficult to model, and experimental datasets are scarce. Here we present NeoPep, a generative deep-learning framework that encodes biophysical principles to accurately design functional peptides de novo. By integrating over 5 million peptide--protein complexes spanning experimentally determined, sequence mimics, and structure ensembles, NeoPep learns the complex biophysical landscape governing peptide function and enables its programmable control. In prospective application across 10 diverse and challenging targets, NeoPep generated potent peptide binders, agonists, and antagonists with hit rates of 12.5--66.7%, even in the absence of defined binding sites or structure information. Beyond de novo co-design, NeoPep supports standalone structure or sequence redesign, readily discriminating subtle context differences. In the structure redesign mode, it generates highly selective peptides with atomic-level conformational accuracy (C RMSD < 2.0 [A] to our solved cryo-EM structure). This structural precision circumvents the need for experimental structure determination, further accelerating iterative sequence redesign to yield a 43.3-fold improvement in potency. These findings establish a general framework for translating biophysical principles into actionable peptide functions, with broad implications for basic research, bioengineering, and medicine.

---

## 论文详细总结（自动生成）

# 论文总结：NeoPep——通过编程生物物理景观实现肽的精确从头设计

## 1. 论文的核心问题与整体含义
- **研究动机**：肽几乎调控所有细胞过程，是生物工程和治疗的变革性分子。但从头设计功能性肽极其困难，因为肽-蛋白质相互作用受微妙且动态的生物物理规律支配，难以建模，且实验数据集非常稀缺。
- **整体含义**：作者提出NeoPep生成式深度学习框架，旨在将生物物理原理转化为可编程的肽功能，为肽类药物的精确设计提供通用平台，有望推动基础研究、生物工程和医学应用。

## 2. 论文提出的方法论
- **核心思想**：通过整合大规模、多样化的肽-蛋白质复合物数据（实验测定、序列模拟、结构集合），学习控制肽功能的复杂生物物理景观，实现肽的精确从头设计。
- **关键技术细节**：
  - 数据整合：超过500万个肽-蛋白质复合物，涵盖实验确定、序列模拟和结构集合三类数据。
  - 生成式深度学习：NeoPep框架能够学习肽功能的生物物理景观，并支持三种设计模式：
    1. **从头协同设计**：同时设计序列和结构。
    2. **独立结构再设计**：固定序列优化结构。
    3. **独立序列再设计**：固定结构优化序列。
  - 模型能够区分细微的上下文差异（如结合位点微环境），生成高选择性肽。
- **算法流程**（文字说明）：
  - 输入：目标蛋白结构或序列信息（可选结合位点信息）。
  - 过程：NeoPep利用学习到的生物物理景观，通过生成模型输出符合功能要求的肽序列和/或结构。
  - 输出：候选肽序列和预测的三维构象。

## 3. 实验设计
- **数据集/场景**：
  - 训练数据：超过500万个肽-蛋白质复合物（实验+模拟+结构集合）。
  - 测试场景：针对10个多样且具有挑战性的靶标，包括缺乏明确结合位点或结构信息的靶点。
- **Benchmark**：未明确提及标准基准数据集，而是使用前瞻性应用（prospective application）验证。
- **对比方法**：摘要中未明确列出对比方法，但强调NeoPep在缺乏结构信息时仍能设计有效肽，暗示其优于依赖结构的方法。

## 4. 资源与算力
- **文中未明确说明**：未提及GPU型号、数量、训练时长等算力信息。仅指出整合了超过500万个复合物数据，但未给出具体训练资源消耗。

## 5. 实验数量与充分性
- **实验数量**：
  - 前瞻性应用：10个不同靶标（涵盖结合物、激动剂、拮抗剂）。
  - 命中率范围：12.5%–66.7%。
  - 结构再设计：针对某一靶标获得冷冻电镜结构验证，Cα RMSD < 2.0 Å。
  - 迭代序列再设计：效力提升43.3倍。
- **充分性与客观性**：
  - 覆盖了多种功能类型（结合、激动、拮抗）和不同靶标，具有一定广度。
  - 有结构验证（冷冻电镜）和效力提升数据，可信度较高。
  - 但未提供消融实验（如不同数据整合策略的影响）、与现有深度学习方法的定量对比，实验充分性略显不足。缺乏标准基准评估，可能引入选择偏差。

## 6. 论文的主要结论与发现
- NeoPep能够从头设计功能性肽，即使在缺乏结合位点或结构信息的靶标上，命中率仍达12.5–66.7%。
- 支持结构或序列的独立再设计，能够区分细微上下文差异，生成高选择性肽。
- 结构再设计生成的肽具有原子级构象精度（与冷冻电镜结构比较Cα RMSD < 2.0 Å），避免了实验结构测定的需要。
- 基于结构精度的迭代序列再设计可使效力提升43.3倍。
- 结论：NeoPep建立了将生物物理原理转化为可行肽功能的通用框架，对基础研究、生物工程和医学有广泛意义。

## 7. 优点
- **数据丰富性**：整合超过500万个多源复合物数据（实验+模拟+集合），有效缓解数据稀缺问题。
- **设计灵活性**：支持从头协同设计、结构再设计、序列再设计三种模式，适应不同应用场景。
- **高命中率**：在10个挑战性靶标上达到12.5–66.7%命中率，展示出实用性。
- **结构精度**：原子级构象精度（Cα RMSD < 2.0 Å）验证了模型的物理合理性。
- **效力提升**：迭代设计实现43.3倍效力提升，证明其优化能力。
- **无需预知结合位点**：部分靶标无明确结合位点仍能设计成功，拓宽了适用性。

## 8. 不足与局限
- **实验覆盖有限**：仅测试了10个靶标，且未涵盖所有肽功能类型（如酶抑制、信号调节等），泛化性待验证。
- **缺乏标准基准对比**：未与现有主流方法（如AlphaFold2-based peptide design、RFdiffusion等）进行定量比较，难以客观评估相对优势。
- **消融实验缺失**：未分析数据来源（实验/模拟/集合）各自贡献，也未探讨不同模型组件的影响。
- **算力信息缺失**：无法评估方法的训练成本与可复现性。
- **命中率波动大**：12.5–66.7%的范围跨度大，部分靶标命中率偏低，可能存在靶标依赖性。
- **仅摘要信息**：由于原始论文访问受限（403错误），无法获取完整方法细节、算法架构、损失函数等，可能遗漏重要技术限制。

（完）
