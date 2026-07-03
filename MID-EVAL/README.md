# Deep Neural Networks, Computer Vision & Model Compression

A comprehensive study and implementation project covering the mathematical foundations of Computer Vision, Deep Learning, Convolutional Neural Networks (CNNs), and Neural Network Compression techniques inspired by the paper **"Deep Compression: Compressing Deep Neural Networks with Pruning, Trained Quantization and Huffman Coding" (ICLR 2016)**.

---

## Overview

This repository contains lecture notes, implementations, experiments, and project work completed as part of the **Deep Neural Networks and Computer Vision** study program.

The project progresses from fundamental image processing concepts to advanced neural network architectures and model compression techniques used for deploying deep learning models on resource-constrained devices.

---

## Objectives

* Understand image representation and processing fundamentals.
* Explore frequency-domain analysis using FFT.
* Implement image filtering and enhancement techniques.
* Study feature extraction and shape detection algorithms.
* Build a custom computer vision data pipeline.
* Learn the mathematical foundations of machine learning.
* Implement and analyze CNN architectures.
* Investigate neural network compression techniques:

  * Network Pruning
  * Weight Quantization
  * Weight Sharing
  * Huffman Encoding

---

## Topics Covered

### 1. Image Representation & Frequency Analysis

* RGB and Grayscale Images
* Matrix-based Image Representation
* Fourier Transform (DFT & FFT)
* Frequency Domain Interpretation
* Low-Pass and High-Pass Filtering

### 2. Image Filters & Color Spaces

* Histograms
* RGB, HSV, and HSL Color Spaces
* Brightness and Contrast Adjustment
* Saturation and Hue Manipulation
* Gamma Correction
* White Balancing

### 3. Convolution & Edge Detection

* Convolution Operations
* Kernel Design
* Average and Gaussian Blur
* Sobel Operator
* Canny Edge Detection
* Laplacian Sharpening
* Unsharp Masking

### 4. Feature Detection & Hough Transform

* Corner Detection
* Line Detection
* Circle Detection
* Hough Transform
* Generalized Hough Transform

### 5. Custom Fruits-360 Data Pipeline

* Dataset Loading
* Feature Engineering
* Color Statistics
* Shape Analysis
* Texture Extraction using LBP
* Edge-based Feature Extraction

### 6. Machine Learning Mathematics

* Linear Regression
* Logistic Regression
* K-Means Clustering
* Multilayer Perceptrons
* Optimization Techniques

### 7. Neural Networks & Generalization

* Bias-Variance Trade-off
* Overfitting and Underfitting
* Regularization Techniques
* Backpropagation
* Universal Approximation Theorem

### 8. Convolutional Neural Networks

* Convolution Layers
* Pooling Operations
* Activation Functions
* CNN Architectures
* Feature Learning

### 9. Model Compression

Inspired by the Deep Compression framework:

#### Pruning

Removing redundant network connections while preserving model accuracy.

#### Quantization

Reducing numerical precision and memory footprint of weights.

#### Weight Sharing

Clustering weights and replacing them with shared centroids.

#### Huffman Coding

Applying entropy coding to further compress model storage requirements.

---

## Key Learning Outcomes

* Developed a strong mathematical understanding of computer vision.
* Implemented classical image processing algorithms.
* Built custom feature extraction pipelines.
* Studied CNN architectures from first principles.
* Explored practical neural network compression techniques.
* Investigated deployment-oriented optimizations for deep learning models.

---

## Reference Paper

[1] Song Han, Huizi Mao, and William J. Dally,
**"Deep Compression: Compressing Deep Neural Networks with Pruning, Trained Quantization and Huffman Coding"**,
International Conference on Learning Representations (ICLR), 2016.

PDF:
[research_paper.pdf](https://github.com/SHUB-1806/EEA_DNN_Compression_CV/blob/main/MID-EVAL/1510.00149v5.pdf)

Original Paper:
[https://arxiv.org/abs/1510.00149](https://arxiv.org/abs/1510.00149)


Key Results:

* AlexNet compressed from 240 MB to 6.9 MB (35× reduction)
* VGG-16 compressed from 552 MB to 11.3 MB (49× reduction)
* No significant loss in classification accuracy

---

## Participants

Group 6

* Aditya Durgapal (Leader)
* Dev Kushawah
* Priyanshu Mehta
* Adish Kapate
* M. Mithilesh
* Shubham Joshi
* Harsh Vardhan
* Chaitanya Gaikwad
* Nakshatra Kumar
