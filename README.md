# Geolocation and Orientation Prediction using Deep Learning

> End-to-end vision system for predicting geolocation (latitude, longitude), camera orientation, and region classification from images using transformer and CNN ensembles. Developed as part of a research-style project at IIIT Hyderabad.

## Project Overview

This project addresses the problem of **localizing and orienting a camera image** captured within a geographical area (IIIT-H campus). The task involves predicting:
- **Latitude & Longitude** – Regression task
- **Camera Angle** – Direction in degrees (0° = North)
  **Region Classification** – Classify into 1 of 15 known regions

We built and trained **state-of-the-art deep learning models** using both CNN and Vision Transformer backbones, combined through custom ensemble strategies and multi-stage training pipelines.


## Key Features

### Direction Prediction (Angle)
- **Models**: DeiT (Vision Transformer), EfficientNetV2 + FPN
- **Loss**: Cosine-angle loss using `(sin θ, cos θ)` encoding
- **Innovations**: Self-attention, Global Context Module, 4-model ensemble

### Geolocation Regression
- **Model**: Swin Transformer
- **Loss**: Smooth L1
- **Techniques**: Adaptive mixup, IQR-based outlier filtering, EMA for stability

### Region Classification
- **Models**: ConvNeXT + FPN, DeiT
- **Strategies**: MixUp, RandAugment, cosine LR decay
- **Focus**: Capturing long-range spatial dependencies and multi-scale features


## 🧪 Performance

| Task                | Method              | Notes                        |
|---------------------|---------------------|------------------------------|
| Latitude/Longitude  | Swin Transformer    | Regression with Smooth L1    |
| Orientation Angle   | DeiT + EffNetV2     | Cosine-angle loss, ensemble  |
| Region Classification | ConvNeXT + DeiT    | Accuracy-based voting        |

Final performance metrics are evaluated on a held-out test set via a Kaggle competition setup.



## Tech Stack

- `PyTorch`, `timm`, `opencv`, `pandas`, `scikit-learn`
- Vision Transformers (DeiT, Swin)
- CNNs (EfficientNetV2, ConvNeXT)
- Feature Pyramid Networks
- Custom Loss Functions & Augmentations


## Dataset & Setup

- Custom dataset of **real-world images** captured around IIIT Hyderabad
- Each image labeled with **timestamp, GPS coordinates, angle, and region**
- Dataset preprocessing includes resizing, normalization, and multi-path augmentation
