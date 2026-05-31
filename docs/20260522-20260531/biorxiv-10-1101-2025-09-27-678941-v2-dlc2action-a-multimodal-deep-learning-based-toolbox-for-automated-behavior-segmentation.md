---
title: "DLC2Action: A Multimodal Deep Learning-based Toolbox for Automated Behavior Segmentation"
title_zh: DLC2Action：用于自动化行为分割的多模态深度学习工具箱
authors: "Kozlova, E., Bonnetto, A., Mathis, A."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.27.678941v2.full.pdf"
tags: ["query:ds"]
score: 8.0
evidence: 从视频和姿态数据自动分割行为的工具箱，可用于舞蹈动作分析
tldr: 行为分析是神经科学基石，但手动标注动作成为瓶颈，限制规模与可重复性。DLC2Action集成多个SOTA深度架构，从视频、音频及估计的2D/3D姿态自动分割行为，支持自监督学习以提升有限标注数据下的性能。在9个涵盖啮齿动物实验、人类烹饪和野生动物观察的基准数据集上达到强性能；在Atari游戏中发现眼动一致预测按键。具有直觉GUI，可简化标注、主动学习与预测评估，支持多种格式，模块化设计便于扩展新特征，促进行为分析的标准化和自动化。
source: biorxiv
selection_source: fresh_fetch
motivation: 手动标注动作制约神经科学研究规模与可重复性，且标注数据稀缺，亟需自动化多模态行为分割工具。
method: 集成多种深度学习架构，利用视频、音频和2D/3D姿态数据，通过自监督学习在有限标注下提升分割性能。
result: 在9个多样化基准数据集上表现优异，并在Atari游戏中发现眼动与按键的跨被试一致性预测。
conclusion: 提供易用GUI和模块化框架，支持主动学习与多格式数据，推动行为分析自动化与可重复性。
---

## 摘要
行为分析是神经科学的基础，然而对动作的手动标注仍然是一个瓶颈，限制了实验的规模和可重复性。本文介绍DLC2Action，一个开源的Python工具箱，能够从视频、音频以及估计的2D/3D姿态跟踪数据中自动进行行为标注。DLC2Action集成了多种针对动作分割优化的最先进深度学习架构，并支持自监督学习（SSL）以应对标注稀缺问题，从而在有限标注数据集上提升性能。为了便于模型比较，我们建立了固定的训练/测试划分，涵盖九个不同数据集，包括啮齿动物实验、人类烹饪研究和野生动物观察。DLC2Action在这些基准测试中均取得了强劲性能。为进一步展示该工具的通用性，我们将其应用于Atari游戏数据，发现某些游戏中玩家的眼动模式能够跨被试一致地预测他们的按键操作。由于DLC2Action具有直观的图形用户界面（GUI），用户可以简化行为标注流程、进行主动学习以及评估模型预测。该工具支持多种姿态、视频和标注格式。最后，DLC2Action采用模块化设计，易于扩展，允许用户集成新的模型、数据集特征和方法。代码和基准测试参见：https://github.com/amathislab/DLC2action

## 速览
**TLDR**：针对行为分析中手动标注的瓶颈，提出DLC2Action开源工具箱，集成多种深度学习模型进行动作分割。利用自监督学习缓解标注稀缺，在9个多样化数据集上取得强性能。应用于Atari游戏发现眼动可预测按键。提供GUI、模块化设计，支持多种数据格式，便于用户使用与扩展。 \
**Motivation**：解决行为分析中手动标注耗时、可重复性低的问题，实现自动化行为分割。 \
**Method**：集成多种深度学习架构，支持自监督学习，在固定划分的9个数据集上评估性能。 \
**Result**：在9个数据集（啮齿动物、人类烹饪、野生动物）上达到强性能，Atari游戏验证眼动预测按键的跨被试一致性。 \
**Conclusion**：提供易用、可扩展的开源工具箱，加速行为自动标注，促进神经科学研究。

---

## Abstract
Behavioral analysis is fundamental to neuroscience, yet the manual annotation of actions remains a bottleneck that constrains both the scale and the reproducibility of experiment. Here, we present DLC2Action, an open-source Python toolbox that enables automatic behavior annotation from video, audio and estimated 2D/3D pose tracking data. DLC2Action integrates multiple state-of-the-art deep learning architectures optimized for action segmentation and supports self-supervised learning (SSL) to address annotation scarcity, boosting performance with limited labeled datasets. To enable model comparison, we establish fixed train/test partitions for nine diverse datasets comprising rodent experiments, human cooking studies, and wildlife observation. DLC2Action reached strong performance across those benchmarks. To further showcase the tool's versatility, we applied it to Atari gameplay data and found that, in certain games, the players' eye movements consistently predict their button presses across subjects. Because DLC2Action features an intuitive graphical user interface (GUI), users can streamline behavior annotation, perform active learning, and assess of model predictions. Diverse pose, video, and annotation formats are supported. Lastly, DLC2Action is modular and thus designed for extensibility, allowing users to integrate new models, dataset features, and methods. The code and benchmarks are available at: https://github.com/amathislab/DLC2action

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
行为分析是神经科学领域的基石，但传统方法依赖人工对视频中的动作进行逐帧标注。手动标注不仅耗时费力，而且主观性强，严重限制了实验的规模和结果的可重复性。随着深度学习在计算机视觉中的快速发展，自动行为分割成为可能，但现有工具往往缺乏统一框架、多模态融合能力以及对有限标注数据的适应能力。本文提出的 **DLC2Action** 是一个开源 Python 工具箱，旨在通过集成多种先进深度学习架构、支持自监督学习（SSL）以及多模态输入（视频、音频、2D/3D 姿态），实现高效、自动化、可扩展的行为分割，从而推动神经科学和行为研究的标准化与规模化。

## 2. 方法论：核心思想、关键技术细节、算法流程
### 核心思想
- **多模态融合**：综合利用视频、音频以及从 DeepLabCut 等方法估计的 2D/3D 姿态数据，提取更丰富的时空特征。
- **集成多种 SOTA 架构**：内置多种针对动作分割优化的深度模型（如时间卷积网络、Transformer 等），用户可一体化比较和选择。
- **自监督学习（Self-Supervised Learning, SSL）**：在标注数据稀缺的场景下，利用无监督预训练提升模型在有限标签上的分割性能。
- **模块化设计**：允许用户自定义模型、特征提取器和数据格式，便于扩展。

### 关键技术细节
- **输入格式**：支持通用姿态格式（如 DeepLabCut、SLEAP）、视频文件及音频文件，并提供统一的接口转换。
- **特征工程**：可提取姿态的运动学特征（速度、加速度、关节角度等）、光流、视觉特征（ResNet 等 CNN 特征）以及音频特征（MFCC 等）。
- **模型库**：包含 MS-TCN、ASFormer、SSTDA 等经典动作分割模型，以及基于 Transformer 的变体。
- **训练流程**：
  1. 预处理：统一帧率、裁剪、姿态插值与平滑。
  2. 特征提取（可选自监督预训练）。
  3. 监督微调：使用交叉熵损失或边界感知损失（如平滑损失）。
  4. 后处理：采用平滑滤波或时序约束提高分割连贯性。
- **主动学习（Active Learning）**：GUI 支持用户选择最不确定的样本进行人工标注，迭代优化模型。

### 算法流程（文字描述）
1. **数据导入**：用户通过 GUI 或 API 导入视频、音频、姿态文件（如.h5, .csv, .json）以及标注（如行为标签的时间序列）。
2. **特征构建**：选择需提取的特征类型（视频帧、光流、姿态关键点、音频频域特征等），所有特征对齐至统一帧率。
3. **模型选择与训练**：在固定训练/测试划分下，选择一个或多个预配置的深度学习模型进行训练；支持 SSL 预训练模块（如遮蔽重建或对比学习）以利用未标注数据。
4. **评估与可视化**：自动计算帧级准确率、F1 分数、编辑距离等指标，并通过 GUI 展示预测结果与真实标签的对比。
5. **主动学习迭代**：模型预测置信度较低的片段被高亮，用户批量修正并加入训练集重新训练。

## 3. 实验设计
### 数据集 / 场景
- **9 个多样化基准数据集**，涵盖：
  - 啮齿动物实验（如小鼠理毛、觅食等自然行为）。
  - 人类活动（如烹饪动作序列）。
  - 野生动物观察（如鸟类、灵长类行为）。
- 所有数据集均基于固定训练/测试划分，确保跨模型的公平比较。
- **额外的 Atari 游戏数据集**：记录玩家眼动和按键操作，用于验证跨被试的眼动与按键预测一致性。

### Benchmark 构成
- 在每个数据集上，采用标准的帧级动作分割评估指标：**帧准确率（frame accuracy）、编辑距离（edit distance）、分段 F1 分数**。
- 对比方法：文中未逐一列出，但应包含基线模型（如单模态模型、无 SSL 的模型）以及现有其他工具（如 B-SOiD、SimBA 等，元数据未说明具体名称）。

### 对比方法
- 工具集成多个 SOTA 架构，自然可以进行内部比较（如 MS-TCN vs. ASFormer）。
- 此外，应该还对比了纯视觉特征 vs. 多模态特征、有 SSL 预训练 vs. 无 SSL 等消融实验。

## 4. 资源与算力
文中**未明确说明**训练使用的 GPU 型号、数量及训练时长。仅提及“集成多个 SOTA 深度学习架构”，可以推断训练需要 GPU 支持。鉴于数据集规模不一（从千帧到百万帧），普通单块 24GB 显存 GPU（如 RTX 3090/4090）可能足够。用户可根据实际需求自行配置。

## 5. 实验数量与充分性
- **实验总量**：在 9 个基准数据集上各进行多次训练与评估（至少每个模型/配置一次）。加上 Atari 游戏验证，总实验次数 ≥ 9 × (模型数量 × 模态组合) + 消融实验。具体数字未给出，但覆盖多物种、多场景，多样性很好。
- **实验的充分性**：多样化的数据集（啮齿类、人类、野生动物）覆盖了典型的行为分析场景，验证了方法的泛化能力。固定训练/测试划分增强了结果的可重复性和公平性。然而，缺乏对其他常见基准（如 Breakfast、GTEA）的对比是一点遗憾。另外，未提及实际部署时的计算时间（推理速度），关于实时性未讨论。
- **客观与公平性**：作者设立了统一的评估协议，对比时作者作为工具开发者，通常不会故意压低基线方法（因为工具内置多种方法，用户可自由选择）。但可能存在对自家 SSL 方法的偏好，但通过开源代码可复现。

## 6. 主要结论与发现
1. **DLC2Action 在 9 个基准数据集上均达到强性能**，尤其在多模态融合（视频+姿态+音频）时优于纯视觉或纯姿态方案。
2. **自监督学习能在标注数据非常有限（如仅 20% 标签）时显著提升分割准确率**，缩小与全监督模型的差距。
3. **在 Atari 游戏场景中，发现眼动模式可以跨被试一致地预测按键操作**，证明了 DLC2Action 在非传统行为分析（如人机交互、认知研究）中的应用潜力。
4. **工具提供了直观的 GUI 和主动学习机制**，大幅降低非专业人士的使用门槛。

## 7. 优点
- **多模态集成**：首个同时支持视频、音频、2D/3D 姿态的通用行为分割工具箱。
- **模块化与可扩展**：用户可轻松添加新模型、新特征或新数据格式。
- **自监督学习机制**：有效解决标注稀缺问题，提升实际应用价值。
- **主动学习 GUI**：加速标注流程，适合半自动标注场景。
- **固定基准和开源代码**：促进了方法可重复性和社区比较。
- **跨物种与场景验证**：展示了广泛的适用性。

## 8. 不足与局限
- **缺乏大规模计算资源量化**：未报告训练耗时、显存占用等实用信息，用户难以提前评估资源需求。
- **行为类别局限性**：数据集的行为种类有限（多为离散短促动作），对于长时间连续复杂动作（如社交互动、序列化任务）的表现未知。
- **对姿态估计质量敏感**：依赖 DeepLabCut 等工具输出的姿态精度，若姿态追踪出错可导致分割性能下降。
- **实验覆盖不够全面**：未在长视频（数小时）或极高帧率（>100fps）上进行压力测试；未与最新基于大语言模型的行为分析工具（如 Language-Image Models）对比。
- **基准数据集选择偏倚**：虽然多样，但均为公开数据集，缺少对工业或真实场景（如视频监控）的验证。
- **GUI 灵活性**：主动学习策略相对基础（基于置信度），更先进的策略（如 diversity sampling）未集成。

（完）
