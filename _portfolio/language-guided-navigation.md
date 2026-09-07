---
title: "Language-Guided Navigation Agent"
excerpt: "A 0.5B-parameter language model that learns to follow natural-language navigation instructions and answer questions about what it finds - built with an RLHF-style recipe in miniature: LoRA SFT on BFS expert demonstrations, then REINFORCE with a KL penalty against a frozen reference."
collection: portfolio
---

An end-to-end language-agent project ([github.com/Amo-Gideon/rl-portfolio/language-guided-navigation](https://github.com/Amo-Gideon/rl-portfolio/tree/main/language-guided-navigation)): a Qwen2.5-0.5B-Instruct model learns to act in a custom text-based grid world, following instructions like *"Go to the red house and report its color"* and emitting structured JSON actions (`move_forward`, `turn_left`, `turn_right`, `look`, `answer`).

* **Environment**: a deterministic grid world with landmarks and verifiable, decomposed rewards (answer accuracy, format validity, action validity)
* **SFT stage**: LoRA fine-tuning on shortest-path expert trajectories generated with BFS
* **RL stage**: REINFORCE with mean baseline and a KL penalty against a frozen reference model - the same SFT-then-RL recipe as large-scale RLHF, reproduced from scratch
* **Results**: success rate improves from 9/20 (45%) after SFT to 11/20 (55%) after RL fine-tuning, with seeded evaluation for reproducibility

Honest current limits, documented in the repo README: the 15-step episode cap and sparse reward leave headroom (the agent sometimes wanders before locating the target).
