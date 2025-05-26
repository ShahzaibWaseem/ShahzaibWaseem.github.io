---
title: "MobiSpectral: Hyperspectral Imaging on Mobile Devices"
date: "2023-10-06"
tags:
  - Python
  - Research
  - Hyperspectral Imaging
  - Computer Vision
  - Machine Learning
  - Android
toc: true
toc_label: "Table of Contents"
toc_icon: "th-list"
toc_sticky: true
---

# ACM MobiCom 2023, Madrid, Spain

## Abstract
Hyperspectral imaging systems capture information in multiple wavelength bands across the electromagnetic spectrum. These bands provide substantial details based on the optical properties of the materials present in the captured scene. The high cost of hyperspectral cameras and their strict illumination requirements make the technology out of reach for end-user and small-scale commercial applications. We propose MobiSpectral, which turns a low-cost phone into a simple hyperspectral imaging system, without any changes in the hardware. We design deep learning models that take regular RGB images and near-infrared (NIR) signals (which are used for face identification on recent phones) and reconstruct multiple hyperspectral bands in the visible and NIR ranges of the spectrum. Our experimental results show that MobiSpectral produces accurate bands that are comparable to ones captured by actual hyperspectral cameras. The availability of hyperspectral bands that reveal hidden information enables the development of novel mobile applications that are not currently possible. To demonstrate the potential of MobiSpectral, we use it to identify organic solid foods, which is a challenging food fraud problem that is currently partially addressed by laborious, unscalable, and expensive processes. We collect large datasets in real environments under diverse illumination conditions to evaluate MobiSpectral. Our results show that MobiSpectral can identify organic foods, e.g., apples, tomatoes, kiwis, strawberries, and blueberries, with an accuracy of up to 94% from images taken by phones.

## Major Modules
![MobiSpectral Overview](/assets/images/ProjectAssets/MobiSpectral/mobispectralOverview.png)

Above is the overview of MobiSpectral. There are two main modules to MobiSpectral:
- Hyperspectral Reconstruction
- Spectral Classification

**Hyperspectral Reconstruction** model, which is designed using vision transformers, is responsible for utilizing the input RGB and NIR image set to spectrally upscale it to output a whole hyperspectral cube. Prior works use hyperspectral reconstruction to get upscaled hyperspectral bands, but this information is not sufficient in a lot of applications. This is because if no information is present regarding the internal chemical changes, the model will start hallucinating details. Compared to prior works, our model considers the NIR band as an extra input, adds new loss functions to enhance accuracy, improves robustness to diverse phones and illuminations, all of which are really important for in the wild usage.

**Spectral Classification** model classifies the hypercubes it receives into one of two labels: *Organic* and *Non-Organic*. The goal for MobiSpectral is to generate hypercubes in the full functional range considered (400-1000 nm). To show the efficacy of the system, we developed a downstream applications that use the power of spectral signatures to output one of the two labels mentioned above.

## Robustness
The deep learning models built are very robust and are built to be used in the real-world scenario. Models in the realm of Hyperspectral imaging are very sensitive to information (or lack of it) and can overfit to its training set. To prevent this from happening, we included examples of various lighting conditions, to prove the robustness, of our dataset which are: Halogen, LED, Fluorescent, and mixed lighting. This is because the inadequate lighting conditions do not contain information in the NIR range (650-1000 nm) and damage these wavelength bands. Similarly, in the dataset, we included examples of multiple fruits, used multiple phones to capture the images, and captured the images from various distances. We also found that images captured from **20-40 cm** performed the best, and anything outside this does not leave enough information for it to make decisive decisions.

For more details about any of the modules, read our [paper](/assets/images/ProjectAssets/MobiSpectral/mobiCom23_MobiSpectral.pdf).

There are some technical aspects of MobiSpectral that are not present in the paper, like how to get the spectral signatures of points in the hypercubes on Android.

### Spectral Signatures
Spectral signatures are the (normalized) pixel values of each wavelength band at a particular pixel in the hypercube. Signatures are what make hyperspectral imaging very powerful as each material has a unique signature (given the hyperspectral range is large), which makes the problem of classification a material classification or classification based on the chemical changes rather than in the traditional classification.

### Get signatures (Android)
PyTorch on Android is a very stripped-down version of the desktop version, as Android does not allow to deal with 3D objects natively. Since this is the case the hyperspectral cubes are represented in a 1D array in Android even in the PyTorch library. This raises a problem when we need to get spectral signatures on Android to perform spectral analysis. The following example is to explain how we solve this problem. In the animation (*gif*) below, there are 4 bands: Red, Green, Blue, and Gray. The width and height of the image are 4 pixels each making the shape 4 * 4 * 4. Each pixel shows its XY coordinate value in the matrix and the color represents the band number. There is a running "control" of the code on the left-hand side and the top of the image shows the current status of the signature array, and the bottom of the animation shows the 1D representation of the hypercube data in native Android data structures.

![Signature Explanation](/assets/images/ProjectAssets/MobiSpectral/SignatureExplaination.gif)

The logic explained above is from the Android code, which can be found in this [file](https://github.com/ShahzaibWaseem/MobiSpectral-Android/blob/master/app/src/main/java/com/shahzaib/mobispectral/fragments/ReconstructionFragment.kt#L443). The first few lines are very straightforward, as for the second last line in the *for loop* in the code it adds the number of values it is away from the next band as the control needs to move on to the next band as soon as one band pixel value is extracted.

```python
idx += remainingX + bitmapsWidth * remainingY + 1
```

Similarly the following operation takes the control from the start of the band to the correct row and column value (which is provided to the function). This operation also gets repeated in the last line of the *for loop*.

```python
bitmapsWidth * row + col
```

## Android Application
The interface of the Android application is shown in the figure below. This application provides the ability to upscale images to full hypercubes and perform spectral analysis on each pixel of the hypercubes.

![MobiSpectral Android](/assets/images/ProjectAssets/MobiSpectral/mobispectralAndroid.png)

### Demo
<video width="405" height="720" controls>
	<source src="/assets/images/ProjectAssets/MobiSpectral/mobispectralApp.mp4" type="video/mp4">
</video>

## Paper Supplementary Material

ACM Mobile Computing and Networking, 2023.

| [[Paper]](/assets/images/ProjectAssets/MobiSpectral/mobiCom23_MobiSpectral.pdf) | [[Code]](https://github.com/mobispectral/mobicom23_mobispectral) | [[Android]](https://github.com/ShahzaibWaseem/MobiSpectral-Android) | [[Dataset]](https://www.frdr-dfdr.ca/repo/dataset/cf34da8b-f794-47c5-b114-88ecdd112a14) | [[BibTex]](/assets/images/ProjectAssets/MobiSpectral/mobispectral.bib) |

## Citation
```
@inproceedings{10.1145/3570361.3613296,
	author = {Sharma, Neha and Waseem, Muhammad Shahzaib and Mirzaei, Shahrzad and Hefeeda, Mohamed},
	title = {MobiSpectral: Hyperspectral Imaging on Mobile Devices},
	year = {2023},
	isbn = {9781450399906},
	publisher = {Association for Computing Machinery},
	address = {New York, NY, USA},
	url = {https://doi.org/10.1145/3570361.3613296},
	doi = {10.1145/3570361.3613296},
	booktitle = {Proceedings of the 29th Annual International Conference on Mobile Computing and Networking},
	articleno = {82},
	numpages = {15},
	keywords = {mobile applications, food fraud, hyperspectral imaging},
	location = {Madrid, Spain},
	series = {ACM MobiCom '23}
}
```