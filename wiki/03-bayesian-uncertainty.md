# III. Bayesian Inference, Uncertainty & Probabilistic ML

[← Back to Wiki Index](../Wiki.md)

---

## Bayesian Foundations

Bayesian methods provide a principled framework for reasoning under uncertainty by treating model parameters as random variables with posterior distributions rather than point estimates.

### Papers

- **Bayesian Data Analysis** — Gelman et al.
  - *Key idea*: The definitive textbook on Bayesian statistics. Covers prior specification, posterior computation (MCMC, HMC), model checking, hierarchical models, and decision theory.
  - *Significance*: Standard reference for applied Bayesian analysis across all scientific fields.
  - 🔗 [Download](http://www.stat.columbia.edu/~gelman/book/)

- **Gaussian Processes for Machine Learning** — Rasmussen & Williams
  - *Key idea*: GPs define distributions over functions, providing nonparametric Bayesian regression and classification with built-in uncertainty estimates. The kernel function encodes assumptions about function smoothness and structure.
  - *Significance*: Foundational reference. GPs are used extensively in normative modeling (brain science) and Bayesian optimization.
  - 🔗 [Download](http://www.gaussianprocess.org/gpml/)

- **How Good is the Bayes Posterior in Deep Neural Networks Really?** — Wenzel et al., 2020
  - *Key idea*: Found that the "true" Bayesian posterior of deep networks often gives poor predictions — a cold posterior (tempered likelihood) works better. Questions whether the standard Bayesian framework is appropriate for overparameterized models.
  - *Breakthrough*: Sparked the "cold posterior effect" debate, challenging the assumption that exact Bayesian inference is always desirable.
  - 🔗 [Download](https://arxiv.org/abs/2002.02405)

### Key Concepts
- **Posterior ∝ Likelihood × Prior**: The posterior distribution incorporates both data evidence and prior knowledge.
- **Gaussian Processes** provide exact uncertainty quantification but scale as O(N³) — motivating sparse GP approximations and scalable alternatives.
- The **cold posterior effect** suggests deep learning models may need different probabilistic frameworks than classical Bayesian theory.

---

## Variational Inference Methods

Variational inference (VI) turns the intractable posterior computation problem into an optimization problem — find the closest member of a tractable family to the true posterior.

### Papers

- **Stochastic Variational Inference** — Hoffman et al., 2013
  - *Key idea*: Applied stochastic optimization (natural gradients) to variational inference, enabling VI to scale to massive datasets by processing mini-batches rather than full data.
  - *Breakthrough*: Made variational inference practical for large-scale models (topic models, Bayesian neural nets).
  - 🔗 [Download](https://arxiv.org/abs/1206.7051)

- **Automatic Differentiation Variational Inference (ADVI)** — Kucukelbir et al., 2017
  - *Key idea*: Automated VI by transforming constrained parameters to unconstrained space and using automatic differentiation to compute ELBO gradients. Implemented in Stan.
  - *Breakthrough*: Made VI accessible to non-experts — any probabilistic model can be fit with VI automatically.
  - 🔗 [Download](https://arxiv.org/abs/1603.00788)

- **Stochastic Gradient Descent as Approximate Bayesian Inference** — Mandt et al., 2017
  - *Key idea*: Showed that SGD with constant learning rate implicitly performs approximate Bayesian inference — the stationary distribution of the iterate is approximately the posterior. This connects optimization and inference.
  - *Breakthrough*: Provided theoretical justification for using SGD iterates to estimate uncertainty.
  - 🔗 [Download](https://arxiv.org/abs/1704.04289)

- **Amortized Variational Inference: When and Why** — Margossian et al., 2024
  - *Key idea*: Analyzes when amortized inference (using a neural network to predict variational parameters) outperforms per-instance optimization. Shows amortization helps when there are many similar inference problems but can hurt with heterogeneous data.
  - 🔗 [Download](https://arxiv.org/abs/2307.11018)

### Key Concepts
- VI converts inference into optimization: minimize **KL(q || p)** where q is the variational approximation and p is the true posterior.
- **Stochastic VI** enables scaling to millions of data points via mini-batch gradients.
- **Amortized VI** uses encoder networks to predict posterior parameters in one forward pass — the backbone of VAEs.
- SGD's implicit Bayesian interpretation connects the worlds of optimization and probabilistic inference.

---

## Uncertainty Quantification in Deep Learning

Quantifying what a model doesn't know is critical for high-stakes applications like medical diagnosis. This collection covers methods from Bayesian neural nets to ensemble-based approaches.

### Papers

- **A Simple Baseline for Bayesian Uncertainty (SWAG)** — Maddox et al., 2019
  - *Key idea*: Fitted a Gaussian distribution to the SGD trajectory (mean + low-rank covariance of weights) to approximate the posterior. Simple to implement on top of any trained model.
  - 🔗 [Download](https://arxiv.org/abs/1902.02476)

- **Posterior Network: Uncertainty Estimation Without OOD Samples** — Charpentier et al., 2020
  - *Key idea*: Predicted a Dirichlet distribution over class probabilities using normalizing flows, enabling separation of aleatoric and epistemic uncertainty without requiring OOD training data.
  - 🔗 [Download](https://arxiv.org/abs/2006.09239)

- **Deep Langevin Ensemble** — Wild et al., 2023
  - *Key idea*: Combined Langevin dynamics (SGLD) with ensembles to approximate the posterior predictive distribution. Each ensemble member explores the posterior via stochastic gradient Langevin dynamics.
  - 🔗 [Download](https://arxiv.org/abs/2302.07760) *(search ICML 2023)*

- **Uncertainty Baselines** — Google, 2021
  - *Key idea*: Comprehensive benchmark of uncertainty methods (MC Dropout, ensembles, SNGP, heteroscedastic models) across tasks. Established standardized evaluation protocols.
  - 🔗 [Download](https://arxiv.org/abs/2106.04015)

- **Uncertainty Quantification for ML in Healthcare: Survey** — Lopez et al., 2025
  - *Key idea*: Reviews UQ methods specifically for healthcare applications — clinical decision support, medical imaging, drug discovery. Identifies gaps between methodological research and clinical deployment.
  - 🔗 [Download](https://arxiv.org/abs/2501.07690) *(search arXiv 2025)*

- **Normalizing Flow Ensembles for Rich Aleatoric and Epistemic Uncertainty** — Berry et al., 2023
  - *Key idea*: Used flow ensembles where each member learns the full conditional distribution (aleatoric) while inter-member disagreement captures epistemic uncertainty.
  - 🔗 [Download](https://arxiv.org/abs/2302.01312)

### Key Concepts
- **Epistemic uncertainty** (model ignorance) decreases with more data; **aleatoric uncertainty** (data noise) is irreducible.
- **Ensembles** remain the gold standard for uncertainty in practice, despite theoretical limitations.
- **SWAG** provides a practical Bayesian approximation by leveraging the SGD trajectory.
- Healthcare demands uncertainty quantification — a model that says "I don't know" is more valuable than one that's confidently wrong.

---

## Conformal Prediction & Calibration

### Papers

- **Conformal Prediction: A Gentle Introduction** — Angelopoulos & Bates, 2021
  - *Key idea*: Conformal prediction wraps any model with a calibration layer that produces prediction sets guaranteed to contain the true answer with a user-specified probability (e.g., 90%). No distributional assumptions needed — only exchangeability.
  - *Breakthrough*: Provides **distribution-free, finite-sample coverage guarantees** — something no other uncertainty method offers.
  - 🔗 [Download](https://arxiv.org/abs/2107.07511)

### Key Concepts
- **Conformal prediction** transforms point predictions into prediction sets with valid coverage.
- Unlike Bayesian methods, conformal prediction makes **no assumptions about the data distribution or the model** — it only requires that test data is exchangeable with calibration data.
- In healthcare, conformal prediction could flag cases where the model's prediction set is too large to be clinically useful.

---

[← Previous: Generative Models](02-generative-models.md) | [→ Next: Graph Neural Networks](04-graph-neural-networks.md)
