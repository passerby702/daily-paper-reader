---
title: Bayesian-Steered Structure Prediction of Mechanical Biomolecules Using Twisted Diffusion
title_zh: 使用扭曲扩散的贝叶斯导向机械生物分子结构预测
authors: "Klaus, C., Sotomayor, M."
date: 2026-05-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724187v1.full.pdf"
tags: ["query:diff-gen"]
score: 9.0
evidence: 使用扭曲扩散进行分子构象生成
tldr: 基于深度学习的蛋白质结构预测工具主要复现实验观测构象，但许多功能相关、实验上代表性不足的非平衡构象难以获取。本文在Boltz-2框架中提出扭曲扩散采样器，利用任意贝叶斯似然对扩散模型进行条件引导，无需额外训练神经网络。成功预测了DNA片段、肌联蛋白和原钙粘蛋白-15等机械生物分子的拉伸状态，以及MscL离子通道的开放构象，结果与实验一致。该方法实现了类似受控分子动力学的扩散模拟，为探索稀有构象提供了有力工具，拓展了结构预测的应用范围。
source: biorxiv
selection_source: fresh_fetch
motivation: 蛋白质结构预测需探索实验中代表性不足的功能构象，但现有工具偏向已知状态，无法有效采样非平衡态。
method: 在Boltz-2中实现扭曲扩散采样，使用任意贝叶斯似然条件化扩散模型，无需重新训练网络。
result: 验证了DNA、肌联蛋白、原钙粘蛋白-15和MscL系统，预测的拉伸和开放构象与实验吻合。
conclusion: 该方法模拟受控分子动力学，为采样非平衡和稀有构象提供新途径，可推广至多种生物大分子。
---

## 摘要
深度学习方法已经彻底改变了蛋白质结构预测。这些工具利用实验数据进行训练，能够重现已报道的构象，但人们对于预测那些可能在功能上相关但在实验中代表性不足的构象抱有浓厚兴趣。由于许多现代结构预测工具使用生成式人工智能扩散模型，我们重新将寻找替代分子构象的问题表述为从以任意贝叶斯似然为条件的扩散分布中进行采样。我们在 Boltz-2 中实现了一个扭曲扩散采样器，以对该条件分布进行采样，并通过在机械系统上实现类似于引导分子动力学模拟的扩散模拟，展示了该方法的实用性，此方法无需对神经网络进行任何额外训练。我们能够重现 DNA 片段、肌肉蛋白肌联蛋白和内耳原钙粘蛋白-15 蛋白的预测拉伸状态，以及与实验结果一致的 MscL 离子通道开放状态。我们期望，导向式结构预测将有助于为许多大分子系统采样那些代表性不足和非平衡构象。

## Abstract
Deep learning approaches have revolutionized protein structure prediction. These tools are trained using experimental data and recapitulate reported conformations, but there is great interest in predicting conformations that may be functionally relevant although experimentally underrepresented. Since many modern structure prediction tools use generative artificial intelligence diffusion models, we reframe the search for alternative molecular conformations as that of sampling from a diffusion distribution conditioned using any arbitrary Bayesian likelihood. We implement a twisted diffusion sampler in Boltz-2 to sample this conditioned distribution and demonstrate the utility of this approach, which does not require any additional training of the neural network, by implementing a diffusion analog of steered molecular dynamics simulations applied to mechanical systems. We can reproduce predicted stretched states of fragments of DNA, the muscle protein titin, and the inner-ear protocadherin-15 protein, as well as open states of the MscL ion channel consistent with experimental results. We expect that steered structure predictions will help sample underrepresented and non-equilibrium conformations for many macromolecular systems.

---

## 论文详细总结（自动生成）

# 论文总结：Bayesian-Steered Structure Prediction of Mechanical Biomolecules Using Twisted Diffusion

## 1. 论文的核心问题与整体含义
- **核心问题**：当前基于深度学习的蛋白质结构预测工具（如AlphaFold、Boltz等）虽能高精度复现实验已有构象，但大量功能相关、却在实验数据集中代表性不足的非平衡构象（如机械拉伸态、离子通道开放态）仍难以获取。如何让扩散模型从条件分布中采样出这类稀有构象，而不重新训练庞大的神经网络，是一个关键挑战。
- **整体含义**：作者将“寻找替代分子构象”重新定义为以任意贝叶斯似然为条件的扩散分布采样问题，通过在 Boltz-2 框架内实现扭曲扩散（twisted diffusion）采样器，实现了类似“受控分子动力学（steered MD）”的扩散模拟，无需额外训练。这为机械生物分子及其他系统的非平衡、稀少构象预测提供了通用工具，极大拓宽了结构预测的应用边界。

## 2. 论文提出的方法论
- **核心思想**：利用贝叶斯后验分解，把扩散模型的条件生成视为从先验扩散分布上施加以似然函数为扭曲项（twist）的采样过程。给定一个预训练好的去噪扩散模型，可以在其逆扩散每一步中，借助外部定义的任意贝叶斯似然（例如距离约束、力谱信息）来引导采样轨迹，而不需要重新训练神经网络。
- **关键技术细节**：
  - **扭曲扩散采样**（Twisted Diffusion Sampler）：在标准扩散去噪过程中，每一步利用当前估计的干净坐标计算似然梯度，以此施加“扭曲”校正，逐步将样本推向满足条件的高概率区域。
  - **贝叶斯似然条件**：似然函数可任意定义，例如用于拉伸的端到端距离约束、通道孔径残基距离约束等。该框架使扩散模型成为受控分子动力学的类比，但完全在扩散隐空间中实现。
  - **与 Boltz-2 集成**：算法嵌入到结构预测模型 Boltz-2 中，利用其预训练权重，通过改装采样流程实现条件生成，无需对扩散网络做任何微调或重新训练。
- **公式或算法流程**（文字概述）：
  1. 初始化：从纯噪声出发。
  2. 对于扩散过程的每一步 \(t\)：
     a. 使用预训练去噪网络预测干净结构 \(\hat{x}_0\)。
     b. 计算似然函数 \(p(y|x)\) 对当前 \(\hat{x}_0\) 的梯度（此处 \(y\) 代表期望的结构特征，如距离约束）。
     c. 将该梯度以“扭曲”形式融入逆扩散更新方程，得到修正后的下一步更干净的样本。
  3. 重复直到 \(t=0\)，输出满足条件的分子构象。

## 3. 实验设计
- **数据集 / 场景**：机械生物分子系统，包括：
  - DNA 片段（验证拉伸状态）
  - 肌肉蛋白肌联蛋白（titin，验证拉伸构象）
  - 内耳原钙粘蛋白-15（protocadherin-15，验证拉伸构象）
  - MscL 离子通道（验证开放构象）
- **Benchmark 与对比方法**：
  - 以实验观察或已有的力谱、分子动力学模拟结果为基准，比较预测的拉伸/开放构象是否一致。
  - 对比对象隐式为标准的无条件扩散采样（即不做引导的 Boltz-2 输出）或基于实验已知的构象。文中未提及与其他生成模型（如 AlphaFold 的条件预测）直接对比，但强调自己的方法无需额外训练。
- **实验指标**：定性评估预测构象是否符合实验特征（如通道孔径大小、域间距离变化等），并可能涉及一些几何参数。

## 4. 资源与算力
- **论文中所披露的算力信息**：当前提供的摘要和元数据中**未明确提及** GPU 型号、数量、训练时长等具体资源细节。论文指出方法不需要额外训练神经网络，主要计算开销在于推理时的扭曲扩散采样。然而，实际测试所用硬件和一次构象采样的耗时与成本未见说明。

## 5. 实验数量与充分性
- **实验数量**：基于摘要，至少测试了 4 个不同系统（DNA、titin、protocadherin-15、MscL），覆盖核酸与蛋白质，以及拉伸与开放两类物理过程。更多定量实验（如多条链、不同约束强度、不同模型版本、消融实验）是否开展，从摘要无法断定。
- **充分性与客观性**：
  - **充分性**：从证明方法可行性的角度看，展示了多个代表性体系，定性匹配实验结果，规模尚可；但缺乏定量统计（如成功率、RMSD分布、所需步数等），可能略显不足。
  - **客观性与公平性**：由于不需要训练，比较主要在“是否实现了所需构象”上，未提及其他条件生成方案（如使用AlphaFold的MCMC采样、其他引导扩散方法）的横向比较，存在一定局限性。

## 6. 论文的主要结论与发现
- 成功在 Boltz-2 中实现扭曲扩散采样，证明了以任意贝叶斯似然引导扩散模型采样非平衡构象的可行性。
- 方法在不改变网络权重的前提下，能够预测 DNA 片段、titin 和 protocadherin-15 的拉伸状态，以及 MscL 的开放构象，与实验一致。
- 该技术可视为“扩散模拟”版的受控分子动力学，为结构预测社区提供了一种灵活且即插即用的稀有构象采样工具，有望推广至多种大分子系统。

## 7. 优点
- **无需额外训练**：充分利用预训练模型，极大节省计算资源与工程复杂度。
- **灵活的条件定义**：使用任意可微贝叶斯似然，对扩散路径进行后验引导，可适配多种物理约束或实验数据。
- **类比受控分子动力学**：以一种新的计算范式将物理直观引入深度学习结构生成，便于领域科学家理解与应用。
- **应用广泛**：从机械拉伸到通道开闭，证明了对不同生物大分子和运动模式的通用性。

## 8. 不足与局限
- **实验覆盖与定量性**：文中仅展示几个典型案例的定性结果，缺少大规模基准测试、统计比较与成功率的定量报告。
- **偏差风险**：引导所产生的构象依赖于似然函数的定义与权重，不当的似然或任意过高的约束可能导致非物理构象；此外，模型局限性（力场精度等）可能隐含偏差。
- **应用限制**：
  - 需要已知目标结构的有效特征（如拉伸距离），不适合完全盲猜的构象探索。
  - 采样过程可能对似然梯度尺度敏感，需调参以确保收敛；效率与通用似然的选择仍需进一步研究。
  - 方法仅限于Boltz-2框架，若移植到其他扩散模型可能需要针对性适配。
- **论文全文缺失**：由于原文网站可能包含访问限制，无法获取完整方法细节、对比实验和消融分析，上述总结均基于摘要和元数据推断，更全面的评估需等待全文公开。

（完）
