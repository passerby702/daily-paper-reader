---
title: De Novo Design of Protein Switches with Diffusion-Based Ensemble Sampling
title_zh: 基于扩散的集合采样的蛋白质开关从头设计
authors: "Omidi, A., He, J., Bui, J. M., Gsponer, J., Syed, S."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.20.739027v1.full.pdf"
tags: ["query:diff-gen"]
score: 8.0
evidence: 使用预训练蛋白质扩散模型生成蛋白质骨架集合用于开关设计，与扩散模型的3D形状生成相关
tldr: 蛋白质开关的设计需要支持刺激依赖构象的序列，但现有方法依赖专家提供多构象主链。本文提出Diff-Switch，利用预训练扩散模型和元动力学偏置采样多样化的全局排列，同时保持局部域几何。在20种蛋白质上，生成的主链集合使下游序列设计成功率提升，并在实际任务中验证有效。该方法降低了开关设计门槛，实现了构象集合的自动化采样。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1397, \"height\": 804}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1383, \"height\": 468}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 786}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1294, \"height\": 513}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 593, \"height\": 310}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 883, \"height\": 537}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 784}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1223, \"height\": 764}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 856, \"height\": 922}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1224, \"height\": 763}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1152, \"height\": 457}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-20-739027-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1301, \"height\": 640}]"
motivation: 现有方法依赖专家知识提供多构象主链，缺乏自动生成开关构象集合的通用方法。
method: Diff-Switch结合扩散模型与元动力学倾斜奖励，在集体变量空间中加入历史偏置，采样局部相似、全局多样的构象集合。
result: 在20种蛋白质评估中，生成集合使开关兼容序列发现成功率显著高于基线采样，并在真实设计任务中成功应用。
conclusion: Diff-Switch为蛋白质开关的自动设计提供了有效的多构象主链采样方法，扩展了从头设计能力。
---

## 摘要
蛋白质开关是一类通过重排其结构元件来响应生化刺激的蛋白质，对细胞信号转导至关重要。此类蛋白质的从头设计需要氨基酸序列具备支持多种刺激依赖性构象的能量景观，然而现有的大多数从头蛋白质设计流程针对单一稳定结构进行了优化。现有的多态逆向折叠方法可以设计兼容多种骨架的序列，但它们假设合适的骨架集合已经存在，这通常需要专家知识。我们提出了Diff-Switch，一个从预训练蛋白质扩散模型中采样开关样骨架集合的框架。给定参考骨架结构和结构域分解，我们的方法在保持局部结构域几何结构的同时，沿着用户指定的集体变量鼓励全局结构域排列的多样性，受元动力学启发。我们通过一个受控的扩散采样器实现这一目标，该采样器具有集合成员之间局部相似性的奖励倾斜，以及在集体变量空间中的历史依赖偏置，以避免重复采样相同的全局排列。得到的集合为下游的多态逆向折叠提供了候选构象状态。在我们包含20种不同蛋白质的评估集上，使用这些生成集合中的构象相比基线采样，提高了找到开关兼容序列的成功率。我们进一步将该方法应用于一个真实的蛋白质开关设计任务，并对所得设计进行了表征。

## Abstract
Protein switches are proteins that can respond to biochemical stimuli by rearranging their structural elements, essential for cells to transduce signals. The de novo design of such proteins requires amino acid sequences whose energy landscapes support multiple stimulus-dependent conformations, yet most current de novo protein design pipelines are optimized for single stable structures. Existing multi-state inverse-folding methods can design sequences compatible with multiple backbones, but they assume that suitable backbone ensembles are already available, often requiring expert knowledge. We introduce Diff-Switch, a framework for sampling switch-like backbone ensembles from pretrained protein diffusion models. Given a reference backbone structure and domain decomposition, our method preserves local domain geometry while encouraging diversity in global domain arrangements along user-specified collective variables, inspired by metadynamics. We implement this objective through a controlled diffusion sampler with reward-tilting for local similarity between the ensemble members and history-dependent bias in collective-variable space to avoid repeated sampling of the same global arrangement. The resulting ensembles provide candidate conformational states for downstream multi-state inverse folding. Across our evaluation set of 20 diverse proteins, using conformations from these generated ensembles improves the success rate of finding switch-compatible sequences over baseline sampling. We further apply the method to a real-world protein switch design task and characterize the resulting designs.

---

## 论文详细总结（自动生成）

# 论文结构化总结：Diff-Switch

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：蛋白质开关（protein switch）需要单个氨基酸序列编码多种刺激依赖的稳定构象，并实现可逆切换。这比设计单一稳定结构困难得多。现行从头设计流程（如RFdiffusion、ProteinMPNN、AlphaFold2/3）本质优化单状态稳定性，无法直接处理多构象需求。
- **现有局限**：多态逆向折叠方法（如ProteinMPNN-MSD、DynamicMPNN）可以设计兼容多人骨干的序列，但假设合适的骨干构象集合已存在。实践中这些集合需通过手动设计、领域专家知识或物理模拟放松获得，难以规模化，且依赖专家干预。
- **本文贡献**：提出Diff-Switch，利用预训练的蛋白质骨干扩散模型（作为先验）结合**元动力学（metadynamics）**，自动采样出局部域结构相似、全局排列多样化的骨干集合，从而为下游多态逆向折叠提供候选构象，降低开关设计门槛。

## 2. 方法论：核心思想与关键技术细节
- **核心思想**：将蛋白质开关设计转化为受控的集合生成问题。给定一个参考骨干结构 \(x_{\text{ref}}\) 和域分解，同时满足两个目标：
  - **局部结构相似性**：每个域的局部几何接近参考（通过奖励倾斜实现）。
  - **全局排列多样性**：域间的相对排列在集体变量（CV）空间上充分多样化（通过元动力学历史偏置实现）。
- **关键技术**：
  - **奖励倾斜后验**：定义奖励 \(r_{\text{ref}}(x) = -\lambda D(x, x_{\text{ref}})\)，其中 \(D\) 为域内RMSD之和，\(\lambda\) 控制约束强度。倾斜后的目标为 \(\pi_{\text{ref}}(x) \propto p(x) \exp(r_{\text{ref}}(x))\)。
  - **扭曲扩散采样器 (Twisted Diffusion Sampler, TDS)**：用于从 \(\pi_{\text{ref}}\) 精确采样，结合顺序蒙特卡洛（SMC）校正，在有限粒子数下近似精确。
  - **元动力学偏置**：在集体变量空间 \(\xi: X \to \mathbb{R}\)（如质心距离）上逐步构建历史依赖偏置 \(V_k(\xi)\)，采用**良温元动力学**（well-tempered metadynamics），每次迭代从当前偏置后验 \(\pi_k(x) \propto p(x) \exp(r_{\text{ref}}(x) - V_k(\xi(x)))\) 采样一批 \(N\) 个骨干，然后更新偏置。公式：\(V_{k+1}(\xi) = V_k(\xi) + \sum_{n=1}^N w_k^{(n)} \exp(-\| \xi - \xi(x_k^{(n)}) \|^2 / (2\sigma^2))\)，其中 \(w_k^{(n)} = \frac{w}{N} \exp(-V_k(\xi(x_k^{(n)}))/(\gamma-1))\)。
  - **算法流程**：迭代 \(K\) 轮（默认 \(K=20, N=5\)），收集所有骨干形成集合 \(\mathcal{E}\)。从中选择与 \(x_{\text{ref}}\) 差异最大的骨干作为 \(x_{\text{alt}}\)，将 \(\{x_{\text{ref}}, x_{\text{alt}}\}\) 对输入多态逆向折叠模型（ProteinMPNN-MSD 或 Caliby），生成候选开关序列。
- **本质**：通过奖励倾斜保持局部保真，通过元动力学在CV空间主动探索，使得扩散模型能覆盖原本稀有的域排列。

## 3. 实验设计
- **数据集与场景**：
  - **主实验**：使用OC23数据集中的20个双态域运动蛋白（剔除3个不适用），每个蛋白皆有关闭和开放两种实验解析结构。模拟“仅知一种状态”场景，分别以关闭或开放构象作为参考 \(x_{\text{ref}}\)。
  - **真实世界任务**：磷酸化诱导的蛋白质开关设计。仅有关闭构象（PDB 7BPL），开放构象需从头生成。
- **基准与对比方法**：
  - **基线**：仅使用单个参考骨干 \(x_{\text{ref}}\) 直接输入多态逆向折叠（即单结构设计）。
  - **Diff-Switch**：使用 \(x_{\text{ref}}\) 和集合中最远骨干 \(x_{\text{alt}}\) 作为双构象输入。
  - **下游逆折叠后端**：ProteinMPNN-MSD 和 Caliby。
- **评估指标**：
  - **自洽性度量**：分别用AlphaFold3预测序列在关闭和开放模板下的结构，计算域对齐RMSD（scRMSD_switch = max(关闭scRMSD, 开放scRMSD)）和TM-score（scTM_switch = min(关闭scTM, 开放scTM)）。成功阈值：scRMSD < 5 Å 或 scTM > 0.5。
  - **成功率曲线AUC**：不同阈值下的成功率，再求AUC。
  - **磷酸化实验**：额外报告质心距离和埋藏界面面积，观察无磷/有磷条件下的结构差异。

## 4. 资源与算力
- **明确说明**：论文声明实验不密集，使用**单块96GB NVIDIA RTX PRO 6000 GPU**。未报告训练时长或具体运行时间。所有实验在单个GPU上完成。

## 5. 实验数量与充分性
- **数量**：
  - 20个蛋白质 × 2种参考构象（开/闭） × 2种逆折叠模型 = 80种条件组合。对每个蛋白，Diff-Switch生成 \(K \times N = 100\) 个骨干，筛选最远骨干。
  - 每个条件设计16条候选序列，每条序列用AF3预测15个结构（3种子×5样本），计算自洽性。
  - 额外独立实验：磷酸化开关案例（16条Diff-Switch序列 vs 16条基线序列）。
- **充分性**：
  - 覆盖多种域运动类型，蛋白长度范围109-801 aa，具有代表性。
  - 对比了两种逆折叠模型，验证方法模型无关性。
  - 采用自举（bootstrap）评估均值和标准差，报告统计显著性（Wilcoxon符号秩检验，p<0.05）。
  - 超参数统一（\(\lambda=3, \sigma=0.3, w=0.1, \gamma=10, K=20, N=5\)），未针对每蛋白调优，保证了公平性但可能未达最优。
  - 磷酸化实验虽小但现实，展示了实际可用性。
- **客观性**：基线方法合理，比较公正。但基线未使用任何构象增强，间接展示Diff-Switch增益。未对比其他多构象生成方法（如手动建模、Rosetta松弛），因为本文是针对自动化生成挑战。

## 6. 主要结论与发现
- Diff-Switch在所有配置下（开/闭参考、ProteinMPNN/Caliby）显著优于基线：
  - AUC提升0.09~0.17（基线AUC 0.51~0.62 vs Diff-Switch 0.68~0.71）。
  - 统计检验显著（p值0.002~0.027）。
  - 磷酸化开关中，25%的Diff-Switch设计序列表现出开关行为，基线为0%。
- 生成的骨干集合能自动恢复两种目标构象和过渡状态，即使只有一种构象作为输入。
- 集体变量（域质心距离）在大多数蛋白上有效，但在少数旋转主导的切换中失效（如P21589），提示CV选择的重要性。

## 7. 优点
- **新颖的方法融合**：将元动力学与预训练扩散模型结合，实现推理时可控的构象集合生成，无需重新训练或专家手动建模。
- **自动化与可扩展性**：只需参考骨干和域划分，即可自动生成多样性集合，降低了开关设计的人工成本。
- **通用性**：方法不依赖特定逆折叠模型，分别在ProteinMPNN和Caliby上验证；集体变量可针对不同开关机制（铰链运动、域分离等）灵活定义。
- **实验设计严谨**：使用多种指标（RMSD、TM、AUC、统计检验），包含真实案例验证，结论可信。
- **理论保证**：TDS在离散时间下精确，良温元动力学保证CV边缘收敛到 \(p(\xi)^{1/\gamma}\)，提供可解释性。

## 8. 不足与局限
- **集体变量选择依赖先验知识**：CV是开关机制的预设（如质心距离），在未知反应坐标时可能无效。论文提及旋转主导的过渡（图5）即为例证。这限制了方法对新类型开关的适用。
- **仅支持半刚性域重排**：对于涉及二级结构转换（如螺旋-片层转换）或无序-有序过渡的复杂折叠变化，当前CV无法捕捉，方法不适用。
- **触发机制设计未系统化**：在磷酸化开关中，触发（磷酸化）是人为引入的；论文指出如何系统设计其它触发（如蛋白-蛋白相互作用）是未来方向。
- **实验覆盖有限**：只有20个蛋白的评估，虽然多样但可能未覆盖所有开关类型；超参数未针对每个蛋白调优，最优性能可能更高但当前作为“地板”结果可以接受。
- **计算资源未充分说明**：虽称不密集，但单批TDS采样需要多次去噪步骤（400步），K=20、N=5共100次，加上AF3多次预测，实际总耗时未报告，但应在可接受范围内。
- **潜在偏差风险**：数据集OC23包含的都是双态域运动明显的蛋白，这些蛋白的切换由域间重排主导，偏向了本文设计的CV。对于域内重排或全折叠切换，表现未知。

（完）
