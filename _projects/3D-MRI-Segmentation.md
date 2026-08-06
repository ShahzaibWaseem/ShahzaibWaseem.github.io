---
title: 3D MRI Brain Tumor Segmentation
date: 2025-05-12
categories:
  - Project
tags: 
  - Python
  - PyTorch
  - PyQt5
toc: true
toc_label: "Table of Contents"
toc_icon: "th-list"
toc_sticky: true
---

**Languages & Tools Used**: Python, PyTorch, PyQt5

**Focus Area**: Medical Image Analysis, 3D Computer Vision, Volumetric Segmentation

**Source Code**: [GitHub Link](https://github.com/ShahzaibWaseem/3D-MRI-Segmentation)

## Goal
The primary objective of this project is to develop a robust deep learning pipeline capable of automatically segmenting anomalies (such as tumors) from 3D Magnetic Resonance Imaging (MRI) scans. Moving beyond standard 2D image processing, this project processes complex volumetric data to assist in medical diagnostics. To handle the massive scale of 3D medical data, the project leverages distributed storage solutions.

## Project Overview
An end-to-end medical imaging system designed to automate the segmentation of brain tumors from 3D MRI scans. Leveraging a robust U-Net deep learning architecture and a relational database, this application provides medical professionals with an intuitive interface for patient management, image processing, and structured diagnostic reporting.

## Technical Stack

| Component       | Technology / Method              |
|-----------------|----------------------------------|
| AI Architecture | U-Net                            |
| User Interface  | PyQt5                            |
| Database        | MySQL                            |
| Dataset         | BraTS (Brain Tumor Segmentation) |
| Data Format     | .h5 MRI Images                   |

## Key Features
### 1. Advanced Image Preprocessing Pipeline
To ensure maximum accuracy before feeding scans to the AI engine, raw MRI data undergoes a strict preprocessing pipeline:
- Noise reduction to clarify raw imaging.
- Bias field correction to fix magnetic field inhomogeneities.
- Intensity normalization to standardize contrast across different scans.
- Skull stripping to isolate brain tissue from the skull and background.

### 2. U-Net Segmentation Engine
The core of the detection system utilizes U-Net, a highly effective convolutional neural network designed specifically for biomedical image segmentation. By leveraging its encoder-decoder architecture, the model accurately captures context and precise spatial localization to generate reliable glioblastoma tumor masks.
![U-Net Architecture](/assets/images/ProjectAssets/3D-MRI-Segmentation/uNetArchitecture.png)

### 3. Interactive Clinical GUI
Built with PyQt5, the interactive graphical interface is tailored specifically for a clinical workflow, allowing users to:
- Register new patients and manage clinical records.
- Dynamically upload and visualize 3D .h5 MRI scans.
- Execute the AI segmentation process with a single click.
- Generate, store, and review structured diagnostic reports.

### 4. Relational Database Backend
The application features a fully integrated MySQL backend utilizing indexing for rapid data retrieval. The schema efficiently links four core entities to maintain a seamless clinical pipeline:
- Patient
- MRIImage
- SegmentationProcess
- DiagnosisReport

## Evaluation Metrics
The U-Net model's tumor detection accuracy is rigorously evaluated using industry-standard spatial overlap metrics to ensure clinical viability:
- **Dice Similarity Coefficient (DSC)**: Measures the spatial overlap between the AI's generated segmentation and ground-truth masks validated by medical experts.
- **Jaccard Index (IoU)**: Evaluates the exact area of intersection over union for the detected tumor boundaries.

## References
You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/3D-MRI-Segmentation) to add more features to the project.