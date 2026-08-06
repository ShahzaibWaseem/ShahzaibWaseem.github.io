---
title: Ship Detector
date: 2019-05-12
categories:
  - Project
tags: 
  - Python
  - TensorFlow
  - Keras
  - OpenCV
toc: true
toc_label: "Table of Contents"
toc_icon: "th-list"
toc_sticky: true
---

**Languages Used**: Python3, TensorFlow, Keras, OpenCV

**Source Code**: [GitHub Link](https://github.com/ShahzaibWaseem/Project-AI)

## Goal
The primary objective of this project is to accurately detect ships in aerial imagery using Convolutional Neural Networks (CNNs). A major focus of this research is to analyze how pre-processing raw dataset images using Digital Image Processing (DIP) techniques impacts the training loss, accuracy, and overall performance of deep learning models like UNET, VGG, and custom-built CNNs.

## Overview
- **Custom DIP Pipeline**: A robust image pre-processing pipeline that applies Binarization, Histogram Equalization, Unsharp Masking, and Median Smoothing to aerial images before feeding them into the models.
- **Multi-Model Architecture**: Evaluates and compares the performance of industry-standard models (UNET, VGG) alongside a custom-built CNN.
- **Comparative DIP Analysis**: A direct performance comparison showing how models perform on raw data versus DIP-enhanced data.
- **Loss Optimization**: Detailed tracking of UNET's loss function to visualize convergence improvements when trained on processed datasets.

## Methodology
### 1. Data Pre-processing
Aerial images often suffer from noise, varying contrast, and weather conditions. To tackle this, the raw dataset is passed through several image processing kernels:
- *Histogram Equalization*: Enhances contrast, making the ships stand out against the water.
- *Binarization*: Simplifies the image data to highlight distinct shapes.
- *Smoothing & Unsharping*: Reduces noise (using median smoothing) while keeping the edges of the ships sharp for the CNN to detect.

### 2. Model Training & Evaluation
The processed images (along with the raw control group) are used to train three distinct architectures:
- *Custom CNN Model*: A baseline lightweight convolutional network.
- *UNET*: Primarily used to evaluate precise localization and feature mapping.
- *VGG*: Used for robust feature extraction.

## Results and Performance
The core finding of this project is the measurable difference in the Loss Function when applying Digital Image Processing (DIP).
- *Without DIP*: The custom model struggles with background noise, leading to higher loss and slower convergence.
![Loss and Accuracy (without DIP)](/assets/images/ProjectAssets/ShipDetector/customModelwithoutDIP.png)
- *With DIP*: The application of our image processing pipeline yields a significantly smoother loss curve, faster convergence, and better overall ship detection accuracy.
![Loss and Accuracy (with DIP)](/assets/images/ProjectAssets/ShipDetector/customModelwithDIP.png)

## References
You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/Project-AI) to add more features to the project.