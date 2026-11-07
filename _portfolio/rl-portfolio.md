---
title: "RL Research Portfolio: World-Model Control of a Robot Arm"
excerpt: "Self-directed reinforcement-learning research on a PyBullet 2-link robot arm: model-free PPO vs a learned world model (MLP ensemble) with CEM planning - 100% vs 82% success, 100% vs 70-80% under OOD physics shifts - plus DQN reproductions, an RLHF pipeline, and a language-guided navigation agent."
collection: portfolio
---

A self-directed research portfolio ([github.com/Amo-Gideon/rl-portfolio](https://github.com/Amo-Gideon/rl-portfolio)) exploring decision-making from model-free control to world-model planning. The flagship project, summarized README-style below, is the robot-arm comparison; the repo also contains [Dueling/Double DQN reproductions from scratch](https://github.com/Amo-Gideon/rl-portfolio/tree/main/01-dueling-dqn-pytorch), an [end-to-end RLHF pipeline](https://github.com/Amo-Gideon/rl-portfolio/tree/main/modern-rlhf) (SFT, reward model, PPO alignment for a 0.5B LM), and a [language-guided navigation agent](/portfolio/language-guided-navigation).

## Task

A planar 2-link robot arm must reach random target points. Two environment implementations share the same task, reward, and interface: a kinematic env (pure forward kinematics) and a dynamics env (PyBullet URDF with real masses, gravity, and a torque-saturated PD servo at 60/240 Hz), so conclusions can be checked against physically real overshoot, settle time, and actuator saturation.

## Methods

* **Model-free**: PPO via Stable-Baselines3 (250k-500k timesteps, CPU) and a from-scratch PPO (Gaussian actor-critic, GAE, clipped surrogate) written in plain PyTorch.
* **Model-based**: 60k transitions collected from the trained PPO policy plus epsilon-random exploration; an ensemble of 5 MLPs learns the dynamics; a CEM planner (400 candidates x 3 iterations, MPC-style, re-planning every step) scores rollouts with the environment reward.

## Results

* **Single-target reaching** (100 shared held-out episodes): CEM 100.0% success vs PPO 83.0%; CEM final distance 0.055 +- 0.017 vs 0.114 +- 0.138, at ~160x more wall time per step - the textbook accuracy/speed tradeoff.
* **OOD physics robustness** (20 episodes per condition, nothing retrained on perturbed physics): CEM holds 100% under doubled link mass, 1.5x gravity, halved torque limit, and halved servo gains; PPO drops to 70-80%. Replanning every step absorbs model error that a frozen policy cannot.
* **Planning-horizon ablation** (30 episodes): horizon 10 dominates (100% success, fastest convergence, 2.5x cheaper than H=20), matching the rollout-error curve - extra horizon buys compute, not accuracy.
* **Obstacle avoidance** (30 episodes, 2 cylinders, 3-waypoint tasks): a clearance cost term inside the planner cuts contact rate from 57% to 23% and attains 57% task success, where five PPO training configurations (0-13%) all failed after a documented debugging trail (blind observations, reward passivity, contact trap basins).
* **Multi-waypoint sequencing and a mini-VLA**: PPO transfers zero-shot to ordered waypoint lists (60% all-waypoint success), and a Qwen2.5-0.5B language planner grounds natural-language instructions into JSON waypoint sequences for the control stack.

## Evaluation protocol

Results are reported over held-out evaluation episodes rather than training seeds: 100 episodes (single-target), 20 episodes per OOD condition, and 30 episodes (waypoint/obstacle tasks). Evaluation configs, checkpoints, and raw metrics are in the repo's `outputs/` and `scripts/`.

Code, training logs, plots, and before/after comparisons: [github.com/Amo-Gideon/rl-portfolio](https://github.com/Amo-Gideon/rl-portfolio) (MIT license).
