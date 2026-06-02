---
title: Using timescale as a state coordinate reveals the metastable geometry of behavior
title_zh: 使用时间尺度作为状态坐标揭示行为的亚稳态几何结构
authors: "Kaur, R., Jain, K., Berman, G. J."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727718v1.full.pdf"
tags: ["query:da"]
score: 6.0
evidence: 时频状态空间方法分析行为时间尺度，可应用于舞蹈动作分析
tldr: 动物行为跨越多个时间尺度，慢变量（如饥饿、觉醒）难以直接测量。本文提出将时间尺度本身作为状态坐标，构建时频状态空间，通过转移算子的前导特征向量同时表达快慢模式。在合成系统、线虫运动和果蝇行为中，该方法揭示了亚稳态盆地表现为从固定权重中心辐射的线性臂结构，并重现了已知行为组织。该框架提供了一种从部分观测时间序列中提取集体慢模式的通用方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 动物行为中的慢变量难以直接测量，而传统固定时间尺度分析无法分离慢模式。
method: 将时间尺度作为状态坐标，构建时频状态空间，利用转移算子的特征向量揭示多时间尺度动力学。
result: 在三个系统中，亚稳态盆地表现为从静止加权中心辐射的线性臂，且慢模式具有重尾分布停留时间。
conclusion: 将时间尺度作为状态坐标可揭示行为的慢组织几何结构，无需预先分解为离散事件。
---

## 摘要
动物行为在多个时间尺度上展开，从快速运动模式到内部状态（如饥饿、觉醒和昼夜节律相位）的缓慢变化。这些慢变量很少被直接测量，而必须通过它们对可观测的快速运动的影响来推断。这里我们提出将时间尺度本身作为状态表示的显式坐标，构建一个时间-频率状态空间，其中快速运动和缓慢调制同时出现。我们发现，慢模式表现为从转移算子的前几个非平凡特征向量中的一个固定加权中心辐射出的线性臂，在三个复杂度递增的系统中，每个亚稳态盆地对应一个臂。在一个合成系统中，该框架恢复了跨越近三个数量级停留时间的隐藏双稳态驱动器，而对同一轨迹的固定时间尺度分析则未发现可分离的慢模式。在线虫运动中，它再现了经典的奔跑-旋转组织。在自由活动的果蝇中，快速腿部运动学比它们构成的行为状态快几个数量级，多时间尺度算子直接从姿势时间序列中识别出四个亚稳态行为盆地，而无需首先分解为一系列刻板动作。我们进一步发现，这些盆地表现出宽尾的停留时间分布。因此，将时间尺度作为状态坐标，揭示了行为慢组织的可预测几何形式，为从部分观测的生物时间序列中提取集体模式提供了一条通用途径，而无需先将动态组织成离散事件。

## Abstract
Animal behavior unfolds across many timescales, from fast movement patterns to slow changes in internal states such as hunger, arousal, and circadian phase. These slow variables are rarely measured directly and must instead be inferred from their effects on the faster movements that can be observed. Here we propose treating timescale itself as an explicit coordinate of the state representation, constructing a time-frequency state space where fast movements and slow modulations appear simultaneously. We find that slow modes emerge as linear arms radiating from a stationary-weighted hub in the leading non-trivial eigenvectors of the transfer operator, with one arm per metastable basin across three systems of increasing complexity. In a synthetic system, the framework recovers a hidden bistable driver across nearly three decades of dwell time, while a fixed-timescale analysis of the same trajectory finds no separable slow modes. In nematode locomotion, it reproduces the canonical run-pirouette organization. In freely moving fruit flies, where fast leg kinematics are orders of magnitude faster than the behavioral states they compose, the multi-timescale operator identifies four metastable behavioral basins directly from the postural time series, without first decomposing into a sequence of stereotyped actions. We further find that these basins exhibit a broad, heavy-tailed distribution of residence times. Treating timescale as a state coordinate thus exposes a predictable geometric form for the slow organization of behavior, providing a general route for extracting collective modes from partially observed biological time series without first organizing the dynamics into discrete events.