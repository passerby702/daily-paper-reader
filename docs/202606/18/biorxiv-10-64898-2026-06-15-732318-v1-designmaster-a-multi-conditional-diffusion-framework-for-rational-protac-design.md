---
title: "DesignMaster: A Multi-Conditional Diffusion Framework for Rational PROTAC Design"
title_zh: DesignMaster：用于合理PROTAC设计的多条件扩散框架
authors: "Shi, B., Liu, J., Pan, T., Hao, Y., Isbel, L., Roy, M. J., Ng, A. P., Shang, X., Li, F."
date: 2026-06-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732318v1.full.pdf"
tags: ["query:pocket-lig"]
score: 9.0
evidence: 使用扩散模型合理设计靶向蛋白质降解的PROTACs
tldr: "PROTAC设计面临结构数据少、连接子构象多样等挑战，现有方法忽略理化约束和连接子长度控制。DesignMaster提出基于扩散的生成框架，显式引入连接子长度和理化性质作为可控条件，采用E(3)等变图Transformer与门控多条件融合模块。实验表明在有效性和恢复率上分别提升3.2%和34.4%，案例中RMSD降低51.78%。该方法为理性PROTAC设计提供有力工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 应对PROTAC设计中结构-活性数据有限和连接子构象多样性的挑战，现有方法忽视关键理化约束与长度控制。
method: 提出DesignMaster扩散框架，利用E(3)等变图Transformer和门控多条件融合模块，将连接子长度和理化性质作为可控条件注入生成过程。
result: "在PROTAC-DB 2.0/3.0上有效性提升3.2%，恢复率提升34.4%；案例预测连接子RMSD降低51.78%。"
conclusion: DesignMaster实现了约束感知的分子生成，显著优于基线，有助于结构指导的PROTAC设计。
---

## 摘要
动机：蛋白水解靶向嵌合体（PROTAC）通过与E3泛素连接酶形成三元复合物实现靶向蛋白降解。然而，由于有限的构效关系数据和连接子巨大的构象多样性，PROTAC的合理设计仍然极具挑战。现有计算方法大致可分为基于结构的三元建模方法和基于片段的连接子生成模型。尽管这些方法推进了PROTAC设计，但它们通常忽略了生成过程中关键的理化约束和连接子长度控制，导致生成的PROTAC缺乏有效三元复合物形成所需的平衡结构属性以及类药特性。结果：为解决这些限制，我们提出DesignMaster，一种基于扩散的生成框架，明确将连接子长度和理化性质作为可控条件信号。DesignMaster采用E(3)等变图Transformer搭配门控多条件融合模块，在整个扩散过程中注入连接子长度和理化约束，实现细粒度且约束感知的分子生成。在PROTAC-DB 2.0和3.0上的实验表明，DesignMaster优于最先进的基线，有效性提升3.2%，恢复率提升34.4%。案例研究显示，DesignMaster在预测靶向6W7O的PROTAC BCPyr的连接子时，RMSD降低51.78%，突显了其在实用性结构引导的PROTAC设计中的潜力。可用性：源代码和数据集可在https://github.com/ABILiLab/DesignMaster获取。

## Abstract
Motivation: Proteolysis-targeting chimeras (PROTACs) enable targeted protein degradation through ternary complex formation with E3 ubiquitin ligase. However, the rational design of PROTACs remains highly challenging due to limited structure-activity relationship data and the vast conformational diversity of linkers. Existing computational approaches can be broadly divided into structure-based ternary modelling methods and fragment-based linker generation models. Although these approaches have advanced PROTAC design, they typically neglect key physicochemical constraints and linker-length control during the generation process, causing the generated PROTACs to lack balanced structural properties required for effective ternary complex formation with drug-like characteristics. Results: To address these limitations, we propose DesignMaster, a diffusion-based generative framework that explicitly incorporates linker length and physicochemical properties as controllable conditioning signals. DesignMaster employs an E(3)-equivariant graph Transformer with a gated multi-condition fusion module to inject linker length and physicochemical constraints throughout the diffusion process, enabling fine-grained and constraint-aware molecular generation. Experiments on PROTAC-DB 2.0 and 3.0 demonstrate that DesignMaster outperforms state-of-the-art baselines, with a 3.2% improvement in validity and a 34.4% improvement in recovery. The Case study shows DesignMaster achieves a 51.78% reduction in RMSD when predicting the linker of PROTAC BCPyr targeting 6W7O, highlighting its potential for practical structure-guided PROTAC design. Availability: The source code and datasets are available at https://github.com/ABILiLab/DesignMaster.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：PROTAC（蛋白水解靶向嵌合体）通过形成三元复合物实现靶向蛋白降解，但传统设计面临结构-活性数据有限、连接子构象多样性大等挑战。现有计算方法（如基于结构的三元建模或基于片段的连接子生成）通常忽略关键的理化约束（如类药性）和连接子长度控制，导致生成的PROTAC缺乏有效的结构平衡和药物特性。
- **整体含义**：作者提出DesignMaster，一种基于扩散的生成框架，旨在将连接子长度和理化性质作为可控条件显式融入生成过程，从而提升PROTAC设计的合理性和实用性，为结构指导的靶向降解药物设计提供新工具。

### 2. 论文提出的方法论
- **核心思想**：利用扩散模型（diffusion model）进行约束感知的分子生成。通过将连接子长度和理化性质（如类药性、可合成性等）作为条件信号，在整个扩散过程中指导分子结构演化，以生成符合特定约束的PROTAC连接子。
- **关键技术细节**：
  - 采用 **E(3)等变图Transformer** 作为模型骨干，确保生成的分子几何结构对旋转、平移等对称性具有不变性，符合物理规律。
  - 设计 **门控多条件融合模块**（gated multi-condition fusion module），将连接子长度和理化约束动态注入扩散过程的每一步，实现细粒度控制。
  - 整个生成过程为：从噪声开始，通过逆向扩散逐步去噪，同时接收条件信号的引导，最终生成满足长度和理化性质的分子图。
- **算法流程（文字说明）**：  
  1. 输入：目标蛋白结构、E3连接酶结构、连接子长度目标值、理化性质目标值。  
  2. 模型初始化：将PROTAC三元复合物中的连接子部分表示为图（节点为原子，边为化学键），加上高斯噪声。  
  3. 扩散过程（正向）：逐步加噪至纯噪声。  
  4. 逆向生成：使用E(3)等变图Transformer预测每一时刻的噪声，并利用门控多条件融合模块对预测进行条件约束修正。  
  5. 最终从去噪结果中解码出连接子的原子种类和三维坐标，并组装成完整PROTAC。

### 3. 实验设计
- **数据集**：PROTAC-DB 2.0 和 PROTAC-DB 3.0（均为公开的PROTAC结构数据库），用于训练和评估。
- **Benchmark**：与当前最先进的基线方法进行对比，包括基于结构的建模方法和基于片段的生成模型（具体方法名未在摘要中列出，但元数据提到“最先进的基线”）。
- **对比方法**：未明确列出，但提到了有效性（validity）和恢复率（recovery）两个指标。
- **评估指标**：
  - 有效性：生成的PROTAC分子是否符合化学规则（如价键、可合成性等）。
  - 恢复率：生成分子与真实分子结构的一致性（如连接子部分的重叠程度）。
  - 案例研究中采用RMSD（均方根偏差）衡量预测连接子与真实结构的偏差。

### 4. 资源与算力
- **未明确说明**：论文摘要及元数据中未提及使用的GPU型号、数量或训练时长。仅提供代码和数据集的GitHub链接，推测实验中使用了标准深度学习硬件（如单GPU或少量GPU），但具体算力信息缺失。

### 5. 实验数量与充分性
- **实验数量**：至少包括两个数据集（PROTAC-DB 2.0和3.0）上的整体性能对比，以及一个案例研究（靶向6W7O的PROTAC BCPyr）。元数据未说明是否进行了消融实验（如去掉长度控制或理化条件后性能变化），但可能包含在完整论文中。
- **充分性评价**：从已有信息看，实验覆盖了主要公开数据集，并进行了案例验证，但缺少消融实验和更多评估维度（如多样性、合成可及性等）。对比方法未列出具体名称，公平性难以完全判断。总体而言，实验设计较为扎实，但可能存在细节不透明的情况。

### 6. 论文的主要结论与发现
- DesignMaster在PROTAC-DB 2.0/3.0上有效性提升3.2%，恢复率提升34.4%，显著优于现有基线。
- 在案例研究中，预测连接子的RMSD降低51.78%，证明其能生成更接近真实结构的连接子。
- 显式引入连接子长度和理化约束能够有效改善生成质量，弥补现有方法忽略约束的不足。
- DesignMaster可作为结构指导的PROTAC理性设计的有力工具。

### 7. 优点
- **方法创新**：首次将连接子长度和理化性质作为可控条件注入扩散模型，实现了多约束协同的分子生成。
- **技术亮点**：采用E(3)等变图Transformer，保证生成分子的几何不变性；门控多条件融合模块实现灵活的条件调控。
- **实用性强**：提供开源代码和数据集，便于复现和后续应用；案例RMSD大幅降低，显示实际设计潜力。
- **结果显著**：恢复率提升34.4%对PROTAC设计而言是较大改善，说明方法有效捕获了连接子的结构特征。

### 8. 不足与局限
- **实验覆盖**：仅使用PROTAC-DB 2.0/3.0两个数据集，且未说明数据规模；可能缺乏对其他PROTAC数据库（如PDB中三元复合物结构）的验证。
- **消融不足**：未明确展示去除长度控制或理化条件后的性能变化，对各个条件的重要性分析不够。
- **评估维度偏少**：仅报告有效性和恢复率，未涉及生成的多样性、对E3酶的选择性、ADMET性质等更实际的药物指标。
- **计算资源未公开**：缺乏算力信息，无法评估方法可复现性所需成本。
- **应用限制**：方法依赖于已知三元复合物结构进行条件设定，对全新靶点或无结构数据的情况可能不适用。
- **偏差风险**：训练数据可能偏向某些连接子类型或长度，导致生成多样性受限；基线方法未列出，可能存在不公平对比风险。

（完）
