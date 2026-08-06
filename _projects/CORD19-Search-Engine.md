---
title: CORD-19 Search Engine
date: 2019-12-21
categories:
  - Project
tags: 
  - Python
  - NLTK
  - SpaCy
  - TensorFlow
  - PyTorch
  - Scikit-Learn
toc: true
toc_label: "Table of Contents"
toc_icon: "th-list"
toc_sticky: true
---

**Languages & Tools Used**: Python, NLTK, SpaCy, TensorFlow, PyTorch, Scikit-Learn

**Focus Area**: Text Classification / Sentiment Analysis (Update with your specific focus)

**Source Code**: [GitHub Link](https://github.com/ShahzaibWaseem/Project-NLP)

## Goal
The primary objective of this project is to process and analyze raw text data to extract meaningful patterns, ultimately building a machine learning model capable of (insert specific task, e.g., classifying text, predicting sentiment, generating text). This project explores the transition from raw, unstructured text to numerical representations (embeddings/n-grams) and evaluates how different models perform on the processed data.

## Key Features
- **Custom Text Pipeline**: A comprehensive preprocessing pipeline handling tokenization, stop-word removal, stemming/lemmatization, and vectorization.
- **Feature Engineering**: Implementation of bag-of-words, N-grams, and TF-IDF to represent text data mathematically.
- **Model Comparison**: Evaluates traditional machine learning models (like Logistic Regression/Naive Bayes) against deep learning approaches (like LSTMs or Transformers).
- **Performance Metrics**: Detailed tracking of accuracy, precision, recall, and F1-score to handle potential class imbalances.

## Methodology
### 1. Text Pre-processing
Raw text data is inherently messy and unstructured. Before feeding it to any model, the dataset goes through several crucial cleaning stages:
- **Tokenization & Normalization**: Converting sentences into individual words/tokens and converting all text to lowercase to ensure uniformity.
- **Noise Removal**: Stripping out HTML tags, special characters, and punctuation.
- **Stop-word Removal**: Filtering out common but uninformative words (e.g., "the", "and", "is") to reduce dimensionality.
- **Lemmatization**: Reducing words to their base dictionary form (e.g., "running" becomes "run").

### 2. Text Vectorization
To make the text understandable for the models, the tokens are mapped into numerical space:
- **TF-IDF (Term Frequency-Inverse Document Frequency)**: Used to weigh the importance of a word within a specific document relative to the whole corpus.
- **Word Embeddings (Optional)**: (If applicable) Utilizing pre-trained vectors like Word2Vec, GloVe, or custom dense layers to capture semantic relationships between words.

### 3. Model Training & Evaluation
The vectorized data is split into training and testing sets, then passed through our chosen architectures:
- **Baseline Model**: (e.g., Naive Bayes or Logistic Regression) Used to establish a performance floor.
- **Deep Learning Model**: (e.g., RNN/LSTM or a Transformer) Used to capture sequential context and deeper contextual meanings in the text.

## Visualizations & Dimensionality Reduction
Rather than relying purely on predictive performance metrics, this project focuses on visually interpreting the high-dimensional text data. The following plots were generated to analyze the underlying structure of the dataset:
- **Clustering Plot**: Visualizes the natural groupings of the documents/text. By applying clustering algorithms (such as K-Means), this plot demonstrates how the text separates into distinct thematic or semantic clusters based on their vector representations.
![Plot Clustering](/assets/images/ProjectAssets/CORD19/Plot(cluster).png)
- **t-SNE (t-Distributed Stochastic Neighbor Embedding) Plot**: A non-linear dimensionality reduction visualization. Because text embeddings exist in hundreds of dimensions, t-SNE compresses this data into a 2D scatter plot while preserving local similarities. This allows us to visually verify if similar texts are being embedded close to one another in the vector space.
![Plot t-SNE](/assets/images/ProjectAssets/CORD19/Plot(t-SNE).png)

## References
You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/Project-NLP) to add more features to the project.