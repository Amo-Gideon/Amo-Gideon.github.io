---
title: "When Reactive Policies Fail: Obstacle-Aware CEM Planning with Learned World Models"
summary: A learned MLP-ensemble world model plus a CEM planner beats PPO on robot-arm reaching, stays robust under OOD dynamics, and solves obstacle avoidance that PPO never learned.
date: 2026-08-18
draft: false

authors:
  - me

tags:
  - Reinforcement Learning
  - World Models
  - Robotics
---

I spent part of this summer trying to answer a simple question: on a PyBullet 2-link robot
arm, is a learned reactive policy (PPO) enough for manipulation, or do you actually need
planning? The short answer — planning wins, and it's not close.

## The baseline

PPO reliably solved single-target reaching at **82–83% success**. That looks fine until
you stress it. Training an obstacle-avoidance variant failed across **five different PPO
configurations** — blind observations, reward shaping for passivity, contact penalties.
The arm either never saw the obstacle in its observation space, learned to sit passively
and collect reward, or got trapped in contact-rich local optima.

## World model + CEM

Instead, I learned an ensemble of MLP dynamics models and planned with the
Cross-Entropy Method (MPC-style, replanning every step). Results on the same task:

- **100% success vs PPO's 83%** on standard reaching.
- **Still 100%** under out-of-distribution shifts (mass ×2, gravity ×1.5, torque ×0.5).
  PPO collapsed into near-miss stalls. Replanning every step absorbs model error that a
  frozen policy cannot.
- Multi-target waypoint sequencing: **66%**.
- Obstacle avoidance as a **CEM planning cost** (clearance penalty) cut the contact rate
  from 57% to 23% and lifted success to **57%, vs 0–13% for PPO**.

The takeaway: when a task is really a *constraint-satisfaction* problem, constraint-aware
MPC beats learned reflexes. A policy has to discover obstacle avoidance by accident;
a planner gets to encode it.

## Honest limits

This isn't free. Residual contact still happens **23%** of the time, and CEM planning
costs roughly **20 seconds per episode** — fine for offline evaluation, not for real-time
control. Faster planners (MPPI, learned proposals) and better world models are the next
steps.

Code: [github.com/Amo-Gideon/rl-portfolio](https://github.com/Amo-Gideon/rl-portfolio)
