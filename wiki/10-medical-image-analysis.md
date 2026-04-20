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
  - 🔗 [Download](https://doi.org/10.1002/mrm.28000)

- **Deep Learning in MR Image Processing**
  - *Key idea*: Focuses on DL for MR image processing — denoising, super-resolution, reconstruction from undersampled k-space data.
  - 🔗 [Download](https://doi.org/10.1002/jmri.27129)

### Key Concepts
- Medical imaging DL faces unique challenges: **small datasets**, **class imbalance**, **annotation cost**, **domain shift** (different scanners/protocols), and **regulatory requirements**.
- **Transfer learning** from ImageNet pretrained models provides strong baselines even for medical images.
- The field is moving from **detection/segmentation** toward **prediction** (outcome, treatment response) and **generation** (synthetic data, super-resolution).

---

## Prostate Cancer Detection

### Papers

- **Deep Learning for Fully Automatic Detection, Segmentation, and Gleason Grade Estimation of Prostate Cancer**
  - *Key idea*: End-to-end pipeline from MRI to Gleason grade — detects suspicious regions, segments them, and estimates cancer aggressiveness. Combines detection (classification), segmentation (pixel-level), and grading (ordinal regression).
  - 🔗 [Download](https://doi.org/10.1016/j.ejrad.2020.108999) *(search European Journal of Radiology)*

- **A Transfer Learning Nomogram for Predicting Prostate Cancer and Benign Conditions on MRI**
  - *Key idea*: Used transfer learning from ImageNet to build a nomogram combining DL features with clinical variables (PSA, age) for prostate cancer prediction.
  - 🔗 [Download](https://doi.org/10.1007/s00330-020-07006-z) *(search European Radiology)*

- **Searching for Prostate Cancer by Fully Automated MRI Classification: Deep Learning vs. Non-Deep Learning**
  - *Key idea*: Head-to-head comparison of DL and traditional ML (SVM, RF) for prostate cancer classification from MRI. DL consistently outperforms traditional methods, especially with multi-parametric MRI.
  - 🔗 [Download](https://doi.org/10.1038/s41598-019-48762-7) *(search Scientific Reports)*

### Key Concepts
- Prostate cancer diagnosis requires **multi-parametric MRI** (T2w, DWI, DCE) — each sequence provides complementary information.
- **Gleason grading** (cancer aggressiveness) from imaging is particularly valuable as it avoids invasive biopsy.
- Combining **DL features with clinical variables** (nomograms) improves upon either alone.

---

## Domain Generalization & Transfer Learning

### Papers

- **Domain Generalization for Medical Image Analysis** — Yoon et al., 2024
  - *Key idea*: Reviews methods to make models robust to domain shift in medical imaging — data augmentation, domain-invariant representations, meta-learning, and federated training.
  - *Significance*: Domain shift (different scanners, hospitals, populations) is the #1 deployment obstacle for medical AI.
  - 🔗 [Download](https://doi.org/10.1016/j.media.2024.103025) *(search MedIA 2024)*

- **Meta Learning with Synthetic Medical Data** — Oh et al., 2024
  - *Key idea*: Generated synthetic medical images to create diverse meta-learning episodes, training models that generalize to unseen domains and rare conditions.
  - 🔗 [Download](https://doi.org/10.1016/j.media.2024.103050) *(search MedIA 2024)*

- **Uncertainty-Aware Meta-Weighted Optimization for Domain-Generalized Medical Image Segmentation** — Oh et al., 2024
  - *Key idea*: Used prediction uncertainty to re-weight training samples during meta-learning — samples where the model is uncertain are given more weight, pushing the model toward robustness.
  - 🔗 [Download](https://doi.org/10.1016/j.media.2024.103100) *(search MedIA 2024)*

- **Interactive Segmentation of Medical Images through Fully Convolutional Neural Networks** — Sakinis et al., 2019
  - *Key idea*: Human-in-the-loop segmentation — the model provides an initial segmentation, the user corrects it, and the model refines based on corrections. Combines efficiency of automation with accuracy of human judgment.
  - 🔗 [Download](https://doi.org/10.1016/j.compmedimag.2019.01.005)

### Key Concepts
- **Domain shift** (different scanners, institutions, populations) causes dramatic performance drops — a model trained at hospital A may fail at hospital B.
- **Domain generalization** techniques: domain randomization (SynthSeg), meta-learning, invariant features, and data augmentation.
- **Uncertainty-aware training** automatically focuses learning on challenging, uncertain cases.

---

## Cancer Symptom Prediction & Pharmacology

### Papers

- **Machine Learning Approaches to Predict Symptoms in People With Cancer: Review** — Zeinali et al., 2024
  - *Key idea*: Reviews ML for predicting cancer symptoms (pain, fatigue, nausea) from clinical data. Models can anticipate symptom burden, enabling proactive management.
  - 🔗 [Download](https://doi.org/10.1016/j.ejca.2024.114050) *(search European Journal of Cancer 2024)*

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
  - 🔗 [Download](https://arxiv.org/abs/1410.2006)

### Key Concepts
- **Symptom prediction** enables proactive care — intervening before symptoms become severe.
- **Population PK/PD modeling** accounts for individual variability in drug response — crucial for precision medicine.
- **Comorbidity analysis** reveals hidden disease relationships that inform treatment strategies.

---

[← Previous: Neurodegenerative Disease](09-neurodegeneration.md) | [→ Next: Federated Learning](11-federated-learning.md)
