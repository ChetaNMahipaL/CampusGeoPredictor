# Geographical Region Classification

## Model Architecture
This project implements an ensemble of two deep learning models to classify geographical regions from satellite imagery:
1. **ConvNeXT Base**: Fine-tuned CNN architecture with Feature Pyramid Network (FPN) for multi-scale feature extraction
2. **DeiT Base (Vision Transformer)**: Fine-tuned transformer model with patch-based image processing

## Preprocessing & Augmentation
- Multiple augmentation strategies (random horizontal flip, color jitter, affine transformations)
- RandAugment for automated augmentation policy
- Mixup and CutMix for data augmentation during training

## Innovative Components
- Global Context Module for improved attention to spatial relationships
- Self-Attention mechanism to capture long-range dependencies
- Feature Pyramid Network for multi-scale feature representation
- Ensemble prediction to leverage strengths of both CNN and transformer architectures
- Cosine learning rate scheduling for optimal convergence

The model achieves strong accuracy on validation data and demonstrates the effectiveness of combining modern CNN and transformer approaches for geographical image classification.

Model Link - https://iiithydstudents-my.sharepoint.com/:f:/g/personal/chetan_mahipal_students_iiit_ac_in/Eh4f4cx3esJCvGFpNyYkctoBEAps0gEq5SYWHQUfx-y7dA?e=cmpf1R