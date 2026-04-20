# The-Self-Pruning-Neural-Network

## 🚀 Overview

This project implements a **Self-Pruning Neural Network** that learns not only to classify images but also to **automatically remove unnecessary connections during training**.

Unlike traditional neural networks, this model introduces **learnable gates** that control whether each weight should be active or pruned.

---

## 🎯 Objectives

* Build a neural network that performs **automatic pruning during training**
* Analyze the **trade-off between accuracy and sparsity**
* Demonstrate how **L1 regularization encourages sparsity**

---

## 🏗️ Model Architecture

```
Input (3072)
   ↓
PrunableLinear (1024)
   ↓
ReLU + Dropout
   ↓
PrunableLinear (512)
   ↓
ReLU + Dropout
   ↓
PrunableLinear (256)
   ↓
ReLU + Dropout
   ↓
PrunableLinear (10)
```

---

## 🔧 Key Concept: Prunable Layer

Each weight is controlled by a learnable gate:

```
Effective Weight = Weight × Sigmoid(Gate Score)
```

* Gate ≈ 1 → Connection is active
* Gate ≈ 0 → Connection is pruned

---

## 📉 Loss Function

```
Total Loss = Classification Loss + λ × Sparsity Loss
```

* **Classification Loss** → Accuracy (CrossEntropy)
* **Sparsity Loss** → L1 norm of gates (encourages pruning)

---

## 📊 Experiments

Different λ values were tested:

| Lambda | Accuracy | Sparsity | Observation    |
| ------ | -------- | -------- | -------------- |
| Low λ  | High     | Low      | No pruning     |
| Medium | Moderate | Moderate | Balanced       |
| High λ | Lower    | High     | Strong pruning |

---

## 🔍 Key Observations

* Increasing λ increases sparsity
* High sparsity reduces model size but may reduce accuracy
* Model learns to **selectively remove less important connections**

---

## 🧪 Dataset

* CIFAR-10 (60,000 images, 10 classes)
* Automatic download via `torchvision`

---

## ⚙️ Tech Stack

* Python
* PyTorch
* NumPy
* Matplotlib

---

## ▶️ How to Run

```bash
git clone <your-repo-link>
cd self-pruning-nn
```

Open in Google Colab or Jupyter and run all cells.

---

## 💡 Future Improvements

* Use CNN instead of fully connected layers
* Apply structured pruning (neurons instead of weights)
* Deploy model with reduced size

---

## 🏁 Conclusion

This project demonstrates how neural networks can **learn efficiency during training**, reducing unnecessary parameters while maintaining performance.

---

## 👨‍💻 Author

Varun saketh

