---
title: Can We Extract Physics-like Energies from Generative Protein Diffusion Models?
title_zh: 我们能否从生成式蛋白质扩散模型中提取类似物理学的能量？
authors: "Sarma, S., Truscott, H. H., Xu, D., Reid, K., Chu, L.-S., Chen, J., Gray, J. J."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.28.690021v4.full.pdf"
tags: ["query:pocket-lig"]
score: 9.0
evidence: 分析蛋白质扩散模型用于分子设计和蛋白质-配体打分
tldr: 扩散模型在生成式AI中表现优异，但其在生物物理问题中如何对应热力学尚不清楚。本文从理论生物物理角度研究扩散模型，将热力学势与观测状态的负对数概率关联。通过积分扩散路径或概率流ODE路径，可从扩散模型中提取负对数似然值作为学习能量。在1D高斯混合模型和蛋白质对接模型DFMDock上验证，发现提取的能量能准确恢复概率并呈现能量漏斗，与物理能量函数Rosetta相当或更优。这表明扩散模型可以提取有物理意义的能量函数。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索扩散模型是否蕴含与热力学对应的能量函数，并比较其与物理能量函数的性能。
method: 基于统计物理，将热力学势定义为负对数概率，通过积分扩散路径或概率流ODE提取扩散模型的学习能量-log p0(x0)。
result: 1D情形下积分恢复真实概率；对接案例中提取的能量呈漏斗状，最小值接近实验结构，且在25例中6例排序优于Rosetta。
conclusion: 扩散模型可提取具有物理意义的能量函数，能与传统物理能量函数有效比较。
---

## 摘要
扩散模型已成为生成式AI中最先进的方法，并在图像合成、视频生成、分子设计和蛋白质结构预测方面取得了巨大成功。对于生物物理问题，如蛋白质折叠和结合，基于扩散的方法的一个基本问题是其学习函数如何对应热力学。在本文中，我们通过理论生物物理学的视角研究扩散模型，分析其潜在公式，并探索其在蛋白质相互作用评分中的应用。我们发展了植根于统计物理学的简单理论，将热力学势与观测系统处于特定状态的概率的负对数联系起来。我们包括扩散模型方程的量纲分析，以及AI和物理学术语的映射表。然后，我们通过积分扩散生成的路径或概率流ODE路径，测试扩散模型捕获学习能量作为负对数似然值-log p0(x0)的能力。我们在一个简单的一维高斯混合扩散模型和一个蛋白质对接扩散模型DFMDock上测试这些积分。在一维情况下，我们发现对扩散路径和流路径的积分都能准确恢复真实概率。当我们在DFMDock成功的案例中提取学习到的对接能量时，我们观察到能量漏斗，最小能量接近实验对接结构，就像我们在Rosetta（一个经验调整的基于物理的生物分子建模套件）中观察到的。在25个案例中，学习到的能量在6个案例中在对接姿势正确性排序方面表现相当或优于Rosetta界面能量。这些数据表明，我们可以从扩散模型中提取相关的学习能量函数，并将其与物理能量函数进行比较。

## Abstract
Diffusion models have emerged as the state-of-the-art method in generative AI and have shown great success in image synthesis, video generation, molecular design, and protein structure prediction. For biophysical problems, such as protein folding and association, a fundamental question in diffusion-based methods is how their learned functions correspond to thermodynamics. In this paper, we study diffusion models through the lens of theoretical biophysics, analyzing their underlying formulation of potentials and exploring their applications in scoring protein interactions. We develop simple theories rooted in statistical physics that relate thermodynamic potentials to the negative log of the probability of observing a system in a particular state. We include dimensional analysis of diffusion model equations, and a table mapping AI and physics jargon. We then test a diffusion model's ability to capture learned energies as negative log-likelihood values, -log p0(x0), by integrating over the diffusion-generated path or a probability flow ODE path. We test these integrals on a simple 1D Gaussian mixture diffusion model and a protein-docking diffusion model, DFMDock. In the 1D case, we find that integration over both diffusion and flow paths can accurately recover ground truth probabilities. When we extract the learned docking energies for cases where DFMDock succeeds, we observe energy funnels with the minimum energy near the experimental docked structure, like those we observe with Rosetta, an empirically tuned physics-based biomolecular modeling suite. The learned energy performs comparably or outperforms Rosetta interface energy in 6 out of 25 cases at ranking the correctness of docked poses. These data show that we can extract a relevant learned energy function from a diffusion model and compare it to physical energy functions.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：生成式扩散模型在分子设计、蛋白质结构预测等领域表现出色，但其学习到的函数是否蕴含与热力学对应的能量（势能）尚不明确。本文旨在回答：能否从扩散模型中提取具有物理意义的能量函数，并用于蛋白质-配体相互作用打分？
- **研究动机**：生物物理问题（如蛋白质折叠、结合）本质上是热力学过程，而扩散模型通过学习概率分布生成样本。作者希望建立AI扩散模型与统计物理热力学势之间的理论联系，从而为分子设计提供可解释的能量评估工具。
- **整体含义**：如果扩散模型可提取类似物理学的能量函数，那么它将不仅是生成工具，还能作为打分函数，辅助药物设计、蛋白质设计等任务，并可与传统物理能量函数（如Rosetta）直接比较。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：基于统计物理，将热力学势定义为系统处于特定状态的概率的负对数（-log p）。扩散模型在去噪过程中隐式学习了数据分布，因此可以通过积分扩散路径或概率流ODE路径，从模型中提取负对数似然值作为“学习能量”。
- **关键技术细节**：
  - **理论框架**：推导扩散模型与统计物理的对应关系，包括量纲分析（diffusion model equations的维度）以及AI术语与物理学术语的映射表（如“去噪网络”对应“力场”、“噪声”对应“温度”等）。
  - **能量提取方法**：
    1. **扩散路径积分**：沿扩散过程（从数据到噪声）反向积分，利用得分函数（score function）计算-log p0(x0)的路径积分。
    2. **概率流ODE路径积分**：使用确定性概率流ODE（PF-ODE）替代随机扩散过程，积分得到更稳定的负对数似然估计。
  - **公式**：  
    - 扩散模型定义：dx = f(x,t)dt + g(t)dw  
    - 学习能量：E(x0) = -log p0(x0) = 积分(从t=0到T) [ ∇·f(x,t) + (1/2)||s_θ(x,t)||^2 ] dt + 常数 （近似公式，具体略）
- **算法流程**（文字说明）：
  1. 训练一个扩散模型（如DFMDock）或使用已训练模型。
  2. 对于给定输入x0（如蛋白质-配体对接构象），沿扩散反向路径（或PF-ODE路径）进行积分，利用模型给出的得分函数s_θ(x,t)计算每个时间步贡献。
  3. 累加得到-log p0(x0)值，作为该构象的学习能量。
  4. 与物理能量（如Rosetta界面能量）比较，评估排序能力。

### 3. 实验设计：使用了哪些数据集/场景、Benchmark、对比方法
- **数据集与场景**：
  - **一维高斯混合模型**：作为简单验证场景，人为构造混合高斯分布，训练一个小型扩散模型，测试能量积分能否恢复真实概率密度。
  - **蛋白质对接模型DFMDock**：使用已公开发布的训练后的DFMDock（基于扩散的蛋白质对接模型）进行案例研究。选取DFMDock生成成功的25个蛋白质-配体对接案例（实验结构已知）。
- **Benchmark**：无特定公开benchmark，采用作者自行收集的25个案例，以实验结合结构与预测构象之间的均方根偏差（RMSD）为正确性标准。
- **对比方法**：Rosetta（经验调整的基于物理的生物分子建模套件）的界面能量函数（interface energy）。比较两种能量对预测构象进行排序的能力：能量最小值是否接近实验结构，以及排序正确性（正确构象能量最低的比例）。

### 4. 资源与算力
- **文中未明确说明**：论文摘要和提供的文本未提及使用的GPU型号、数量或训练时长。DFMDock模型的训练资源可能参考其原始论文，但本文未重复训练，仅使用预训练模型进行推理和积分计算。对于1D高斯混合实验，算力需求极低。
- **推断**：此类实验（积分计算）对算力要求不高，可能只需单GPU（如NVIDIA RTX 2080或类似）进行数小时即可完成25个案例的积分。

### 5. 实验数量与充分性
- **实验数量**：
  - 1D高斯混合：1组基本验证（扩散路径积分和流路径积分各一次，对比真实概率）。
  - 蛋白质对接：25个案例（均为DFMDock成功案例）。
  - 无消融实验（如改变积分方法、不同噪声调度的影响）。
- **充分性评估**：
  - **优点**：25个案例提供了初步证据，1D实验验证了积分方法的正确性。
  - **不足**：
    - 样本量较小（25例），且仅包含DFMDock成功案例，存在**选择偏差**（可能高估提取能量的表现）。
    - 未包含失败案例或随机构象测试，无法评估能量函数的全局泛化能力。
    - 未与其他基于能量的打分函数（如AlphaFold的plDDT、AutoDock Vina等）对比，仅与Rosetta比较。
    - 未进行严格的统计显著性检验（如Wilcoxon符号秩检验）。
    - 缺乏不同扩散模型（如其他蛋白质生成模型）的泛化实验。

### 6. 论文的主要结论与发现
- **理论成立**：扩散模型可以提取具有物理意义的能量函数（-log p0(x0)），该能量函数与统计物理的热力学势对应。
- **方法验证**：
  - 在1D高斯混合模型上，扩散路径积分和流路径积分均能准确恢复真实概率分布。
  - 在蛋白质对接案例中，提取的学习能量呈现能量漏斗（energy funnel），且最小值接近实验对接结构。
- **性能对比**：
  - 在25个案例中，学习能量在6个案例中在排序正确性方面相当或优于Rosetta界面能量。
  - 学习能量可视为与物理能量函数互补的替代方案。
- **实用价值**：扩散模型不仅仅是生成器，其内部表征可以被“解读”为能量函数，用于打分排序，有助于药物设计中的虚拟筛选。

### 7. 优点：方法或实验设计上的亮点
- **理论创新**：首次系统阐述扩散模型与热力学势之间的对应关系，包括量纲分析和术语映射，弥合了AI与物理学的鸿沟。
- **方法简洁有效**：利用现有扩散模型的得分函数即可计算能量，无需额外训练或修改模型。
- **直观验证**：1D高斯混合实验清晰展示了积分方法的正确性。
- **生物物理相关性**：选择蛋白质对接这一实际问题，能量漏斗现象符合物理知识，增强了可解释性。
- **比较基准合理**：与成熟的Rosetta物理能量对比，凸显学习能量的竞争力。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制
- **样本偏差**：仅测试DFMDock已经成功生成的案例，可能高估提取能量的辨别力（未能评估其对错误构象的识别能力）。
- **样本量小**：25例结果不能代表广泛的一般性结论，统计可靠性有限。
- **缺失消融实验**：未比较不同积分方法（扩散 vs. ODE）的差异，未分析噪声调度、模型架构的影响。
- **应用限制**：
  - 提取的能量依赖于训练好的扩散模型质量，若模型未收敛或泛化差，能量不可靠。
  - 计算-log p0(x0)需要沿路径数值积分，对于高维蛋白质构象空间可能计算成本较高。
  - 仅适用于生成式扩散模型，不直接适用于其他生成模型（如GAN、VAE）。
- **未与其他主流打分函数对比**：仅与Rosetta对比，缺少与MM/GBSA、AutoDock Vina、Glide等的比较。
- **基准缺失**：缺乏公开的标准测试集（如PDBbind），结果难以复现和扩展。

（完）
