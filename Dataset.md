# Brain Tumor MRI Dataset

This project uses the **Brain Tumor MRI Scans** dataset hosted on Kaggle.

🔗 **Dataset Link:**  
https://www.kaggle.com/datasets/rm1000/brain-tumor-mri-scans

---

## About the Dataset

The dataset contains MRI scans categorized into:

- **No Tumor**
- **Glioma Tumor**
- **Meningioma Tumor**
- **Pituitary Tumor**

It is suitable for classification tasks and anomaly detection setups such as the autoencoder workflow used in this project.

---

## Usage Notes

- The dataset is **not included in this repository** due to size and licensing restrictions.
- You must download it manually from Kaggle and unzip it locally.
- The project assumes the following directory structure:

```
  DATA_ROOT/
├── train/
│ └── no_tumor/
├── test/
│ ├── no_tumor/
│ ├── glioma_tumor/
│ ├── meningioma_tumor/
│ └── pituitary_tumor/

```
If your extracted dataset differs, reorganize it accordingly.

---

## Licensing

The dataset is provided by its creator on Kaggle.  
Make sure you comply with the dataset’s terms of use on the Kaggle page.

This repository does **not** redistribute or modify the dataset.

