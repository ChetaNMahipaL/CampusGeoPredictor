# Image Direction Prediction Model

## Model Architecture
This project implements an ensemble approach combining multiple deep learning models for predicting the main direction in images:
- **Vision Transformer (DeiT)**: Fine-tuned DeiT base model with patch size 16
- **EfficientNetV2**: Multiple variants with custom head architectures
- **Feature Pyramid Network (FPN)**: Integrated with EfficientNetV2 for multi-scale feature processing

## Preprocessing and Augmentation Techniques
- Advanced data augmentations: RandAugment, color jittering, affine transformations
- Multiple transformation pipelines creating an extended dataset (3x original size)
- Vector representation for angles using sine/cosine encoding to handle the circular nature of angles

## Innovative Approaches
- Self-attention mechanisms and Global Context Module for better feature extraction
- Ensemble of 4 complementary models to reduce prediction variance
- Cosine-based angle loss function optimized for circular targets
- FPN architecture to leverage multi-scale features from the backbone network

The same base models yielded significantly different results through optimization strategies, custom loss functions, and extensive augmentation pipelines.

Model Link - https://iiithydstudents-my.sharepoint.com/:f:/g/personal/chetan_mahipal_students_iiit_ac_in/Eh4f4cx3esJCvGFpNyYkctoBEAps0gEq5SYWHQUfx-y7dA?e=cmpf1R