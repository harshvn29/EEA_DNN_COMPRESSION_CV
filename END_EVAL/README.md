# Deep Compression of Neural Networks using Pruning, Quantization and Huffman Coding

A modular implementation of the **Deep Compression Pipeline** for neural networks, inspired by the landmark paper:

> **Deep Compression: Compressing Deep Neural Networks with Pruning, Trained Quantization and Huffman Coding**
> Song Han, Huizi Mao, William J. Dally (ICLR 2016)

This project investigates how neural networks can be compressed for deployment on memory-constrained systems while preserving predictive performance.

---

# Project Overview

Modern neural networks often contain a large number of redundant parameters, resulting in excessive memory consumption and storage requirements.

This project implements a complete compression workflow consisting of:

1. Feature-Based Data Processing
2. MLP Training
3. Magnitude-Based Weight Pruning
4. Fine-Tuning
5. Weight Sharing Quantization
6. NPZ Model Serialization
7. Huffman Encoding
8. Storage and Memory Analysis

The architecture is intentionally modular, allowing future integration with CNN-based feature extractors while retaining the same compression framework.

---

# Compression Pipeline

```text
Images
   ↓
Feature Extraction
   ↓
Feature Vectors
   ↓
MLP Training
   ↓
Weight Pruning
   ↓
Fine-Tuning
   ↓
Weight Quantization
   ↓
NPZ Serialization
   ↓
Huffman Encoding
   ↓
Compressed Deployable Model
```

---

# Objectives

* Train an MLP on image-derived feature vectors.
* Investigate network redundancy through pruning.
* Reduce storage requirements using quantization.
* Serialize compressed models using NPZ format.
* Apply entropy coding through Huffman Encoding.
* Measure compression ratio, storage size, and RAM usage.
* Preserve or improve classification accuracy after compression.

---

# Model Architecture

Current implementation uses a fully connected Multi-Layer Perceptron (MLP):

```text
Input Features
      ↓
Linear Layer (784 → 512)
      ↓
ReLU
      ↓
Linear Layer (512 → 256)
      ↓
ReLU
      ↓
Linear Layer (256 → 10)
      ↓
Softmax Classification
```

For the current implementation:

* Dataset: MNIST
* Input Dimension: 784
* Hidden Layers: 512, 256
* Output Classes: 10

The compression framework remains independent of the classifier architecture and can later be applied to CNN-based systems.

---

# Deep Compression Stages

## 1. Baseline Training

The model is first trained using standard 32-bit floating-point weights.

### Baseline Performance

| Metric        | Value     |
| ------------- | --------- |
| Test Accuracy | 96.88%    |
| Storage Size  | 0.8955 MB |
| Precision     | Float32   |

---

## 2. Magnitude-Based Pruning

Small-magnitude weights are removed according to:

```math
|w| < \tau \rightarrow 0
```

where:

```text
τ = 0.5
```

### Pruning Results

| Metric                     | Value  |
| -------------------------- | ------ |
| Sparsity Achieved          | 50%    |
| Accuracy After Pruning     | 96.44% |
| Accuracy After Fine-Tuning | 97.73% |

Fine-tuning successfully recovers and improves model performance.

---

## 3. Weight Sharing Quantization

Remaining weights are clustered using K-Means.

### Configuration

```text
Quantization Bits = 8
Clusters Per Layer = 256
```

Instead of storing every weight independently, multiple weights share the same centroid value.

### Results

| Metric            | Value     |
| ----------------- | --------- |
| Accuracy          | 97.75%    |
| Storage Size      | 0.1119 MB |
| Compression Ratio | 8×        |

---

## 4. NPZ Serialization

Compressed model parameters are stored in:

```text
compressed_model.npz
```

Only necessary tensors and metadata are preserved.

Benefits:

* Reduced storage footprint
* Faster loading
* Portable deployment format

---

## 5. Huffman Encoding

Quantized weights are further compressed using Huffman Coding.

The encoder exploits non-uniform weight distributions to generate variable-length codes.

### Final Results

| Metric                  | Value     |
| ----------------------- | --------- |
| Huffman Encoded Size    | 0.1104 MB |
| Final Compression Ratio | 8.1×      |
| Final Accuracy          | 97.75%    |

---

# Experimental Results

| Stage                  | Accuracy | Storage   |
| ---------------------- | -------- | --------- |
| Baseline Model         | 96.88%   | 0.8955 MB |
| After Pruning          | 96.44%   | 0.8955 MB |
| After Fine-Tuning      | 97.73%   | 0.8955 MB |
| After Quantization     | 97.75%   | 0.1119 MB |
| After Huffman Encoding | 97.75%   | 0.1104 MB |

---

# Memory Analysis

The project evaluates:

* Model Storage Size
* Runtime RAM Consumption
* Compression Ratio
* Sparsity Levels

This allows comparison between:

* Original Model
* Pruned Model
* Quantized Model
* Huffman Encoded Model

for deployment on resource-constrained devices.

---

# Future Extensions

The current implementation intentionally avoids CNN training and focuses on the compression framework itself.

Future work includes:

* CNN-based feature extraction
* CNN compression
* Sparse matrix storage (CSR/CSC)
* Structured pruning
* Quantization-aware training
* Hardware-aware deployment
* Edge-device benchmarking
---

## Project Report

📄 [End Evaluation Report](https://github.com/SHUB-1806/EEA_DNN_Compression_CV/blob/main/END-EVAL/DNN%26CV_REPORT_endeval.pdf)

---

# Authors

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

---

# License

This repository is intended for academic, educational and research purposes.
