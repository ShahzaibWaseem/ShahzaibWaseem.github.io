---
title: Spatial Pyramid Pooling
date: 2020-11-22
categories:
  - Project
tags: 
  - Python
  - TensorFlow
  - PyTorch
toc: true
toc_label: "Table of Contents"
toc_icon: "th-list"
toc_sticky: true
---

**Languages & Tools Used**: Python, PyTorch, TensorFlow

**Focus Area**: Custom CNN Architectures, Computer Vision, Feature Extraction

**Source Code**: [GitHub Link](https://github.com/ShahzaibWaseem/SpatialPyramidPooling_tf2)

## Goal
The objective of this project is to implement a custom Spatial Pyramid Pooling (SPP) layer. Standard Convolutional Neural Networks (CNNs) require a fixed-size input image (e.g., $224 \times 224$) because of their fully connected layers. This custom layer breaks that constraint, allowing the network to process images of arbitrary dimensions and aspect ratios without requiring cropping or warping, which can distort the original image data.

## Key Features
- Arbitrary Input Sizes: Removes the rigid input constraints of traditional CNNs, making the model more flexible for real-world image datasets.
- Multi-Scale Feature Aggregation: Extracts and pools features at multiple spatial scales (local and global), improving the model's ability to recognize objects regardless of their size in the frame.
- Plug-and-Play Integration: Designed to be easily integrated into existing backbone architectures (like VGG or ResNet) right before the fully connected layers.

## Architecture & Visual Flow
Traditional CNNs break when image sizes change because the transition from convolutional feature maps to linear fully connected layers requires a fixed number of neurons. SPP solves this mathematically.
![Spatial Pyramid Pooling Architecture](/assets/images/ProjectAssets/SpatialPyramidPooling/SPPArchitecture.png)

### Network Topology Details
The SPP layer acts as a bridge between the convolutional layers and the fully connected layers:
- *Input Feature Maps*: The final convolutional layer outputs a feature map of variable dimensions (depending on the original image size).
- *Multi-Level Pooling*: The SPP layer divides this feature map into multiple fixed grids (for example, a $1 \times 1$ bin, a $2 \times 2$ bin, and a $4 \times 4$ bin).
- *Concatenation*: Max-pooling is applied to each grid, and the results are flattened and concatenated. This guarantees that regardless of the initial feature map's size, the output vector will always have the exact same length.

## Methodology
### 1. The Fixed-Size Problem
In standard computer vision pipelines, images are forcefully resized or cropped before being fed into a CNN.
- Cropping risks cutting off vital parts of the object.
- Warping distorts spatial geometry (e.g., making a circle look like an oval).

### 2. The SPP Solution
By dynamically calculating the pooling window size and stride based on the incoming feature map's dimensions, the SPP layer creates a fixed-length representation. If you configure the layer to output $16$, $4$, and $1$ bins across $256$ channels, the fully connected layer will always receive exactly $(16 + 4 + 1) \times 256 = 5376$ features.

## References
Spatial pyramid pooling layers for keras, based on the paper ![Spatial Pyramid Pooling in Deep Convolutional Networks for Visual Recognition](https://arxiv.org/abs/1406.4729).

I used this starter code, which is in tensorflow 1.0, ![Author GitHub](https://github.com/yhenon/keras-spp). This code is for tensorflow 2.0.

You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/SpatialPyramidPooling_tf2) to add more features to the project.