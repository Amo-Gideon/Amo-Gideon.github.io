---
title: "Class-Adaptive Focal Sharpness-Aware Minimization for Long-Tailed Visual Recognition"
collection: publications
category: manuscripts
permalink: /publication/2026-ca-focal-sam
excerpt: 'CA-Focal-SAM redistributes sharpness-aware minimization at the optimizer level: a frequency-conditioned GammaAdaptor assigns per-class focal parameters, improving tail-class accuracy by 6.03% on CIFAR-10-LT (IR=200) with no architectural change and zero inference overhead.'
date: 2026-06-01
venue: 'Manuscript in preparation (target: CVPR)'
paperurl: 'https://github.com/Amo-Gideon/sfca-ltr'
citation: 'Appau, Gideon Kofi Amo, and Wang, Pengkun. (2026). &quot;Class-Adaptive Focal Sharpness-Aware Minimization for Long-Tailed Visual Recognition.&quot; <i>Manuscript in preparation</i>.'
---

Standard Sharpness-Aware Minimization applies a uniform perturbation to all classes and ignores how training-data scarcity changes optimization difficulty. CA-Focal-SAM instead adapts how class contributions enter the nominal and perturbed gradient components of SAM:

* **GammaAdaptor** — just 2 learnable scalars map class frequency to per-class focal parameters, so rare classes receive a larger effective SAM weight.
* **Quadratic perturbation-radius curriculum** — a smooth \\(\rho(t)\\) schedule that yields flatter minima, verified by Hessian spectral analysis (\\(\lambda_{\max}\\) 114.7 vs. Focal-SAM 121.4 via stochastic Lanczos quadrature).

Evaluated with a pre-registered multi-seed protocol (3 seeds, mean ± std) on CIFAR-10/100-LT, ImageNet-LT, and CUB-200-LT, with 20+ qualitative analyses (t-SNE embeddings, 2D/3D loss landscapes, confusion matrices). Code and experiment logs: [github.com/Amo-Gideon/sfca-ltr](https://github.com/Amo-Gideon/sfca-ltr).
