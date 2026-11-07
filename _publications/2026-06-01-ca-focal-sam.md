---
title: "Class-Adaptive Focal Sharpness-Aware Minimization for Long-Tailed Visual Recognition"
collection: publications
category: manuscripts
permalink: /publication/2026-ca-focal-sam
excerpt: 'CA-Focal-SAM redistributes sharpness-aware minimization at the optimizer level: a frequency-conditioned GammaAdaptor assigns per-class focal parameters, improving tail-class accuracy by 6.03% on CIFAR-10-LT (IR=200) with no architectural change and zero inference overhead.'
date: 2026-06-01
venue: "Master's thesis work (USTC, School of Software Engineering); manuscript in preparation"
paperurl: 'https://github.com/Amo-Gideon/sfca-ltr'
citation: 'Appau, Gideon Kofi Amo, and Wang, Pengkun. (2026). &quot;Class-Adaptive Focal Sharpness-Aware Minimization for Long-Tailed Visual Recognition.&quot; <i>Master&apos;s thesis work (USTC), manuscript in preparation</i>.'
---

Standard Sharpness-Aware Minimization applies a uniform perturbation to all classes and ignores how training-data scarcity changes optimization difficulty. CA-Focal-SAM instead adapts how class contributions enter the nominal and perturbed gradient components of SAM:

* **GammaAdaptor**: just 2 learnable scalars map class frequency to per-class focal parameters, so rare classes receive a larger effective SAM weight.
* **Quadratic perturbation-radius curriculum**: a smooth \\(\rho(t)\\) schedule that yields flatter minima, verified by Hessian spectral analysis (\\(\lambda_{\max}\\) 114.7 vs. Focal-SAM 121.4 via stochastic Lanczos quadrature).

Evaluated with a pre-registered multi-seed protocol on CIFAR-10/100-LT (the principal controlled study), with ImageNet-LT and Places-LT as exploratory single-seed screens, plus 20+ qualitative analyses (t-SNE embeddings, 2D/3D loss landscapes, confusion matrices). Code and experiment logs: [github.com/Amo-Gideon/sfca-ltr](https://github.com/Amo-Gideon/sfca-ltr).
