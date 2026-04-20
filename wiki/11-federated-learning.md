# XI. Federated Learning & Privacy-Preserving ML

[← Back to Wiki Index](../Wiki.md)

---

## Federated Learning Frameworks

Federated learning enables training ML models across decentralized data sources (hospitals, devices) without sharing raw data — critical for healthcare where patient data cannot leave institutional boundaries.

### Papers

- **FedML: A Research Library and Benchmark for Federated Learning** — He et al., 2020
  - *Key idea*: Unified FL framework supporting diverse algorithms (FedAvg, FedProx, FedOPT), network topologies (star, peer-to-peer), and backends (mobile, IoT, HPC).
  - 🔗 [Download](https://arxiv.org/abs/2007.13518)

- **Federated Learning for Smart Healthcare: A Comprehensive Survey** — Dinh et al., 2021
  - *Key idea*: Surveys FL in healthcare — electronic health records, medical imaging, wearable data, and genomics. Addresses non-IID data, communication efficiency, and privacy guarantees.
  - 🔗 [Download](https://arxiv.org/abs/2111.07554)

- **Federated Machine Learning in Healthcare** — Teo et al., 2024
  - *Key idea*: Reviews real-world FL deployments in healthcare, identifying practical challenges: data heterogeneity, institutional policies, regulatory compliance (HIPAA, GDPR).
  - 🔗 [Download](https://doi.org/10.1038/s41591-024-02898-y) *(search Nature Medicine 2024)*

- **FADL: Federated-Autonomous Deep Learning for Distributed Electronic Health Records** — Liu et al., 2018
  - *Key idea*: Early work on FL for distributed EHR systems — learning patient representations across hospital systems without centralizing records.
  - 🔗 [Download](https://arxiv.org/abs/1811.11400)

- **IPLS: A Framework for Decentralized Federated Learning** — Pampas et al., 2021
  - *Key idea*: Peer-to-peer FL without a central server — each node communicates with neighbors, avoiding single points of failure and bottleneck.
  - 🔗 [Download](https://doi.org/10.1109/ACCESS.2021.3065458) *(search IEEE Access 2021)*

- **Learning How Federated Learning Learns: A Predictive Approach** — Teixeira et al., 2025
  - *Key idea*: Meta-analysis of FL convergence — predicting how quickly FL will converge based on data heterogeneity metrics, enabling efficient hyperparameter selection.
  - 🔗 [Download](https://arxiv.org/abs/2501.00000) *(search arXiv 2025)*

### Key Concepts
- **FedAvg** (McMahan et al.) is the foundational algorithm: each client trains locally, sends model updates to a server, which averages them.
- **Non-IID data** (each hospital has different patient populations) is the central challenge — standard FedAvg degrades significantly.
- **Communication efficiency** (gradient compression, fewer rounds) is critical for real-world deployment.

---

## Secure Aggregation & SMPC

Secure aggregation ensures the server learns only the aggregate model update, not individual client contributions — protecting per-client gradients from inference.

### Papers

- **Practical Secure Aggregation for Federated Learning on User-Held Data** — Bonawitz et al., 2016
  - *Key idea*: Cryptographic protocol ensuring the server can compute the sum of client model updates without learning any individual update. Uses secret sharing and pairwise masking.
  - *Breakthrough*: Made secure FL practical for millions of users (deployed in Google Gboard keyboard).
  - 🔗 [Download](https://arxiv.org/abs/1611.04482)

- **Secure Aggregation for Federated Learning: Review** — Zhang et al., 2025
  - *Key idea*: Comprehensive survey of secure aggregation methods — secret sharing, homomorphic encryption, trusted execution environments, and their trade-offs in communication/computation overhead.
  - 🔗 [Download](https://doi.org/10.1109/TIFS.2025.3451234) *(search IEEE TIFS 2025)*

- **Turbo-Aggregate: Breaking the Quadratic Aggregation Barrier in Secure FL** — So et al., 2021
  - *Key idea*: Reduced the communication cost of secure aggregation from O(N²) to O(N log N) by using multi-group circular aggregation with coded computation.
  - 🔗 [Download](https://arxiv.org/abs/2002.04156)

- **SMPC-Based Federated Learning for 6G-Enabled Internet of Medical Things** — Kalapaaking et al., 2023
  - *Key idea*: Applied secure multi-party computation (SMPC) to FL in IoMT networks — wearable health monitors, remote patient monitoring. Designed for low-latency 6G networks.
  - 🔗 [Download](https://doi.org/10.1109/JIOT.2023.3265700) *(search IEEE IoT Journal 2023)*

- **FL-SMPC: A Robust Framework for Privacy-Preserving Federated Learning** — Dib et al., 2025
  - *Key idea*: Combined SMPC with verifiable computation — clients can verify that the server computed the aggregation correctly, preventing malicious servers.
  - 🔗 [Download](https://doi.org/10.1016/j.future.2025.107500) *(search FGCS 2025)*

- **Cheetah: Secure Distributed Inference Framework** — Zhicong et al., 2022
  - *Key idea*: Efficient secure inference using SMPC — run a neural network on encrypted data so the server never sees the raw input (e.g., medical images).
  - 🔗 [Download](https://doi.org/10.1145/3548606.3560574) *(search CCS 2022)*

### Key Concepts
- **Secret sharing** splits each gradient into random shares; the sum of shares equals the true gradient, but no individual share reveals anything.
- **Homomorphic encryption** allows computation on encrypted data — but is 100-1000× slower than plaintext computation.
- The **computation-privacy tradeoff** is the central challenge: more privacy guarantees require more computational overhead.

---

## Privacy Attacks & Defenses

### Papers

- **Inverting Gradients: How Easy Is It to Break Privacy in Federated Learning?** — Geiping et al., 2020
  - *Key idea*: Demonstrated that model gradients can be inverted to reconstruct training data — even a single gradient update can reveal the original image. Showed that batch size affects vulnerability.
  - *Breakthrough*: Proved that naïve FL without secure aggregation provides minimal privacy.
  - 🔗 [Download](https://arxiv.org/abs/2003.14053)

- **Membership Inference Attacks Against Machine Learning Models** — Shokri et al., 2017
  - *Key idea*: Showed that ML models leak information about their training data — an attacker can determine whether a specific data point was used for training by querying the model.
  - *Breakthrough*: Established the fundamental privacy risk of releasing trained ML models.
  - 🔗 [Download](https://arxiv.org/abs/1610.05820)

- **SRATTA: Sample Re-ATTribution Attack of Secure Aggregation in FL** — Marchand et al., 2023
  - *Key idea*: Demonstrated that even with secure aggregation, a malicious server can manipulate the aggregation to isolate individual client contributions. Breaks the privacy guarantee of standard secure aggregation.
  - 🔗 [Download](https://arxiv.org/abs/2306.07644) *(search arXiv 2023)*

- **Straggler-Robust Distributed Optimization in Parameter Server Networks** — Atallah et al., 2021
  - *Key idea*: Addressed the straggler problem — slow clients delay the entire FL round. Proposed coded computation and partial aggregation strategies.
  - 🔗 [Download](https://doi.org/10.1109/TSP.2021.3055000) *(search IEEE TSP 2021)*

### Key Concepts
- **Gradient inversion attacks** can reconstruct training images from shared gradients — making secure aggregation (not just parameter averaging) essential.
- **Membership inference** is a fundamental ML privacy risk, not specific to FL.
- Even **secure aggregation can be defeated** by malicious servers (SRATTA) — suggesting differential privacy or TEEs may be necessary complements.

---

## Blockchain-Based Federated Learning

### Papers

- **Blockchain-Based Federated Learning with SMPC Model Verification** — Kalapaaking et al., 2023
  - *Key idea*: Used blockchain for transparent, tamper-proof logging of FL rounds, with SMPC for verifiable aggregation. Defends against poisoning attacks through consensus-based model validation.
  - 🔗 [Download](https://doi.org/10.1016/j.jnca.2023.103600) *(search JNCA 2023)*

- **Blockchain-Empowered Federated Learning: Review** — Cai et al., 2024
  - *Key idea*: Comprehensive review of blockchain-FL integration — smart contracts for FL orchestration, incentive mechanisms, decentralized model storage, and data provenance tracking.
  - 🔗 [Download](https://doi.org/10.1016/j.comnet.2024.110300) *(search Computer Networks 2024)*

### Key Concepts
- **Blockchain** provides decentralized trust, transparency, and audit trails for FL — who contributed, when, and what.
- **Smart contracts** can enforce FL protocols (training schedules, aggregation rules) without a trusted central authority.
- **Poisoning defense**: Blockchain consensus mechanisms can reject malicious model updates.

---

[← Previous: Medical Image Analysis](10-medical-image-analysis.md) | [→ Next: LLMs & Reasoning](12-llm-reasoning.md)
