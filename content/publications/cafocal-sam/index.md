---
title: "Class-Adaptive Focal Sharpness-Aware Minimization for Long-Tailed Visual Recognition"
authors:
- me
- Wang, Pengkun
date: "2026-01-15T00:00:00Z"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article"]

# Publication metadata — structured fields used by citation styles and BibTeX export.
# Preprints typically have no formal venue; omit `publication` until the work is accepted.

peer_reviewed: false

abstract: |
  Sharpness-Aware Minimization (SAM) finds flat minima that generalize better, but its
  uniform perturbation radius treats all classes equally — a poor fit for long-tailed
  recognition, where rare tail classes need stronger regularization than frequent head
  classes. We propose Class-Adaptive Focal Sharpness-Aware Minimization (CA-Focal-SAM),
  which modulates SAM per class via a GammaAdaptor, a tiny two-parameter module that maps
  class frequency to focal loss parameters. A quadratic curriculum on the perturbation
  radius stabilizes early training. CA-Focal-SAM improves tail-class accuracy on
  long-tailed benchmarks (CIFAR-10/100-LT, ImageNet-LT) with head accuracy preserved and
  no inference-time overhead.

# Summary. An optional shortened abstract.
summary: A class-adaptive variant of SAM that maps class frequency to per-class focal parameters via a tiny GammaAdaptor, improving tail accuracy on long-tailed benchmarks with no inference overhead.

tags:
- Long-Tailed Learning
- Sharpness-Aware Minimization
- Computer Vision

featured: true

links:
- type: code
  url: https://github.com/Amo-Gideon/sfca-ltr

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

**Status:** Manuscript in preparation.

CA-Focal-SAM replaces SAM's one-size-fits-all perturbation with a per-class schedule:
the GammaAdaptor reads each class's frequency and outputs focal parameters that scale the
sharpness objective, so tail classes are flattened more aggressively while head classes
keep their capacity. Combined with a quadratic curriculum on the perturbation radius and
Hessian-verified flatness checks, the method gains **+6.03% tail accuracy on CIFAR-10-LT
(IR = 200)** while preserving head accuracy, verified across a 99-run local audit.
