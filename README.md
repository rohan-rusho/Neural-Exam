# Neural Network Lab Exam Study Guide

## 1. LeNet

**Developed by**: Yann LeCun (1998)  
**Purpose**: Handwritten digit recognition (e.g., MNIST)

**Architecture:**
- Input: 32x32 grayscale image
- Layers:
  1. Convolution (C1): 6 filters, 5x5, stride 1, tanh activation
  2. Subsampling/Pooling (S2): 2x2 average pooling
  3. Convolution (C3): 16 filters, 5x5
  4. Subsampling/Pooling (S4): 2x2 average pooling
  5. Fully Connected (C5 & F6): Dense layers
  6. Output: 10-way softmax

**Key Points:**
- Early example of Convolutional Neural Networks (CNNs)
- Uses tanh/sigmoid activations
- Local connectivity and parameter sharing

---

## 2. VGG

**Developed by**: Visual Geometry Group, Oxford (2014)  
**Purpose**: ImageNet classification

**Architecture:**
- Uses only 3x3 convolutions, 2x2 max pooling
- Depth: VGG-16, VGG-19 (number = total layers)
- Example (VGG-16):
  - [Conv3x3, ReLU] x2 → MaxPool
  - [Conv3x3, ReLU] x2 → MaxPool
  - [Conv3x3, ReLU] x3 → MaxPool
  - [Conv3x3, ReLU] x3 → MaxPool
  - [Conv3x3, ReLU] x3 → MaxPool
  - 2 Fully Connected (FC) layers (4096 each)
  - Output FC (1000 classes)

**Key Points:**
- Deep, simple, uniform architecture
- Only 3x3 convolutions
- More parameters, memory-intensive

---

## 3. ResNet (Residual Network)

**Developed by**: Kaiming He et al. (2015)  
**Purpose**: Image classification (ImageNet), very deep networks (up to 152 layers)

**Architecture:**
- Residual blocks with "skip connections" or "identity shortcuts"
- Block:  
  `output = F(x) + x`  
  Where F(x) is the output of a few convolutional layers, x is the input to the block

- Example (ResNet-50):
  - Multiple stacked residual blocks
  - Each block: Conv-BN-ReLU, skip connection

**Key Points:**
- Solves vanishing gradient problem
- Enables training of ultra-deep networks
- Identity/skip connections pass input to later layers

---

## 4. GoogLeNet (Inception)

**Developed by**: Szegedy et al. (2014, Google)  
**Purpose**: ImageNet classification

**Architecture:**
- Inception module: Multiple convolutions (1x1, 3x3, 5x5) + 3x3 max pooling in parallel, concatenate outputs
- Uses 1x1 conv for dimensionality reduction
- 22 layers deep

**Key Points:**
- Efficient: fewer parameters than VGG, despite being deeper
- Parallel convolutional paths (Inception modules)
- Auxiliary classifiers for better gradient flow

---

## Comparison Table

| Model      | Year | Depth | Key Feature           | Pros                  | Cons                |
|------------|------|-------|-----------------------|-----------------------|---------------------|
| LeNet      | 1998 | 5-7   | Simple CNN, pooling   | Easy to train, classic| Not for big images  |
| VGG        | 2014 | 16-19 | 3x3 Conv, deep        | Simple, effective     | Many parameters     |
| ResNet     | 2015 | 50+   | Residual blocks       | Very deep possible    | Complex to design   |
| GoogLeNet  | 2014 | 22    | Inception modules     | Efficient, deep       | Complex modules     |

---

## Tips for Lab Exam

- **Know the architecture diagrams!**
- **Be able to explain the purpose of each layer.**
- **Understand the advantages of each architecture.**
- **Be ready to write/interpret basic PyTorch or TensorFlow code for these models.**
