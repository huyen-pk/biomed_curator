# XV. Distributed Systems & Infrastructure

[← Back to Wiki Index](../Wiki.md)

---

## Distributed Computing & Edge Processing

### Papers

- **Elastic Processing of Analytical Query Workloads on IaaS Clouds** — Kllapi et al., 2015
  - *Key idea*: Designed an elastic query processing engine for cloud infrastructure — dynamically scaling compute resources based on workload demand. Optimizes cost vs. latency trade-offs for analytical queries.
  - 🔗 [Download](https://doi.org/10.1145/2723372.2749431) *(search SIGMOD)*

- **Exoshuffle: An Extensible Shuffle Architecture** — Luan et al., 2023
  - *Key idea*: Redesigned the shuffle stage of distributed data processing (the most expensive bottleneck in MapReduce/Spark). Achieves 2-3× speedup through better scheduling and data placement.
  - 🔗 [Download](https://arxiv.org/abs/2203.05072)

- **DeCaf: Iterative Collaborative Processing over the Edge**
  - *Key idea*: Distributed edge computing framework that splits neural network inference across multiple edge devices, collaboratively processing data closer to the source.
  - 🔗 [Download](https://www.usenix.org/system/files/hotedge19-paper-kumar.pdf) *(search SIGCOMM 2021)*

- **Straggler-Robust Distributed Optimization in Parameter Server Networks** — Atallah et al., 2021
  - *Key idea*: Addressed slow workers (stragglers) in distributed training using coded computation — adding redundancy so the aggregation can proceed without waiting for all workers.
  - *(Also listed under Federated Learning)*
  - 🔗 [Download](https://arxiv.org/abs/2108.09173)

### Key Concepts
- **Shuffle operations** (redistributing data between map and reduce phases) are the dominant cost in distributed data processing.
- **Elastic scaling** (cloud) vs. **fixed topology** (edge) present different optimization challenges.
- **Coded computation** adds redundancy to tolerate slow or failed workers — a key technique for reliable distributed training.

---

[← Previous: Optimization & RL](14-optimization-rl.md) | [→ Cross-Topic Intersections](intersection-dl-neuroimaging.md)
