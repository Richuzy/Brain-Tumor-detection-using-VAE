# Brain Tumor Detection Using Convolutional Autoencoder (Grayscale)

This project implements an **unsupervised anomaly-detection pipeline** for brain-tumor MRI images using a **Convolutional Autoencoder (ConvAE)**.  
The autoencoder is trained **only on NON-tumor (normal) images**, and tumor cases are detected later using reconstruction-error–based anomaly scoring.

This README describes all steps covered up to the notebook cell:

> **"===== Anomaly scoring on 4-class test set (grayscale) + heatmaps ====="**

---

## 1. Overview

The workflow consists of:

1. Preparing MRI images (resizing, grayscale conversion, normalization).
2. Defining a convolutional **encoder–decoder autoencoder**.
3. Training the model to reconstruct *normal* brain MRIs.
4. Loading the trained checkpoint for evaluation.
5. Computing anomaly scores on a 4-class dataset (one normal class + three tumor classes).
6. Automatically selecting a threshold for anomaly detection.
7. Generating heatmaps to highlight suspicious tumor regions.

---

## 2. Dataset Structure

The notebook expects a directory structured as:

