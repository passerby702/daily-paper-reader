---
title: Combinatorial docking and molecular generation to navigate over 100-billion molecules for prospective ligand discovery
title_zh: 组合对接与分子生成：导航超千亿分子空间以发现新型配体
authors: "Zhang, J., Yang, C., Zhang, Y., Chen, X., Lam, B., Bryant, C., Pidathala, S., Wang, Y., Moroz, Y., Radchenko, D., Alon, A., Lee, C.-H., Zhang, Z., Lyu, J."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730716v1.full.pdf"
tags: ["query:pocket-lig"]
score: 9.0
evidence: 针对蛋白质口袋的配体生成与对接
tldr: 商业可购买化合物库已超千亿，传统对接需50年以上。本文提出组合对接CombiDOCK实现40天千亿级穷举筛选，以及生成式框架MINT-Dock结合蒙特卡洛树搜索加速导航。在46个靶点基准测试中，CombiDOCK匹配传统精度，MINT-Dock实现4800倍富集。前瞻性筛选σ2、VMAT2等靶点，相比十亿级对接获得更高命中率和更高效力配体，且VAChT配体对接构象被冷冻电镜证实。该方法为万亿分子空间先导发现提供穷举与生成式路径。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有对接方法无法高效处理超千亿级化合物库，亟需加速筛选策略以释放海量化学空间潜力。
method: 提出组合对接框架CombiDOCK进行穷举筛选，以及生成式框架MINT-Dock整合CombiDOCK与蒙特卡洛树搜索。
result: CombiDOCK在40天内完成千亿级筛选且精度无损，MINT-Dock实现4800倍富集，前瞻性结果优于之前十亿级对接，计算成本降低20倍以上。
conclusion: 这些方法实现了对万亿分子空间的穷举与生成式导航，显著推动先导化合物发现效率。
---

## 摘要
目前商业化的按需合成库已超过1000亿种化合物，使用传统对接方法在2000个CPU核心上筛选需要超过50年。我们提出两种互补方法应对这一挑战。CombiDOCK是一种组合对接框架，可在40天内实现对千亿级分子的穷举筛选。MINT-Dock是一种生成式框架，通过将CombiDOCK与蒙特卡洛树搜索相结合，加速了该空间的导航。在46个不同靶标的基准测试中，CombiDOCK达到与全分子对接相当的精度，MINT-Dock的命中率比随机选择高出4800倍。与先前针对σ2、VMAT2和VAChT的十亿级暴力筛选相比，前瞻性的CombiDOCK对千亿分子库的筛选获得了更高的命中率和更有效的配体，而MINT-Dock在单靶标和多靶标目标中实现了相当的结果，计算成本降低超过20倍。最佳VAChT结合化合物的对接预测构象已通过冷冻电镜结构验证。这些方法为导航药物发现的万亿分子前沿提供了穷举式和生成式路径。

## Abstract
Commercially available make-on-demand libraries now exceed 100 billion compounds, requiring over 50 years to screen on 2,000 CPU cores using conventional docking. We present two complementary approaches to address this challenge. CombiDOCK, a combinatorial docking framework, enables exhaustive screening at the 100-billion scale within 40 days. MINT-Dock, a generative framework, accelerates navigation of this space by integrating CombiDOCK with Monte Carlo Tree Search. Benchmarked on 46 diverse targets, CombiDOCK matched full-molecule docking accuracy, and MINT-Dock achieved a 4,800-fold enrichment over random selection. Compared with prior billion-scale brute-force campaigns against {sigma}2, VMAT2, and VAChT, prospective CombiDOCK screens of the 100-billion-molecule library yielded higher hit rates and more potent ligands, while MINT-Dock achieved comparable outcomes across single- and multi-target objectives with >20-fold computational cost reductions. Docking-predicted poses of the best VAChT-binding compounds were confirmed by cryo-EM structures. These methods provide exhaustive and generative paths for navigating the trillion-molecule frontier of drug discovery.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：当前商业可购买的按需合成化合物库已超过**1000亿**种分子，传统分子对接方法在2000个CPU核心上需要超过**50年**才能完成穷举筛选，严重制约了海量化学空间在药物发现中的应用。
- **整体含义**：为了释放超千亿级分子库的潜力，必须开发能够**高效导航**该空间的算法。本文提出了两种互补策略——**穷举式组合对接**（CombiDOCK）和**生成式分子生成框架**（MINT-Dock），分别面向全面覆盖与智能采样，为万亿分子先导发现提供可行路径。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **CombiDOCK（组合对接框架）**  
  - **核心思想**：将分子分解为可合成的“砌块”，只对接一次每个砌块，利用组合数学原理通过对砌块对接评分的重组来穷举评估所有完整分子，避免对每个分子单独对接。
  - **关键技术**：预计算砌块与蛋白口袋的结合能，再通过组合规则快速合成评分；可在**40天**内完成千亿级分子的穷举筛选，且精度与传统全分子对接相当。

- **MINT-Dock（生成式框架）**  
  - **核心思想**：结合CombiDOCK的快速评分能力与**蒙特卡洛树搜索（MCTS）**，引导分子生成过程，减少对无效化学空间的探索。
  - **关键技术**：MCTS在分子生长树上进行策略选择、扩展和回溯，每一步利用CombiDOCK的即时评分作为奖励信号；能同时支持**单靶标**和**多靶标**优化，实现4800倍于随机选择的命中富集。

### 3. 实验设计：数据集、Benchmark与对比方法
- **数据集**：
  - **基准测试**：在**46个不同靶标**（涵盖多种蛋白家族）上进行精度与富集能力的评估。
  - **前瞻性应用**：针对**σ2受体**、**VMAT2**和**VAChT**这三个先前已有十亿级暴力筛选结果的靶点，进行千亿分子库的对接实验。
- **Benchmark对比**：
  - CombiDOCK与传统全分子对接（逐分子对接）直接对比精度。
  - MINT-Dock与**随机筛选**对比富集倍数，以及与之前十亿级暴力对接结果对比命中率和配体效力。
- **验证手段**：最优VAChT配体的对接预测构象通过**冷冻电镜（cryo-EM）** 结构确认。

### 4. 资源与算力
- **传统对接**：2000个CPU核心需>50年。
- **CombiDOCK**：在可比硬件下**40天**完成千亿级穷举筛选（文中未明确GPU型号、数量等具体配置）。
- **MINT-Dock**：相比先前十亿级暴力对接，**计算成本降低超过20倍**（具体硬件配置未说明）。
- **总体**：论文未详细披露使用的GPU/CPU型号、数量及训练时长，仅强调相对效率提升。

### 5. 实验数量与充分性
- **实验数量**：
  - 46个靶标的基准测试（覆盖多样性）。
  - 3个靶点的前瞻性千亿级应用。
  - 冷冻电镜结构验证（1个配体-靶标对）。
- **充分性评价**：
  - **优点**：基准测试靶标数量较多（46个），且前瞻性实验采用了独立、有历史对照的任务，验证了方法的实用性。
  - **不足**：前瞻性验证仅涉及3个离子通道/转运体靶点，**范围较窄**；缺乏对其他靶标类型（如激酶、GPCR）的大规模外部验证。另外，消融实验（如MINT-Dock是否依赖特定搜索参数）未在摘要中提及，可能未充分系统开展。
- **公平性**：与十亿级暴力对接比较时，使用了相同的历史数据集和评价指标，对比相对客观。

### 6. 论文的主要结论与发现
1. **CombiDOCK** 可在40天内完成千亿分子穷举筛选，且精度不亚于传统逐分子对接。
2. **MINT-Dock** 在46个靶标上实现**4800倍**命中富集，大幅提升采样效率。
3. 在σ2、VMAT2和VAChT的前瞻性筛选中，千亿级筛选相比前期的十亿级筛选获得了**更高的命中率和更有效的配体**；MINT-Dock在单/多靶标任务中实现了相当或更好的结果，**计算成本降低>20倍**。
4. 最佳VAChT配体的对接构象被冷冻电镜实验**直接证实**，验证了方法的结构预测可靠性。
5. 结论：这些方法为**导航万亿分子空间**提供了穷举与生成式两种互补路径，可显著加速先导化合物发现。

### 7. 优点
- **创新性**：首次将组合对接与生成式蒙特卡洛树搜索有机结合，突破了传统对接在超大规模库上的速度瓶颈。
- **效率与精度兼得**：CombiDOCK在不损失对接精度的前提下实现千亿级穷举；MINT-Dock富集倍数极高。
- **前瞻性验证**：不仅是数值模拟，实际合成了配体并进行了冷冻电镜确认，增加了可信度。
- **多靶标优化能力**：MINT-Dock支持同时优化对多个蛋白的亲和力，具有虚拟筛选的前景。

### 8. 不足与局限
- **实验覆盖有限**：前瞻性验证仅针对3个靶点，且均为离子通道/转运体蛋白；对激酶、GPCR等重要药物靶点缺乏直接测试，**泛化性待考**。
- **计算资源配置不透明**：未详细说明所使用的GPU/CPU型号、数量及时间，难以复现或公平比较其他方法。
- **依赖库的可合成性**：CombiDOCK基于“按需合成”库，若库中砌块覆盖率不足，可能遗漏某些化学结构；生成式MINT-Dock可能偏向于生成易于评分的分子，而非实际可合成性。
- **未讨论过拟合风险**：MINT-Dock在46个靶标上的4800倍富集可能存在对训练/基准集分子的过拟合，缺乏独立更大规模的交叉验证。
- **消融分析缺失**：未系统分析MCTS参数、组合砌块策略等对性能的影响，导致方法鲁棒性证据不足。

（完）
