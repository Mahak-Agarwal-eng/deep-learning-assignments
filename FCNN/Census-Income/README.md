# Census Income Classification (From Scratch)

## Problem Statement
The goal of this project is to predict whether a person’s annual income exceeds **$50K/year** based on census data attributes such as age, education, occupation, working hours, etc.

This is a **binary classification problem**, commonly known as the **Census Income / Adult Income Dataset** problem.

---

## Dataset
- **Source**: UCI Machine Learning Repository (Adult Dataset)
- **Target Variable**:  
  - `<=50K`  
  - `>50K`
- **Features include**:
  - Age
  - Education
  - Occupation
  - Workclass
  - Marital Status
  - Hours per week
  - Capital gain/loss
  - Gender, Race, etc.

Categorical features are encoded before training.

---

## Model Architecture
The model is implemented **from scratch using NumPy**, without using deep learning frameworks like TensorFlow or PyTorch.

**Fully Connected Neural Network (FCNN):**
- Input Layer
- Hidden Layer 1 (ReLU)
- Hidden Layer 2 (ReLU)
- Output Layer (Sigmoid)

---

## Implementation Details
- **Weight Initialization**: He Initialization  
- **Bias Initialization**: Zeros  
- **Activation Functions**:
  - ReLU (Hidden Layers)
  - Sigmoid (Output Layer)
- **Loss Function**: Binary Cross-Entropy Loss  
- **Optimizer**: Mini Batch Gradient Descent 
- **Frameworks Used**:  
  - NumPy  
  - Standard Python Libraries only

## Effect of Feature Scaling on Model Performance
The model was trained twice—once with raw data and once with Min-Max Scaled data—to observe the impact on gradient stability and accuracy.

| Feature Set        | Convergence Behavior                                                                 | Test Accuracy |
|--------------------|--------------------------------------------------------------------------------------|---------------|
| Raw Data           | Highly unstable gradients due to varying feature scales, prone to overflow           | ~76.37%      |
| Min-Max Scaled     | Stable and smooth loss curve; gradients are well-balanced across features            | ~83.91%       |

