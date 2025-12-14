# Brain Tumor Detection Using Convolutional Autoencoder (Grayscale)

This project implements an **unsupervised anomaly-detection pipeline** for brain-tumor MRI images using a **Convolutional Autoencoder (ConvAE)**.  
The autoencoder is trained **only on NON-tumor (normal) images**, and tumor cases are detected later using reconstruction-error–based anomaly scoring.


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
```text
DATA_ROOT/
├── train/
│ └── no_tumor/ # ONLY normal images (used for AE training)
├── test/
│ ├── no_tumor/ # normal class
│ ├── glioma_tumor/
│ ├── meningioma_tumor/
│ └── pituitary_tumor/
```
- **Train set:** must contain **only non-tumor images**.
- **Test set:** contains **1 normal class + 3 tumor classes**.

---

## 3. Image Preprocessing

All images go through:

```python
IMG_SIZE = 224

transforms.Compose([
    transforms.Resize((IMG_SIZE, IMG_SIZE), interpolation=Image.BICUBIC),
    transforms.Grayscale(num_output_channels=1),
    transforms.ToTensor(),
    transforms.Normalize([0.5], [0.5]),   # pixel range → [-1, 1]
])
