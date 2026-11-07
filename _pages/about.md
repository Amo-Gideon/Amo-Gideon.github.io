---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am **Gideon Kofi Amo Appau**, a master's student in Software Engineering (AI/ML) at the [University of Science and Technology of China (USTC)](https://en.ustc.edu.cn), advised by [Assoc. Res. Pengkun Wang](http://home.ustc.edu.cn/~pengkun/index.html), and a Chinese Government Scholarship (CSC) recipient. Previously, I earned a B.Sc. in Information Technology Education (First Class Honours, Top 10%) from the University of Education, Winneba, Ghana.

My research centers on **reinforcement learning and learning under data scarcity**. For my master's thesis I studied class-adaptive sharpness-aware minimization for long-tailed visual recognition: [CA-Focal-SAM](/publication/2026-ca-focal-sam) redistributes SAM's per-class emphasis through a frequency-conditioned GammaAdaptor, and a frozen log-scarcity prior distilled from it improves tail-class accuracy over Focal-SAM by 2.50 percentage points at CIFAR-100-LT imbalance ratio 100 and 1.98 points at IR=200 (4 fixed seeds each, zero inference overhead). Its [SFCA](/publication/2026-sfca) extension adds online, geometry-driven feedback; evaluated under a pre-specified falsification protocol (polarity under two outer losses, signal-destruction controls, a hindsight-oracle bound, and class-level regression), the feedback carried no measurable information — the gains trace to the frozen scarcity prior. Alongside the thesis, I maintain a [self-directed RL portfolio](/portfolio/): on a PyBullet 2-link robot arm, a learned world model (MLP ensemble) with CEM planning reaches 100% single-target success where PPO reaches 82%, and holds 100% under out-of-distribution physics shifts (doubled link mass, 1.5x gravity, halved torque limits) that reduce PPO to 70-80%; obstacle clearance as a planning cost cuts collision rates from 57% to 23% where five PPO training configurations failed.

**I am seeking funded PhD opportunities for Spring/Fall 2027** in reinforcement learning — continual and long-horizon RL, world models, and model-based control — and machine learning more broadly. Here is my [CV](/cv/) ([PDF](/files/Appau_Gideon_CV.pdf)).

Research interests
======
* Continual and long-horizon reinforcement learning; world models and model-based RL for embodied AI
* Efficient and robust optimization: sharpness-aware minimization and long-tailed visual recognition
* LLM agents, retrieval-augmented generation, and RLHF

News
======
* **Oct 2026** - Completed a pre-registered falsification study of SFCA's online feedback channel: null polarity under two outer losses, signal-destruction controls indistinguishable from intact feedback, and a hindsight-oracle bound below the frozen prior. The CIFAR experiment program is complete (~200 runs under a uniform recipe).
* **Aug 2026** - Completed a CIFAR-100-C corruption-robustness evaluation (exploratory, pre-uniform-recipe checkpoints); the SAM family shows large calibration advantages over reweighting baselines (ECE in the low single digits vs ~15%).
* **Jun 2026** - Completed mechanism-level study of CA-Focal-SAM on CIFAR-100-LT across imbalance ratios 50/100/200 with CE, Logit Adjustment, and LDAM outer objectives.
* **Mar 2026** - Added obstacle-avoidance CEM costs to the robot-arm world-model planner; collision rate drops from 57% to 23% where five PPO training configurations fail.
* **2024** - Started M.S. at USTC as a Chinese Government Scholarship (CSC) recipient.
