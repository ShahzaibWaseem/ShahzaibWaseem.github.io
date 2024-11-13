---
title: "MobiSpectral: Hyperspectral Imaging on Mobile Devices"
date: "2023-10-06"
tags: "Python"
---

# ACM MobiCom 2023, Madrid, Spain

## Abstract
Hyperspectral imaging systems capture information in multiple wavelength bands across the electromagnetic spectrum. These bands provide substantial details based on the optical properties of the materials present in the captured scene. The high cost of hyperspectral cameras and their strict illumination requirements make the technology out of reach for end-user and small-scale commercial applications. We propose MobiSpectral, which turns a low-cost phone into a simple hyperspectral imaging system, without any changes in the hardware. We design deep learning models that take regular RGB images and near-infrared (NIR) signals (which are used for face identification on recent phones) and reconstruct multiple hyperspectral bands in the visible and NIR ranges of the spectrum. Our experimental results show that MobiSpectral produces accurate bands that are comparable to ones captured by actual hyperspectral cameras. The availability of hyperspectral bands that reveal hidden information enables the development of novel mobile applications that are not currently possible. To demonstrate the potential of MobiSpectral, we use it to identify organic solid foods, which is a challenging food fraud problem that is currently partially addressed by laborious, unscalable, and expensive processes. We collect large datasets in real environments under diverse illumination conditions to evaluate MobiSpectral. Our results show that MobiSpectral can identify organic foods, e.g., apples, tomatoes, kiwis, strawberries, and blueberries, with an accuracy of up to 94% from images taken by phones.

## Overview
![MobiSpectral Overview](/assets/images/ProjectAssets/MobiSpectral/mobispectralOverview.png)

# Android Application Demo
<video width="420" height="300" controls>
	<source src="/assets/images/ProjectAssets/MobiSpectral/MobiSpectralApp(online).mp4" type="video/mp4">
</video>

ACM Mobile Computing and Networking, 2023.

| [[Paper]](https://www.cs.sfu.ca/~mhefeeda/Papers/mobiCom23_MobiSpectral.pdf) | [[Code]](https://github.com/mobispectral/mobicom23_mobispectral) | [[Android]](https://github.com/ShahzaibWaseem/MobiSpectral-Android) | [[Dataset]](https://www.frdr-dfdr.ca/repo/dataset/cf34da8b-f794-47c5-b114-88ecdd112a14) | [[BibTex]](/assets/images/ProjectAssets/MobiSpectral/mobispectral.bib) |

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