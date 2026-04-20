# VIII. Normative Modeling & Brain Morphometry

[← Back to Wiki Index](../Wiki.md)

---

## Normative Modeling Frameworks

Normative modeling is a paradigm shift in neuroimaging: instead of comparing group averages (patients vs. controls), it characterizes **individual deviation** from a normative range — akin to growth charts for the brain.

### Papers

- **Normative Models: Review** — Marquand et al., 2019
  - *Key idea*: Definitive review establishing normative modeling as a framework. Maps brain features against age/sex norms to produce individual deviation scores (z-scores). Captures heterogeneity within diagnostic categories.
  - *Breakthrough*: Shifted the field from "average patient" to "this specific patient" — each brain is compared against the expected trajectory, not the group mean.
  - 🔗 [Download](https://doi.org/10.1016/j.biopsych.2018.07.014)

- **Conceptualizing Mental Disorders as Deviations from Normative Functioning** — Marquand et al., 2019
  - *Key idea*: Articulated the theoretical foundation — psychiatric disorders are not discrete categories but positions in a continuous space of brain variation. Normative models map this space.
  - 🔗 [Download](https://doi.org/10.1038/s41380-019-0441-1)

- **Normative Methods** — Review/tutorial
  - *Key idea*: Technical overview of normative modeling approaches — Gaussian process regression, hierarchical Bayesian models, and warped Bayesian regression for non-Gaussian features.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2021.118715) *(search NeuroImage)*

- **Normative Modelling with Scalable Multi-Task Gaussian Processes** — Kia et al., 2018
  - *Key idea*: Scaled normative modeling to large datasets using multi-task GPs that share information across brain regions. Handles the high dimensionality of neuroimaging (100K+ voxels).
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2022.119567) *(search NeuroImage)*

- **Brain Morphology Normative Modelling Platform (Brain Monocle)** — Little et al., 2025
  - *Key idea*: An open-source platform for computing normative centile scores (like pediatric growth charts) for brain morphological features. Enables clinicians to assess whether an individual brain is developing/aging normally.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2025.121050) *(search NeuroImage 2025)*

- **An Enhanced Conditional VAE-Based Normative Model** — Mai Ho, 2025
  - *Key idea*: Used conditional VAEs for normative modeling — conditioning on age/sex produces expected brain patterns; deviations in reconstruction error and latent space indicate abnormality.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2025.120976)

- **Normative Modeling on Alzheimer's with Adversarial Autoencoders** — Walter et al., 2020
  - *Key idea*: AAEs provide sharper normative distributions than VAEs. Adversarial training enforces a prior distribution on the latent space more effectively than KL regularization.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2020.116610)

- **Deep Normative Modelling for Multi-Modal Neuroimaging** — Aguila et al., 2025
  - *Key idea*: Extended normative models to jointly model multiple MRI modalities (structural, diffusion, functional). Multi-modal deviations capture complementary aspects of pathology.
  - 🔗 [Download](https://doi.org/10.1016/j.media.2025.103440) *(search MedIA 2025)*

- **Gaussian Process-Based Prediction and Detection of Gray Matter Abnormalities in Alzheimer's** — Ziegler et al., 2014
  - *Key idea*: Early normative modeling work using GPs to predict gray matter density from age, then detecting AD as deviations from the predicted norm.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2014.04.006)

### Key Concepts
- **Growth charts for the brain**: Normative models establish what's "normal" at each age/sex, then quantify individual deviation.
- Psychiatric diagnoses are **heterogeneous** — two patients with the same diagnosis can have opposite brain deviations. Normative models reveal this hidden structure.
- The evolution: **GP-based** (interpretable, exact uncertainty, limited scale) → **deep learning-based** (VAEs, AAEs — scalable, multi-modal, less interpretable).
- **Centile scores** (Brain Monocle) make results clinically interpretable — a brain region in the 2nd centile is clearly abnormal.

---

## Applications: Alzheimer's, Schizophrenia, ADHD

### Papers

- **Normative Model to Map the Heterogeneity in ADHD** — Wolfers et al., 2019
  - *Key idea*: Applied normative modeling to ADHD, revealing that the disorder is not a single entity but a collection of distinct neurobiological subtypes. Different patients show deviations in different brain regions.
  - *Breakthrough*: Demonstrated that group-level differences in ADHD virtually disappeared when individual heterogeneity was accounted for — the "average ADHD brain" is a misleading concept.
  - 🔗 [Download](https://doi.org/10.1016/j.biopsych.2019.06.003)

- **Normative Model to Detect Schizophrenia from Longitudinal MRI** — Bloch et al., 2015
  - *Key idea*: Used normative brain aging trajectories to detect schizophrenia as accelerated aging. Patients showed brain age significantly higher than chronological age.
  - 🔗 [Download](https://doi.org/10.1016/j.schres.2015.10.042) *(search Schizophrenia Research)*

- **Computational Approaches for Stratifying Psychiatric Disorders** — Marquand et al., 2016
  - *Key idea*: Proposed using computational methods (clustering, normative models) to stratify patients within diagnostic categories rather than comparing diagnostic groups.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2016.03.008)

- **Pattern Recognition for Neuroimaging-Based Psychiatric Diagnostics** — Wolfers et al., 2015
  - *Key idea*: Review of machine learning for psychiatric diagnosis from neuroimaging. Highlighted the problem of small effect sizes and the need for individual-level prediction rather than group statistics.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2015.05.085)

- **Promises and Pitfalls of Deep Neural Networks in Neuroimaging-Based Psychiatric Research** — Eitel et al., 2023
  - *Key idea*: Critical review of DL in psychiatric neuroimaging. Warns about overfitting, confounds (head motion, scanner effects), and the gap between classification accuracy and clinical utility.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2023.120063)

- **Deep Learning Frameworks for MRI-Based Diagnosis of Neurological Disorders: Meta Review** — Ali et al., 2025
  - *Key idea*: Meta-review of DL for neurological diagnosis — Alzheimer's, Parkinson's, MS, epilepsy. Identifies common methodological weaknesses: small datasets, lack of external validation, information leakage.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2025.121020) *(search NeuroImage 2025)*

- **Deep Learning for Classification of Psychiatric Disorders Using Neuroimaging Data: Meta Review** — Quaak et al., 2021
  - *Key idea*: Systematic meta-review showing that reported classification accuracies for psychiatric disorders are often inflated due to methodological issues (leakage, small samples, lack of replication).
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2021.118002)

### Key Concepts
- **Heterogeneity is the rule**: Within any psychiatric diagnosis, patients show vastly different brain profiles. This explains why group-average comparisons yield small effect sizes.
- **Brain age gap** (chronological age minus predicted brain age) is a powerful biomarker — accelerated aging appears in schizophrenia, AD, and other disorders.
- **Methodological rigor** is critical — many published DL results in psychiatry don't replicate due to data leakage, small samples, or confounds.

---

## Brain Morphometry & Cortical Complexity

### Papers

- **Universality in Human Cortical Folding in Health and Disease** — Wang et al., 2016
  - *Key idea*: Discovered universal scaling laws in cortical folding — the relationship between cortical thickness, surface area, and folding degree follows power laws that are conserved across species and disrupted in disease.
  - *Breakthrough*: Revealed fundamental physical constraints on brain morphology — cortical folding obeys the same mathematical laws across mammals.
  - 🔗 [Download](https://doi.org/10.1073/pnas.1610175113)

- **Neuro-Evolutionary Evidence for a Universal Fractal Primate Brain Shape** — Wang et al., 2024
  - *Key idea*: Showed that primate brains have a conserved fractal geometry across evolution — the fractal dimension of cortical surfaces is remarkably stable despite vast differences in brain size.
  - 🔗 [Download](https://doi.org/10.7554/eLife.90025)

- **Cortical Complexity Estimation Using Fractal Dimension: A Systematic Review** — Maregalli et al., 2022
  - *Key idea*: Reviews methods for computing fractal dimension of cortical surfaces — box-counting, spherical harmonic analysis, and cortical complexity indices. Shows fractal dimension changes in aging and neurodegenerative disease.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2022.119801) *(search NeuroImage)*

- **Local Cortical Surface Complexity Maps from Spherical Harmonic Reconstructions** — Yotter et al., 2011
  - *Key idea*: Proposed computing vertex-wise cortical complexity using spherical harmonic reconstructions, enabling spatial maps of local folding complexity.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2011.01.069)

- **Independent Components of Human Brain Morphology** — Wang, Little et al., 2021
  - *Key idea*: Applied ICA to brain morphological features (thickness, area, volume, curvature), discovering independent modes of variation that are shared across populations and relate to genetic and clinical factors.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2021.118005)

- **Multiscale Cortical Morphometry: Regional and Scale-Dependent Variations Across the Lifespan** — Leiberg & Little, 2024
  - *Key idea*: Analyzed cortical morphometry at multiple spatial scales, showing that fine-scale morphological features (local gyrification) change differently with age than coarse-scale features (regional volume).
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2024.120600) *(search NeuroImage 2024)*

### Key Concepts
- **Fractal geometry** of the cortex reflects the physical mechanics of cortical folding — the brain literally folds according to mathematical scaling laws.
- **Cortical complexity** (fractal dimension, gyrification index) decreases with aging and is altered in neuropsychiatric disorders.
- **Multi-scale analysis** reveals that different spatial scales of brain morphology are affected by different biological processes.
- The **universality** findings (Wang et al.) suggest fundamental biophysical constraints that transcend species — a remarkable convergence of neuroscience and physics.

---

[← Previous: Brain Segmentation](07-brain-segmentation.md) | [→ Next: Neurodegenerative Disease](09-neurodegeneration.md)
