# FCNN From Scratch Using NumPy  
### Adult Income Classification (No Frameworks)

## Overview
This project implements a **3-layer Fully Connected Neural Network (FCNN) from scratch** using only **NumPy and standard Python libraries**.  
The task is binary classification on the **Adult Income (Census) dataset**, predicting whether a person earns more than **$50K per year**.

No deep learning frameworks (PyTorch / TensorFlow / Keras) are used.

---

## Dataset
The **Adult Income dataset** contains demographic and employment-related census data.

### Features
- **Numerical:** age, fnlwgt, education-num, capital-gain, capital-loss, hours-per-week  
- **Categorical:** workclass, education, marital-status, occupation, relationship, race, sex, native-country  

**Target:**  
- `1` → income > $50K  
- `0` → income ≤ $50K  

---

## Data Preprocessing
- Missing values (`?`) replaced with `NaN`
- Categorical features encoded using **one-hot encoding**
- First category dropped to avoid dummy-variable trap
- Provided files used:
  - `adult.data` (training)
  - `adult.test` (testing)
- Test set reindexed to match training features

---

## Model Architecture
A **3-layer FCNN**:
- Input layer: number of input features  
- Hidden Layer 1: 64 neurons, **ReLU**
- Hidden Layer 2: 32 neurons, **ReLU**
- Output Layer: 1 neuron, **Sigmoid**

### Initialization
- **He Initialization** for weights  
- Biases initialized to zero  

---

## Training Details
- Loss Function: **Binary Cross-Entropy**
- Optimizer: **Stochastic Gradient Descent (SGD)**
- Learning Rate: `0.01`
- Epochs: `100,000`
- Loss printed **every 100 iterations**
- One sample used per update (true SGD)



## Feature Scaling Experiment
The model is trained twice:
1. Using **raw (unscaled) data**
2. Using **Min-Max scaled data**

Min-Max Scaling:

---

## Results

### Accuracy Comparison

| Dataset Type | Test Accuracy |
|-------------|---------------|
| Raw Data (Unscaled) | **76.37%** |
| Min-Max Scaled Data | **83.85%** |

The scaled model converges faster and generalizes better.

---

## Effect of Scaling on Gradients
- Raw data has features with very different ranges (e.g., Age vs Capital Gain)
- Large-scale features dominate gradients
- Leads to unstable and slow SGD updates

**After scaling:**
- Gradients are well-conditioned
- Faster convergence
- Higher final accuracy

---

## Conclusion
This project successfully demonstrates a **from-scratch FCNN implementation using NumPy**.  
Feature scaling plays a critical role in stabilizing gradients and improving performance.  
The final model exceeds the required **75% test accuracy**, fulfilling all assignment requirements.

--
