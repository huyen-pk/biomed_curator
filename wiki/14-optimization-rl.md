# XIV. Optimization, Reinforcement Learning & Scientific Discovery

[← Back to Wiki Index](../Wiki.md)

---

## Reinforcement Learning

### Papers

- **Reinforcement Learning and Dynamic Programming** — Textbook/Survey
  - *Key idea*: Covers the foundations — Markov decision processes, value iteration, policy gradient, temporal difference learning, and function approximation.
  - 🔗 [Download](http://incompleteideas.net/book/the-book.html) *(Sutton & Barto textbook)*

- **Neural Combinatorial Optimization with Reinforcement Learning** — Bello et al., 2017
  - *Key idea*: Trained a pointer network with RL (REINFORCE) to solve the Traveling Salesman Problem. The network learns to construct tours by attending to city embeddings.
  - *Breakthrough*: First successful application of deep RL to NP-hard combinatorial optimization, without hand-designed heuristics.
  - 🔗 [Download](https://arxiv.org/abs/1611.09940)

### Key Concepts
- RL optimizes sequential decision-making through trial and error — the agent learns a policy mapping states to actions.
- **Policy gradient** methods (REINFORCE) optimize the policy directly, unlike value-based methods (Q-learning).
- RL for **combinatorial optimization** learns heuristics that can generalize to unseen problem instances.

---

## Combinatorial Optimization

### Papers

- **A Review on Learning to Solve Combinatorial Optimisation Problems** — Zhang et al., 2023
  - *Key idea*: Comprehensive survey of ML for combinatorial optimization — graph neural networks for TSP/VRP, RL for scheduling, and hybrid methods combining learned heuristics with exact solvers.
  - 🔗 [Download](https://arxiv.org/abs/2210.09615)

- **Design-Bench: Benchmarks for Data-Driven Offline Model-Based Optimization** — Trabucco et al., 2022
  - *Key idea*: Standardized benchmarks for offline optimization — designing proteins, molecules, and materials using only static datasets without active experimentation. Tests how well models extrapolate beyond training data.
  - 🔗 [Download](https://arxiv.org/abs/2202.08450)

- **Constraint Active Search for Multiobjective Design** — Malkomes et al., 2021
  - *Key idea*: Active learning for multi-objective optimization under constraints — efficiently finding the Pareto frontier of feasible designs by intelligently selecting which experiments to run.
  - 🔗 [Download](https://proceedings.mlr.press/v139/malkomes21a.html)

- **Exploring Large Action Sets with Hyperspherical Embeddings** — Bendada et al., 2025
  - *Key idea*: Addressed the challenge of RL/optimization with enormous discrete action spaces by embedding actions on a hypersphere and using von Mises-Fisher sampling for action exploration.
  - 🔗 [Download](https://arxiv.org/abs/2507.00518)

- **Active Learning** — Aggarwal et al., 2014
  - *Key idea*: Survey of active learning strategies — pool-based, stream-based, and query synthesis. The model selects which examples to label, minimizing annotation cost.
  - ⚠️ No verified link available

### Key Concepts
- **Offline optimization** (Design-Bench) is critical for science — you can't always run new experiments; you must design from existing data.
- **Active learning** closes the loop between model and experiment — the model decides what to measure next.
- **Multi-objective optimization** is realistic — real designs must balance multiple competing objectives (efficacy, toxicity, cost).

---

## Symbolic Regression & Interpretable ML

### Papers

- **Interpretable Machine Learning for Science with PySR and SymbolicRegression.jl** — Cranmer, 2023
  - *Key idea*: Genetic programming-based symbolic regression that discovers mathematical equations from data. Unlike neural networks, the output is a human-readable formula.
  - *Significance*: Enables scientific discovery — the discovered equations can reveal physical laws.
  - 🔗 [Download](https://arxiv.org/abs/2305.01582)

- **Sparse Identification of Nonlinear Dynamical Systems (SINDy)** — Brunton et al., 2016
  - *Key idea*: Discovers governing equations by sparse regression over candidate function libraries. The key insight: most physical laws involve only a few terms from a large library of possible functions.
  - *(Also listed under Physics-Informed ML)*
  - 🔗 [Download](https://doi.org/10.1073/pnas.1517384113)

### Key Concepts
- **Symbolic regression** searches the space of mathematical expressions, not just parameters — finding the structure of equations.
- **Interpretability** is essential for scientific applications — a neural network that predicts well but can't be understood provides limited scientific insight.
- SINDy and PySR represent complementary approaches: SINDy assumes a fixed library; PySR evolves expressions.

---

## AI for Scientific Discovery

### Papers

- **Scientist AI** — Bengio, 2025
  - *Key idea*: Envisions AI systems that can perform the full scientific method — hypothesis generation, experimental design, data analysis, and theory revision. Discusses what's missing from current LLMs for genuine scientific reasoning.
  - 🔗 [Download](https://arxiv.org/abs/2502.15657)

- **GFlowNets for AI-Driven Scientific Discovery** — Jain et al., 2023
  - *Key idea*: GFlowNets sample diverse high-reward candidates — ideal for scientific discovery where you want many promising hypotheses, not just the single best.
  - *(Also listed under Generative Models)*
  - 🔗 [Download](https://doi.org/10.1039/d3dd00002h)

- **Data-Driven Science and Engineering** — Brunton & Kutz
  - *Key idea*: Textbook on the intersection of data science and physical science — dimensionality reduction, sparse sensing, dynamical systems, and machine learning for engineering.
  - 🔗 [Download](https://www.databookuw.com/)

### Key Concepts
- **AI for science** requires going beyond pattern matching to causal reasoning, hypothesis testing, and theory formation.
- **Diversity in candidate generation** (GFlowNets) mirrors the scientific principle that multiple hypotheses should be explored simultaneously.
- The convergence of **symbolic AI** (interpretable equations) and **neural AI** (pattern recognition) may be key to scientific AI.

---

[← Previous: Immunology & Molecular Biology](13-immunology-molecular.md) | [→ Next: Distributed Systems](15-distributed-systems.md)
