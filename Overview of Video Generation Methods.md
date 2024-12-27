# Overview of Video Generation Methods

## 1. Variational Auto-Encoder (VAE)

### Foundation
- Based on the transformer architecture

### Key Challenges
- Text-to-video training faces ambiguity issues: multiple valid video interpretations can exist for a single text description
- Need for additional contextual information beyond text input

### Solution Architecture
The VAE approach uses two key components:

1. **Information Model (Encoder)**
   - Trained alongside the image generation model
   - Extracts contextual information from input
   - Output can be abstract (vectors) rather than human-interpretable

2. **Image Generation Model (Decoder)**
   - Generates output based on text and encoded information

### Training Objective
- Minimize the difference between input and output images
- Both encoder and decoder are trained simultaneously
- No requirement for human-interpretable intermediate representations

### Testing Process
- Generate outputs through vector sampling from the learned latent space

## 2. Flow-Based Models

### Key Characteristics
- Focuses solely on decoder training
- Uses invertible architecture
- Encoder functionality achieved through decoder inversion

## 3. Diffusion Models

### Core Concepts
- Implements iterative denoising process
- Uses transformer architecture for denoising model
- Decoder applied multiple times in sequence

## 4. Generative Adversarial Networks (GAN)

### Architecture Components
1. **Generator**
   - Aims to create convincing outputs
   - Learns from discriminator feedback
   - Can be combined with VAE, flow-based, or diffusion approaches

2. **Discriminator**
   - Evaluates text-image pairs
   - Similar to CLIP's evaluation mechanism
   - Functions analogously to a reward model in RLHF

### Training Process
- Alternates between generator and discriminator training
- Requires both positive and negative examples
- Adversarial training framework

### Notable Characteristics
- Flexible architecture that can be integrated with other generation methods
- Similar conceptual framework to RLHF (Reinforcement Learning from Human Feedback)

## References
1. https://www.youtube.com/watch?v=OYN_GvAqv-A&list=PLJV_el3uVTsPz6CTopeRp2L2t4aL_KgiI&index=19
2. language model for documentation improvement.

---

> **Note**: This document is part of the learning notes series on video generation methods.
