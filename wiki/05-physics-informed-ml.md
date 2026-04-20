# V. Physics-Informed ML & Scientific Computing

[← Back to Wiki Index](../Wiki.md)

---

## Physics-Informed Neural Networks (PINNs)

PINNs embed physical laws (PDEs) directly into the neural network loss function, enabling data-efficient solutions to forward and inverse problems in physics and engineering.

### Papers

- **PINN: A Review** — Ren et al., 2025
  - *Key idea*: Comprehensive review of PINN architectures, training strategies (adaptive weighting, curriculum learning), and applications across fluid dynamics, solid mechanics, heat transfer, and biomedical engineering.
  - 🔗 [Download](https://doi.org/10.3390/app15148092)

- **Physics-Informed Neural Networks and Neural Operators for Parametric PDEs** — Zhang et al., 2025
  - *Key idea*: Compares PINNs (which solve one PDE instance at a time) with neural operators (which learn solution operators across parameter families). Neural operators amortize the cost of solving related PDEs.
  - 🔗 [Download](https://arxiv.org/abs/2511.04576)

- **Using PINNs for Tumor Cell Growth Modeling** — Rodrigues et al., 2024
  - *Key idea*: Applied PINNs to solve reaction-diffusion equations modeling tumor growth, combining imaging data with mechanistic models to predict spatial tumor evolution.
  - 🔗 [Download](https://doi.org/10.3390/math12081195)

- **Physics-Informed Machine Learning in Biomedical Science and Engineering** — Ahmadi et al., 2025
  - *Key idea*: Survey of physics-informed ML in biomedical contexts — hemodynamics, cardiac mechanics, drug delivery, and neural dynamics. Shows how physics constraints reduce data requirements.
  - 🔗 [Download](https://arxiv.org/abs/2510.05433)

### Key Concepts
- PINNs add **PDE residual loss** to the standard data loss: the network is penalized for violating physical laws at collocation points.
- **Inverse problems**: PINNs can simultaneously solve PDEs and estimate unknown parameters from sparse data.
- **Biomedical applications**: Physics constraints compensate for the extreme data scarcity in clinical settings.

---

## Neural Operators & PDE Solvers

Neural operators learn mappings between infinite-dimensional function spaces — given input functions (initial conditions, geometry), they directly predict solution functions without iterative PDE solving.

### Papers

- **DIMON: Learning Solution Operators of PDEs with Diffeomorphic Mapping** — Yin & Brody, 2024
  - *Key idea*: Combined neural operators with diffeomorphic coordinate transformations to handle complex geometries. The network learns in a canonical domain and maps solutions back to physical coordinates.
  - 🔗 [Download](https://arxiv.org/abs/2402.07250)

- **AFNO: Adaptive Fourier Neural Operator** — Guibas et al., 2022
  - *Key idea*: Performed global token mixing in Fourier space, achieving O(N log N) complexity. Applied to weather prediction and turbulence modeling at high resolution.
  - *Breakthrough*: Enabled neural operators at resolutions previously impossible (1000×1000+ grids).
  - 🔗 [Download](https://arxiv.org/abs/2111.13587)

- **Learning Data-Driven Discretizations for PDEs** — Bar-Sinai et al., 2019
  - *Key idea*: Used neural networks to learn optimal finite-difference stencils that achieve the accuracy of fine grids on coarse grids, effectively learning better numerical methods.
  - 🔗 [Download](https://doi.org/10.1073/pnas.1814058116)

- **Solving PDEs on Unknown Manifolds with Machine Learning** — Liang et al., 2021
  - *Key idea*: Extended PDE solvers to unknown curved manifolds using point cloud representations and neural networks, without requiring mesh generation or explicit surface parameterization.
  - 🔗 [Download](https://arxiv.org/abs/2106.06682)

### Key Concepts
- **Neural operators** generalize neural networks from finite-dimensional vectors to infinite-dimensional functions.
- **Fourier neural operators** exploit spectral representations for efficient global information mixing.
- Unlike PINNs (which solve one instance), neural operators **amortize** — one trained model solves entire families of PDEs.

---

## Neural Differential Equations

Neural ODEs/CDEs/SDEs replace discrete neural network layers with continuous-time dynamics, enabling flexible modeling of temporal processes.

### Papers

- **Neural Controlled Differential Equations for Irregular Time Series** — Kidger et al., 2020
  - *Key idea*: Extended Neural ODEs to handle irregularly-sampled time series by driving the ODE with a data-dependent control path. The hidden state evolves continuously and is "controlled" by incoming observations.
  - *Breakthrough*: First principled deep learning framework for irregular time series that doesn't require imputation or discretization.
  - 🔗 [Download](https://arxiv.org/abs/2005.08926)

- **Continuous-Time Modeling of Counterfactual Outcomes Using Neural CDEs** — Seedat et al., 2022
  - *Key idea*: Used Neural CDEs for causal inference — modeling what would have happened to a patient under an alternative treatment. Continuous-time formulation handles the irregular observation patterns typical of clinical data.
  - 🔗 [Download](https://arxiv.org/abs/2206.08311)

- **Score-Based Generative Modeling through SDEs** — Song et al., 2021
  - *Key idea*: Formulated diffusion models as continuous-time SDEs, unifying DDPM and score-matching approaches. Generation is the reverse-time SDE.
  - *(Also listed under Generative Models)*
  - 🔗 [Download](https://arxiv.org/abs/2011.13456)

### Key Concepts
- **Neural ODEs** treat depth as continuous time: dx/dt = f_θ(x, t). The number of function evaluations adapts to problem difficulty.
- **Neural CDEs** extend this to driven systems — ideal for time series where observations arrive irregularly.
- **Neural SDEs** add stochastic noise, capturing inherent randomness in the dynamics.

---

## Data-Driven Dynamical Systems

### Papers

- **Sparse Identification of Nonlinear Dynamical Systems (SINDy)** — Brunton et al., 2016
  - *Key idea*: Discovered governing equations from data using sparse regression over a library of candidate functions. Finds the simplest differential equations that explain the observed dynamics.
  - *Breakthrough*: Automated scientific discovery of physical laws from data. The resulting equations are interpretable, unlike neural network models.
  - 🔗 [Download](https://doi.org/10.1073/pnas.1517384113)

- **Data-Driven Science and Engineering** — Brunton & Kutz
  - *Key idea*: Textbook covering SVD, Fourier analysis, DMD, SINDy, reinforcement learning, and deep learning for scientific applications. Emphasizes the interplay between data-driven methods and domain knowledge.
  - 🔗 [Download](https://www.databookuw.com/)

- **Linking Dynamical Systems with Human Neuroimaging** — John et al., 2022
  - *Key idea*: Reviewed how dynamical systems theory (attractors, bifurcations, phase transitions) can be applied to neuroimaging data — modeling brain states, transitions, and neural stability.
  - 🔗 [Download](https://doi.org/10.1162/netn_a_00230)

### Key Concepts
- **SINDy** is the "equation discovery" approach — finding sparse, interpretable differential equations from data.
- **Dynamical systems × neuroimaging** models the brain as a dynamical system, where mental states correspond to attractors and disorders to bifurcations.
- The tension between interpretable sparse models (SINDy) and flexible black-box models (Neural ODEs) is a central theme.

---

[← Previous: Graph Neural Networks](04-graph-neural-networks.md) | [→ Next: Neuroimaging Pipelines](06-neuroimaging-pipelines.md)
