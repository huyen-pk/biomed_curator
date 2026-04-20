# VII. Brain Segmentation & Lesion Detection

[← Back to Wiki Index](../Wiki.md)

---

## Whole-Brain Segmentation

Whole-brain segmentation partitions the brain into anatomical regions — cortical parcels, subcortical structures, and white matter tracts — enabling quantitative analysis of brain structure.

### Papers

- **Whole Brain Segmentation** — Fischl et al., 2002
  - *Key idea*: Probabilistic atlas-based segmentation using spatial priors and intensity models in a Bayesian framework with MRF regularization.
  - 🔗 [Download](https://doi.org/10.1016/S0896-6273(02)00569-X)

- **SynthSeg: Segmentation of Brain MRI Scans on Synthesis Images** — Billot et al., 2023
  - *Key idea*: Trained entirely on synthetic images with random contrasts, achieving segmentation that works on any MRI scanner or acquisition protocol without retraining. Uses label maps + generative model to create unlimited training data.
  - *Breakthrough*: Eliminated the domain gap problem in brain segmentation. Now the default in FreeSurfer 7.2+.
  - 🔗 [Download](https://arxiv.org/abs/2107.09559)

- **SAMSEG: Longitudinal Whole-Brain and White Matter Lesion Segmentation** — Cerri et al., 2023
  - *Key idea*: Sequence-adaptive segmentation using a generative model that simultaneously estimates tissue contrasts and segments. Longitudinal extension models within-subject changes over time.
  - 🔗 [Download](https://doi.org/10.1016/j.nicl.2023.103354)

- **Deep Learning Enables Automatic Detection and Segmentation** — General review of DL-based medical image segmentation approaches.
  - 🔗 [Download](https://doi.org/10.1002/jmri.26766)

### Key Concepts
- **Atlas-based methods** (FreeSurfer, SAMSEG) use probabilistic templates but are slow; **deep learning methods** (FastSurfer, SynthSeg) are fast but need training data.
- **SynthSeg's domain randomization** paradigm — training on synthetic data to achieve domain-invariant models — is a breakthrough applicable beyond neuroimaging.
- **Longitudinal segmentation** (SAMSEG) is critical for tracking disease progression over time.

---

## Brain Tumor Detection & Segmentation

### Papers

- **Brain Tumor Segmentation with Deep Neural Networks** — Review
  - *Key idea*: Survey of deep learning approaches for brain tumor segmentation, covering U-Net variants, multi-scale architectures, and the BraTS challenge.
  - 🔗 [Download](https://arxiv.org/abs/1505.03540) *(search arXiv, BraTS challenge papers)*

- **A Deep Learning Approach for Brain Tumor Classification**
  - *Key idea*: CNN-based classification of brain tumors from MRI — distinguishing gliomas, meningiomas, and pituitary tumors.
  - 🔗 [Download](https://doi.org/10.3390/healthcare9020153)

- **Automatic Brain Tumor Detection and Segmentation Using U-Net** — Dong et al., 2017
  - *Key idea*: Comprehensive review of methods from traditional (region growing, atlas-based) to deep learning (FCN, U-Net, attention) for tumor detection.
  - 🔗 [Download](https://arxiv.org/abs/1705.03820)

- **Raidionics: Brain and Lesion Segmentation** — Bouget et al., 2021/2023
  - *Key idea*: Open-source framework for preoperative and postoperative brain tumor segmentation with automatic standardized reporting. Designed for clinical integration.
  - *Significance*: Bridges the gap between research models and clinical deployment.
  - 🔗 [Download](https://doi.org/10.3390/cancers13184674)

### Key Concepts
- **U-Net architecture** (encoder-decoder with skip connections) remains the dominant paradigm for medical image segmentation.
- **Multi-modal MRI** (T1, T1ce, T2, FLAIR) provides complementary information — tumors appear differently on each contrast.
- **Clinical integration** (Raidionics) requires not just accuracy but also fast inference, standardized reporting, and robustness to varied scan quality.

---

## Stroke & Ischemic Lesion Segmentation

### Papers

- **Artificial Intelligence for Diagnosing Acute Stroke: A 25-Year Retrospective** — Wang et al., 2024
  - *Key idea*: Reviews AI for acute stroke imaging — detection of large vessel occlusion, ischemic core estimation, penumbra identification, and hemorrhage detection. Covers the clinical pipeline from symptom onset to AI-assisted diagnosis and treatment decision.
  - 🔗 [Download](https://preprints.jmir.org/preprint/59711)

- **Artificial Intelligence in Stroke Imaging: A Comprehensive Review** — Koska & Selver, 2023
  - *Key idea*: Covers AI applications across the stroke imaging pipeline — automated ASPECTS scoring, perfusion analysis, vessel occlusion detection, and outcome prediction.
  - 🔗 [Download](https://doi.org/10.5152/eurasianjmed.2023.23347)

- **Automatic Brain Ischemic Stroke Segmentation with Deep Learning: A Review** — Abbasi et al., 2023
  - *Key idea*: Focused review on DL architectures for ischemic lesion segmentation — 2D vs 3D networks, attention mechanisms, and multi-scale processing.
  - 🔗 [Download](https://doi.org/10.1016/j.neuri.2023.100145)

- **Automatic Segmentation in Acute Ischemic Stroke: Prognosis on Stroke Volumes and Outcome** — Wong et al., 2022
  - *Key idea*: Used automated lesion segmentation to predict clinical outcomes — larger infarct volumes correlate with worse functional status at 90 days.
  - 🔗 [Download](https://doi.org/10.1016/j.nicl.2022.103279) *(search NeuroImage: Clinical 2022)*

- **Group-Derived and Individual Disconnection in Stroke Prognosis** — Bey et al., 2025
  - *Key idea*: Modeled stroke outcomes using brain disconnection patterns (graph-based) rather than lesion volume alone, showing that network disruption better predicts functional impairment.
  - 🔗 [Download](https://doi.org/10.1101/2025.07.02.25330753)

### Key Concepts
- Stroke is a **time-critical emergency** — AI can reduce image interpretation time from minutes to seconds.
- **Disconnection-based prognosis** (Bey) is superior to simple lesion volume because the same-sized lesion in different locations disrupts different brain networks.
- The field is transitioning from **lesion segmentation** alone to **outcome prediction** and **treatment decision support**.

---

## Anomaly Detection in Brain Imaging

### Papers

- **Unsupervised Brain Anomaly Detection and Segmentation with Transformers** — Walter Hugo Lopez Pinaya et al., 2021
  - *Key idea*: Used variational autoencoders to learn normal brain appearance, then detected anomalies as reconstruction errors. No labeled pathological data needed for training.
  - 🔗 [Download](https://arxiv.org/abs/2102.11650)

- **AnoDDPM: Anomaly Detection with Denoising Diffusion Models** — Wyatt et al., 2022
  - *Key idea*: Diffusion models denoise brain MRI — the difference between input and denoised output reveals anomalies that the model cannot explain as normal variation.
  - 🔗 [Download](https://github.com/Julian-Wyatt/AnoDDPM)

- **Unsupervised Lesion Detection in Brain CT Using Bayesian CNN** — Pawlowski et al., 2018
  - *Key idea*: Combined Bayesian CNNs (MC Dropout) with VAE-based anomaly detection to detect lesions in CT scans. Uncertainty estimates help distinguish true anomalies from reconstruction artifacts.
  - 🔗 [Download](https://openreview.net/forum?id=S1hpzoisz)

### Key Concepts
- **Unsupervised anomaly detection** requires only healthy training data — learns "normal" then flags deviations. Crucial for rare pathologies.
- **Diffusion models** (AnoDDPM) outperform VAEs for anomaly detection because they produce sharper reconstructions.
- Combining anomaly scores with **uncertainty estimates** reduces false positives from reconstruction artifacts.

---

[← Previous: Neuroimaging Pipelines](06-neuroimaging-pipelines.md) | [→ Next: Normative Modeling](08-normative-modeling.md)
