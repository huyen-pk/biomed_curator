# IV. Graph Neural Networks & Relational Learning

[← Back to Wiki Index](../Wiki.md)

---

## GNN Foundations & Expressiveness

Graph neural networks extend deep learning to non-Euclidean, relational data — social networks, molecules, brain connectomes, and physical systems.

### Papers

- **Graph Neural Networks: A Review of Methods and Applications** — Zhou et al., 2020
  - *Key idea*: Comprehensive survey covering spectral and spatial GNN methods (GCN, GAT, GraphSAGE), readout functions, and applications. Establishes taxonomy: recurrent GNNs, convolutional GNNs, graph autoencoders, and spatial-temporal GNNs.
  - 🔗 [Download](https://arxiv.org/abs/1812.08434)

- **How Powerful Are Graph Neural Networks?** — Xu et al., 2019
  - *Key idea*: Proved that standard message-passing GNNs are at most as expressive as the Weisfeiler-Lehman (WL) graph isomorphism test. Proposed GIN (Graph Isomorphism Network) which achieves this upper bound.
  - *Breakthrough*: Established the theoretical expressiveness limits of GNNs — fundamentally, standard GNNs cannot distinguish certain non-isomorphic graphs.
  - 🔗 [Download](https://arxiv.org/abs/1810.00826)

- **Survey on Graph Neural Networks** — Vretos et al., 2024
  - *Key idea*: Updated survey covering recent advances: graph transformers, equivariant GNNs, heterogeneous graphs, and scalability solutions.
  - 🔗 [Download](https://doi.org/10.1109/ACCESS.2024.3456913)

- **Graph Neural Networks: A Bibliometric Mapping** — da Silva et al., 2024
  - *Key idea*: Bibliometric analysis of GNN research trends — most active research groups, citation networks, and emerging application domains.
  - 🔗 [Download](https://doi.org/10.3390/info15100626)

### Key Concepts
- **Message passing**: Nodes aggregate information from neighbors, then update their representations. Repeated for K layers to capture K-hop neighborhoods.
- **WL expressiveness bound**: Standard GNNs cannot count substructures or distinguish certain graph topologies. Higher-order GNNs and graph transformers address this.
- **Graph transformers** apply self-attention across all node pairs, breaking the locality constraint of message passing.

---

## GNNs for Time Series & Dynamical Systems

### Papers

- **A Survey on Graph Neural Networks for Time Series: Forecasting, Classification, Imputation, Anomaly Detection** — Jin et al., 2024
  - *Key idea*: Comprehensive survey of GNNs for temporal data — spatial-temporal GNNs for traffic/weather, temporal knowledge graphs, and multivariate time series where inter-variable relationships form graphs.
  - 🔗 [Download](https://arxiv.org/abs/2307.03759)

- **GNN Applications in Mechanics-Related Domains** — Zhao et al., 2024
  - *Key idea*: Reviews GNNs for simulating physical systems — fluid dynamics, structural mechanics, molecular dynamics. Mesh-based GNNs treat simulation meshes as graphs.
  - 🔗 [Download](https://arxiv.org/abs/2404.10765) *(search arXiv 2024)*

### Key Concepts
- **Spatial-temporal GNNs** model both spatial relationships (graph edges) and temporal dynamics (recurrence or temporal attention).
- In mechanics, GNNs can learn **mesh-based simulations** that generalize across different geometries and boundary conditions.

---

## GNNs in Biology & Neuroscience

GNNs are natural fits for biological data — molecular graphs, protein interaction networks, brain connectomes, and gene regulatory networks.

### Papers

- **Graph Neural Networks for Single-Cell Omics Data** — Li et al., 2025
  - *Key idea*: Applied GNNs to single-cell RNA-seq data, modeling cell-cell similarity graphs for clustering, trajectory inference, and batch correction. GNNs capture the manifold structure of cell populations.
  - 🔗 [Download](https://doi.org/10.1093/bib/bbaf109)

- **scapGNN: Graph Neural Network for Active Pathway and Gene Module Inference** — Han et al., 2023
  - *Key idea*: Built cell-gene bipartite graphs and used GNNs to infer active signaling pathways at single-cell resolution, identifying cell-type-specific pathway activities.
  - 🔗 [Download](https://doi.org/10.1371/journal.pbio.3002369)

- **Group-Derived and Individual Disconnection in Stroke Prognosis: Deep Graph Learning** — Bey et al., 2025
  - *Key idea*: Modeled brain structural disconnection after stroke as graphs, using GNNs to predict patient outcomes from lesion-induced connectivity disruptions.
  - 🔗 [Download](https://doi.org/10.1101/2025.07.02.25330753)

- **Fractal and Multifractal Properties of Electrographic Recordings of Human Brain Activity** — França & Wang, 2018
  - *Key idea*: Analyzed the fractal structure of EEG signals, showing that brain activity exhibits multifractal scaling — different temporal scales have different fractal dimensions, reflecting the hierarchical organization of neural dynamics.
  - 🔗 [Download](https://doi.org/10.3389/fphys.2018.01767)

- **Uncovering Insurance Fraud Conspiracy with Network Learning**
  - *Key idea*: Applied graph neural networks to detect fraud rings by learning representations of transaction networks where suspicious patterns emerge from relational structure.
  - 🔗 [Download](https://arxiv.org/abs/2002.12789)

### Key Concepts
- **Biological graphs** are naturally heterogeneous — gene-gene, protein-protein, cell-cell interactions all have different semantics.
- GNNs for **brain connectomes** can capture how structural damage (stroke) propagates through networks to affect function.
- **Single-cell GNNs** exploit the manifold structure of gene expression space, outperforming methods that treat cells independently.

---

[← Previous: Bayesian Inference](03-bayesian-uncertainty.md) | [→ Next: Physics-Informed ML](05-physics-informed-ml.md)
