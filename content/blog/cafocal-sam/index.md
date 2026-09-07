---
title: "From Focal-SAM to CA-Focal-SAM: Making Sharpness-Aware Minimization Class-Adaptive"
summary: SAM's uniform perturbation radius mistreats tail classes in long-tailed recognition. A tiny two-parameter GammaAdaptor that maps class frequency to focal parameters fixes it — +6.03% tail accuracy on CIFAR-10-LT (IR = 200).
date: 2026-06-15
draft: false

authors:
  - me

tags:
  - Long-Tailed Learning
  - Optimization
  - Computer Vision
---

## The problem

In long-tailed recognition, a few head classes dominate the data while hundreds of tail
classes see only a handful of examples. Sharpness-Aware Minimization (SAM) improves
generalization by seeking flat minima — it perturbs parameters to find weights that keep
the loss low under worst-case perturbation. But SAM applies a **uniform perturbation
radius to every class**. Head classes, with thousands of samples, don't need aggressive
regularization; tail classes, with a few dozen, do. One-size-fits-all flattens the wrong
things.

## The idea: a GammaAdaptor

Our fix is almost embarrassingly small. A **GammaAdaptor** is a two-parameter module that
takes a class's frequency and outputs the focal loss parameters for that class, so SAM's
sharpness objective is modulated per class. Frequent classes keep their capacity; rare
classes get flattened harder. Two parameters means negligible cost and no inference
overhead — the adaptor only shapes training.

We also added a **quadratic curriculum on the perturbation radius**: start conservative,
widen the perturbation as training stabilizes. Early-training SAM with a large radius was
one of the main instability sources we observed.

## Results

- **+6.03% tail accuracy on CIFAR-10-LT (IR = 200)**, with head accuracy preserved.
- **Hessian verification:** largest eigenvalue of the loss landscape drops from 121.4
  (SAM baseline) to **114.7** — CA-Focal-SAM genuinely lands in flatter minima, not just
  different ones.
- A **99-run local audit** across configurations confirmed the gains are stable, not a
  lucky seed.

## Current status

This work is my M.S. research at USTC with my advisor Pengkun Wang, and the manuscript is
in preparation — full ImageNet-LT and CIFAR-100-LT results, ablations, and theory will
land there first. Code is at
[github.com/Amo-Gideon/sfca-ltr](https://github.com/Amo-Gideon/sfca-ltr).

The broader lesson I'd take away: a lot of "uniform" training recipes implicitly assume
balanced data. Long-tailed learning is often about identifying which knobs were never
meant to be uniform in the first place.
