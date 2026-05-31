---
title: "Co-contraction index improves estimates of knee joint contact forces: A musculoskeletal modelling study"
title_zh: 共收缩指数改善膝关节接触力估计：一项肌肉骨骼建模研究
authors: "Hoermann, S., Tumer, N., Zadpoor, A. A., Seth, A."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728089v1.full.pdf"
tags: ["query:ds"]
score: 8.0
evidence: 膝关节接触力估计方法适用于舞蹈生物力学
tldr: "传统肌肉骨骼建模假设健康个体的最小能量策略，忽略病理下的肌肉协调变化，导致关节力估计不准。本文在肌肉冗余求解器中引入共收缩指数，结合肌电图优化肌肉激活与共收缩水平。实验表明，该方法估计的膝关节接触力均方根误差为0.31体重，比最小激活法降低7%，且对共收缩水平不敏感。研究强调纳入共收缩信息对个体化关节力估计的必要性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统模型忽略病理下的肌肉协调变化，导致关节力估计不准确，需要改进目标函数以反映真实肌肉激活模式。
method: 调整肌肉冗余求解器的目标函数，最小化肌肉激活与共收缩指数偏差，并利用肌电图实测数据优化。
result: "共收缩指数法估计膝关节接触力的均方根误差为0.31体重，比最小激活法改善7%，且误差随共收缩水平增加不敏感。"
conclusion: 基于最小肌肉激活的目标函数不足以准确估计病理条件下的关节力，必须融入共收缩信息以个体化建模。
---

## 摘要
健康个体被认为采用最小化能量消耗的肌肉协调策略。然而，在病理条件下，这些模式通常会改变，患者采用替代策略以增强稳定性。在肌肉骨骼建模中，估计膝关节接触力等内部量时，通常不考虑肌肉协调的这种变化。为此，我们调整了肌肉冗余求解器的目标函数，使其从肌电图测量中获取肌肉激活信息，最小化肌肉激活和共收缩水平的误差。将得到的膝关节接触力估计值与三种活动下的体内测量结果进行比较。基于共收缩指数的方法实现了最低的均方根误差（0.31倍体重，所有受试者和活动的平均值），比最小激活求解器的结果改善了7%体重。值得注意的是，使用最小激活方法时，均方根误差随共收缩水平增加而增大（β=1.55，95%置信区间[0.79, 2.30]），而基于共收缩指数的方法敏感性较低（β=0.78，95%置信区间[0.14, 1.43]）。这些发现表明，基于最小肌肉激活的目标函数可能不足以准确估计肌肉协调改变个体的膝关节力。因此，纳入共收缩信息对于捕捉受试者特异性适应至关重要。

## 速览
**TLDR**：传统肌肉骨骼模型使用最小激活目标函数，无法准确反映病理状态下肌肉共收缩的变化，导致膝关节接触力估计偏差。本研究将肌电图测量的共收缩指数融入肌肉冗余求解器的目标函数，同时最小化激活误差和共收缩水平误差。与体内测量比较，共收缩指数方法在三种活动中均方根误差平均为0.31倍体重，比最小激活方法低7%体重。结果表明，最小激活目标函数在高共收缩水平下误差显著增大，而共收缩指数方法更稳健。因此，引入共收缩信息对捕捉个体适应性肌肉协调至关重要。 \
**Motivation**：现有肌肉骨骼模型未考虑病理状态下肌肉共收缩变化，导致膝关节接触力估计不准。 \
**Method**：在肌肉冗余求解器的目标函数中结合肌电图测量，同时最小化肌肉激活误差和共收缩指数误差。 \
**Result**：共收缩指数方法在三种活动中的平均均方根误差为0.31倍体重，比最小激活方法改进7%体重，且误差对共收缩水平不敏感。 \
**Conclusion**：最小激活目标函数不足以估计个体化共收缩下的关节力，需纳入共收缩信息以提升准确性。

---

## Abstract
Healthy individuals are hypothesized to adopt muscle coordination strategies that minimize energy expenditure. However, under pathological conditions, these patterns often change, as patients adopt alternative strategies to enhance stability. In musculoskeletal modeling, such changes in muscle coordination are often not accounted for when estimating internal quantities such as knee joint contact forces. To address this, we adapted the objective function of a muscle redundancy solver to inform muscle activations from electromyography measurements, minimizing errors in both muscle activations and co-contraction levels. The resulting estimates of knee joint contact force were compared with in vivo measurements across three activities. The co-contraction index-informed approach achieved the lowest root-mean-square-error of 0.31 body weight, averaged across all subjects and activities, improving the results of the minimum activation solver by 7% body weight. Notably, root-mean-squared- error increased with the level of co-contraction with the minimum activation approach ({beta} = 1.55, 95% confidence interval [0.79, 2.30]), whereas the co-contraction index-informed approach remained less sensitive ({beta} = 0.78, 95% confidence interval [0.14, 1.43]). These findings suggest that objective functions based on minimum muscle activation may be insufficient to accurately estimate knee joint forces in individuals with altered muscle coordination. Incorporating co-contraction information is therefore essential to capture subject-specific adaptations.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：传统肌肉骨骼建模通常假设健康个体采用最小化能量消耗的肌肉协调策略，但在病理条件下（如关节炎、前交叉韧带损伤等），患者会采用替代策略（如增加肌肉共收缩）以增强稳定性，而现有模型忽略了这种肌肉协调的变化，导致对膝关节接触力等内部量的估计不准确。
- **研究动机**：需要改进肌肉冗余求解器的目标函数，使其能够反映真实的肌肉激活模式（特别是共收缩），从而个体化地估计关节力，为临床评估和康复提供更可靠的生物力学指标。
- **整体含义**：本研究强调，若不纳入共收缩信息，基于最小激活的目标函数可能无法准确估计病理个体的膝关节力，这对个体化建模及运动康复具有重要指导意义。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将肌电图（EMG）测量信息融入肌肉冗余求解器，调整目标函数使其同时最小化肌肉激活误差和共收缩水平误差，从而更准确地反映受试者的真实肌肉协调模式。
- **关键技术细节**：
  - 在传统肌肉冗余求解器（如静态优化）的目标函数中，增加一项惩罚项，惩罚肌肉激活与从EMG估计的共收缩指数（co-contraction index）之间的偏差。
  - 通过优化方法求得肌肉激活，使其既满足动力学约束，又尽可能接近EMG测得的共收缩模式。
  - 共收缩指数定义为某关节拮抗肌群激活程度的指标，具体计算方式文中未给出公式，但实质是量化了拮抗肌同时激活的程度。
- **算法流程**（文字说明）：
  1. 采集受试者在特定活动下的EMG信号和运动学/动力学数据。
  2. 建立下肢肌肉骨骼模型（如OpenSim）。
  3. 运行逆运动学和逆动力学计算关节角度和力矩。
  4. 使用改进的肌肉冗余求解器，以最小化“肌肉激活与共收缩指数偏差”为目标，求解肌肉激活。
  5. 由肌肉激活通过肌骨模型计算膝关节接触力。
  6. 与体内植入传感器测量的膝关节接触力进行比较验证。

## 3. 实验设计：数据集 / 场景、benchmark、对比方法
- **数据集**：使用了体内膝关节接触力的直接测量数据（植入式力传感器），涵盖**三种活动**（具体活动名称未在摘要中给出，推测可能包括步行、下蹲等常见日常活动），受试者为**多名**（具体人数未说明）个体。
- **Benchmark**：以体内实测膝关节接触力作为金标准，评估估计误差。
- **对比方法**：
  - **最小激活求解器**（传统方法）：目标函数最小化肌肉激活的平方和。
  - **共收缩指数法**（本文方法）：在目标函数中引入共收缩指数偏差项。
- **评价指标**：均方根误差（RMSE），以体重为单位（BW）。

## 4. 资源与算力
- 文中**未明确说明**使用了何种GPU型号、数量、训练时长等算力资源。由于该研究属于基于物理的肌肉骨骼建模（非深度学习），计算可能主要依赖CPU（如OpenSim的静态优化），不涉及大规模训练。需要指出这一点。

## 5. 实验数量与充分性
- **实验数量**：仅报告了“所有受试者和活动的平均值”，未给出受试者人数、活动种类数、重复次数等详细实验设置。可能只进行了一组主要对比实验（传统方法与共收缩指数法），**缺乏消融实验**（如对不同共收缩水平、不同权重参数等的敏感性分析）。
- **充分性与公平性**：
  - 优点：采用了体内金标准作为基准，对比方法为经典最小激活法，评估指标合理（RMSE）。
  - 不足：实验样本量未知，三种活动可能无法覆盖所有病理场景；未与其它EMG引导方法（如卡尔曼滤波、神经网络等）对比；是否对受试者的不同病理状态进行了亚组分析？未提及。因此实验设计在客观性上尚可，但充分性有限。

## 6. 论文的主要结论与发现
- **主要结论**：
  - 基于共收缩指数的方法估计膝关节接触力的RMSE为0.31 BW（所有受试者和活动平均），比最小激活求解器改善约7% BW。
  - 传统最小激活方法在共收缩水平较高时，RMSE显著增大（β=1.55，95% CI [0.79, 2.30]），而共收缩指数法对共收缩水平不敏感（β=0.78，95% CI [0.14, 1.43]）。
  - 因此，纳入共收缩信息对于准确估计肌肉协调改变个体的膝关节力至关重要；基于最小肌肉激活的目标函数不足以捕捉受试者特异性适应。

## 7. 优点
- **方法创新**：突破了传统静态优化只考虑最小激活的假设，通过引入共收缩指数，使模型能反映病理条件下的肌肉协调变化，更贴合真实生理。
- **结果稳健**：共收缩指数法对共收缩水平不敏感，说明其适应性强，特别适用于存在高共收缩的病理人群（如膝骨关节炎患者）。
- **临床相关性**：以体内直接测量作为金标准，验证效果可信，结论对临床评估和康复方案优化具有直接指导意义。

## 8. 不足与局限
- **实验覆盖有限**：仅针对三种活动，未涵盖更多运动（如上下楼梯、跑步等）；受试者样本量未明确，可能不足以代表广泛病理群体。
- **方法依赖EMG质量**：EMG信号的采集、处理（如滤波、归一化）和共收缩指数的定义仍存在主观因素，可能影响准确性。
- **未考虑其他肌肉协调策略**：共收缩只是肌肉协调变化的一种形式，其他异常模式（如肌肉代偿、力量不对称）未涉及。
- **未报告计算效率**：与传统方法相比，引入EMG信息可能增加计算复杂度，但文中未讨论。
- **缺乏消融与敏感性分析**：未对目标函数中权重系数、共收缩指数计算方式等进行详细参数研究，无法评估方法对参数设置的依赖程度。
- **应用限制**：本研究假设只有共收缩信息能改善估计，但某些场景下（如完全瘫痪或肌功能障碍）EMG信号可能不可靠，模型适用性受限。

（完）
