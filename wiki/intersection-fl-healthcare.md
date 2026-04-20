# Federated Learning × Healthcare

[← Back to Wiki Index](../Wiki.md)

---

> *Training medical AI across hospitals without sharing patient data*

## The Fundamental Tension

Medical AI needs **massive, diverse datasets** to be clinically useful. But medical data is:
- **Siloed** across hospitals (legal, regulatory, competitive barriers)
- **Protected** by HIPAA, GDPR, and institutional review boards
- **Heterogeneous** — different scanners, protocols, populations across sites

Federated learning resolves this tension: **bring the model to the data, not the data to the model.**

---

## How FL Works in Healthcare

### The Basic Protocol (FedAvg)
```
Round t:
  1. Server sends global model θ_t to all hospitals
  2. Each hospital trains on local data: θ_i = LocalTrain(θ_t, D_i)
  3. Hospitals send model updates Δθ_i = θ_i - θ_t to server
  4. Server aggregates: θ_{t+1} = θ_t + (1/N)Σ Δθ_i
  5. Repeat until convergence
```

**FedML** provides the framework for implementing this — supporting PyTorch, TensorFlow, and various aggregation strategies.

### Healthcare-Specific Challenges

**Non-IID data**: Hospital A specializes in stroke, Hospital B in tumors. Their data distributions are fundamentally different. Standard FedAvg struggles with this statistical heterogeneity.

**FADL (Federated Autonomous Deep Learning)**: Addresses non-IID by allowing each hospital to maintain a personalized model while still benefiting from collaborative training.

**Brain segmentation across sites**: SynthSeg ([Billot et al., 2023](https://arxiv.org/abs/2301.07756)) sidesteps the federation problem for segmentation by training on synthetic data — but federated learning is still needed for tasks requiring real clinical labels (diagnosis, prognosis, treatment response).

---

## Privacy Attacks: Why Naive FL Isn't Enough

**Gradient inversion attacks** demonstrate that raw model updates can reveal training data:
- From gradients alone, attackers can reconstruct the **exact brain MRI** used for training
- Even averaged gradients leak information about individual patients

**Membership inference**: Can determine whether a specific patient's data was used in training — violating privacy even without reconstructing the image.

**SRATTA** (Secure Robust Aggregation against Targeted Attacks): Addresses both privacy AND adversarial robustness — malicious hospitals might send corrupted updates.

**The uncomfortable truth**: Federated learning alone does **not** guarantee privacy. It reduces the attack surface but requires additional protections.

---

## Secure Multi-Party Computation (SMPC) + FL

**Bonawitz et al.** ([2017](https://eprint.iacr.org/2017/281.pdf)) designed secure aggregation where:
- Each hospital encrypts its model update
- The server can compute the **aggregate** without seeing any individual update
- Even if the server is compromised, individual hospital updates remain private

**Turbo-Aggregate** scales this to thousands of participants with near-linear communication cost.

**SMPC for IoMT** (Internet of Medical Things): Extends secure aggregation to edge devices — wearables, continuous monitors, point-of-care devices.

**Cheetah** ([Huang et al., 2022](https://www.usenix.org/system/files/sec22-huang-zhicong.pdf)): Ultra-fast secure 2-party computation for neural network inference — enabling private prediction where neither the model owner nor the patient reveals their private input.

**FL-SMPC** combined: The model is trained federally (distributed across hospitals) AND the aggregation is secured cryptographically. This provides both **data locality** and **update privacy**.

---

## The Straggler Problem in Medical FL

**Real-world challenge**: Hospital C has an old GPU and takes 10× longer than others. Waiting for all participants creates an unacceptable bottleneck.

**Coded computation** (Atallah 2021): Add redundancy to tolerate slow workers — the aggregation can proceed with a subset of responses while maintaining the quality of the full aggregate.

**Connection to distributed systems**: The same straggler mitigation techniques from Exoshuffle and elastic cloud computing apply to federated medical training.

---

## Blockchain for FL Audit Trails

**Medical compliance** requires audit trails — who trained what model on which data and when.

**Blockchain-based FL** provides:
- Immutable record of all training rounds
- Verification that aggregation was performed correctly (SMPC verification)
- Transparent governance for multi-institution collaborations

---

## What Medical FL Enables

### Cross-Scanner Brain Segmentation
- Train a brain segmentation model across 50 hospitals with different MRI scanners
- The model learns scanner-invariant features naturally
- This directly addresses the **domain generalization** problem in medical imaging

### Rare Disease Detection
- Any single hospital may see only 5-10 cases of a rare condition
- Federated learning aggregates knowledge from hundreds of hospitals
- **Normative modeling** benefits especially: the normative distribution is estimated from the combined population

### Clinical Trial Prediction
- Predict treatment response using data from multiple trial sites
- Privacy preserved: no individual patient data leaves the site
- **Bayesian FL**: Propagate uncertainty through the federation to get calibrated predictions

---

## The Full Privacy-Preserving Medical AI Stack

```
┌─────────────────────────────────────┐
│          Clinical Interface          │
│    (Uncertainty-aware predictions)   │
├─────────────────────────────────────┤
│       Conformal Prediction           │
│   (Distribution-free guarantees)     │
├─────────────────────────────────────┤
│    Bayesian Neural Network           │
│   (Calibrated uncertainties)         │
├─────────────────────────────────────┤
│      Federated Training              │
│   (Data stays at each hospital)      │
├─────────────────────────────────────┤
│     Secure Aggregation (SMPC)        │
│   (Updates encrypted in transit)     │
├─────────────────────────────────────┤
│    Differential Privacy              │
│   (Noise added to updates)           │
├─────────────────────────────────────┤
│      Blockchain Audit Trail          │
│   (Compliance & governance)          │
└─────────────────────────────────────┘
```

**The vision**: A medical AI system that is trained across hundreds of hospitals, provides calibrated uncertainty estimates, protects patient privacy at every layer, and maintains a verifiable audit trail.

---

### Relevant Topic Pages
- [XI. Federated Learning & Privacy](11-federated-learning.md)
- [VII. Brain Segmentation](07-brain-segmentation.md)
- [III. Bayesian & Uncertainty Methods](03-bayesian-uncertainty.md)
- [XV. Distributed Systems](15-distributed-systems.md)
