---
title: "RipeTrack: Assessing Fruit Ripeness using Smartphones"
date: "2024-09-20"
tags:
  - Python
  - Research
toc: true
toc_label: "Table of Contents"
toc_icon: "th-list"
toc_sticky: true
---

## Abstract
Several studies showed that a significant fraction of fresh fruits are discarded at the retail and consumer levels, wasting precious resources, polluting the environment, and increasing food prices. An important factor contributing to this problem is the lack of scalable solutions for determining fruit ripeness and remaining lifetime. We propose a cost-effective solution that utilizes the sensing capabilities of phones and machine learning models to analyze the optical properties of fruits in different ripening stages. The proposed solution is non-invasive, works for different fruits, and produces intuitive outputs, e.g., Unripe/Ripe/Expired and the percentage of remaining lifetime, enabling retailers and consumers to minimize food waste. We implement a proof-of-concept mobile application, RipeTrack, and demonstrate the accuracy and robustness of the proposed approach using an extensive empirical study with multiple fruits, including avocados, pears, bananas, nectarines, and mangoes. Our results show, for example, that RipeTrack can identify the ripeness level of avocados and pears with an accuracy of 95% and 98%, respectively, and it can predict their remaining lifetimes with an accuracy of 93% and 95%. Our results also show that RipeTrack can easily be extended to new fruits using transfer learning, and it functions in realistic environments, e.g., homes and grocery stores, that have diverse illuminations.

## Major Components
![RipeTrack Overview](/assets/images/ProjectAssets/RipeTrack/ripetrackOverview.png)

Above is the overview of RipeTrack. There are two main components to RipeTrack:
- Hyperspectral Reconstruction
- Spatio-Spectral Classification

![RipeTrack Hyperspectral Reconstruction](/assets/images/ProjectAssets/RipeTrack/reconstructionArchitecture.png)
**Hyperspectral Reconstruction** model, which is designed using vision Transformers, is responsible for utilizing the input RGB and NIR image set to spectrally upscale it to output a whole hyperspectral cube. Compared to prior works, however, our model considers the NIR band as an extra input, adds new loss functions to enhance accuracy, improves robustness to diverse phones and illuminations, and significantly reduces memory requirements and training and inference times; all are critical factors for smartphones.

![RipeTrack Spatio-Spectral Classification](/assets/images/ProjectAssets/RipeTrack/classifierArchitecture.png)
**Spatio-Spectral Classification** model classifies the hypercubes it recieves into easy to understand labels for Ripeness level (*Unripe*, *Ripe*, *Expired*) and Remaining lifetime (*10%*, *20%*, ..., *100%*). The Spatio-Spectral classification model considers both the spatial (X and Y axis in Cartesian space) and spectral (Z axis in Cartesian space) characteristics of the input hyperspectral bands. This is crucial for identifying the subtle differences among a fruit's spectral signatures at different points in its lifetime.

## Robustness
The deep learning models built are very robust and are built to be used in the real world scenario. Models in the realm of Hyperspectral imaging are very sensitive to information (or lack of) and can be overfit to its training set. To prevent this from happening, we included examples of various lighting conditions, to prove the robustness, in our dataset which are: Halogen, LED, Fluorescent, and mixed lighting. This is because, the inadequate lighting conditions do not contain information in the NIR range (650-1000 nm) and damages these wavelength bands. Similarly, in the dataset we included examples of multiple fruits, used multiple phones to capture the images, captured the images from various distances. We also found that images captured form **20-40 cm** performed the best, and anything outside this does not leave enough information for it to make decisive decisions.

For more details about any of the modules, read our paper.

There are some technical aspects of RipeTrack which are not present in the paper, like how to get the spectral signatures of points in the hypercubes on Android.

### Spectral Signatures
Spectral signatures are the (normalized) pixel values of each wavelength band at a particular pixel in the hypercube. Signatures are what make hyperspectral imaging very powerful as each material has a unique signature (given the hyperspectral range is large), which makes the problem of classification a material classification or classification based on the chemical changes rather than in the traditional classification.

### Extracting spectral signatures (Android)
PyTorch on Android is a very stripped down version of the desktop version, as Android does not allow to deal with 3D objects natively. Since this is the case the hyperspectral cubes are represented in a 1D array in Android even in the PyTorch library. This raises a problem when we need to get spectral signatures on Android to perform spectral analysis. The following example is to explain how we solve this problem. In the animation (*gif*) below, there are 4 bands: Red, Green, Blue and Gray. The width and height of the image are 4 pixels each making the shape $4 \times 4 \times 4$. Each pixel shows its XY coordinate value in the matrix and the color represents the band number. There is a running "control" of the code on the left hand side and the top of the image shows the current status of the signature array, and the bottom of the animation shows the 1D representation of the hypercube data.

![Signature Explanation](/assets/images/ProjectAssets/RipeTrack/SignatureExplaination.gif)

The first few lines are very straight forward, as for the second last line in the *for loop* in the code it adds the number of values it is away from the next band. As the control needs to move on to the next band as soon as one band pixel value is extracted.

```py
idx += remainingX + bitmapsWidth * remainingY + 1
```

Similarly the following operation takes the control from the start of the band to the correct row and column value (which is provided to the function). This operation also gets repeated in the last line of the *for loop*.

```python
bitmapsWidth * row + col
```

## Android Application

The interface of the android application is shown in the figure below. This shows the the application has a feature to predict single and multiple fruits as well as, signature analysis can be performed on the hypercubes.

![RipeTrack Android](/assets/images/ProjectAssets/RipeTrack/ripetrackAndroid.png)

## Paper Supplementary Material

<!-- IEEE Transactions on Mobile Computing, 2024. -->

| [[Code]](https://github.com/ShahzaibWaseem/RipeTrack) | [[Android]](https://github.com/ShahzaibWaseem/RipeTrack-Android) |