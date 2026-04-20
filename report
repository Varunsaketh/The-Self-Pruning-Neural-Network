# 📄 Self-Pruning Neural Network — Detailed Report

## 1. Introduction

Neural networks often contain a large number of redundant parameters, leading to inefficiency in computation and memory usage. This project explores a method where the network **learns to prune itself during training**, eliminating unnecessary connections.

---

## 2. Problem Statement

Traditional pruning methods are applied **after training**, requiring additional steps. The goal of this project is to:

* Integrate pruning **into the training process**
* Reduce model complexity
* Maintain acceptable accuracy

---

## 3. Methodology

### 3.1 Prunable Linear Layer

A custom layer is introduced where each weight is multiplied by a learnable gate:

[
W' = W \cdot \sigma(G)
]

Where:

* ( W ) = weight matrix
* ( G ) = gate scores
* ( \sigma ) = sigmoid function

---

### 3.2 Sparsity Regularization

To encourage pruning, L1 regularization is applied to gate values:

[
L_{sparsity} = \sum \sigma(G)
]

This pushes gate values toward zero.

---

### 3.3 Total Loss Function

[
L = L_{classification} + \lambda \cdot L_{sparsity}
]

---

## 4. Dataset

* CIFAR-10 dataset
* 10 classes
* 32×32 RGB images

---

## 5. Model Architecture

* Fully connected network
* Input: 3072 features
* Hidden layers: 1024 → 512 → 256
* Output: 10 classes

Activation: ReLU
Regularization: Dropout

---

## 6. Training Details

* Optimizer: Adam
* Learning Rate: 0.003
* Epochs: 50
* Batch Size: 128

---

## 7. Experiments

Multiple values of λ were tested:

### Low λ

* High accuracy (~90%+)
* No pruning observed

### Medium λ

* Moderate sparsity
* Slight drop in accuracy

### High λ

* High sparsity (many weights pruned)
* Noticeable accuracy reduction

---

## 8. Results

The experiments show a clear trade-off:

* Increasing λ → increases sparsity
* Increasing sparsity → reduces accuracy

---

## 9. Analysis

* The model successfully learns which connections are less important
* Sparsity emerges naturally due to L1 regularization
* Threshold selection affects measured sparsity

---

## 10. Limitations

* Fully connected architecture (not optimal for images)
* Pruning is unstructured (weight-level)
* Requires tuning of λ

---

## 11. Future Work

* Extend to CNN architectures
* Use structured pruning (filters, neurons)
* Deploy optimized model for inference

---

## 12. Conclusion

This project demonstrates that neural networks can be trained to become **efficient and compact** by integrating pruning into the learning process. The balance between accuracy and sparsity is controlled by the regularization parameter λ.

---

## 13. References

* PyTorch Documentation
* CIFAR-10 Dataset
* Research on Neural Network Pruning
