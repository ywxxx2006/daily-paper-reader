---
title: "TracktorLive: an integrated real-time object tracking and response system"
title_zh: TracktorLive：一个集成的实时目标跟踪与响应系统
authors: "Minasandra, P., Sridhar, V. H., Roche, D. G., Planas-Sitja, I."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.12.711471v2.full.pdf"
tags: ["query:da"]
score: 7.0
evidence: 提供可用于舞蹈动作分析的运动捕捉实时追踪开源系统
tldr: 实时跟踪和自动响应系统对行为研究至关重要，但现有方案存在硬件成本高、计算延迟大、学习曲线陡等问题。TracktorLive通过并发架构和模块化cassette设计，利用传统计算机视觉实现低延迟实时跟踪与响应。在鱼类刺激传递测试中，其响应精度和稳定性优于人类实验者。该开源软件降低了实时闭环实验的门槛，可广泛应用于神经科学、野生动物管理等领域。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决现有实时跟踪系统硬件昂贵、延迟高、使用门槛高的问题，实现廉价高效的闭环实验。
method: 采用传统计算机视觉进行对象检测，通过并发服务端和客户端并行化跟踪与响应，利用可复制粘贴的cassette简化工作流。
result: 在鱼类刺激传递任务中，TracktorLive的响应准确性和一致性优于人类实验者，尤其对快速移动目标。
conclusion: TracktorLive作为开源软件，凭借其易用性、模块化和高效性，促进了实时跟踪系统的跨学科普及。
---

## 摘要
实时跟踪与自动响应系统对于标准化实验、减少观察者偏差以及提高运动和行为研究的可重复性至关重要。然而，现有解决方案面临重大挑战：基于人工智能的跟踪系统需要昂贵的硬件并带来计算延迟，给闭环实验带来困难；现有的实时跟踪工具缺乏标准化的响应交付实现；陡峭的学习曲线限制了没有编程或计算机视觉专业知识的用户的可及性。在这里，我们介绍TracktorLive，这是一个开源Python包，旨在通过并发和模块化的、基于脚本模块（cassette）的架构来克服这些挑战。TracktorLive利用传统计算机视觉技术进行基于图像的目标检测，无需昂贵的硬件或深度学习。通过将目标跟踪和响应交付并行化为独立的并发服务器和客户端进程，该软件最小化了帧处理时间，实现了快速的实时分析和响应交付。用户友好的脚本模块——可复制粘贴到脚本中的便携式代码片段——使具有最少编程经验的用户能够实现用于实验和实际应用的复杂工作流程。我们通过多个应用展示了TracktorLive的实用性，包括基于微控制器的刺激传递用于位置依赖性操作；仅在感兴趣事件期间激活的条件视频记录；使用实时速度计算的基于运动学的响应触发；以及结合多种功能的多脚本模块实验设计。提供了详细的教程，以使用户熟悉TracktorLive的操作和功能，并且不断增长的脚本模块库支持处理实时和预录制视频的各种应用。我们通过涉及两种鱼类的刺激传递任务，将其响应时间与人类实验者进行比较来验证该软件，其中TracktorLive表现出始终更高的准确性和更低的变异性，特别是对于快速移动的受试者。除了实验生物学，TracktorLive独特的架构和多功能性可以支持从神经科学到野生动物管理等领域的许多不同应用。作为结合了可访问性、模块化和计算效率的开源软件，TracktorLive有助于跨学科实现实时跟踪和自动响应系统的民主化。

## Abstract
Real-time tracking and automated response systems are essential for standardising experiments, reducing observer bias, and improving reproducibility in studies of movement and behaviour. However, existing solutions face significant challenges: AI-based tracking systems require expensive hardware and impose computational delays, creating challenges for closed-loop experiments; existing real-time tracking tools lack standardised implementations for response delivery; and steep learning curves limit accessibility for users without programming or computer vision expertise. Here, we introduce TracktorLive, an open-source Python package designed to overcome these challenges through concurrency and a modular,  cassette-based architecture. TracktorLive leverages traditional computer vision techniques to perform image-based object detection without the need for expensive hardware or deep learning. By parallelizing object tracking and response delivery into separate, concurrent server and client processes, the software minimizes frame processing time, enabling rapid, real-time analysis and response delivery. User-friendly  cassettes--portable code snippets that can be copy-pasted into scripts--enable users with minimal programming experience to implement complex workflows for use in experiments and practical applications. We demonstrate TracktorLives utility through several applications, including microcontroller-based stimulus delivery for location-dependent manipulations; conditional video recording that activates only during events of interest; kinematic-based response triggering using real-time velocity computations; and multi-cassette experimental designs combining multiple functionalities. Detailed tutorials are provided to familiarize users with TracktorLives operation and functionality, and a growing library of cassettes supports diverse applications for processing both real-time and pre-recorded video. We validated the software by comparing its response timing to human experimenters in a stimulus delivery task involving two fish species, where TracktorLive demonstrated consistently higher accuracy and lower variability, particularly for fast-moving subjects. Beyond experimental biology, TracktorLives unique architecture and versatility could support many different applications in fields ranging from neuroscience to wildlife management. As an open-source software combining accessibility, modularity, and computational efficiency, TracktorLive can help democratize real-time tracking and automated response systems across disciplines.