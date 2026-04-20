# Physics-Informed ML × Brain Dynamics

[← Back to Wiki Index](../Wiki.md)

---

> *Treating the brain as a dynamical system governed by (discoverable) differential equations*

## The Deep Connection

The brain is a physical system. Neural activity follows differential equations — reaction-diffusion of neurotransmitters, wave propagation of electrical signals, fluid dynamics of cerebrospinal flow. Physics-informed ML provides the tools to learn these equations from data.

---

## Neural ODEs and Brain Dynamics

### The Mathematical Foundation

**Neural ODEs** (Chen 2018) parameterize the derivative dz/dt = f_θ(z, t) with a neural network. Instead of discrete layers, the network is a continuous dynamical system solved with ODE integrators.

**Neural CDEs** (Kidger 2020) extend this to **controlled** differential equations — the input signal drives the dynamics. For brain time series: the observed fMRI/EEG signal controls the latent neural state evolution.

**Counterfactual Neural CDEs** answer: "How would this patient's brain trajectory have changed under a different treatment?" This connects physics-informed dynamics to **causal inference in neuroscience**.

### Application to Brain Trajectories

**Stochastic Differential VAE** (Hess 2024): Models patient brain trajectories as stochastic differential equations in latent space. The drift term captures disease progression; the diffusion term captures individual variability.

```
Normal aging trajectory:    z(t) = z₀ + ∫ f_healthy(z,s)ds + σW(t)

Disease trajectory:         z(t) = z₀ + ∫ f_disease(z,s)ds + σW(t)

Deviation = disease - normal: captures pathological acceleration
```

**The Virtual Brain (TVB)**: Simulates whole-brain dynamics using coupled neural mass models at each cortical region. TVB represents the "first principles" approach — physics-informed ML represents the "data-driven" approach. Their convergence is where neuroscience is heading.

---

## SINDy: Discovering Brain Equations

**Sparse Identification of Nonlinear Dynamical Systems** (Brunton 2016) discovers governing equations from time series data using sparse regression over a library of candidate terms.

**Applied to neuroscience**: Given fMRI or EEG time series, SINDy can discover:
- The effective connectivity equations between brain regions
- Nonlinear coupling terms (e.g., inhibition, facilitation)
- How these equations change with disease

**Example**: From resting-state fMRI of the default mode network:
```
dx₁/dt = -0.3x₁ + 0.2x₂ - 0.1x₁x₃
dx₂/dt = 0.15x₁ - 0.4x₂ + 0.05x₃²
```

These discovered equations are **interpretable** — each term has a neurobiological meaning (self-decay, excitatory/inhibitory coupling, nonlinear interaction).

**PySR** (Cranmer 2023) provides an alternative approach — symbolic regression that evolves expressions rather than selecting from a fixed library. It might discover coupling terms that SINDy's library doesn't contain.

---

## Neural Operators for Brain PDEs

### PINNs for Brain Processes

**Physics-Informed Neural Networks** model brain processes governed by PDEs:

- **Tumor growth** (Cho 2024): The Fisher-KPP equation describes tumor cell proliferation and diffusion through brain tissue. PINNs solve this PDE with MRI-derived brain geometry, predicting tumor progression.

- **Neurotransmitter diffusion**: Reaction-diffusion equations for dopamine, serotonin spreading through synaptic and extrasynaptic space.

- **CSF flow**: Navier-Stokes equations for cerebrospinal fluid dynamics — relevant for hydrocephalus and intrathecal drug delivery.

### Neural Operators

**DIMON** (Yin 2024): Learns the solution operator of PDEs — mapping initial conditions to solutions directly, without solving the PDE each time. Orders of magnitude faster than numerical solvers.

**AFNO** (Guibas 2022): Fourier Neural Operator with attention — efficient for high-resolution 3D brain volumes where standard operators struggle with memory.

---

## Fractal Geometry and Scale-Free Brain Dynamics

**Fractal dimension** (Wang 2024 review): The brain's cortical surface has fractal properties — self-similar structure across scales. Fractal dimension decreases with aging and neurodegeneration.

**The physics connection**: Scale-free dynamics (1/f noise, power-law distributions) in neural activity arise from **criticality** — the brain operates near a phase transition between order and chaos.

**Jarzynski equality** and nanoscale thermodynamics (Jarzynski 2011) connect to the brain through:
- **Information thermodynamics**: Neural computation has thermodynamic costs
- **Free energy principle** (Friston): The brain minimizes variational free energy — a concept directly from statistical physics
- **Protein folding** (prions, amyloids): The thermodynamics of misfolding underlies neurodegeneration

---

## The Dynamical Systems View of Neurodegeneration

Bringing it all together: neurodegeneration can be modeled as a **dynamical system** where:

1. **Prion-like protein spreading** (Prusiner, Kandel) follows a reaction-diffusion PDE on the brain's structural connectome
2. **Biomarker cascades** (Jack 2013) represent the temporal ordering of the system's state variables
3. **Normative deviations** (Marquand 2019) measure how far the system has departed from its healthy attractor
4. **Neural ODEs** can model the continuous trajectory from health to disease

```
Structural Connectome (graph)
        │
        ▼
Protein Spreading PDE ← Physics-Informed Neural Network
(reaction-diffusion      
 on connectome)          
        │
        ▼
Regional Atrophy Trajectory ← Neural ODE / SDE-VAE
        │
        ▼
Normative Z-Scores ← GP / VAE Normative Model
        │
        ▼
Clinical Staging ← Biomarker Cascade Model
```

**The vision**: A physics-informed digital twin of the brain that:
- Uses the structural connectome as its spatial domain
- Evolves protein pathology via reaction-diffusion PDEs
- Predicts atrophy trajectories via neural SDEs
- Estimates disease stage from normative deviations
- Is personalized to each patient using their own MRI

This is exactly what **The Virtual Brain** project aims to achieve — and physics-informed ML provides the computational tools to make it feasible.

---

### Relevant Topic Pages
- [V. Physics-Informed ML](05-physics-informed-ml.md)
- [IX. Neurodegeneration](09-neurodegeneration.md)
- [VIII. Normative Modeling](08-normative-modeling.md)
- [IV. Graph Neural Networks](04-graph-neural-networks.md)
- [I. Foundational Deep Learning](01-foundational-deep-learning.md)
