---
title: CA-Focal-SAM
date: 2026-06-15
links:
  - type: site
    url: https://github.com/Amo-Gideon/sfca-ltr
tags:
  - Long-Tailed Learning
  - Optimization
  - Computer Vision
---

Class-adaptive Sharpness-Aware Minimization for long-tailed visual recognition: a tiny
GammaAdaptor maps class frequency to per-class focal parameters, so SAM's perturbation
radius is modulated per class instead of one-size-fits-all.

<!--more-->

Key components and results:

- **GammaAdaptor:** a two-parameter module mapping class frequency to focal loss
  parameters, adapting SAM's sharpness objective per class at negligible cost.
- **Quadratic curriculum** on the perturbation radius to stabilize early training.
- **+6.03% tail accuracy** on CIFAR-10-LT (IR = 200) with head accuracy preserved.
- **Hessian-verified flatness:** largest eigenvalue 114.7 vs 121.4 for the SAM baseline.
- Verified across a **99-run local audit**; no inference-time overhead.
- Manuscript in preparation.
