---
title: Effect-oriented automated muscle path modeling via gradient-specified optimization using muscle surface mesh and moment arm
title_zh: 基于肌肉表面网格和力矩臂的梯度指定优化的面向效果的自动化肌肉路径建模
authors: "Chen, Z., Hu, T., Haddadin, S., Franklin, D. W."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.15.718668v2.full.pdf"
tags: ["query:db"]
score: 6.0
evidence: 提供可用于舞蹈生物力学的肌肉路径建模方法
tldr: 传统肌肉路径建模仅关注几何特征，未能保证长度和力矩臂-关节角关系的模拟精度，影响生物力学仿真可靠性。本文提出效应导向的自动化路径建模方法，利用肌肉表面网格和实验力矩臂数据，通过混合标定构建三目标优化：路径穿过椭圆截面、力矩臂匹配实验值、力矩臂符号正确。采用梯度指定优化求解，在可见人体男性网格和文献力矩臂数据集上，42条肌肉路径在20.1分钟内完成建模，解剖真实且力矩臂曲线与实验吻合。梯度指定方法比默认数值梯度更快速准确，适用于大规模个性化模型构建。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统肌肉路径建模仅关注几何特征，无法确保仿真所需的长度-力矩臂关系准确性，需面向效果优化。
method: 基于肌肉表面网格和力矩臂数据，提出三目标优化：路径穿过椭圆截面、力矩臂匹配实验值、力矩臂符号正确，采用梯度指定优化求解。
result: 在可见人体男性网格和文献数据上，42条路径平均20.1分钟完成建模，解剖真实且力矩臂曲线与实验吻合。
conclusion: 梯度指定优化比默认数值梯度更快更准，适用于大规模个体化肌肉路径建模。
---

## 摘要
肌腱路径建模不仅仅是调整一条线以反映肌肉-肌腱单元的几何特征。从模拟准确性的角度来看，关键在于复制目标肌肉的长度-关节角度关系和力矩臂-关节角度关系。在本研究中，我们提出了一种面向效果的自动化路径建模方法，通过基于肌肉表面网格和力矩臂的混合校准。任务被表述为一个优化问题，具有三个目标：1）路径穿过代表肌肉横截面的多个椭圆，2）产生与实验测量匹配的力矩臂，3）产生具有指定符号的力矩臂。我们的优化框架的性能通过来自可见人体男性的肌肉骨骼表面网格和文献中的力矩臂数据集得到证明——在20.1分钟内生成42条解剖学上真实且生物力学上准确的路径。我们的优化框架是梯度指定的，这比使用默认数值梯度更快、更准确，使其适用于大规模特定于个体的应用。

## Abstract
There is more to musculotendon path modeling than aligning a cable to reflect the geometric features of a muscle-tendon unit. From the perspective of simulation accuracy, the key is to replicate the length- and moment arm-joint angle relations of the target muscle. In this study, we propose an effect-oriented approach of automated path modeling, via hybrid calibration based on muscle surface mesh and moment arm. The task is formulated as an optimization problem with a threefold objective for the path to: 1) pass through multiple ellipses representing muscle cross-sections, 2) yield moment arms that match experimental measurements, and 3) yield moment arms with the designated signs. The performance of our optimization framework is demonstrated with the musculoskeletal surface mesh from the Visible Human Male and moment arm datasets from literature--producing 42 paths that are anatomically realistic and biomechanically accurate in 20.1 min. Our optimization framework is gradient-specified, which is faster and more accurate than using the default numerical gradient, making it applicable for large-scale subject-specific uses.