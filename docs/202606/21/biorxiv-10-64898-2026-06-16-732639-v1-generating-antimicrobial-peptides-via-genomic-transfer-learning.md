---
title: Generating antimicrobial peptides via genomic transfer learning
title_zh: 通过基因组迁移学习生成抗菌肽
authors: "Polloni, L., Bieniasz, K. D., Gonteri, I., Frost, J. M."
date: 2026-06-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.16.732639v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 使用GPT迁移学习生成多肽分子
tldr: "抗菌肽设计面临已验证数据集规模小、多样性不足的问题。本文提出基于基因组迁移学习的生成式流程，先在大规模无标注基因组数据集AMPSphere上预训练GPT，再在DBAASP上微调，结合Bi-LSTM、ESM-2和QSAR特征构建的MIC预测委员会筛选候选肽。微调模型测试损失降低28%，生成的肽在理化合理性和新颖性上均优于基线，排名靠前的候选肽活性与多粘菌素B相当。该方法证明了将海量基因组数据迁移至目标肽发现场景的通用有效性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 克服合成验证抗菌肽数据集规模小、多样性有限的问题，利用基因组大数据提升生成肽的多样性和设计效果。
method: 在863k条目的AMPSphere基因组数据集预训练GPT，再在7k条目的DBAASP微调，后用BUILT-LSTM、ESM-2和QSAR的MIC预测委员会过滤生成序列。
result: "微调GPT测试损失降低28%，生成肽同时更新颖和更理化可行，顶级候选取代活性与多粘菌素B相当。"
conclusion: 该迁移学习框架可泛化用于利用大规模无标注基因组数据赋能目标肽发现，实验验证已提交2027 AMP挑战赛。
---

## 摘要
我们提出了一种用于线性抗菌肽（AMPs）设计的生成式机器学习流程。为了在合成验证的肽数据集（约7,000条）之外扩展多样性，我们应用迁移学习：首先在基因组来源的AMPSphere数据集（约863,000条）上训练生成式预训练Transformer（GPT），然后在抗菌肽活性与结构数据库（DBAASP）上进行微调。我们使用基于Bi-LSTM架构、ESM-2和QSAR特征向量构建的最小抑菌浓度（MIC）预测模型委员会对筛选的序列进行评估。与仅在DBAASP上训练相比，微调后的GPT模型测试损失降低了28%，并且生成的肽同时具有更高的新颖性和更合理的物理化学性质。我们排名靠前的候选物被预测具有与多粘菌素B相当的抗菌活性。我们预期这种迁移学习方法可广泛用于利用大规模未标记的基因组数据集来丰富靶向肽发现。我们确定的序列已提交至2027年AMP挑战赛（团队名称\textsc{Vinci}）进行实验验证，完整的代码库和工作流程已开源。

## Abstract
We present a generative machine learning pipeline for the design of linear antimicrobial peptides (AMPs). To extend diversity beyond synthetically validated peptide datasets ($\sim$7,000 entries), we apply transfer learning by training a Generative Pre-trained Transformer (GPT) on the genomically derived AMPSphere dataset ($\sim$863,000 entries), before fine-tuning on the Database of Antimicrobial Activity and Structure of Peptides (DBAASP). We assess the filtered sequences with a committee of Minimum Inhibitory Concentration (MIC) predictive models built with a Bi-LSTM architecture, and ESM-2 and QSAR feature vectors. The fine-tuned GPT model produced a $28\%$ reduction in test loss compared to training on DBAASP alone, and generates peptides that are simultaneously more novel and more physicochemically plausible. Our top-ranked candidates are predicted to possess antimicrobial activity comparable to polymyxin B. We anticipate this transfer-learning approach is broadly applicable for leveraging massive, unlabelled genomic datasets to enrich targeted peptide discovery. Our identified sequences have been submitted to the 2027 AMP Challenge\cite{noauthor_szczurek-labamp-challenge-2027_2026} (team name \textsc{Vinci}) for experimental validation, and the complete codebase and workflow are open source\cite{zenodo.20618061}.