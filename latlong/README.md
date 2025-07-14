# Geolocation Prediction from Satellite Imagery

## Model Architecture
- **Base Model**: Fine-tuned Swin Transformer (swin_base_patch4_window7_224)
- **Approach**: Regression model that predicts latitude and longitude coordinates from satellite images

## Preprocessing & Data Handling
- Coordinate normalization with outlier removal using IQR-based filtering
- Multiple data augmentations: RandAugment, ColorJitter, RandomErasing, GaussianBlur
- Extended dataset creation with multiple augmentation strategies

## Training Techniques
- Enhanced adaptive mixup with dynamic switching between standard mixup and cutmix
- Smooth L1 Loss for coordinate regression
- Exponential Moving Average (EMA) for model weights
- Cosine annealing learning rate scheduler

## Innovations
- Dataset extension through complementary augmentation techniques
- Anomaly handling for specific problematic data points
- Multi-stage normalization and denormalization for robust coordinate prediction
- Batch-wise augmentation strategy that balances between geometric and color transformations

Model Link - https://iiithydstudents-my.sharepoint.com/:f:/g/personal/chetan_mahipal_students_iiit_ac_in/Eh4f4cx3esJCvGFpNyYkctoBEAps0gEq5SYWHQUfx-y7dA?e=cmpf1R