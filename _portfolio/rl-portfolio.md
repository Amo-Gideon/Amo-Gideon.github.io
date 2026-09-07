---
title: "RL Research Portfolio"
excerpt: "Self-directed reinforcement-learning research: DQN reproductions from scratch, an end-to-end RLHF pipeline for a 0.5B language model, and a learned world model (MLP ensemble) with CEM planning that reaches 100% success on a PyBullet robot arm and stays robust where PPO fails."
collection: portfolio
---

A self-directed research portfolio ([github.com/Amo-Gideon/rl-portfolio](https://github.com/Amo-Gideon/rl-portfolio)) exploring decision-making from tabular RL to world-model planning:

* Reproduced **Dueling/Double DQN** from scratch, with ablations on target-network updates and exploration schedules.
* Built an end-to-end **RLHF pipeline** (SFT, reward model, PPO alignment) for a 0.5B-parameter language model.
* On a PyBullet 2-link robot arm, **PPO reaches 82% single-target success** while a learned world model (MLP ensemble) with **CEM planning reaches 100%**, and stays robust under out-of-distribution physics shifts.
* **Obstacle avoidance as a CEM cost term** cut collision rates from 57% to 23% in a setting where five PPO training configurations failed.
