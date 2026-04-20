# IX. Neurodegenerative Disease & Alzheimer's Research

[← Back to Wiki Index](../Wiki.md)

---

## Molecular Mechanisms: Prions, Amyloids, Mitochondria

Understanding neurodegenerative disease requires molecular-level knowledge of the protein misfolding, aggregation, and cellular dysfunction that drive neuronal death.

### Papers

- **Biology and Genetics of Prions Causing Neurodegeneration** — Prusiner
  - *Key idea*: Prions are misfolded proteins (PrP^Sc) that template their conformation onto normal proteins (PrP^C), propagating without nucleic acids. This mechanism underlies Creutzfeldt-Jakob disease and may extend to other neurodegenerative diseases.
  - *Breakthrough*: Nobel Prize-winning work establishing the protein-only hypothesis of infectious agents.
  - 🔗 [Download](https://doi.org/10.1146/annurev-genet-110711-155524)

- **Neurodegenerative Diseases and Prions** — Prusiner
  - *Key idea*: Extended the prion concept to Alzheimer's (Aβ, tau), Parkinson's (α-synuclein), and ALS (SOD1). Proposed that all these diseases involve prion-like propagation of misfolded proteins through neural networks.
  - *Breakthrough*: Unified theory of neurodegeneration — the same protein misfolding mechanism may underlie apparently different diseases.
  - ⚠️ No verified link available

- **Functional Prions in the Brain** — Eric Kandel
  - *Key idea*: Discovered that prion-like proteins (CPEB) play a normal physiological role in long-term memory formation. The self-propagating conformational change that maintains synaptic strength uses the same mechanism that causes disease in pathological prions.
  - *Breakthrough*: Showed that prion-like behavior is not inherently pathological — it's co-opted from a normal cellular function (memory storage).
  - 🔗 [Download](https://doi.org/10.1073/pnas.1501844112)

- **Amyloidogenic Nanoplaques**
  - *Key idea*: Nanoscale characterization of amyloid plaques — structure, composition, and formation kinetics at the individual plaque level.
  - 🔗 [Download](https://doi.org/10.3233/JAD-200237)

- **Thioflavin T as an Amyloid Dye: Fibril Quantification, Optimal Concentration, and Effect on Aggregation** — Xue et al., 2017
  - *Key idea*: Characterized the biophysics of ThT binding to amyloid fibrils — the standard fluorescence assay for monitoring amyloid aggregation. Optimized protocols for quantitative measurement.
  - 🔗 [Download](https://doi.org/10.1038/s41598-017-07761-4)

- **Mitochondrial Links Between Brain Aging and Alzheimer's Disease**
  - *Key idea*: Reviews how mitochondrial dysfunction (oxidative stress, impaired energy metabolism, dysregulated apoptosis) contributes to both normal brain aging and the accelerated neurodegeneration in Alzheimer's.
  - 🔗 [Download](https://doi.org/10.1186/s40035-021-00261-2)

- **Human Microglial State Dynamics in AD Progression**
  - *Key idea*: Characterized the transcriptomic states of microglia (brain immune cells) during Alzheimer's progression — from homeostatic to disease-associated states (DAM). Showed that microglial responses are dynamic and heterogeneous.
  - 🔗 [Download](https://doi.org/10.1016/j.cell.2023.08.037)

- **Decoding the Complexity of Alzheimer's Disease** — ScienceDaily
  - *Key idea*: Overview of multi-factor Alzheimer's pathology — amyloid cascade, tau propagation, neuroinflammation, vascular contributions, and genetic risk factors (APOE4).
  - 🔗 [Download](https://www.sciencedaily.com/releases/2023/09/230928151511.htm)

### Key Concepts
- **Prion-like propagation** is now considered a unifying mechanism across neurodegenerative diseases. Misfolded proteins spread through neural networks in stereotyped patterns.
- **Functional prions** (Kandel) reveal that prion mechanisms serve normal biology (memory) — disease occurs when the mechanism goes awry.
- **Alzheimer's is multifactorial**: amyloid plaques, tau tangles, neuroinflammation (microglia), mitochondrial dysfunction, and vascular changes all contribute.
- The progression from molecular mechanisms to brain-level imaging connects this section to [Normative Modeling](08-normative-modeling.md) and [Brain Segmentation](07-brain-segmentation.md).

---

## Biomarker Staging & Diagnosis

### Papers

- **Staging Alzheimer's Disease Risk by Sequencing Brain Function and Structure, CSF, and Cognition Biomarkers**
  - *Key idea*: Proposed an ordering of when different biomarkers become abnormal in AD progression: amyloid PET → CSF tau → structural MRI atrophy → cognitive decline. This staging allows early detection before symptoms appear.
  - *Breakthrough*: Established the temporal cascade of AD biomarkers, enabling presymptomatic diagnosis.
  - 🔗 [Download](https://doi.org/10.3233/JAD-160537)

- **Corpus Callosum Shape Changes in Early Alzheimer's Disease** — Ardekani et al., 2013
  - *Key idea*: Used the OASIS brain database to show that corpus callosum shape (thinning of specific subregions) is an early marker of AD. Shape analysis is more sensitive than volume alone.
  - 🔗 [Download](https://doi.org/10.1007/s00429-013-0503-0)

- **Cerebrospinal Fluid Biomarker-Supported Diagnosis**
  - *Key idea*: Reviews CSF biomarkers for AD diagnosis — Aβ42 (decreased), total tau (increased), p-tau (increased). CSF biomarkers provide molecular-level evidence complementing imaging.
  - 🔗 [Download](https://doi.org/10.1016/j.jalz.2018.02.017) *(search Alzheimer's & Dementia)*

### Key Concepts
- **Biomarker cascades** establish temporal ordering: which tests become positive first? This enables early intervention.
- **Structural imaging biomarkers** (hippocampal volume, cortical thickness, corpus callosum shape) are among the latest to change — molecular markers precede them by years.
- Combining **fluid biomarkers** (CSF, blood) with **imaging biomarkers** provides the most comprehensive staging.

---

## Computational Brain Simulation

### Papers

- **The Virtual Brain (TVB/EBRAINS): Alzheimer's Disease Simulation** — Stefanovski et al., 2019
  - *Key idea*: Built a biophysically realistic whole-brain simulation using individual patient connectomes, simulating neural dynamics at the macroscale. Applied to Alzheimer's by modeling the effect of amyloid burden on neural coupling.
  - *Breakthrough*: Demonstrated that patient-specific brain simulations can explain clinical symptoms from molecular pathology — bridging from molecules to behavior through computational modeling.
  - 🔗 [Download](https://doi.org/10.1016/j.neuroimage.2019.04.079)

### Key Concepts
- **The Virtual Brain** connects molecular pathology (amyloid, tau) to macroscale neural dynamics through biophysical models.
- Patient-specific simulations require individual **connectome data** (from diffusion MRI tractography).
- This bridges the gap between molecular neuroscience (prions, amyloid) and clinical neuroimaging (fMRI, EEG).

---

[← Previous: Normative Modeling](08-normative-modeling.md) | [→ Next: Medical Image Analysis](10-medical-image-analysis.md)
