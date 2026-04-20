# I. Foundational Deep Learning

[← Back to Wiki Index](../Wiki.md)

---

## Convolutional Networks & Image Recognition

The convolutional neural network (CNN) revolution began with AlexNet's ImageNet victory (2012) and deepened through architectures that systematically improved depth, efficiency, and accuracy.

### Papers

- **ImageNet Classification with Deep Convolutional Neural Networks** — Krizhevsky, Sutskever, Hinton
  - *Key idea*: Demonstrated that deep CNNs trained on GPUs could dramatically outperform hand-crafted features on large-scale image classification (ImageNet). Introduced ReLU activations, dropout regularization, and data augmentation as standard techniques.
  - *Breakthrough*: Won ILSVRC 2012 by a massive margin, launching the deep learning era.
  - 🔗 [Download](https://papers.nips.cc/paper/2012/hash/c399862d3b9d6b76c8436e924a68c45b-Abstract.html)

- **Large Scale Image Recognition with Deep CNNs (VGGNet)** — Simonyan & Zisserman, 2014
  - *Key idea*: Showed that network depth (16-19 layers) with small 3×3 convolution filters consistently improves performance. Established that deeper = better, within limits.
  - *Breakthrough*: VGG-16/19 became standard feature extractors for transfer learning.
  - 🔗 [Download](https://arxiv.org/abs/1409.1556)

- **Image Super-Resolution Using CNN** — Dong et al., 2015
  - *Key idea*: SRCNN demonstrated that a simple 3-layer CNN could learn end-to-end mappings from low to high resolution images, outperforming traditional interpolation and sparse-coding methods.
  - *Breakthrough*: First successful application of deep learning to image super-resolution.
  - 🔗 [Download](https://arxiv.org/abs/1501.00092)

- **EfficientNet: Rethinking Model Scaling for CNNs** — Tan & Le, 2019
  - *Key idea*: Proposed compound scaling that uniformly scales depth, width, and resolution using a fixed ratio. Uses neural architecture search (NAS) to find a base model.
  - *Breakthrough*: Achieved state-of-the-art accuracy while being 8× smaller and 6× faster than previous best models.
  - 🔗 [Download](https://arxiv.org/abs/1905.11946)

- **MobileNets: Efficient CNNs for Mobile Vision Applications** — Howard et al., 2017
  - *Key idea*: Introduced depthwise separable convolutions to dramatically reduce computation while maintaining accuracy. Width and resolution multipliers allow tuning for resource constraints.
  - 🔗 [Download](https://arxiv.org/abs/1704.04861)

- **MobileNetV2: Inverted Residuals and Linear Bottlenecks** — Sandler et al., 2018
  - *Key idea*: Introduced inverted residual blocks with linear bottlenecks — expand in low-dimensional space, filter, then project back. Prevents information loss in thin layers.
  - 🔗 [Download](https://arxiv.org/abs/1801.04381)

- **YOLO: You Only Look Once** — Redmon et al., 2016
  - *Key idea*: Unified object detection as a single regression problem from image pixels to bounding boxes and class probabilities. Processes images in one forward pass through the network.
  - *Breakthrough*: Enabled real-time object detection (45 FPS) while maintaining competitive accuracy.
  - 🔗 [Download](https://arxiv.org/abs/1506.02640)

### Key Concepts
- The progression from shallow to deep networks (AlexNet → VGG → ResNet → EfficientNet) revealed that **depth and architectural efficiency** are the dominant factors in visual recognition.
- **Depthwise separable convolutions** (MobileNets) decoupled spatial filtering from channel mixing, enabling mobile deployment.
- **Compound scaling** (EfficientNet) showed depth, width, and resolution should be scaled together.

---

## Transformers & Attention Mechanisms

The transformer architecture has become the dominant paradigm across NLP, vision, and increasingly, scientific computing. This collection traces the evolution from early attention mechanisms to modern multi-modal transformers.

### Papers

- **Attention Is All You Need** — Vaswani et al., 2017
  - *Key idea*: Replaced recurrence entirely with multi-head self-attention, enabling parallel processing of sequences. Introduced positional encoding to inject order information.
  - *Breakthrough*: The Transformer architecture became the foundation for BERT, GPT, and virtually all modern NLP and vision models.
  - 🔗 [Download](https://arxiv.org/abs/1706.03762)

- **Neural Machine Translation by Jointly Learning to Align and Translate** — Bahdanau et al., 2015
  - *Key idea*: Introduced the additive attention mechanism that allows a decoder to selectively focus on different parts of the input. Solved the "bottleneck" problem of fixed-length context vectors.
  - *Breakthrough*: First successful attention mechanism — the precursor to all transformer architectures.
  - 🔗 [Download](https://arxiv.org/abs/1409.0473)

- **Effective Approaches to Attention-based Neural Machine Translation** — Luong et al., 2015
  - *Key idea*: Proposed global vs. local attention, and multiplicative (dot-product) attention — simpler and faster than Bahdanau's additive attention.
  - 🔗 [Download](https://arxiv.org/abs/1508.04025)

- **An Image is Worth 16×16 Words: Vision Transformer (ViT)** — Dosovitskiy et al., 2021
  - *Key idea*: Applied a pure transformer to sequences of image patches, showing that with sufficient data, transformers can match or exceed CNNs on vision tasks without any convolution.
  - *Breakthrough*: Demonstrated that the inductive bias of convolutions is not necessary — scale and data are sufficient.
  - 🔗 [Download](https://arxiv.org/abs/2010.11929)

- **AFNO: Adaptive Fourier Neural Operator as Efficient Token Mixer for Transformers** — Guibas et al., 2022
  - *Key idea*: Replaces standard self-attention token mixing with learned Fourier-domain operations, achieving global mixing in O(N log N) instead of O(N²).
  - *Breakthrough*: Enabled transformer-scale models for high-resolution inputs (weather prediction, scientific imaging).
  - 🔗 [Download](https://arxiv.org/abs/2111.13587)

- **Performers: Fast Attention Via Positive Orthogonal Random Features** — Choromanski et al., 2022
  - *Key idea*: Approximates softmax attention using random feature maps (FAVOR+), reducing attention from O(N²) to O(N) in both time and memory.
  - 🔗 [Download](https://arxiv.org/abs/2009.14794)

- **Structured Attention Networks** — Kim et al., 2017
  - *Key idea*: Extended attention to produce structured outputs (trees, segments) rather than flat distributions, using CRFs and other structured prediction methods inside the attention layer.
  - 🔗 [Download](https://arxiv.org/abs/1702.00887)

- **Cross-table Pretraining for Tabular Transformers / XTab** — Zhu et al., 2023
  - *Key idea*: Adapted transformers for tabular data by pretraining across multiple heterogeneous tables, with federated learning-inspired column alignment.
  - 🔗 [Download](https://arxiv.org/abs/2305.06090)

- **TransMorph: Transformer for Unsupervised Medical Image Registration** — Chen et al., 2022
  - *Key idea*: Combined Swin Transformer with a ConvNet decoder for deformable medical image registration. Self-attention captures long-range spatial correspondences that CNNs miss.
  - 🔗 [Download](https://arxiv.org/abs/2111.10480)

### Key Concepts
- **Self-attention** computes pairwise relationships between all elements, enabling global context — but at O(N²) cost.
- **Linear attention** approximations (Performers, AFNO) bring transformer-like modeling to high-resolution and long-sequence domains.
- Transformers' lack of inductive bias is both a weakness (need more data) and a strength (generalize across modalities).

---

## Residual Learning & Efficient Architectures

### Papers

- **Deep Residual Learning for Image Recognition (ResNet)** — He et al., 2016
  - *Key idea*: Introduced skip connections that allow gradients to flow directly through identity mappings. This solved the degradation problem where deeper networks paradoxically performed worse.
  - *Breakthrough*: Enabled training of 152+ layer networks; won ILSVRC 2015. The skip connection became a universal building block.
  - 🔗 [Download](https://arxiv.org/abs/1512.03385)

- **Reversible Residual Network: Backprop Without Storing Activations** — Gomez et al., 2017
  - *Key idea*: Made residual blocks invertible so activations can be recomputed from outputs during backpropagation, eliminating the need to store them in memory. Reduces memory from O(L) to O(1) in depth.
  - *Breakthrough*: Enabled training much deeper networks on limited GPU memory.
  - 🔗 [Download](https://arxiv.org/abs/1707.04585)

### Key Concepts
- **Skip connections** are one of the most important architectural innovations in deep learning — they appear in ResNets, U-Nets, DenseNets, and transformers.
- **Memory-efficient backpropagation** through reversible layers trades compute for memory, critical for large-scale training.

---

## Neural Implicit Representations (NeRF, SIREN)

Neural implicit representations encode continuous signals (3D scenes, images, audio) as the weights of a neural network, enabling resolution-independent and compact representations.

### Papers

- **NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis** — Mildenhall et al., 2020
  - *Key idea*: Encodes a 3D scene as a continuous volumetric function mapping (x, y, z, θ, φ) → (color, density). Novel views are rendered by volumetric ray marching through the learned field.
  - *Breakthrough*: Achieved photorealistic novel view synthesis from sparse images, spawning hundreds of follow-up works.
  - 🔗 [Download](https://arxiv.org/abs/2003.08934)

- **Neural Radiance Field in 3D Vision: A Comprehensive Review** — Gao et al., 2025
  - *Key idea*: Surveys the NeRF ecosystem — fast training methods, dynamic scenes, generalization, and applications in robotics, AR/VR, and medical imaging.
  - 🔗 [Download](https://arxiv.org/abs/2210.00379)

- **Neural Radiance Field in Medical Imaging: Challenges** — Wang et al., 2024
  - *Key idea*: Reviews NeRF adaptations for medical imaging — CT/MRI view synthesis, sparse-view reconstruction, and surgical scene understanding. Identifies key challenges: data scarcity, physical accuracy, and real-time rendering.
  - 🔗 [Download](https://arxiv.org/abs/2404.07160)

- **Implicit Neural Representations with Periodic Activation Functions (SIREN)** — Sitzmann et al., 2020
  - *Key idea*: Used sine activations instead of ReLU to represent signals with their derivatives. Periodic activations are natural fits for signals with complex structure.
  - *Breakthrough*: First implicit representation that accurately captured gradients, Laplacians, and other differential properties — crucial for physics-based applications.
  - 🔗 [Download](https://arxiv.org/abs/2006.09661)

- **Neural Style Transfer** — Gatys et al., 2016
  - *Key idea*: Separated content and style in CNN feature space by optimizing an image to match content features of one image and Gram-matrix style features of another.
  - *Breakthrough*: Demonstrated that neural networks learn disentangled representations of content and artistic style.
  - 🔗 [Download](https://arxiv.org/abs/1508.06576)

### Key Concepts
- **Implicit representations** trade discrete grids for continuous neural functions — enabling infinite resolution and compact storage.
- **NeRF** unified 3D reconstruction and rendering through differentiable volumetric rendering.
- **SIREN** showed that activation function choice profoundly affects what a network can represent, especially for signals governed by differential equations.

---

[→ Next: Generative Models & Density Estimation](02-generative-models.md)
