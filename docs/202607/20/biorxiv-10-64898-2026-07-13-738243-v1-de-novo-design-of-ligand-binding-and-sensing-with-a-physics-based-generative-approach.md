---
title: De novo design of ligand binding and sensing with a physics based generative approach
title_zh: 基于物理生成方法的配体结合与传感从头设计
authors: "Zhang, Y., Ke, Y., Zhi, R., Jin, Q., Feng, Y., Wang, C., Fang, M., Liao, J., Chen, D., Liu, J., Cao, L."
date: 2026-07-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.13.738243v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 从头设计结合小分子的蛋白质
tldr: 从头设计配体结合蛋白在生物传感器领域潜力巨大，但实现配体诱导构象变化或调控蛋白-蛋白相互作用仍是挑战。本文提出基于物理的生成方法，在模拟蛋白质折叠的同时并行构建可定制的配体结合口袋，实现精确结构控制。成功针对血清素、多巴胺等5种小分子和2种金属离子设计结合蛋白，晶体结构与计算模型高度吻合。通过分裂蛋白策略构建了血清素和多巴胺传感器，并利用锌诱导折叠机制开发了锌传感器。该方法为开发配体响应型生物传感器提供了鲁棒框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738243-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1661, \"height\": 1099, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738243-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1694, \"height\": 1669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738243-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1687, \"height\": 1181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738243-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1514, \"height\": 2041, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738243-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1640, \"height\": 1893, \"label\": \"Figure\"}]"
motivation: 从头设计配体结合蛋白并转化为功能传感器需要配体诱导构象变化或调节蛋白相互作用，现有方法难以实现。
method: 提出的物理生成方法在模拟蛋白质折叠的同时并行形成可定制配体结合口袋，实现蛋白-配体复合物的精确架构控制。
result: 成功设计针对5种小分子（含血清素、多巴胺）和2种金属离子的结合蛋白，晶体结构验证，并构建了基于分裂蛋白和诱导折叠的传感器。
conclusion: 为从头设计配体结合蛋白和开发配体响应型生物传感器提供了通用且鲁棒的计算框架。
---

## 摘要
配体结合蛋白质的从头设计具有革新生物传感器技术的巨大潜力，但由于需要配体诱导的构象变化或蛋白质-蛋白质相互作用的调节，将这些设计转化为功能性传感器仍是一项重大挑战。在此，我们介绍一种基于物理的生成方法，用于从头创建结合小分子和金属离子的蛋白质。我们的方法在模拟蛋白质折叠的同时实现了可定制的配体结合口袋形成，从而能够精确控制蛋白质-配体复合物的结构，并促进基于配体触发蛋白质重新结合（通过分裂蛋白质重组）或配体诱导蛋白质折叠的生物传感器的开发。我们通过成功设计针对五种小分子（包括非常小的神经递质血清素和多巴胺）以及两种金属离子，证明了我们计算方法的多样性。生物物理表征证实了正确的配体结合，晶体结构与计算模型高度吻合。我们通过使用分裂蛋白质策略构建血清素和多巴胺传感器，并探索了多种增强传感器活性的方法，展示了这些设计在生物传感器工程中的潜力。此外，我们通过锌离子诱导的蛋白质折叠机制开发了一种锌传感器。总体而言，我们的基于物理的生成方法为配体结合蛋白质的从头设计提供了一个稳健的框架，为开发配体响应型生物传感器开辟了新途径。

## Abstract
The de novo design of ligand-binding proteins has tremendous potential to revolutionize biosensor technology, yet converting these designs into functional sensors remains a major challenge due to the need for ligand-induced conformational changes or modulation of protein-protein interactions. Here, we introduce a physics-based generative approach for the de novo creation of proteins that bind small molecules and metal ions. Our method achieves customizable ligand-binding pocket formation in parallel with simulated protein folding, allowing for precise architectural control of the protein-ligand complex and facilitating the development of biosensors based on either ligand-triggered protein reassociation via split-protein reassembly or ligand-induced protein folding. We demonstrate the versatility of our computational method through successful designs targeting five small molecules, including the very small neurotransmitters serotonin and dopamine, and two metal ions. Biophysical characterization confirmed correct ligand binding, and crystal structures closely matched computational models. We demonstrated the biosensor engineering potential of these designs by constructing serotonin and dopamine sensors using a split protein strategy and explored several approaches to enhance sensor activity. Additionally, we developed a zinc sensor through a zinc-induced protein folding mechanism. Overall, our physics-based generative approach provides a robust framework for the de novo design of ligand-binding proteins, opening new avenues for the development of ligand-responsive biosensors.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）
- **核心问题**：从头设计配体结合蛋白并转化为功能传感器面临重大挑战，传统方法依赖预存支架库或深度学习模型，难以同时实现配体诱导的构象变化/蛋白-蛋白相互作用调节，限制了它们在生物传感器中的应用。
- **动机**：开发一种通用、鲁棒的计算框架，能够直接针对小分子和金属离子设计具有精确结构控制的结合蛋白，并使其易于转化为配体响应型生物传感器。

### 论文提出的方法论
- **核心思想**：基于物理的生成方法，在模拟蛋白质折叠的同时并行构建定制的配体结合口袋，实现蛋白-配体复合物的架构控制。方法包括以下关键步骤：
  1. **小分子配体**：生成配体构象集合 → 使用Rotamer Interaction Field (RIF) 方法枚举有利的侧链-配体相互作用 → 定义锚点残基。
  2. **金属离子**：构建配位残基RIF表（根据配位几何和残基类型系统采样），如Zn²⁺的四面体配位（His/Asp/Glu）。
  3. **蛋白质骨架生成**：采用蒙特卡罗片段组装方法，从随机选定的RIF锚点（折叠根）开始逐步折叠；使用复合评分函数同时优化蛋白质折叠（RPX分数）和配体结合（RIF分数）。若连续失败则重新分配折叠根。
  4. **序列设计与过滤**：对生成的骨架进行Rosetta和ProteinMPNN序列优化，依据脱辅基蛋白折叠、配体相互作用能、氢键数量/几何（或配位残基数量/几何）、形状互补性等标准严格过滤，并与AlphaFold2预测结构比较。
- **关键技术细节**：螺旋束架构（四/五/六螺旋）、小分子结合蛋白设计为120残基，金属离子结合蛋白设计为65残基紧凑四螺旋束；允许强制或加权关键相互作用（如氢键）。

### 实验设计
- **数据集/场景**：
  - **小分子靶点**：多替拉韦（DTG，抗HIV药物）、儿茶素（CIA，抗氧化黄酮类）、DFHBI（荧光染料）、血清素（SRO）、多巴胺（DPA），共5种小分子。
  - **金属离子靶点**：Zn²⁺（四面体）、Ni²⁺（八面体）。
- **基准与对比**：
  - 未直接与现有方法进行系统基准对比（如对接方法、深度学习方法），但文中提及与iSeroSnFR传感器（文献47）比较灵敏度（EC₅₀：539.9 vs 959 μM）和传感器模块大小（129 vs 272 aa）。
  - 通过与高分辨率晶体结构比较验证设计准确性（Cα RMSD 0.446–0.97 Å，配体RMSD 0.883–1.997 Å）。
- **实验类型**：
  - **表达与纯化**：E. coli表达、SEC验证单体。
  - **结合验证**：ITC测定亲和力、突变破坏实验（Ala或位阻突变）。
  - **结构验证**：X射线晶体学获得4个复合物结构（SRO_30、SRO_26_L7F、DPA_9、ZK2）。
  - **传感器构建**：分裂蛋白+spsfGFP（SRO/DPA）或分裂NanoLuc（Zn²⁺）；高通量平板筛选（SRO传感器）或低通量测试（DPA、SRO_26、Zn²⁺）。
  - **性能表征**：荧光滴定、特异性测试、HEK293T细胞成像、实时显微镜。

### 资源与算力
- **未明确说明**：论文未提及训练或运行方法所需的GPU型号、数量、训练时长等算力信息。仅提到使用ProBuilder蛋白质设计包，计算步骤包括蒙特卡罗模拟、RIF生成、Rosetta/ProteinMPNN序列设计，但未提供具体硬件资源。

### 实验数量与充分性
- **实验数量**：
  - 小分子：筛选96个DTG设计（14个结合）、94个CIA（20个结合）、32个DFHBI（2个结合）、38个SRO（6个结合）、33个DPA（1个结合）。
  - 金属离子：各10个设计（Zn²⁺：8个单体、4个显示EDTA敏感；Ni²⁺：8个单体、1个显示EDTA敏感）。
  - 结构表征：4个晶体结构。
  - 传感器优化：SRO传感器经高通量筛选（数千菌落）、界面突变、linker优化；SRO_26和DPA传感器仅低通量测试（n=24和n=9）。
- **充分性与公平性**：
  - 结合验证实验充分（ITC、突变对照、SEC、CD），结构验证有力。
  - 传感器部分：SRO传感器经过多轮优化（重复螺旋、界面突变、linker），性能较好；但DPA传感器仅初步验证（ΔF/F₀=37.5%），且未与现有其他从头设计传感器（如文献6）直接对比。
  - 消融实验：通过突变关键残基验证结合口袋，通过EDTA处理证明金属离子诱导折叠。
  - 总体客观，但缺乏与现有计算设计方法的系统比较（如RFdiffusion、LigandMPNN等），也未报告设计成功率与文献对比。

### 论文主要结论与发现
1. 基于物理的生成方法能够从头设计针对多种小分子（包括非常小、极性的血清素和多巴胺）和金属离子（Zn²⁺、Ni²⁺）的结合蛋白，成功率高。
2. 高分辨率晶体结构证明设计模型与实验结构高度一致（Cα RMSD < 1 Å），验证了方法的准确性。
3. 设计的螺旋束蛋白易于通过分裂策略转化为功能生物传感器：
   - 分裂蛋白+cpGFP构建血清素传感器（wcSRO30_1.0）：ΔF/F₀=339.9%，EC₅₀=539.9 μM，高特异性，可在HEK293T细胞中响应。
   - 分裂NanoLuc构建锌传感器（ZK2_Nluc）：EC₅₀~75 nM，高选择性（优于Irving-Williams系列）。
4. 关键设计技巧：重复螺旋可增加自结合屏障，降低背景信号；界面突变和截短可进一步提升传感器响应。

### 优点
- **方法创新**：物理生成方法可精确控制蛋白质拓扑和结合口袋，无需预存支架库，适合小极性分子；同时显式建模折叠与结合能，可设计配体诱导折叠的蛋白质。
- **结果丰富**：涵盖5种小分子和2种金属离子，晶体结构验证，传感器验证（包括细胞成像），实验证据链完整。
- **实用性**：设计的传感器模块尺寸较小（129 aa），便于递送；锌传感器选择性优异。
- **可解释性**：RIF、RPX等基于物理的评分提供清晰的优化路径。

### 不足与局限
- **算力资源未说明**：无法评估计算成本或可复现性。
- **传感器性能有限**：血清素传感器ΔF/F₀ (411%) 低于iSeroSnFR (930%)；DPA传感器初步性能较低（37.5%），且未与现有最优传感器比较；传感器动态范围、响应速度等未充分优化。
- **泛化性未充分验证**：仅测试了两种金属离子，且Ni²⁺结合蛋白仅1个显示EDTA敏感性，设计成功率低；未尝试其他金属或更复杂的配体。
- **比较不充分**：未与RFdiffusion、LigandMPNN等深度学习方法进行直接基准测试；成功率的定义（如结合与否的阈值）未统一。
- **偏差风险**：筛选过程依赖ITC和荧光，可能遗漏弱亲和力或动力学不利的候选；突变破坏实验仅针对少数设计，其他结合模式可能未被捕获。
- **应用限制**：传感器目前需在体外或过表达系统中测试，体内应用（如脑成像）仍需进一步验证；传感器对pH、温度等环境因素的稳定性未提及。
- **方法局限性**：基于螺旋束架构，可能不适合某些非螺旋结合模式；未探索β-桶或混合架构。

（完）
