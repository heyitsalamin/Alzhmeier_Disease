# DenseNet121–ViT: Hybrid Feature Fusion for Image Classification

A hybrid deep learning framework that combines **DenseNet121 and Vision Transformer (ViT)** to learn complementary local and global image representations. The model uses bidirectional cross-attention and feature-fusion mechanisms to improve image classification.

## Overview

Convolutional neural networks are effective at extracting local visual features, while Vision Transformers capture long-range relationships between image regions. This project combines both approaches in a unified architecture to leverage their complementary strengths.

## Key Features

- **DenseNet121:** Extracts hierarchical spatial features using ImageNet-pretrained weights.
- **Vision Transformer (ViT):** Processes image patches to learn global contextual representations.
- **Bidirectional Cross-Attention:** Enables interaction between CNN and transformer features.
- **Feature Fusion:** Combines complementary representations using projection and residual connections.
- **SE Gating:** Adaptively recalibrates fused feature channels.
- **Classification Head:** Uses fully connected layers and softmax for four-class prediction.

## Model Architecture

1. Input image resized to `224 × 224 × 3`.
2. Parallel feature extraction using DenseNet121 and ViT.
3. Bidirectional cross-attention between the two feature branches.
4. Feature concatenation, projection, and residual processing.
5. Squeeze-and-excitation-based feature recalibration.
6. Dropout and fully connected classification layers.

## Training Strategy

The model uses a two-stage training strategy:

- **Stage 1:** Freeze the pretrained DenseNet121 backbone and train the transformer and fusion components.
- **Stage 2:** Unfreeze DenseNet121 and jointly fine-tune the network using a reduced learning rate.

## Technologies

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- scikit-learn

## Evaluation

The model can be evaluated using accuracy, precision, recall, F1-score, ROC-AUC, and a confusion matrix. Actual experimental results should be reported after evaluation on the designated test set.

## Project Status

Research and development.

## Disclaimer

This project is intended for research and educational purposes. It is not a substitute for professional medical diagnosis if applied to medical images.
