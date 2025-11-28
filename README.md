# TB Detection using ResNet50 Transfer-Learning

## Project Overview
This project demonstrates the application of Transfer Learning using the ResNet50V2 deep convolutional neural network to build a Computer-Aided Diagnostic (CAD) system for classifying Chest X-rays (CXR) as Normal or Tuberculosis (TB) Positive.

The core innovation of this project lies in the integration of Explainable AI (XAI), providing visual evidence (heatmaps) to justify the model's clinical predictions, which is essential for building trust in medical AI applications.

##  Key Features and Technologies
*Transfer Learning:* Utilizes the ResNet50V2 model pre-trained on ImageNet weights, fine-tuned specifically for CXR feature extraction.

*Dual-Stage Training:* Employs a robust strategy of (1) Head Training (frozen base) followed by (2) Fine-Tuning (unfrozen top layers) with a very low learning rate.

*Explainable AI (XAI):* Implements Grad-CAM (Gradient-weighted Class Activation Mapping) to generate heatmaps that highlight the specific pathological regions of the lung influencing the model's prediction.

*Performance Metrics:* Focuses on clinically relevant metrics such as Area Under the Curve (AUC), Recall, and Precision.

*Framework:* TensorFlow 2.x and Keras.

## Data
kaggle : Chest X-ray Dataset_(Montgomery_and_Shenzhen)
Chest X-ray Datasets: Montgomery County & Shenzhen Hospital
Sources
Montgomery County CXR Set
https://data.lhncbc.nlm.nih.gov/public/Tuberculosis-Chest-X-ray-Datasets/Montgomery-County-CXR-Set/MontgomerySet/index.html

Shenzhen Hospital CXR Set
https://data.lhncbc.nlm.nih.gov/public/Tuberculosis-Chest-X-ray-Datasets/Shenzhen-Hospital-CXR-Set/index.html
