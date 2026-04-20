# Uncertainty Quantification × Clinical Decision Making

[← Back to Wiki Index](../Wiki.md)

---

> *Why knowing what you don't know is the most important capability for medical AI*

## The Core Problem

Medical AI faces a unique challenge: **the cost of errors is asymmetric and extreme**. A false negative (missing a tumor) can be fatal. A false positive (unnecessary surgery) is harmful. A confident wrong prediction is worse than an honest "I don't know."

This intersection brings together Bayesian methods, conformal prediction, and normative modeling to address: **When should a model defer to a human expert?**

---

## Bayesian Deep Learning in Medicine

### Why Bayesian?
Standard neural networks output point predictions with no indication of confidence. Bayesian neural networks maintain distributions over weights, producing **calibrated uncertainty estimates** for every prediction.

### The Methods Stack

1. **Full Bayesian inference** ([Gelman et al. textbook](http://www.stat.columbia.edu/~gelman/book/)): The gold standard — posterior over all parameters. Computationally intractable for deep networks.

2. **Variational inference** ([Blei et al., 2017](https://arxiv.org/abs/1601.00670), Kucukelbir [ADVI](https://arxiv.org/abs/1603.00788)): Approximate the posterior with a simpler distribution. Scales to deep networks but approximation quality varies.

3. **SWAG** ([Maddox et al., 2019](https://arxiv.org/abs/1902.02476)): Approximates the posterior using SGD trajectory statistics — essentially free, since it uses information already computed during standard training.

4. **Posterior Networks** ([Charpentier et al., 2020](https://arxiv.org/abs/2006.09239)): Predict parameters of an evidence distribution in a single forward pass — no sampling needed at inference time. Maps inputs to Dirichlet distributions for classification.

5. **Deep Langevin dynamics** ([Welling & Teh, 2011](https://icml.cc/2011/papers/398_icmlpaper.pdf) / [Saatçi & Wilson, 2017](https://arxiv.org/abs/1705.09558)): Use stochastic gradient Langevin dynamics to sample from the true posterior — theoretically grounded but requires careful tuning.

### Application to Healthcare

**Uncertainty-Aware Healthcare** papers demonstrate that:
- Models should **abstain** when uncertainty is high, routing to human experts
- **Epistemic uncertainty** (model doesn't know) vs. **aleatoric uncertainty** (data is inherently noisy) require different responses
- **Calibration** — the predicted probability should match the true frequency of outcomes

---

## Conformal Prediction: Distribution-Free Guarantees

**The fundamental limitation of Bayesian methods**: they require assumptions about the data distribution and the model posterior. If these assumptions are wrong, the uncertainty estimates are unreliable.

**Conformal prediction** provides **distribution-free** coverage guarantees:
- Given a desired confidence level α, conformal prediction produces prediction sets that contain the true label with probability ≥ 1−α
- No distributional assumptions required
- Works with **any** base model (neural network, random forest, etc.)

**For clinical applications**: Instead of "this patient has a 78% chance of Alzheimer's," conformal prediction says "with 95% confidence, this patient's diagnosis is one of: {mild cognitive impairment, early Alzheimer's, normal aging}." The prediction **set size** indicates uncertainty — larger sets mean more uncertainty.

---

## Normative Modeling as Clinical Uncertainty

**Normative models** ([Marquand et al., 2019](https://arxiv.org/abs/1902.04689), [Kia et al., 2018](https://arxiv.org/abs/1811.05943)) reframe clinical diagnosis as uncertainty quantification:

- Train a model of **normal brain variation** as a function of age, sex, and other covariates
- For a new patient, compute how many standard deviations they fall from the normative trajectory
- **The z-score at each brain region IS an uncertainty statement**: z = 0 means "exactly as expected," |z| > 2 means "clinically unusual"

**The connection to Bayesian methods**: Gaussian Process normative models directly provide posterior uncertainty. Deep learning normative models (VAEs, AAEs) provide approximate uncertainty through reconstruction error or latent space distances.

**Multi-task GP** ([Kia et al., 2018](https://arxiv.org/abs/1811.05943)): Models multiple brain regions jointly, capturing correlations. If the hippocampus is atrophied, the entorhinal cortex is likely atrophied too — this correlation **reduces uncertainty** in prediction.

---

## Out-of-Distribution Detection in Clinical Settings

A model trained on one scanner/population may encounter patients from a different demographic or scanner. OOD detection asks: **is this input from the same distribution as training data?**

- **Energy-based models** ([Grathwohl et al., 2020](https://arxiv.org/abs/1912.03263)): The model's energy function provides a natural OOD score
- **WAIC** (Watanabe 2010, [Nalisnick et al., 2019](https://arxiv.org/abs/1810.09136)): Information criterion that detects OOD by measuring prediction variability across posterior samples
- **Deep Ensembles** ([Lakshminarayanan et al., 2017](https://arxiv.org/abs/1612.01474)): Disagreement between ensemble members indicates OOD inputs

**Critical clinical scenario**: A brain segmentation model trained on young healthy subjects encounters an elderly patient with severe atrophy. Without OOD detection, the model produces a confident but wrong segmentation. With OOD detection, the system flags this case for manual review.

---

## The Clinical Decision Framework

```
Patient Brain Scan
        │
        ▼
┌──────────────────────┐
│  OOD Detection       │──→ Flag for manual review
│  (Is this in-domain?)│
└──────────────────────┘
        │ In-distribution
        ▼
┌──────────────────────┐
│  Normative Model     │──→ Z-scores per region
│  (Is this normal?)   │    (deviation from norm)
└──────────────────────┘
        │ Abnormal regions detected
        ▼
┌──────────────────────┐
│  Bayesian Classifier │──→ P(diagnosis | data) with
│  + Conformal Sets    │    calibrated uncertainty
└──────────────────────┘
        │
        ├── High confidence ──→ AI recommendation
        │
        └── Low confidence ──→ Defer to clinician
```

**The key insight**: Uncertainty isn't a single number — it's a **cascade** of questions:
1. Is the data in-distribution? (OOD detection)
2. Is the brain normal? (normative modeling)
3. What's the diagnosis? (classification with uncertainty)
4. Should I trust this prediction? (conformal guarantees)

---

### Relevant Topic Pages
- [III. Bayesian & Uncertainty Methods](03-bayesian-uncertainty.md)
- [VIII. Normative Modeling](08-normative-modeling.md)
- [X. Medical Image Analysis](10-medical-image-analysis.md)
- [II. Generative Models](02-generative-models.md)
