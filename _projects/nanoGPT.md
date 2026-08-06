---
title: nanoGPT (Custom Transformer Implementation)
date: 2025-05-20
categories:
  - Project
tags: 
  - Python
  - PyTorch
  - CUDA
toc: true
toc_label: "Table of Contents"
toc_icon: "th-list"
toc_sticky: true
---

**Languages & Tools Used**: Python, PyTorch, CUDA

**Focus Area**: Generative AI, Large Language Models (LLMs), Natural Language Processing

**Source Code**: [GitHub Link](https://github.com/ShahzaibWaseem/nanoGPT)

## Goal
The objective of this project is to build and train a lightweight, efficient implementation of the GPT (Generative Pre-trained Transformer) architecture from scratch. Based on the fundamental concepts of attention mechanisms, this repository serves as a deep dive into the inner workings of modern Large Language Models, optimizing the training loop for custom text datasets.

## Key Features
- *From-Scratch Transformer Architecture*: Implements the core building blocks of GPT, including Multi-Head Self-Attention, Feed-Forward layers, and Positional Encodings.
- *Efficient Training Pipeline*: Utilizes PyTorch optimizations for faster convergence and memory management, capable of running on single consumer-grade GPUs.
- *Custom Tokenization*: Implements character-level or sub-word tokenization to efficiently convert raw text into sequence data for the model.
- *Text Generation*: Features a sampling pipeline to generate novel, context-aware text sequences based on a trained checkpoint.

## Architecture & Visual Flow
To understand the core engine of nanoGPT, here is the standard Transformer block architecture that powers the model:
![Transformer Architecture](/assets/images/ProjectAssets/nanoGPT/attentionArchitecture.png)

## Network Topology Details
- *Multi-Head Self-Attention*: Allows the model to look at different parts of the input sequence simultaneously, capturing both short and long-range dependencies.
- *Layer Normalization & Residual Connections*: Stabilizes the deep network during training by normalizing the inputs to each layer and allowing gradients to flow directly through skip connections.
- *Causal Masking*: Ensures that the model only attends to past tokens when predicting the next token, preserving the autoregressive nature of text generation.

## References
nanoGPT is based on the paper [Attention is all you need](https://arxiv.org/abs/1706.03762).

You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/nanoGPT) to add more features to the project.