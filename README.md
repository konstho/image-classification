# Deep Learning Based Image Classification – CIFAR-100

This repository contains the report and experimental results for a project that compares **a CNN trained from scratch** with **transfer learning using ResNet-18** on the CIFAR-100 dataset.

The goal is to understand how pretrained representations improve performance on complex multi-class image recognition problems.

---

## Dataset

CIFAR-100 consists of:

- 60,000 RGB images  
- 100 classes  
- Image resolution: 32×32  
- 50,000 training / 10,000 testing samples  

---

## Methods

### Baseline CNN
A convolutional neural network composed of convolution → batch normalization → ReLU → pooling blocks, followed by fully connected layers.

### ResNet-18 (Transfer Learning)
A pretrained network (ImageNet) where the final classification layer is replaced with a 100-class output and fine-tuned.

---

## Training Configuration

- Loss: Cross-Entropy  
- Optimizer: SGD  
- Momentum: 0.9  
- Weight decay: 5e-4  
- Learning rate: 0.1 with scheduling  
- Augmentation: RandomCrop + HorizontalFlip  
- Normalization using CIFAR-100 statistics  

---

## Results Summary

| Metric | Value |
|-------|------|
| Accuracy | ~58% |
| Macro F1 | ~0.58 |
| Macro AUC | ~0.98 |

The high AUC indicates strong class separability, even though predicting the single best class among 100 remains challenging.

---

## Visualizations

### Confusion Matrix
![Confusion Matrix](results/confusion_matrix.png)

### ROC Curve
![ROC](results/roc_curve.png)

### t-SNE Feature Embedding
![t-SNE](results/tsne.png)

---

## Key Findings

✔ The model learns highly discriminative internal representations.  
✔ Errors mainly occur between visually similar categories.  
✔ No strong systematic confusion patterns are present.  

---

## Limitations

- Very low image resolution (32×32)  
- Limited training resources  
- Only ResNet-18 explored in depth  
- No advanced augmentation (MixUp, CutMix, etc.)

---

## Report

Full details, methodology, and analysis are available here:

📄 **[Read the report](report/Deep-Learning Based Image Classification.pdf)**

---

## Authors
Temuuren  
Konsta
