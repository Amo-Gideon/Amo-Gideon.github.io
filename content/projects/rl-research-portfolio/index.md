---
title: RL Research Portfolio
date: 2026-08-01
links:
  - type: site
    url: https://github.com/Amo-Gideon/rl-portfolio
tags:
  - Reinforcement Learning
  - World Models
  - Robotics
---

A collection of deep reinforcement learning projects and reproductions, including Dueling
and Double DQN, an RLHF pipeline for a 0.5B language model, and PPO for a PyBullet robot
arm.

<!--more-->

Highlights:

- Reproductions of Dueling and Double DQN on classic control and Atari benchmarks.
- An RLHF pipeline (reward model + PPO) fine-tuning a 0.5B parameter language model.
- PPO locomotion and manipulation for a PyBullet robot arm (82–83% success on a
  single-target reaching task).
- Model-based control with a learned MLP-ensemble world model + CEM/MPC planner:
  **100% success vs PPO's 83%**, and still 100% under out-of-distribution shifts
  (mass ×2, gravity ×1.5, torque ×0.5) because replanning absorbs model error.
- Obstacle-aware CEM planning, where obstacle clearance as a planning cost cut the
  contact rate from 57% to 23% and lifted success to 57% vs PPO's 0–13%.
- A language-conditioned mini-VLA using a Qwen2.5-0.5B planner to translate natural
  language instructions into low-level robot actions.
