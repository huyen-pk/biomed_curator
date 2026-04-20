# Generative Models × Molecular Discovery

[← Back to Wiki Index](../Wiki.md)

---

> *How VAEs, diffusion models, and GFlowNets are designing the molecules of the future*

## The Convergence

Drug discovery, protein engineering, and materials science share a common challenge: navigating vast combinatorial spaces to find molecules with desired properties. Generative models — originally developed for images and text — have become the engine of molecular design.

---

## VAEs: The First Generation of Molecular Generators

**Gómez-Bombarelli et al.** ([2018](https://arxiv.org/abs/1610.02415)) launched the field by encoding molecules (as SMILES strings) into a continuous latent space using a VAE, then optimizing in that latent space for desired properties (drug-likeness, solubility, synthetic accessibility).

**Why this matters**: Chemistry operates in a discrete space (atoms and bonds). VAEs transform this into a continuous manifold where gradient-based optimization becomes possible. Instead of testing molecules one by one, you can smoothly navigate chemical space.

**Connection to brain science**: The same VAE architecture used for molecular design (Gómez-Bombarelli) is used for normative brain modeling (Mai Ho 2025, Walter 2020). In both cases, the VAE learns "what's normal" — normal molecules that are drug-like, or normal brain structure at a given age. Abnormality is detected as departure from the learned distribution.

---

## GFlowNets: Diverse Candidate Generation

**The key limitation of standard optimization**: it finds a single optimum. In drug discovery, you want **many diverse candidates** because:
1. The top-scoring molecule might fail clinical trials
2. Patent landscapes require alternatives
3. Multi-objective design has a Pareto frontier, not a single best

**GFlowNets** ([Bengio et al., 2021](https://arxiv.org/abs/2106.04399), [Jain et al., 2022](https://arxiv.org/abs/2203.04115)) solve this by sampling proportionally to reward — generating diverse high-quality candidates rather than collapsing to a single mode.

**Application to molecules** ([Jain et al., 2023](https://arxiv.org/abs/2302.04040)): GFlowNets discovered diverse small molecules for biological targets, outperforming RL and Bayesian optimization in both quality and diversity of candidates.

**Ant Colony GFlowNets** ([Rektoris et al., 2024](https://arxiv.org/abs/2402.13848)): Combined swarm intelligence with GFlowNets for combinatorial optimization — populations of agents explore solution space collaboratively, discovering diverse solutions.

---

## AlphaFold: Structure Prediction Meets Generative Design

**AlphaFold 2** ([Jumper et al., 2021](https://doi.org/10.1038/s41586-021-03819-2)) solved protein structure prediction. **AlphaFold 3** ([Abramson et al., 2024](https://doi.org/10.1038/s41586-024-07487-w)) extended to protein-ligand complexes.

**The design loop** is now:
```
Design molecule → Predict binding pose (AlphaFold 3)
  ↑                        │
  │                        ▼
  │                  Evaluate binding affinity
  │                        │
  └── Generate new ────────┘
      candidates
      (GFlowNet/VAE/Diffusion)
```

**Fpocket** provides the binding site detection step — identifying where on a protein surface a drug could bind.

**Large-scale DNA synthesis** closes the loop from computational design to physical molecules — synthesized genes can express designed proteins for experimental validation.

---

## Diffusion Models for Molecular Generation

Diffusion models' success in images has inspired molecular diffusion:
- **Structure generation**: Diffusing atom coordinates and recovering 3D molecular structures
- **Sequence generation**: Diffusing protein sequences to design new proteins
- **Guided generation** (analogous to classifier-guided diffusion in images): Steering generation toward molecules with desired properties

**AlphaFold 3's key innovation** was switching from the coordinate regression of AlphaFold 2 to a **diffusion-based** structure generator — treating structure prediction as conditional generation.

---

## Topological Data Analysis as a Bridge

**Amézquita et al.** ([2020](https://doi.org/10.1038/s42254-020-0260-y)) applied persistent homology to biological structures, revealing that:
- **Protein shapes** have topological features (tunnels, cavities, voids) that correlate with function
- **Molecular surfaces** can be characterized by their Betti numbers — a more robust descriptor than geometric features

TDA provides a **representation** for molecular structure that is invariant to rotation, translation, and continuous deformation — exactly the properties needed for machine learning on molecules.

---

## The Emerging Drug Discovery Pipeline

```
Target Identification
        │
        ▼
Binding Site Detection ← Fpocket
        │
        ▼
Candidate Generation ← VAE / GFlowNet / Diffusion
        │
        ▼
Binding Pose Prediction ← AlphaFold 3
        │
        ▼
Property Prediction ← GNNs on molecular graphs
        │
        ▼
Diversity Optimization ← GFlowNet
        │
        ▼
Synthesis Planning ← Large-scale DNA synthesis
        │
        ▼
Experimental Validation
```

**The key insight across this collection**: Every major generative architecture — VAEs, diffusion models, normalizing flows, GFlowNets — has found a natural application in molecular design. The mathematical structures that generate realistic images also generate realistic molecules.

---

### Relevant Topic Pages
- [II. Generative Models](02-generative-models.md)
- [XIII. Immunology & Molecular Biology](13-immunology-molecular.md)
- [XIV. Optimization & RL](14-optimization-rl.md)
- [IV. Graph Neural Networks](04-graph-neural-networks.md)
