# VI. Neuroimaging: Acquisition, Preprocessing & Pipelines

[← Back to Wiki Index](../Wiki.md)

---

## MRI Physics & Data Formats

### Papers

- **Geometry in Medical Imaging: DICOM and NIfTI**
  - *Key idea*: Explains coordinate systems, affine transformations, and spatial conventions used in DICOM (clinical standard) and NIfTI (research standard) formats. Understanding voxel-to-world coordinate mappings is essential for correct image processing.
  - 🔗 [Download](https://nipy.org/nibabel/coordinate_system.html) *(reference documentation)*

- **WADO Protocol (Web Access to DICOM Objects)**
  - *Key idea*: Standard protocol for web-based retrieval of DICOM images from PACS servers. Part of the DICOMweb ecosystem enabling modern web applications to access medical imaging data.
  - 🔗 [Download](https://www.dicomstandard.org/using/dicomweb)

- **Statistical Challenges in Big Data Human Neuroimaging** — Smith et al., 2017
  - *Key idea*: Identified key statistical challenges in large neuroimaging studies (UK Biobank, HCP): multiple testing across millions of voxels, confound correction, cross-validation pitfalls, and the need for reproducible analysis pipelines.
  - 🔗 [Download](https://doi.org/10.1016/j.neuron.2017.12.018)

### Key Concepts
- **DICOM** stores metadata (patient info, scanner parameters) alongside image data; **NIfTI** is a simpler research format with a compact header.
- **Affine matrices** map voxel indices to real-world coordinates (mm in scanner space). Correct orientation handling prevents left-right flip errors.
- Big data neuroimaging introduces **unique statistical challenges** — massive multiple testing, spatial correlations, and confound control.

---

## FreeSurfer & Cortical Surface Analysis

FreeSurfer is the dominant software suite for automated cortical reconstruction, parcellation, and morphometric analysis.

### Papers

- **Cortical Surface-Based Analysis (FreeSurfer Pipeline)** — Dale et al., 1999
  - *Key idea*: Established the cortical surface reconstruction pipeline — intensity normalization, skull stripping, white/pial surface extraction, cortical thickness estimation, and inflation to a sphere for cross-subject registration.
  - *Breakthrough*: Enabled vertex-wise cortical analysis, moving beyond voxel-based methods to respect the folded geometry of the cortex.
  - 🔗 [Download](https://doi.org/10.1006/nimg.1998.0396)

- **Automatically Parcellating the Human Cerebral Cortex** — Fischl et al., 2004
  - *Key idea*: Automated the Desikan-Killiany atlas parcellation using a probabilistic atlas and surface-based registration. Each vertex is assigned to one of 34 cortical regions per hemisphere.
  - *Breakthrough*: Replaced manual parcellation with a fully automated, reproducible pipeline used in thousands of studies.
  - 🔗 [Download](https://doi.org/10.1093/cercor/bhg087)

- **Whole Brain Segmentation** — Fischl et al., 2002
  - *Key idea*: Automated subcortical segmentation using a probabilistic atlas with Markov random field spatial regularization. Segments hippocampus, amygdala, caudate, putamen, and other structures.
  - 🔗 [Download](https://doi.org/10.1016/S0896-6273(02)00569-X)

- **FastSurfer: A Fast and Accurate Deep Learning-Based Neuroimaging Pipeline** — Henschel et al., 2020
  - *Key idea*: Replaced FreeSurfer's slow atlas-based segmentation with a deep CNN (FastSurferCNN), reducing processing from ~8 hours to ~1 hour while matching or exceeding FreeSurfer accuracy.
  - *Breakthrough*: Made cortical analysis feasible for large-scale datasets (UK Biobank). CNN-based parcellation with spectral surface processing.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2020.117012)

- **FastSurferLIT: Lesion Inpainting Tool for Whole-Brain MRI Segmentation** — Pollak et al., 2025
  - *Key idea*: Extended FastSurfer with lesion inpainting — fills lesion regions with synthetic healthy tissue before segmentation, preventing lesions from corrupting parcellation.
  - 🔗 [Download](https://doi.org/10.1162/imag_a_00446)

- **LeAPP: A Lesion-Aware Automated Processing Framework** — Bey et al., 2023
  - *Key idea*: End-to-end pipeline for processing brains with lesions — lesion segmentation, inpainting, then standard FreeSurfer processing on the inpainted brain.
  - 🔗 [Download](https://doi.org/10.1002/hbm.26701)

### Key Concepts
- FreeSurfer's **surface-based** approach (meshes) respects cortical folding geometry, unlike volumetric methods.
- **Deep learning pipelines** (FastSurfer, SynthSeg) are replacing atlas-based methods, reducing processing time from hours to minutes.
- **Lesion handling** is critical for clinical populations — standard pipelines fail on damaged brains, motivating inpainting approaches.

---

## SPM & Statistical Neuroimaging

SPM (Statistical Parametric Mapping) is the other major neuroimaging analysis framework, emphasizing voxel-wise statistical testing.

### Papers (SPM Slides Collection)

- **Introduction to SPM** — Overview of the SPM software and the mass-univariate approach to neuroimaging.
- **fMRI Preprocessing** — Motion correction, slice timing, spatial normalization, and smoothing.
- **General Linear Model (GLM)** — The workhorse of fMRI analysis: modeling BOLD signal as a linear combination of experimental conditions convolved with the hemodynamic response function.
- **Contrasts and Inference** — How to specify and test hypotheses using contrast vectors in the GLM framework.
- **Group Analysis** — Random-effects analysis for population-level inference, handling inter-subject variability.
- **Thresholding** — Multiple comparison correction: FWE, FDR, cluster-level inference, and TFCE.
- **Voxel-Based Morphometry (VBM)** — Comparing gray matter volume across groups after spatial normalization and modulation.
- **Experimental Design** — Efficiency and power considerations for block, event-related, and mixed designs.
- **Event-Related fMRI** — Modeling individual stimulus events with flexible HRF estimation.
- **Bayesian Inference in SPM** — Posterior probability maps as an alternative to classical null-hypothesis testing.
- **Dynamic Causal Modeling (DCM)** — Modeling effective connectivity between brain regions using bilinear state-space models fit to fMRI data.
- **DCM: Testing Hypotheses** — Bayesian model comparison for selecting among competing network models.

### Key Concepts
- The **GLM** is the foundation: Y = Xβ + ε, where Y is the brain signal, X is the design matrix, and β are parameters of interest.
- **VBM** compares brain structure (gray matter volume) voxel-by-voxel across groups — e.g., patients vs. controls.
- **DCM** goes beyond localization to model **directed causal interactions** between brain regions.
- **Bayesian inference** in SPM provides posterior probability maps, avoiding the arbitrary thresholds of frequentist testing.

---

## Deep Learning Neuroimaging Pipelines

### Papers

- **Deep Learning Applications in Magnetic Resonance Imaging** — Review
  - *Key idea*: Survey of DL for MRI — reconstruction, segmentation, registration, and quality assessment. Covers U-Nets, GANs for super-resolution, and self-supervised pretraining.
  - 🔗 [Download](https://doi.org/10.3390/diagnostics11122181)

- **Deep Learning in MR Image Processing** — Review
  - *Key idea*: Covers DL for MRI processing — denoising, artifact removal, reconstruction from undersampled k-space, and motion correction.
  - 🔗 [Download](https://doi.org/10.13104/imri.2019.23.2.81)

- **QuickNAT: CNN for Brain Segmentation** — Roy et al., 2019
  - *Key idea*: Fully convolutional network with dense connections and unpooling for fast whole-brain segmentation. Processes a brain in ~20 seconds vs. FreeSurfer's ~8 hours.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2019.01.025)

- **Deep Learning-Based Desikan-Killiany Parcellation Using Diffusion MRI** — Sadegheih et al., 2025
  - *Key idea*: Performed cortical parcellation directly from diffusion MRI (tractography) rather than structural T1w, using deep learning to map white matter connectivity patterns to cortical regions.
  - 🔗 [Download](https://arxiv.org/abs/2508.07815)

- **Data Augmentation for Brain-Tumor Segmentation: A Review** — Nalepa et al., 2019
  - *Key idea*: Techniques for augmenting neuroimaging data — spatial deformations, intensity transformations, synthetic generation, and mix-up strategies to combat small sample sizes in brain tumor segmentation.
  - 🔗 [Download](https://doi.org/10.3389/fncom.2019.00083)

### Key Concepts
- Deep learning has **compressed neuroimaging processing times** from hours to seconds/minutes.
- **SynthSeg** and similar approaches achieve **contrast-agnostic** segmentation by training on synthetic data.
- **Diffusion MRI parcellation** demonstrates that cortical regions can be defined by their connectivity patterns, not just their anatomical location.

---

[← Previous: Physics-Informed ML](05-physics-informed-ml.md) | [→ Next: Brain Segmentation & Lesion Detection](07-brain-segmentation.md)
