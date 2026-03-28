# 🧠 Autoencoder Assignment (Deep Learning)

## 📌 Overview
This repository contains the implementation of **Autoencoders (AE)** for understanding:
- Latent space representation
- Image reconstruction
- Denoising and robustness
- Anomaly detection
- Ablation study

---

## 📂 Datasets Used
- **MNIST** – 28×28 grayscale images
- **Tiny-ImageNet-10** – 64×64 RGB images (10 classes)

---

## ⚙️ Technical Details
- Optimizer: Adam  
- Loss: Mean Squared Error (MSE)  
- Epochs: 30  
- Architectures:
  - Fully Connected AE (MNIST)
  - Convolutional AE (Tiny-ImageNet)

---

# 🧩 Part 1: Bottleneck Challenge (Undercomplete AE)

## 🎯 Goal
Understand compression into latent space.

## 🏗 Architecture
Encoder: `784 → 128 → 64 → N`  
Decoder: `N → 64 → 128 → 784`

## 🧪 Experiments
- N = 2  
- N = 32  

## 📊 Observation
- N=2 → Blurry images  
- N=32 → Better reconstruction  

## 💡 Reason
Smaller bottleneck → less information capacity → higher loss

---

# 🧩 Part 2: Denoising Autoencoder

## 🎯 Goal
Reconstruct clean images from noisy input.

## 🛠 Method
Noise added:
- Gaussian Noise  
- Salt & Pepper Noise  

## 🔁 Pipeline
Noisy Image → Autoencoder → Clean Image  

## 📊 Output
- Original Image  
- Noisy Image  
- Reconstructed Image  

## Insight
Model learns robust and meaningful features

---

# Part 3: Latent Space Visualization

## 🔹 3.1 MNIST (2D Latent Space)

- Extract latent vectors (N=2)
- Plot scatter graph

## Observation
- Similar digits cluster together  
- Some overlap (e.g., 1 & 7)

---

## 3.2 Anomaly Detection (Tiny-ImageNet)

## Method
- Train on 9 classes  
- Test on unseen class  

## Metric
Reconstruction Error (MSE)

## Observation
- Seen → Low error  
- Unseen → High error  

## Conclusion
Autoencoder can detect anomalies

---

#  Part 4: Ablation Study

## Goal
Compare activation functions

## 🧪 Experiment
- Sigmoid vs Tanh
- Sigmoid performs better for [0,1] images  
