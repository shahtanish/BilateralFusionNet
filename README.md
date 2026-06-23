# BilateralFusionNet

## A Multimodal Deep Learning Framework for Multi-Label Ocular Disease Classification Using Bilateral Fundus Images and Patient Metadata with Explainable AI

### Overview

Ocular diseases are among the leading causes of preventable blindness worldwide. Early diagnosis is critical for preventing irreversible vision loss, but manual screening requires experienced ophthalmologists and significant clinical resources.

BilateralFusionNet is a novel multimodal deep learning framework designed to classify multiple ocular diseases simultaneously using:

* Bilateral Fundus Images (Left and Right Eye)
* Patient Metadata (Age and Gender)
* Explainable AI Techniques (Grad-CAM and SHAP)

The framework leverages the complete structure of the ODIR-5K dataset and introduces a Bilateral Cross-Attention mechanism to capture clinically important inter-eye relationships.

---

## Research Motivation

Most existing ocular disease classification systems:

* Process only a single eye image
* Ignore patient metadata
* Force single-label predictions
* Provide limited explainability

However, many eye diseases occur simultaneously and often exhibit asymmetrical patterns between the left and right eyes.

BilateralFusionNet addresses these limitations through multimodal learning and explainable AI.

---

## Key Contributions

### 1. Bilateral Cross-Attention Fusion

A novel attention mechanism allowing:

* Left eye features to attend to right eye features
* Right eye features to attend to left eye features

This captures clinically meaningful inter-eye asymmetry.

### 2. Metadata Fusion

Patient metadata including:

* Age
* Gender

is encoded using a dedicated Metadata MLP and fused with image features.

### 3. True Multi-Label Classification

Unlike traditional softmax-based systems, BilateralFusionNet uses:

* Sigmoid Activation
* Multi-Label Focal Loss

allowing simultaneous prediction of multiple diseases.

### 4. Dual Explainable AI

#### Grad-CAM

Visualizes disease-related regions within retinal images.

#### SHAP

Explains the influence of patient metadata on model predictions.

---

## Dataset

### ODIR-5K

The Ocular Disease Intelligent Recognition (ODIR-5K) dataset contains:

* 5,000 Patient Records
* Bilateral Fundus Images
* Patient Metadata
* Multi-Disease Labels

### Disease Categories

* Normal
* Diabetes
* Glaucoma
* Cataract
* Age-related Macular Degeneration (AMD)
* Hypertension
* Myopia
* Other Ocular Diseases

---

## System Architecture

ODIR-5K Dataset
(Left Eye + Right Eye + Metadata)

↓

EfficientNet-B3 Encoder (Left Eye)

EfficientNet-B3 Encoder (Right Eye)

↓

Bilateral Cross-Attention Fusion

↓

Metadata MLP

↓

Feature Concatenation

↓

Multi-Label Classifier

↓

Disease Predictions

↓

Explainable AI Outputs

* Grad-CAM
* SHAP

---

## Module Identification

### M1 – Data Pipeline

* ODIR-5K Loading
* Bilateral Pairing
* Metadata Encoding
* Stratified Dataset Split

### M2 – Bilateral Encoder

* Shared EfficientNet-B3 Backbone

### M3 – Cross-Attention Fusion

* Bidirectional Multi-Head Attention
* Layer Normalization
* Feed Forward Networks

### M4 – Metadata MLP

* Age and Gender Embeddings

### M5 – Multi-Label Classifier

* Fully Connected Layers
* Sigmoid Output

### M6 – Explainable AI Module

* Grad-CAM
* SHAP

---

## Technology Stack

### Programming Language

* Python

### Deep Learning Framework

* PyTorch

### Model Backbone

* EfficientNet-B3

### Libraries

* timm
* shap
* pytorch-grad-cam
* NumPy
* Pandas
* Scikit-Learn
* Matplotlib

### Development Platform

* Kaggle Notebook
* Tesla T4 GPU

---

## Training Configuration

| Parameter         | Value                       |
| ----------------- | --------------------------- |
| Batch Size        | 32                          |
| Epochs            | 30                          |
| Learning Rate     | 1e-4                        |
| Optimizer         | AdamW                       |
| Scheduler         | CosineAnnealingWarmRestarts |
| Loss Function     | Multi-Label Focal Loss      |
| Mixed Precision   | Enabled                     |
| Gradient Clipping | 1.0                         |

---

## Explainable AI

### Grad-CAM

Provides visual explanations by highlighting retinal regions responsible for disease predictions.

### SHAP

Provides metadata-level explanations showing the contribution of:

* Age
* Gender

towards each disease prediction.

---

## Ablation Study

The contribution of each component is evaluated through:

1. Baseline Model
2. * Bilateral Images
3. * Cross-Attention
4. * Metadata Fusion
5. Full BilateralFusionNet

This validates the effectiveness of each proposed innovation.

---

## Research Outcomes

* Improved utilization of bilateral retinal information
* Enhanced disease prediction through metadata fusion
* Multi-label disease classification
* Clinically interpretable AI predictions
* Lightweight architecture suitable for practical deployment

---

## Future Work

* Integration with Vision Transformers
* Real-time Clinical Screening System
* Mobile-Based Retinal Diagnosis
* Federated Learning for Privacy-Preserving Training
* Multi-Hospital Deployment

---

## Author

**Shah Tanish**

Master of Computer Applications (MCA)

Vellore Institute of Technology, Chennai

Guided by:

Dr. Jani Anbarasi L

Associate Professor

School of Computer Science and Engineering

VIT Chennai

---


## License

This project is developed for academic and research purposes.
