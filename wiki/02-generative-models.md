# II. Generative Models & Density Estimation

[← Back to Wiki Index](../Wiki.md)

---

## Variational Autoencoders (VAEs)

VAEs marry probabilistic inference with deep learning, learning a latent space where sampling produces realistic data. They provide both generation and a principled framework for representation learning.

### Papers

- **Auto-Encoding Variational Bayes (VAE)** — Kingma & Welling, 2014/2019
  - *Key idea*: Introduced the reparameterization trick to make stochastic gradient descent work with latent variable models. The encoder maps data to a distribution in latent space; the decoder reconstructs from samples.
  - *Breakthrough*: Created a tractable framework for learning latent representations with theoretical guarantees (ELBO maximization). Foundation for conditional generation, disentanglement, and semi-supervised learning.
  - 🔗 [Download](https://arxiv.org/abs/1312.6114)

- **Tutorial on Variational Autoencoders** — Doersch, 2016
  - *Key idea*: Pedagogical walkthrough of VAEs — from the evidence lower bound (ELBO) derivation to practical training tricks. Clarifies the relationship between reconstruction loss and KL divergence.
  - 🔗 [Download](https://arxiv.org/abs/1606.05908)

- **VQ-VAE: Neural Discrete Representation Learning** — van den Oord et al., 2018
  - *Key idea*: Replaced the continuous latent space with a discrete codebook using vector quantization. The encoder maps to the nearest codebook entry, enabling autoregressive priors over discrete tokens.
  - *Breakthrough*: Bridged continuous autoencoders and discrete language models; became a key building block for DALL-E and audio synthesis.
  - 🔗 [Download](https://arxiv.org/abs/1711.00937)

- **An Enhanced Conditional VAE-Based Normative Model for Neuroimaging** — Mai Ho, 2025
  - *Key idea*: Extended cVAE for normative modeling of brain data, conditioning on age/sex to model expected brain variation and detect abnormalities as deviations from the learned norm.
  - 🔗 [Download](https://doi.org/10.1101/2025.01.05.631276)

- **Bayesian Neural Controlled Differential Equations** — Hess et al., 2024
  - *Key idea*: Combined Bayesian inference with neural controlled differential equations to model continuous-time patient trajectories, capturing both the latent health state and temporal dynamics of disease progression. Published at ICLR 2024.
  - 🔗 [Download](https://arxiv.org/abs/2310.17463)

- **Normative Modeling on Alzheimer's with Adversarial Autoencoders** — Pinaya (Walter) et al., 2020
  - *Key idea*: Used adversarial autoencoders (AAE) to learn normative brain aging trajectories, then detected Alzheimer's as deviations. AAEs provide sharper latent distributions than standard VAEs.
  - 🔗 [Download](https://doi.org/10.1101/2020.02.10.931824)

### Key Concepts
- The **ELBO** = Reconstruction − KL Divergence: balances faithful reconstruction against latent space regularization.
- **VQ-VAE** showed that discrete latent spaces enable powerful autoregressive priors and better prevent "posterior collapse."
- VAEs in medical AI serve dual purpose: **generation** (data augmentation) and **anomaly detection** (measuring deviation from the learned distribution).

---

## Diffusion Models

Diffusion models have become the dominant generative paradigm, surpassing GANs in image quality while offering stable training and flexible conditioning. This collection spans the mathematical foundations through modern applications.

### Papers

- **Deep Unsupervised Learning Using Nonequilibrium Thermodynamics** — Sohl-Dickstein et al., 2015
  - *Key idea*: Proposed learning a generative model by gradually destroying data with noise (forward process) and learning to reverse the process (denoising). Grounded in statistical physics and nonequilibrium thermodynamics.
  - *Breakthrough*: Laid the theoretical foundation for all diffusion models. The forward process is a Markov chain of Gaussian noise additions; the reverse process learns to denoise step by step.
  - 🔗 [Download](https://arxiv.org/abs/1503.03585)

- **Reverse-Time Diffusion Equation Models** — Anderson, 1982
  - *Key idea*: Proved mathematically that a forward stochastic differential equation has a unique reverse-time counterpart. Established the theoretical basis that diffusion processes can be inverted.
  - *Breakthrough*: This 1982 result from applied mathematics became the mathematical backbone of score-based diffusion models 38 years later.
  - 🔗 [Download](https://doi.org/10.1016/0304-4149(82)90051-5)

- **Denoising Diffusion Probabilistic Models (DDPM)** — Ho et al., 2020
  - *Key idea*: Simplified the diffusion framework with a concrete training objective: predict the noise added at each step. Used a U-Net architecture with sinusoidal time embeddings.
  - *Breakthrough*: Made diffusion models practical. Achieved image quality rivaling GANs with stable training and no mode collapse.
  - 🔗 [Download](https://arxiv.org/abs/2006.11239)

- **Denoising Diffusion Implicit Models (DDIM)** — Song et al., 2020
  - *Key idea*: Generalized DDPM to non-Markovian processes, enabling deterministic sampling with far fewer steps (50-100× fewer than DDPM). Showed that the same trained model can be sampled in different ways.
  - *Breakthrough*: Made diffusion models fast enough for practical applications.
  - 🔗 [Download](https://arxiv.org/abs/2010.02502)

- **Score-Based Generative Modeling through Stochastic Differential Equations** — Song et al., 2021
  - *Key idea*: Unified DDPM and score matching under a continuous SDE framework. The forward process is an SDE; generation is the reverse SDE solved with score function estimates.
  - *Breakthrough*: Provided the unifying mathematical framework for all diffusion models. Connected noise-conditional score networks with denoising objectives.
  - 🔗 [Download](https://arxiv.org/abs/2011.13456)

- **Diffusion Models Beat GANs on Image Synthesis (Guided Diffusion)** — Dhariwal & Nichol, 2021
  - *Key idea*: Introduced classifier guidance — using gradients from a classifier to steer diffusion sampling toward a target class. Also improved U-Net architecture with adaptive group normalization.
  - *Breakthrough*: First time diffusion models surpassed GANs on FID scores for ImageNet generation.
  - 🔗 [Download](https://arxiv.org/abs/2105.05233)

- **High-Resolution Image Synthesis with Latent Diffusion Models (LDM)** — Rombach et al., 2022
  - *Key idea*: Performed the diffusion process in the latent space of a pretrained autoencoder rather than pixel space. Cross-attention layers enable conditioning on text, layouts, and other modalities.
  - *Breakthrough*: Made high-resolution diffusion practical (Stable Diffusion). Decoupled perceptual compression from generative learning.
  - 🔗 [Download](https://arxiv.org/abs/2112.10752)

- **Cold Diffusion: Diffusion Without Noise** — Bansal et al., 2022
  - *Key idea*: Showed that the diffusion framework works with arbitrary degradations (blur, masking, downsampling), not just Gaussian noise. Any invertible corruption process can define a generative model.
  - *Breakthrough*: Expanded the theoretical understanding of why diffusion works — it's about iterative refinement, not specifically noise.
  - 🔗 [Download](https://arxiv.org/abs/2208.09392)

- **Diffusion Models: A Comprehensive Survey** — Yang et al., 2024
  - *Key idea*: Holistic review covering three formulations (DDPM, score-based, SDE), conditioning methods, acceleration techniques, and applications across vision, audio, science, and medicine.
  - 🔗 [Download](https://arxiv.org/abs/2209.00796)

- **AnoDDPM: Anomaly Detection with Denoising Diffusion Models Using Simplex Noise** — Wyatt et al., 2022
  - *Key idea*: Used DDPM for medical anomaly detection — reconstruct brain MRI and compare with input. Simplex noise provides spatially correlated corruption that better preserves anatomical structure.
  - *Breakthrough*: Demonstrated diffusion models for unsupervised pathology detection without labeled anomalies.
  - 🔗 [Download](https://arxiv.org/abs/2206.04530)

- **Zero-Shot Image Restoration Using Denoising Diffusion Null-Space Model** — Wang et al., 2022
  - *Key idea*: Solved inverse problems (inpainting, super-resolution, colorization) using pretrained diffusion models without task-specific fine-tuning by projecting intermediate samples onto the measurement-consistent manifold.
  - 🔗 [Download](https://arxiv.org/abs/2212.00490)

- **Invertible Diffusion Models for Compressed Sensing** — Chen et al., 2025
  - *Key idea*: Combined diffusion models with invertible neural networks for MRI compressed sensing reconstruction.
  - 🔗 [Download](https://arxiv.org/abs/2403.17006)

- **Shedding Light on Large Generative Networks: Estimating Epistemic Uncertainty in Diffusion Models** — Berry et al., 2024
  - *Key idea*: Developed methods to quantify model uncertainty (epistemic) in diffusion model predictions, distinguishing what the model doesn't know from inherent data noise (aleatoric uncertainty).
  - 🔗 [Download](https://arxiv.org/abs/2406.18580)

- **Diffusion Normalizing Flow** — Zhang, 2021
  - *Key idea*: Hybrid architecture combining the flexible density estimation of normalizing flows with the iterative refinement of diffusion models.
  - 🔗 [Download](https://arxiv.org/abs/2110.07579)

- **SynthSeg: Segmentation of Brain MRI Scans on Synthesis Images** — Billot et al., 2023
  - *Key idea*: Trained brain segmentation networks entirely on synthetic images generated from label maps with random contrast/resolution, achieving contrast-agnostic segmentation without retraining.
  - *Breakthrough*: Enabled a single model to segment brain MRI from any scanner, contrast, or resolution — deployed in FreeSurfer.
  - 🔗 [Download](https://arxiv.org/abs/2107.09559)

### Key Concepts
- **Forward diffusion** gradually adds noise; **reverse diffusion** learns to denoise. The training objective is simply noise prediction.
- **Score function** ∇_x log p(x) is the key quantity — it points "uphill" toward high-density regions.
- **Latent diffusion** separates compression (autoencoder) from generation (diffusion), making high-resolution generation tractable.
- **Classifier-free guidance** (Dhariwal) became the standard conditioning technique for text-to-image models.

---

## Normalizing Flows

Normalizing flows provide exact likelihood computation by learning invertible transformations from a simple base distribution to the data distribution.

### Papers

- **Density Estimation by Dual Ascent of the Log-Likelihood (Invertible Flows)** — Tabak & Turner, 2010
  - *Key idea*: Proposed learning a sequence of invertible mappings to transform a simple distribution into a complex one, with exact likelihood via the change-of-variables formula.
  - *Breakthrough*: Foundational work establishing normalizing flows as a density estimation framework.
  - ⚠️ No verified link available

- **Density Estimation Using Real-NVP** — Dinh et al., 2017
  - *Key idea*: Introduced affine coupling layers — split dimensions and apply invertible affine transforms, with efficient Jacobian computation. Enabled practical deep normalizing flows.
  - *Breakthrough*: Made normalizing flows scalable to high-dimensional data (images). The coupling layer design is used in nearly all subsequent flow architectures.
  - 🔗 [Download](https://arxiv.org/abs/1605.08803)

- **Normalizing Flow Ensembles for Rich Aleatoric and Epistemic Uncertainty Modeling** — Berry et al., 2023
  - *Key idea*: Used ensembles of normalizing flows to disentangle aleatoric (data noise) from epistemic (model ignorance) uncertainty, providing calibrated uncertainty estimates.
  - 🔗 [Download](https://arxiv.org/abs/2302.01312)

### Key Concepts
- Flows provide **exact log-likelihoods** (unlike VAEs which give a lower bound), enabling principled model comparison.
- The **change-of-variables formula** requires computing the Jacobian determinant of the transformation — coupling layers make this tractable.
- Flows are **bidirectional**: can both generate samples (forward) and evaluate density (inverse).

---

## GFlowNets & Combinatorial Generation

GFlowNets (Generative Flow Networks) are a novel class of generative models that sample diverse, high-reward objects proportional to a reward function — designed for discrete, combinatorial spaces.

### Papers

- **Flow Network-Based Generative Models for Non-Iterative Diverse Candidate Generation** — Bengio et al., 2021
  - *Key idea*: Proposed GFlowNets that learn a policy to construct objects (molecules, sequences) step by step, with the probability of generating an object proportional to its reward. Unlike RL which collapses to the mode, GFlowNets sample diverse high-reward solutions.
  - *Breakthrough*: Created a fundamentally new generative paradigm for discrete structured objects.
  - 🔗 [Download](https://arxiv.org/abs/2106.04399)

- **Biological Sequence Design with GFlowNets** — Jain et al., 2022
  - *Key idea*: Applied GFlowNets to design DNA/protein sequences that satisfy biological objectives. Demonstrated diverse candidate generation for wet-lab experimental cycles.
  - 🔗 [Download](https://arxiv.org/abs/2203.04115)

- **GFlowNets for AI-Driven Scientific Discovery** — Jain et al., 2023
  - *Key idea*: Surveyed GFlowNet applications across drug discovery, materials science, and combinatorial optimization. Showed how reward-proportional sampling enables efficient exploration of vast search spaces.
  - 🔗 [Download](https://doi.org/10.1039/d3dd00002h)

- **Trajectory Balance for GFlowNets** — Malkin et al., 2023
  - *Key idea*: Introduced the trajectory balance objective which considers complete generation trajectories rather than individual transitions, providing lower-variance gradients and more stable training.
  - *Breakthrough*: Solved key training instability issues of original GFlowNets; became the standard training objective.
  - 🔗 [Download](https://arxiv.org/abs/2201.13259)

- **Ant Colony Sampling with GFlowNets for Combinatorial Optimization** — Kim et al., 2025
  - *Key idea*: Combined GFlowNets with ant colony optimization heuristics, using GFlowNets to generate diverse high-quality starting solutions and ants to locally refine them.
  - 🔗 [Download](https://arxiv.org/abs/2403.07444)

### Key Concepts
- GFlowNets generate objects **proportional to reward**, unlike RL (which finds the maximum) or MCMC (which requires mixing).
- **Trajectory balance** unifies forward/backward flow constraints across entire generation paths.
- Ideal for **scientific discovery** where diversity matters — you want many good drug candidates, not just the single best one.

---

## Energy-Based Models & OOD Detection

### Papers

- **Your Classifier Is Secretly an Energy-Based Model** — Grathwohl et al., 2020
  - *Key idea*: Reinterpreted the logits of a standard classifier as unnormalized log-probabilities (energies), enabling the same network to perform classification, OOD detection, and generation.
  - *Breakthrough*: Showed that discriminative and generative modeling are two sides of the same coin.
  - 🔗 [Download](https://arxiv.org/abs/1912.03263)

- **Do Deep Generative Models Know What They Don't Know?** — Nalisnick et al., 2019
  - *Key idea*: Showed that deep generative models (VAEs, flows) can assign higher likelihood to out-of-distribution data than in-distribution data. Likelihood alone is not sufficient for OOD detection.
  - *Breakthrough*: Revealed a fundamental limitation of likelihood-based generative models and motivated typicality-based and energy-based alternatives.
  - 🔗 [Download](https://arxiv.org/abs/1810.09136)

- **A Baseline for Detecting Misclassified and Out-of-Distribution Examples** — Hendrycks & Gimpel, 2017
  - *Key idea*: Showed that the maximum softmax probability is a surprisingly effective baseline for detecting misclassified and OOD inputs. Established benchmarks for OOD detection.
  - 🔗 [Download](https://arxiv.org/abs/1610.02136)

- **Deep Anomaly Detection with Outlier Exposure** — Hendrycks et al., 2019
  - *Key idea*: Fine-tuned models on auxiliary OOD data ("outlier exposure") to produce low-confidence predictions on anomalous inputs. Simple and effective across domains.
  - 🔗 [Download](https://arxiv.org/abs/1812.04606)

- **WAIC/Generative Ensemble for Robust Anomaly Detection** — Choi & Jang, 2019
  - *Key idea*: Used the Watanabe-Akaike Information Criterion (WAIC) from an ensemble of generative models for anomaly scoring, which is more robust than raw likelihood.
  - 🔗 [Download](https://arxiv.org/abs/1810.01392)

- **Estimation of Non-Normalized Statistical Models by Score Matching** — Hyvärinen, 2005
  - *Key idea*: Proposed score matching — fitting model parameters by matching the gradient of the log-density, avoiding the need to compute the intractable normalizing constant.
  - *Breakthrough*: Foundational technique that later became central to score-based diffusion models.
  - 🔗 [Download](https://jmlr.org/papers/v6/hyvarinen05a.html)

### Key Concepts
- **Likelihood is not enough for OOD detection** — a key cautionary finding. Typicality and energy-based scores are more reliable.
- **Score matching** avoids normalizing constants, enabling training of unnormalized models (EBMs, score-based diffusion).
- The **energy interpretation** of classifiers unifies discriminative and generative perspectives.

---

[← Previous: Foundational Deep Learning](01-foundational-deep-learning.md) | [→ Next: Bayesian Inference & Uncertainty](03-bayesian-uncertainty.md)
