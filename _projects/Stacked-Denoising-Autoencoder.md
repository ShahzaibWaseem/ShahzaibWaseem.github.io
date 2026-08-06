---
title: Stacked Denoising AutoEncoder
date: 2022-05-19
categories:
  - Project
tags: 
  - Python
  - PyTorch
  - NumPy
toc: true
toc_label: "Table of Contents"
toc_icon: "th-list"
toc_sticky: true
---

**Languages & Tools Used**: Python, PyTorch, NumPy

**Focus Area**: Deep Learning Architecture, Unsupervised Feature Extraction, Denoising

**Source Code**: [GitHub Link](https://github.com/ShahzaibWaseem/StackedAutoEncoder)

## Goal
The objective of this project is to build a custom, modular Stacked Denoising AutoEncoder (SDAE) from scratch using PyTorch. Instead of relying on off-the-shelf high-level wrappers, this project implements a deep, multi-layered autoencoder architecture where the inputs are concatenated and carried forward through three distinct denoising stages to robustly reconstruct corrupted data and extract meaningful latent representations. The purpose of this was to implement it in PyTorch because there was no implementation of it in PyTorch publically available.

## Key Features
- *Custom PyTorch Architecture*: A from-scratch implementation bypassing standard pre-packaged autoencoder modules to allow for granular control over forward and backward passes.
Multi-Stage Forward Concatenation: Implements a specialized architecture where the output of each autoencoder is concatenated with the previous layers' outputs before being fed into the next stage, preserving low-level features deeper in the network.
- *Dynamic Noise Injection*: Introduces controlled noise to the input data during training, forcing the network to learn robust, generalized features rather than simply memorizing the input (Identity mapping).
- *Modular Training Logic*: Supports flexible training regimens. The model can be trained layer-by-layer (greedy layer-wise pre-training) or end-to-end as a complete system.

## Architecture & Visual Flow
To understand how the data flows through this custom implementation, here is a look at the standard Stacked Denoising architecture principle:
![Stacked Denoising AutoEncoder Architecture](/assets/images/ProjectAssets/StackedDenoisingAE/model.svg)

## Methodology & Architecture
### 1. The Denoising Principle
Standard autoencoders are prone to learning the identity function (simply copying input to output) if the hidden capacity is too large. By artificially corrupting the input data (e.g., via Gaussian noise or masking) and tasking the model with reconstructing the original, uncorrupted data, the autoencoder is forced to learn the fundamental structure and latent representations of the dataset.

### 2. Network Topology
The architecture consists of three distinct AutoEncoder (AE) blocks:
- *AE Block 1*: Takes the noisy input and compresses it into the first latent representation.
- *AE Block 2*: Takes the concatenated output of the original input and Block 1, extracting higher-level features.
- *AE Block 3*: The final stage, which aggregates previous representations to produce the definitive clean reconstruction.

3. Training Loop & Loss Tracking
- *Loss Function*: Utilizes Mean Squared Error (MSE) or a custom reconstruction loss to measure the distance between the final output and the uncorrupted ground truth.
- *Optimization*: Backpropagation through the stacked layers, with logic built-in to isolate gradients if training is done modularly per block.

## References
You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/StackedAutoEncoder) to add more features to the project.