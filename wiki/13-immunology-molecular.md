# XIII. Immunology, mRNA & Molecular Biology

[← Back to Wiki Index](../Wiki.md)

---

## Immune Response & Vaccines

### Papers

- **Long-Term Durability of Immune Response to mRNA COVID Vaccines**
  - *Key idea*: Studied antibody and T-cell responses over 6-12+ months after mRNA vaccination (Pfizer/Moderna). Showed that while antibody titers wane, memory B and T cell responses persist, providing durable protection against severe disease.
  - *Significance*: Established that mRNA vaccines generate long-lasting immunological memory despite declining antibody levels.
  - 🔗 [Download](https://doi.org/10.1101/2021.10.13.21264957)

- **Role of B Cells as Antigen-Presenting Cells**
  - *Key idea*: B cells serve dual roles — antibody production and antigen presentation to T cells. B cells process and present antigens on MHC-II, providing co-stimulatory signals that shape the T cell response.
  - *Significance*: Explains the critical bridge between innate and adaptive immunity.
  - 🔗 [Download](https://doi.org/10.3389/fimmu.2022.954936)

- **A Synthetic Human 3D In Vitro Lymphoid Model**
  - *Key idea*: Engineered a 3D tissue model recapitulating human lymph node function — B cell zones, T cell zones, and germinal centers. Enables in vitro study of immune responses without animal models.
  - 🔗 [Download](https://doi.org/10.1016/j.isci.2022.105741)

### Key Concepts
- **mRNA vaccines** work by delivering instructions for cells to produce the spike protein, triggering both antibody and T-cell responses.
- **Immunological memory** (memory B/T cells) provides long-term protection even after antibody levels decline.
- **3D lymphoid models** enable mechanistic immunology studies in controlled environments.

---

## RNA Biology & Therapeutics

### Papers

- **mRNA Targeting Immune Cells** — Review
  - *Key idea*: Reviews strategies for targeting mRNA therapeutics to specific immune cell populations using lipid nanoparticles with cell-type-specific ligands. Different LNP formulations preferentially target dendritic cells, macrophages, or T cells.
  - 🔗 [Download](https://doi.org/10.3389/fimmu.2023.1294929)

- **Single-Stranded Small Interfering RNA Are More Immunostimulatory Than Double-Stranded** — Sioud, 2006
  - *Key idea*: Discovered that single-stranded siRNAs trigger stronger innate immune responses via TLR7/8 than double-stranded siRNAs. This has implications for both RNA therapeutics (immune side effects) and immunotherapy (deliberate immune activation).
  - 🔗 [Download](https://doi.org/10.1002/eji.200535708)

- **RNAInter v4.0: RNA Interactome Repository**
  - *Key idea*: Comprehensive database of RNA-RNA, RNA-protein, and RNA-compound interactions. Enables systems-level analysis of RNA biology.
  - 🔗 [Download](https://doi.org/10.1093/nar/gkab997) *(search NAR 2022)*

### Key Concepts
- **mRNA therapeutics** extend beyond vaccines to cancer immunotherapy, gene therapy, and protein replacement.
- **Innate immune activation** by RNA is both a challenge (unwanted inflammation) and an opportunity (adjuvant effect).
- **RNA interactomics** reveals the vast network of RNA-mediated regulation in cells.

---

## Protein Structure & Drug Discovery

### Papers

- **AlphaFold: Highly Accurate Protein Structure Prediction** — Jumper et al., 2021
  - *Key idea*: Predicted 3D protein structures from amino acid sequences at experimental accuracy using attention-based architecture with evolutionary (MSA) and structural (pair representation) inputs.
  - *Breakthrough*: Solved the 50-year protein folding problem. Median GDT-TS of 92.4 at CASP14. Transformed structural biology.
  - 🔗 [Download](https://doi.org/10.1038/s41586-021-03819-2)

- **AlphaFold 3** — Abramson et al., 2024
  - *Key idea*: Extended to predict structures of protein-ligand, protein-DNA, protein-RNA, and multi-protein complexes — not just individual proteins. Used a diffusion-based architecture for structure generation.
  - *Breakthrough*: Generalized structure prediction to the full molecular machinery of biology.
  - 🔗 [Download](https://doi.org/10.1038/s41586-024-07487-w)

- **Automatic Chemical Design Using a Data-Driven Continuous Representation of Molecules** — Gómez-Bombarelli et al., 2017
  - *Key idea*: Encoded molecules as continuous latent vectors using VAEs (SMILES-to-SMILES), enabling gradient-based optimization in chemical space. Generated novel molecules with desired properties by optimizing in latent space.
  - *Breakthrough*: First successful application of deep generative models to de novo drug design.
  - 🔗 [Download](https://arxiv.org/abs/1610.02415)

- **Fpocket: An Open Source Platform for Ligand Pocket Detection**
  - *Key idea*: Fast algorithm for detecting binding pockets on protein surfaces using Voronoi tessellation and alpha spheres. Essential preprocessing for structure-based drug design.
  - 🔗 [Download](https://doi.org/10.1186/1471-2105-10-168)

- **Large-Scale De Novo DNA Synthesis: Technologies and Applications**
  - *Key idea*: Reviews DNA synthesis technologies — from oligonucleotide assembly to enzymatic synthesis. Enables construction of synthetic genes, genomes, and gene circuits.
  - 🔗 [Download](https://doi.org/10.1038/nmeth.2918)

- **Genomic Variant Identification with Generative AI**
  - *Key idea*: Applied generative AI models to identify and classify genomic variants — distinguishing pathogenic from benign mutations using sequence context and evolutionary conservation.
  - 🔗 [Download](https://doi.org/10.1093/bib/bbac314)

### Key Concepts
- **AlphaFold** transformed biology from sequence → structure prediction. AlphaFold 3 extends to complexes.
- **VAE-based molecular design** (Gómez-Bombarelli) enables navigation of chemical space through continuous optimization.
- The pipeline from **structure prediction** → **pocket detection** → **molecular design** → **synthesis** is becoming increasingly automated.

---

## Nanotechnology & Biosynthesis

### Papers

- **Biodistribution of Gold Nanoparticles Synthesized**
  - *Key idea*: Studied how gold nanoparticles distribute in the body after administration — organ accumulation, clearance rates, and size-dependent biodistribution patterns.
  - 🔗 [Download](https://doi.org/10.1088/2043-6262/5/2/025009)

- **CdTe and CdSe Quantum Dots Synthesis and Characterization**
  - *Key idea*: Synthesis protocols and optical characterization of semiconductor quantum dots — tunable fluorescence from UV to near-IR based on size.
  - 🔗 [Download](https://doi.org/10.1088/2043-6262/3/4/043001)

- **Inkjet-Printed Unclonable Quantum Dot Fluorescent Anti-Counterfeiting Labels**
  - *Key idea*: Used quantum dots with random printing patterns to create physically unclonable functions (PUFs) for anti-counterfeiting. Each label has a unique fluorescent pattern that cannot be reproduced.
  - 🔗 [Download](https://doi.org/10.1038/s41467-019-10406-7)

- **Equalities and Inequalities: Thermodynamics at Nanoscale** — Jarzynski, 2011
  - *Key idea*: Reviews the Jarzynski equality and Crooks fluctuation theorem — relating free energy differences to non-equilibrium work measurements. These statistical mechanics results apply at the nanoscale where thermal fluctuations are significant.
  - *Significance*: Foundational for understanding molecular motors, protein folding, and nanoscale measurements.
  - 🔗 [Download](https://doi.org/10.1146/annurev-conmatphys-062910-140506)

- **Topological Data Analysis and Biology, Molecules** — Amézquita et al., 2020
  - *Key idea*: Applied persistent homology (TDA) to biological structures — protein shape analysis, molecular surface topology, and plant morphology. Topological features capture shape information that traditional descriptors miss.
  - 🔗 [Download](https://doi.org/10.1002/dvdy.175)

- **An Introduction to Topological Data Analysis** — Chazal, 2017
  - *Key idea*: Tutorial on persistent homology, Betti numbers, and persistence diagrams. Provides the mathematical foundation for applying TDA to data.
  - 🔗 [Download](https://arxiv.org/abs/1710.04019)

### Key Concepts
- **Quantum dots** provide tunable fluorescence for bioimaging and anti-counterfeiting — size determines emission wavelength.
- **Topological data analysis** captures shape features (holes, voids, loops) that persist across scales — complementary to geometric descriptors.
- **Nanoscale thermodynamics** (Jarzynski equality) bridges statistical physics and molecular biology.

---

[← Previous: LLMs & Reasoning](12-llm-reasoning.md) | [→ Next: Optimization & RL](14-optimization-rl.md)
