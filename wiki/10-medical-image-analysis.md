# X. Medical Image Analysis & Clinical AI

[← Back to Wiki Index](../Wiki.md)

---

## Deep Learning for Medical Imaging (Reviews)

### Papers

- **An Overview of Deep Learning in Medical Imaging** — Litjens et al., 2017
  - *Key idea*: Landmark survey covering DL applications across radiology — classification, detection, segmentation, registration, and content-based image retrieval. Maps the landscape of architectures (U-Net, FCN, GAN) to clinical tasks.
  - *Breakthrough*: Established the taxonomy and benchmarks for the field of medical image analysis.
  - 🔗 [Download](https://doi.org/10.1016/j.media.2017.07.005)

- **Deep Learning Applications in Magnetic Resonance Imaging**
  - *Key idea*: Reviews DL for the full MRI pipeline — reconstruction, artifact removal, segmentation, and quantitative mapping.
  - 🔗 [Download](https://doi.org/10.3390/diagnostics11122181)

- **Deep Learning in MR Image Processing**
  - *Key idea*: Focuses on DL for MR image processing — denoising, super-resolution, reconstruction from undersampled k-space data.
  - 🔗 [Download](https://doi.org/10.13104/imri.2019.23.2.81)

### Key Concepts
- Medical imaging DL faces unique challenges: **small datasets**, **class imbalance**, **annotation cost**, **domain shift** (different scanners/protocols), and **regulatory requirements**.
- **Transfer learning** from ImageNet pretrained models provides strong baselines even for medical images.
- The field is moving from **detection/segmentation** toward **prediction** (outcome, treatment response) and **generation** (synthetic data, super-resolution).

---

## Domain Generalization & Transfer Learning

### Papers

- **Domain Generalization for Medical Image Analysis** — Yoon et al., 2024
  - *Key idea*: Reviews methods to make models robust to domain shift in medical imaging — data augmentation, domain-invariant representations, meta-learning, and federated training.
  - *Significance*: Domain shift (different scanners, hospitals, populations) is the #1 deployment obstacle for medical AI.
  - 🔗 [Download](https://arxiv.org/abs/2310.08598)

- **Uncertainty-Aware Meta-Weighted Optimization for Domain-Generalized Medical Image Segmentation** — Oh et al., 2024
  - *Key idea*: Used prediction uncertainty to re-weight training samples during meta-learning — samples where the model is uncertain are given more weight, pushing the model toward robustness. Applied to echocardiography segmentation across different devices.
  - 🔗 [Download](https://papers.miccai.org/miccai-2024/810-Paper0708.html)

- **Interactive Segmentation of Medical Images through Fully Convolutional Neural Networks** — Sakinis et al., 2019
  - *Key idea*: Human-in-the-loop segmentation — the model provides an initial segmentation, the user corrects it, and the model refines based on corrections. Combines efficiency of automation with accuracy of human judgment.
  - 🔗 [Download](https://arxiv.org/abs/1903.08205)

### Key Concepts
- **Domain shift** (different scanners, institutions, populations) causes dramatic performance drops — a model trained at hospital A may fail at hospital B.
- **Domain generalization** techniques: domain randomization (SynthSeg), meta-learning, invariant features, and data augmentation.
- **Uncertainty-aware training** automatically focuses learning on challenging, uncertain cases.

---

## Cancer Symptom Prediction & Pharmacology

### Papers

- **Machine Learning Approaches to Predict Symptoms in People With Cancer: Review** — Zeinali et al., 2024
  - *Key idea*: Reviews ML for predicting cancer symptoms (pain, fatigue, nausea) from clinical data. Models can anticipate symptom burden, enabling proactive management.
  - 🔗 [Download](https://doi.org/10.2196/52322)

- **AI Pharmacology**
  - *Key idea*: Overview of AI/ML applications in pharmacology — drug-drug interactions, dosing optimization, adverse event prediction, and pharmacokinetic modeling.
  - 🔗 [Download](https://doi.org/10.1016/j.tips.2023.06.001) *(search Trends in Pharmacological Sciences)*

- **Nonlinear Mixed-Effects Model Development and Simulation Using nlmixr** — Fidler et al., 2019
  - *Key idea*: Open-source R package for population pharmacokinetic/pharmacodynamic (PK/PD) modeling. Enables nonlinear mixed-effects models that account for inter-individual variability in drug metabolism.
  - 🔗 [Download](https://doi.org/10.1002/psp4.12445)

- **Open Source Pharmacokinetic/Pharmacodynamic**
  - *Key idea*: Reviews open-source tools for PK/PD modeling — NONMEM alternatives, population modeling, and simulation-based approaches.
  - 🔗 [Download](https://doi.org/10.1002/psp4.12445) *(search CPT: Pharmacometrics & Systems Pharmacology)*

- **Comorbidity Analysis with Bayesian Nonparametric Methods** — Ruiz et al., 2014
  - *Key idea*: Applied Bayesian nonparametric models (Indian Buffet Process) to discover latent comorbidity patterns — which diseases tend to co-occur and why. Automatically infers the number of comorbidity factors.
  - 🔗 [Download](https://jmlr.org/papers/v15/ruiz14a.html)

### Key Concepts
- **Symptom prediction** enables proactive care — intervening before symptoms become severe.
- **Population PK/PD modeling** accounts for individual variability in drug response — crucial for precision medicine.
- **Comorbidity analysis** reveals hidden disease relationships that inform treatment strategies.

---

[← Previous: Neurodegenerative Disease](09-neurodegeneration.md) | [→ Next: Federated Learning](11-federated-learning.md)
