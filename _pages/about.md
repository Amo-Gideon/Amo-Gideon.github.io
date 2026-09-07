---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am **Appau Gideon Kofi Amo**, a master's student in Software Engineering (AI/ML) at the [University of Science and Technology of China (USTC)](https://en.ustc.edu.cn), advised by [Assoc. Res. Pengkun Wang](http://home.ustc.edu.cn/~pengkun/index.html), and a Chinese Government Scholarship (CSC) recipient. Previously, I earned a B.Sc. in Information Technology Education (First Class Honours, Top 10%) from the University of Education, Winneba, Ghana.

My research sits at the intersection of **optimization and efficient learning**. For my master's thesis I study class-adaptive sharpness-aware minimization for long-tailed visual recognition: [CA-Focal-SAM](/publication/2026-ca-focal-sam) redistributes SAM's per-class emphasis through a frequency-conditioned GammaAdaptor, and its [SFCA](/publication/2026-sfca) extension adds online, geometry-driven feedback from SAM's own ascent step, improving tail-class accuracy on CIFAR-100-LT (IR=200) from 22.45% to 24.49% with zero inference overhead. Alongside this, I maintain a [self-directed reinforcement-learning portfolio](/portfolio/), where a learned world model with CEM planning reaches 100% success on a robot-arm control task and stays robust under out-of-distribution physics shifts.

**I am seeking funded PhD opportunities for Spring/Fall 2027** in efficient AI, long-tailed/computer vision, and world models & embodied AI. Here is my [CV](/cv/) ([PDF](/files/Appau_Gideon_CV.pdf)).

Research interests
======
* Efficient and robust optimization: sharpness-aware minimization and long-tailed visual recognition
* World models and model-based reinforcement learning for embodied AI
* LLM agents, retrieval-augmented generation, and human feedback alignment

News
======
* **Aug 2026** - SFCA (Sharpness-Feedback Classwise Allocation) validated on CIFAR-100-C: strongest corrupted tail accuracy among compared checkpoints.
* **Jun 2026** - Completed mechanism-level study of CA-Focal-SAM on CIFAR-100-LT across imbalance ratios 50/100/200 with CE, Logit Adjustment, and LDAM outer objectives.
* **Mar 2026** - Added obstacle-avoidance CEM costs to the robot-arm world-model planner; collision rate drops from 57% to 23% where five PPO training configurations fail.
* **2024** - Started M.S. at USTC as a Chinese Government Scholarship (CSC) recipient.
