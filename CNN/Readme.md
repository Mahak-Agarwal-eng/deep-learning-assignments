# 🖼️ Convolutional Neural Networks (CNN) Assignment

## 📌 Objective
The goal of this assignment is to understand the spatial intelligence of Convolutional Neural Networks (CNNs) through hands-on experiments and analysis. The assignment is divided into four parts, each focusing on a specific aspect of CNNs.

---

## 📂 Datasets Used
- **MNIST**: 28×28 grayscale images of handwritten digits.
- **Tiny-ImageNet-10**: 64×64 RGB images (10 classes).

---

## ⚙️ Technical Specifications
- **Library Constraint**: Use `torch.nn` (PyTorch) or `tf.keras.layers` (Keras).
- **Mandatory Component**: Implement a custom forward pass (PyTorch) or use the Functional API (Keras) instead of a simple Sequential stack.
- **Tasks**:
  - Manual dimension calculations for CNN layers.
  - Comparison of Fully Connected Neural Networks (FCNNs) and CNNs.
  - Visualization of learned features and activation maps.
  - Experiments on optimization techniques and data augmentation.

---

# 🧩 Part 1: The Geometry of Convolutions

### 🎯 Goal
Understand how spatial dimensions change across layers in a CNN.

### 🏗 Task 1.1: Manual Dimension Map
- **Input**: 64×64×3 (Tiny-ImageNet-10).
- **Architecture**:
  - 3 Convolutional layers (3×3 kernels).
  - 2 Max-Pooling layers (2×2, stride 2).
  - 1 Fully Connected layer.
- **Deliverable**:
  - Calculate the output shape for each layer manually.
  - Verify calculations using `print(x.shape)` (PyTorch) or `model.summary()` (Keras).

### 🧠 Thought Experiment
- **Without Pooling**: How many more parameters does the Fully Connected layer require?  
- **Parameter Explosion**: Discuss why removing pooling layers leads to a significant increase in parameters.

---

# 🧩 Part 2: The "Why CNN?" Experiment (Spatial Invariance)

### 🎯 Goal
Demonstrate the robustness of CNNs compared to FCNNs for vision tasks.

### 🏗 Task 2.1: The Robustness Duel
- **Models**:
  1. **Model A**: Best FCNN from the previous assignment.
  2. **Model B**: A simple 2-layer CNN.
- **Dataset**: MNIST.
- **Experiment**:
  - Train both models on MNIST.
  - Test on a "Shifted MNIST" dataset (images shifted 4 pixels to the right).
- **Deliverable**:
  - Report the accuracy drop for both models.
  - Analyze why CNNs maintain higher accuracy despite the shift.
  - Discuss the role of weight sharing in convolutional layers.

---

# 🧩 Part 3: Feature Extraction & Visual Interpretability

### 🎯 Goal
Visualize how CNNs learn to "see" textures and objects.

### 🏗 Task 3.1: The Filter Gallery
- **Task**:
  - Extract and plot the weights of the first layer kernels for CNNs trained on MNIST and Tiny-ImageNet-10.
- **Deliverable**:
  - Display the kernels in a grid.
  - Identify "Gabor-like" filters (e.g., edge detectors, color blobs).
  - Compare the filters learned for MNIST and Tiny-ImageNet-10.
  - Analyze differences between FCNN and CNN filters.

### 🏗 Task 3.2: The Receptive Field Experiment
- **Task**:
  - Select one image from each dataset.
  - Pass it through the network and visualize the activation maps after:
    1. The first convolutional layer.
    2. The final convolutional layer.
- **Deliverable**:
  - Display the original image alongside the activation maps.
  - Analyze how the network's focus changes across layers.
  - Compare the activation maps for MNIST and Tiny-ImageNet-10.

---

# 🧩 Part 4: Advanced Optimization & Robustness

### 🎯 Goal
Master advanced techniques to improve CNN performance.

### 🏗 Task 4.1: The Depth vs. Normalization Duel
- **Dataset**: Tiny-ImageNet-10.
- **Experiment**:
  - Build a deep CNN (6-8 layers).
  - Train the model:
    1. Without Batch Normalization.
    2. With Batch Normalization after every convolutional layer.
- **Deliverable**:
  - Plot the mean and variance of activations for the 5th layer across 500 batches.
  - Quantitatively show how Batch Normalization reduces internal covariate shift.

### 🏗 Task 4.2: Data Augmentation "Sanity Check"
- **Dataset**: Tiny-ImageNet-10.
- **Experiment**:
  - Implement a data augmentation pipeline using:
    - `transforms.RandomRotation(30)`
    - `transforms.ColorJitter()`
  - Train the model:
    1. Without data augmentation.
    2. With data augmentation.
- **Deliverable**:
  - Report the final test accuracy for both cases.
  - Analyze whether augmentation helps more on the training set or the test set, and explain why.

---

## 📊 Conclusion
This assignment provides a comprehensive understanding of CNNs, including their spatial intelligence, robustness, and optimization techniques. By completing these tasks, you will gain insights into the inner workings of CNNs and their superiority over FCNNs for vision tasks.