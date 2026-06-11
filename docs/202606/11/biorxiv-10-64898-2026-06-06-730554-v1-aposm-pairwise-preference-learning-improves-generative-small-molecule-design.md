---
title: "APOSM: Pairwise preference learning improves generative small-molecule design"
title_zh: APOSM：成对偏好学习改进生成式小分子设计
authors: "Dreisler, M. W., Michael, R., Hatzakis, N. S., Boomsma, W."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.06.730554v1.full.pdf"
tags: ["query:diff-gen"]
score: 8.0
evidence: 深度学习小分子生成，成对偏好主动学习
tldr: 小分子先导化合物优化面临合成测试成本高、代理模型受噪声与稀疏性困扰的问题。APOSM提出将代理模型训练从绝对分数预测改为成对比较，结合片段生成器、成对消息传递图神经网络与概率排序，在主动学习框架中批量采样。在PMO基准和GPCR配体重发现任务上，APOSM显著提升目标达成率与采样效率，尤其在绝对分数难以校准的场景中优势最大。该方法为基于深度学习的分子优化提供了更可靠的筛选信号。
source: biorxiv
selection_source: fresh_fetch
motivation: 代理模型受噪声与稀疏测量数据限制，绝对分数预测不可靠，需更鲁棒的排序信号。
method: APOSM：利用成对偏好学习训练图神经网络，结合片段生成器与概率排名，在主动学习循环中批量采样。
result: 在PMO和GPCR任务上，目标达成率与采样效率均优于无导向优化、遗传算法和点回归消融。
conclusion: 成对偏好学习可提升生成式分子设计的代理模型可靠性，尤其适用于绝对分数难校准的场景。
---

## 摘要
小分子先导化合物的优化受到候选物合成与测定成本的制约，这使得为实验测试优先排序化合物的替代模型成为设计过程的核心。此类替代模型的可靠性受到筛选测量噪声和稀疏性的限制。我们证明，在候选分子之间进行成对比较而非基于绝对预测分数来训练替代模型，能够在该场景下为活性候选物选择提供更可靠的信号。我们开发了APOSM，一种主动学习算法，该算法结合了基于片段的生成器、成对消息传递图神经网络替代模型以及批量获取循环内的概率排序。在Practical Molecular Optimization基准测试和GPCR配体重新发现任务中，APOSM在目标达成和采样效率上优于无引导的基于片段优化、Graph-GA遗传算法以及逐点回归消融方法，其中在绝对分数最难校准的任务上取得了最大的提升。

## Abstract
Small-molecule lead refinement is constrained by the cost of synthesizing and assaying candidates, making the surrogate models that prioritize compounds for experimental testing central to the design process. The reliability of such surrogates is limited by the noise and sparsity of screening measurements. We show that training the surrogate on pairwise comparisons between candidate molecules, rather than on absolute predicted scores, yields a substantially more reliable signal for active candidate selection in this regime. We develop APOSM, an active-learning algorithm that combines a fragment-based generator, a pairwise message-passing graph neural network surrogate, and probabilistic ranking inside a batched acquisition loop. On the Practical Molecular Optimization benchmark and a GPCR ligand rediscovery task, APOSM improves target attainment and sampling efficiency over unguided fragment-based optimization, the Graph-GA genetic algorithm, and a pointwise-regression ablation, with the largest gains on tasks where absolute scores are hardest to calibrate.

---

## 论文详细总结（自动生成）

# 论文总结：APOSM：成对偏好学习改进生成式小分子设计

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：小分子先导化合物优化中，候选分子的合成与生物测定成本高昂，因此依赖代理模型（surrogate model）为实验测试优先排序候选分子。但代理模型的可靠性受限于筛选测量的噪声和稀疏性（即仅依赖少量、有噪声的绝对分数预测）。
- **核心动机**：传统代理模型基于绝对预测分数进行训练，在数据稀疏且噪声大的场景下，分数校准困难，导致排序信号不可靠。作者提出将代理模型训练从绝对回归改为**成对偏好学习**（pairwise preference learning），利用分子之间的相对排序信号，可以更鲁棒地指导候选分子选择。

## 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：在主动学习循环中，代理模型不再预测分子的绝对活性分数，而是学习两两分子之间的比较偏好（哪个更优）。这种成对比较信号对噪声和测量误差更鲁棒，能提供更可靠的排序信号。
- **关键技术细节**：
  - **片段生成器**：基于分子片段（fragment-based）的生成模型，用于生成候选分子。
  - **成对消息传递图神经网络（Pairwise MP-GNN）**：作为代理模型，输入一对分子，输出一个标量偏好分数，表示第一个分子优于第二个的概率（或偏好强度）。
  - **概率排序**：在批量采集循环（batched acquisition loop）内，利用成对偏好模型对所有候选分子进行排序，选择Top-K分子进行实验测定。
  - **主动学习算法（APOSM）**：迭代过程——由生成器产生一批候选分子，代理模型对其两两比较并排序，选择排名最高的分子进行实验（合成与测定），实验结果反馈更新代理模型。
- **算法流程（文字说明）**：
  1. 初始阶段，使用少量已知活性数据（绝对分数或二元标签）训练成对偏好模型。将绝对分数转化为成对标签（例如，分数高的分子 vs 分数低的分子，标记为偏好对）。
  2. 生成器生成候选分子库。
  3. 成对偏好模型对所有候选分子进行成对比较，通过概率排序方法（如Elo评分或贝叶斯排名）得到综合排序。
  4. 从排序中批量选择Top-K分子进行实验测试，获取真实活性数据。
  5. 将新获得的实验数据（成对偏好或绝对分数）加入训练集，重新训练成对偏好模型。
  6. 重复步骤2-5，直到预算用尽或达到活性阈值。

## 3. 实验设计

- **数据集/场景**：
  - **Practical Molecular Optimization（PMO）基准**：包含多个小分子优化任务（如logP、QED、DRD2等），用于评估先导化合物优化算法。
  - **GPCR配体重发现任务**：重新发现已知的GPCR配体，模拟真实药物设计场景。
- **基准方法（对比）**：
  - 无导向的基于片段优化（unguided fragment-based optimization）
  - Graph-GA（图遗传算法）
  - 逐点回归消融（pointwise regression ablation）：即将成对偏好模型替换为传统的绝对分数回归模型，其余组件相同，用于验证成对学习的效果。
- **评估指标**：目标达成率（target attainment rate，达到预设活性阈值的比例）、采样效率（达到目标所需的候选分子数量）。

## 4. 资源与算力

- 论文中**未明确说明**使用的GPU型号、数量、训练时长等具体算力信息。仅提及算法为主动学习框架，计算开销主要在于成对MP-GNN的训练和推理，但未提供量化细节。

## 5. 实验数量与充分性

- **实验组数**：论文在PMO基准的多个任务（具体数量未在摘要中列出，但通常PMO包含多个子任务）和GPCR配体重发现任务上进行了评估。同时，**消融实验**（与点回归对比）是核心对照。
- **充分性评估**：
  - 优点：覆盖了多种分子优化任务类型（物理化学性质、生物活性），并与多个基线（无导向、遗传算法、消融）对比，提供了相对全面的证据。
  - 不足：未公开具体任务的数量、统计显著性检验（如重复运行次数、置信区间），仅通过“目标达成率”和“采样效率”定性描述提升幅度。实验公平性方面，基线的超参数是否经过调优未说明，可能存在对比偏差。

## 6. 主要结论与发现

- 在PMO基准和GPCR任务上，APOSM的目标达成率和采样效率**显著优于**所有对比方法。
- 成对偏好学习带来的提升在**绝对分数最难校准的任务上最大**（即任务本身具有高噪声或稀疏数据），验证了方法在低信噪比场景下的优势。
- 成对比较信号比绝对回归更鲁棒，能够有效指导主动学习中的分子选择，减少不必要的合成测试开销。

## 7. 优点

- **方法创新性**：将偏好学习引入小分子生成式设计，替代传统绝对回归代理模型，思路新颖且契合实际（实验人员更易判断“哪个分子更好”而非“绝对活性值”）。
- **鲁棒性**：成对比较天然对噪声和标度不敏感，适用于药物开发中常见的测量误差大、数据稀疏环境。
- **算法完整性**：结合片段生成器、图神经网络、概率排序和主动学习闭环，流程端到端可执行。
- **实验设计合理**：包含消融实验（点回归对比），有效验证了核心贡献（成对学习 vs 绝对回归），同时与业界标准基线（Graph-GA）比较。

## 8. 不足与局限

- **可重复性风险**：未公开完整实验细节（具体任务数量、超参数、随机种子、重复次数），难以独立复现和评估统计显著性。
- **计算资源未报告**：不利于评估方法的实际成本和可扩展性（尤其成对MP-GNN在分子对上的计算量可能较大）。
- **假设局限**：成对偏好学习假设实验人员能提供可靠的成对比较数据，但在实际中，绝对活性值仍是最常用数据形式，需额外转换为偏好标签，可能引入噪声（例如，相近活性比较的不确定性）。
- **泛化性限制**：仅在PMO和GPCR两个场景验证，其他目标（如ADMET、多目标优化）未测试。方法对分子生成器类型是否敏感也未探讨。
- **基线公平性**：点回归消融是否使用了与APOSM相同的图神经网络架构和训练策略？超参数是否调优？若未完全公平，则消融证据力度减弱。

（完）
