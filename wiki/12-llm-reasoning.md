# XII. Large Language Models & Reasoning

[← Back to Wiki Index](../Wiki.md)

---

## LLM Architectures

### Papers

- **DeepSeek-V3 Technical Report** — DeepSeek, 2024
  - *Key idea*: Mixture-of-Experts (MoE) architecture with 671B total parameters but only 37B active per token. Multi-head latent attention (MLA) compresses KV cache. Trained on 14.8T tokens.
  - *Significance*: Demonstrated that efficient MoE architectures can match or exceed dense models at a fraction of the compute.
  - 🔗 [Download](https://arxiv.org/abs/2412.19437)

- **DeepSeek-R1** — DeepSeek, 2025
  - *Key idea*: Reasoning-focused model trained with reinforcement learning to develop chain-of-thought reasoning. Shows emergent "aha moments" and self-verification behaviors.
  - *Significance*: Open-weight model matching o1-class reasoning capabilities. Demonstrated that RL can elicit structured reasoning from language models.
  - ⚠️ No verified link available

- **DeepSeek LLM** — DeepSeek, 2024
  - *Key idea*: Scaling laws analysis for LLMs — data, model size, and compute scaling relationships. Established training recipes for efficient large-scale LLM training.
  - 🔗 [Download](https://arxiv.org/abs/2401.02954)

- **SuperARC: Benchmark Framework for Superintelligence** — Espinosa et al., 2025
  - *Key idea*: Proposed evaluation benchmarks for superhuman AI capabilities — abstract reasoning, novel problem solving, and scientific discovery beyond human baselines.
  - 🔗 [Download](https://arxiv.org/abs/2503.16743)

- **HyperCluster: Decentralized LLM Inference over Peer-to-Peer** — Jain et al., 2026
  - *Key idea*: Distributed LLM inference across heterogeneous peer-to-peer networks — model parallelism without centralized infrastructure. Handles dynamic node availability and varying hardware.
  - 🔗 [Download](https://openreview.net/forum?id=NJz796yuDX)

### Key Concepts
- **Mixture-of-Experts** enables massive parameter counts with manageable compute by activating only relevant experts per token.
- **Reasoning through RL** (DeepSeek-R1) shows that structured thinking can emerge from reward signals without explicit chain-of-thought supervision.
- **Decentralized inference** (HyperCluster) addresses the compute concentration problem for LLM deployment.

---

## Chain-of-Thought & Prompting

### Papers

- **Chain-of-Thought Prompting Elicits Reasoning in Large Language Models** — Wei et al., 2023
  - *Key idea*: Demonstrated that prompting LLMs with step-by-step reasoning examples ("Let's think step by step") dramatically improves performance on math, logic, and commonsense reasoning tasks.
  - *Breakthrough*: Showed that reasoning ability can be unlocked through prompting alone — no fine-tuning needed. Sparked the entire prompt engineering field.
  - 🔗 [Download](https://arxiv.org/abs/2201.11903)

- **Automatic Chain of Thought Prompting** — Zhang et al., 2022
  - *Key idea*: Automated the creation of CoT demonstrations — instead of manually crafting examples, cluster questions by similarity and generate diverse CoT examples automatically.
  - 🔗 [Download](https://arxiv.org/abs/2210.03493)

- **Large Language Models are Zero-Shot Reasoners** — Kojima et al., 2023
  - *Key idea*: The simple prompt "Let's think step by step" enables zero-shot reasoning without any examples. This single phrase unlocks latent reasoning capabilities in LLMs.
  - *Breakthrough*: Showed that reasoning is a latent capability that can be activated without demonstrations.
  - 🔗 [Download](https://arxiv.org/abs/2205.11916)

- **Aligning Books and Movies** — Zhu et al., 2015
  - *Key idea*: Learned representations by aligning books with their movie versions — an early form of multimodal contrastive learning using story structure as supervision.
  - 🔗 [Download](https://arxiv.org/abs/1506.06724)

- **Scientist AI** — Bengio, 2025
  - *Key idea*: Explores how AI could assist or replace aspects of the scientific process — hypothesis generation, experimental design, and theory synthesis. Discusses what makes scientific reasoning different from standard LLM reasoning.
  - 🔗 [Download](https://arxiv.org/abs/2502.15657)

### Key Concepts
- **Chain-of-thought** showed that LLMs have latent reasoning capabilities that are only expressed through appropriate prompting.
- **Zero-shot CoT** ("Let's think step by step") is a remarkably simple but effective technique.
- The gap between **memorization and reasoning** is a central open question — do LLMs truly reason or simulate reasoning patterns from training data?

---

## AI Safety & Adversarial Attacks

### Papers

- **POISONPROMPT: Backdoor Attack on LLMs**
  - *Key idea*: Demonstrated that LLMs can be backdoored through poisoned prompts — specific trigger phrases cause the model to produce attacker-chosen outputs while behaving normally otherwise.
  - 🔗 [Download](https://arxiv.org/abs/2310.12439)

- **Prompt-Specific Poisoning Attacks**
  - *Key idea*: Showed that instruction-tuned models are vulnerable to targeted poisoning — an attacker can corrupt model behavior on specific prompts by injecting a small number of poisoned training examples.
  - 🔗 [Download](https://arxiv.org/abs/2310.13828) *(search arXiv 2023)*

- **Glaze: Protecting Artists from Style Mimicry**
  - *Key idea*: Applied adversarial perturbations to artwork images that are imperceptible to humans but cause AI models to learn a different style. Protects artists from unauthorized style transfer.
  - *Significance*: First practical defense for creators against generative AI art theft.
  - 🔗 [Download](https://arxiv.org/abs/2302.04222)

- **Debiasing Word Embeddings** — Bolukbasi et al., 2016
  - *Key idea*: Showed that word embeddings encode gender stereotypes (man:computer programmer :: woman:homemaker) and proposed post-hoc debiasing through projection onto a gender subspace.
  - *Breakthrough*: Highlighted that ML models amplify societal biases present in training data.
  - ⚠️ No verified link available

### Key Concepts
- **Backdoor attacks** are particularly dangerous because they persist through fine-tuning and are invisible during normal usage.
- **Adversarial robustness** in generative AI has dual aspects: protecting models from attack and protecting creators from misuse.
- **Bias in embeddings** reflects training data distributions — debiasing is necessary but insufficient (biases reappear in downstream tasks).

---

## Multimodal Foundation Models

### Papers

- **Chameleon: Mixed-Modal Early-Fusion Foundation Model** — Meta, 2025
  - *Key idea*: Single transformer that natively processes text, images, and code in a unified token space ("early fusion"). Unlike CLIP (separate encoders), Chameleon uses a single architecture for all modalities.
  - *Significance*: Moves toward truly multimodal understanding where modalities are treated equivalently.
  - 🔗 [Download](https://arxiv.org/abs/2405.09818)

### Key Concepts
- **Early fusion** (single unified model) vs. **late fusion** (separate encoders, combined later) is a key architectural choice.
- Multimodal models can relate information across modalities — understanding an image by relating it to text descriptions and vice versa.

---

[← Previous: Federated Learning](11-federated-learning.md) | [→ Next: Immunology & Molecular Biology](13-immunology-molecular.md)
