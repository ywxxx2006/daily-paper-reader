---
title: Neural networks learn forward dynamics when freed from numerical integration
title_zh: 神经网络在免于数值积分时学习前向动力学
authors: "Bahdasariants, S., Yakovenko, S."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728310v1.full.pdf"
tags: ["query:db"]
score: 6.0
evidence: 神经网络前向动力学用于肢体，可应用于舞蹈运动预测
tldr: 人机交互中学习肢体动力学映射常面临数值不稳定问题。现有直接映射方法对未训练扰动预测误差大。本文提出人工物理引擎(APE)，将运动方程近似与时间数值积分分离，先学习动力学结构再积分求解。实验表明，在外部扰动下APE误差远低于直接映射RNN，且保持稳定。该方法通过引入因果物理结构，显著提升了人机界面对外部和内部变异的鲁棒性。
source: biorxiv
selection_source: fresh_fetch
motivation: 直接映射神经网络预测前向动力学存在数值不稳定，泛化差，需更鲁棒的动力学学习架构。
method: 提出人工物理引擎(APE)，先训练网络近似运动方程，再独立进行数值积分计算状态更新。
result: APE在未训练外部扰动下预测误差低至直接映射RNN的几分之一，且稳定性显著提升。
conclusion: 分离运动方程近似与数值积分的学习范式可增强模型对变异的鲁棒性，推动物理约束型人机界面设计。
---

## 摘要
人类与机器之间的无缝交互需要能够在生物信号和物理环境固有的变异性下保持鲁棒性的接口。先进的人机接口越来越依赖机器学习来预测或控制肢体动力学。这些系统必须学习控制变量与肢体状态之间的输入-输出映射，例如作用于分段手臂关节的肌肉力或关节力矩随时间变化到肢体姿态的映射。这种统计性的输入-输出转换可能导致预测的肌肉骨骼运动学和动力学数值不稳定。实现生物运动控制的鲁棒性需要解决前向和逆动力学问题；然而，这些问题在计算上是不对称的，因为它们涉及相反的操作——积分和微分。由于我们之前已经证明，当训练神经网络在到达过程中将运动学映射到动力学信号时，它们可以解决逆动力学问题，因此我们假设分别表示运动方程及其时间数值积分的近似可能捕获前向动力学问题的相关计算结构。我们通过比较传统的直接映射循环神经网络和两阶段模型（人工物理引擎）来检验这一假设。在预测训练期间未遇到的外部扰动下的两段系统状态时，直接映射的整体模型产生了与预期交互扭矩不一致的大预测误差，而人工物理引擎在新型初始条件和扰动下保持了低误差并保持稳定。按照运动方程来映射系统动力学，通过在人机接口设计中施加基于因果关系的物理结构，提高了对内在和外在变异性源的鲁棒性。

## Abstract
Seamless interaction between humans and machines requires interfaces that remain robust to the variability inherent in biological signals and physical environments. Advanced human-machine interfaces (HMIs) increasingly rely on machine learning to predict or control limb dynamics. These systems must learn input-to-output mappings between control variables and limb state, such as the mapping from muscle forces or joint torques acting about segmented arm joints to limb posture over time. Such statistical input-to-output transformations can result in numerical instability of predicted musculoskeletal kinematics and dynamics. Achieving the robustness of biological motor control requires solving both forward and inverse dynamics problems; however, these problems are computationally asymmetric because they entail opposing operations-integration and differentiation. Since we have previously shown that neural networks solve the inverse dynamics problem when trained to map kinematic to dynamic signals during reaching, we hypothesized that representing separately the approximation of equations of motion (EOM) and their temporal numerical integration may capture the relevant computational structure of the forward dynamics problem. We tested this hypothesis by comparing a conventional direct-mapping recurrent neural network (RNN) with a two-stage model, the artificial physics engine (APE). When predicting the state of a two-segment system under external perturbations not encountered during training, the direct-mapping, monolithic model produced large prediction errors inconsistent with the expected interaction torque, whereas the APE maintained low error and remained stable under novel initial conditions and perturbations. Mapping system dynamics in the terms of the EOM improves robustness against intrinsic and extrinsic sources of variability by imposing a causal, physics-based structure on HMI design.