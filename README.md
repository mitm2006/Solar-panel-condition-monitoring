# Solar Panel Condition Monitoring using CNN

## Overview

This project presents a Convolutional Neural Network (CNN) designed to automatically classify the condition of solar panels based on image data. The goal is to enable efficient and scalable monitoring of solar panel health, reducing the need for manual inspection and improving maintenance workflows.

The model is trained on a labeled dataset of solar panel images and is further evaluated on external images sourced from the internet to assess its generalization capability.

---

## Model Architecture

The CNN architecture is built using PyTorch and consists of multiple convolutional blocks followed by fully connected layers.

### Key Components:

* **Convolutional Layers**: Extract spatial features using progressively increasing channel depth.
* **Batch Normalization**: Stabilizes and accelerates training.
* **Leaky ReLU Activation**: Prevents dead neurons and improves gradient flow.
* **Max Pooling**: Reduces spatial dimensions while preserving important features.
* **Dropout**: Helps prevent overfitting by randomly disabling neurons during training.
* **Fully Connected Layers**: Perform final classification.

### Architecture Flow:

1. Input image
2. Four convolutional blocks with increasing feature maps
3. Flattening layer
4. Dense layers for classification output

---

## Training Details

* **Loss Function**: CrossEntropyLoss (with class weighting to handle imbalance)
* **Optimizer**: Adam
* **Learning Rate Scheduler**: ReduceLROnPlateau (reduces LR when validation loss stagnates)
* **Regularization**:

  * Dropout layers
  * Weight decay

### Training Strategy:

* Model trained over multiple epochs
* Validation performed after each epoch
* Early stopping implemented to prevent overfitting
* Best model saved based on validation accuracy

---

## Performance Metrics

The following metrics were tracked during training:

* **Training Loss**
* **Validation Loss**
* **Validation Accuracy**

The model showed steady convergence with decreasing loss and increasing accuracy over epochs.

---

## Generalization Testing (External Data)

To evaluate real-world applicability, the trained model was tested on images downloaded from the internet that were not part of the original dataset.

### Observations:

* The model performed well on unseen data
* Maintained strong classification accuracy
* Demonstrated robustness to variations in lighting, angle, and image quality

This indicates that the model has learned meaningful and transferable features rather than memorizing the training dataset.

---

## Key Features of the Project

* Custom CNN architecture tailored for solar panel inspection
* Handles class imbalance using weighted loss
* Includes learning rate scheduling and early stopping
* Validated on both dataset and external real-world images
* Designed for scalability in automated monitoring systems

---

## Limitations

* Performance may vary on extremely low-quality or highly noisy images
* Model depends on diversity of training data for optimal generalization
* Real-time deployment would require further optimization

---

## Future Improvements

* Incorporate data augmentation for better robustness
* Experiment with deeper architectures (e.g., ResNet, EfficientNet)
* Deploy as a real-time monitoring system
* Integrate thermal image analysis for enhanced fault detection

---

## Conclusion

This project demonstrates the effectiveness of CNNs in solar panel condition monitoring. The model not only performs well on the training dataset but also generalizes effectively to unseen real-world images, making it a promising solution for automated inspection systems in renewable energy applications.

---
