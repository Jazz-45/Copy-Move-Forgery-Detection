# 🕵️‍♂️ Copy-Move Forgery Detection using UNET and DCT | CoMoFoD Dataset

This repository presents an in-depth comparison between **UNET-based deep learning** and **DCT-based classical** approaches for detecting **copy-move image forgeries**. The experiments were conducted on the **CoMoFoD (Copy-Move Forgery Detection) dataset** with various transformations and post-processing techniques.

> 🔬 This work was carried out as part of an internship focused on **digital image forensics**.

---

## 📁 Repository Structure

Copy-Move/
│
├── Algorithm/ # Main detection algorithms
│ ├── UNET.ipynb
│ ├── DCT-1.ipynb
│ ├── DCT-2.ipynb
│ └── Updated.ipynb # Morphological comparison (UNET vs DCT)
│
├── Analysis/ # Exploratory data analysis & visualizations
│ └── Analysis.ipynb
│
├── Results/ # Precomputed results used in analysis
│ ├── UNET/
│ └── DCT/
│
├── Models/ # Trained UNET models (.h5 and .keras)
│ └── unet_comofod_complete.h5
│
├── assets/ # Images for README and plots
│ ├── sample_outputs/
│ ├── comparisons/
│ └── architecture/
│
└── README.md # You are here!



---

## 📌 Project Objectives

- ✅ Build and train a **UNET segmentation model** to detect forged regions in images.
- ✅ Implement a **DCT + SIFT-based classical pipeline** for comparison.
- ✅ Perform **quantitative and qualitative evaluations** using metrics: `Precision`, `Recall`, `F1-Score`, and `IoU`.
- ✅ Handle a variety of **transformations** (translation, scaling, rotation, distortion) and **post-processing** effects (blurring, noise, JPEG compression, etc.).
- ✅ Visualize and compare model performances using plots, confusion matrices, and trend graphs.

---

## 🧠 Algorithms

### 1. 🔬 UNET (Deep Learning)
- Implemented using TensorFlow / Keras.
- Custom architecture for binary segmentation (forgery vs original).
- Trained on forged images and binary masks (ground truth).
- Evaluated across 200 CoMoFoD image sets.

📂 Code: [`Algorithm/UNET.ipynb`](Algorithm/UNET.ipynb)  
📦 Trained Model: [`Models/unet_comofod_complete.h5`](Models/unet_comofod_complete.h5)

---

### 2. 🧩 DCT + SIFT Matching (Classical)
- Discrete Cosine Transform used for feature representation.
- SIFT keypoints extracted and matched using BruteForce matcher.
- Forgery localization through patch similarity analysis.

📂 Code:  
- [`Algorithm/DCT-1.ipynb`](Algorithm/DCT-1.ipynb)  
- [`Algorithm/DCT-2.ipynb`](Algorithm/DCT-2.ipynb)

---

### 3. ⚙️ Morphological Post-Processing
- Applied to improve mask accuracy and remove noise.
- Shown for both UNET and DCT predictions.

📂 Code: [`Algorithm/Updated.ipynb`](Algorithm/Updated.ipynb)

---

## 📈 Analysis & Visualizations

The [`Analysis.ipynb`](Analysis/Analysis.ipynb) notebook covers:

- 📊 Metric comparisons (F1, IoU, Precision, Recall)
- 📉 Post-processing trends for different levels
- 🔵 Donut charts showing good vs bad detection count
- 🔥 Confusion matrix heatmaps
- 📈 Transformation-wise performance trends

> Results used from: [`Results/`](Results/) folder  
> Sample visuals in: [`assets/comparisons/`](assets/comparisons/)

---

## 📦 Trained Models

| Model Type        | File                                     |
|-------------------|------------------------------------------|
| UNET (Full)       | `Models/unet_comofod_complete.h5`        |
| UNET (Keras Format) | `Models/unet_comofod_complete.keras`   |

> These models can be used with `Using-Model.ipynb` from the private repo or in a deployed Streamlit app.

---

## 📊 Dataset

This project used a **smaller variant** of the [CoMoFoD Dataset](https://github.com/fenrus75/CoMoFoD) that includes:
- 200 base images with transformations
- Binary masks for forged regions
- Post-processed images (Brightness, Color Adj, JPEG Compression, etc.)

> 🛑 **Note**: Dataset is **not included** in this repository. You can organize your own folder structure based on how the model was trained.

---

## 🚀 Running the Code

 Clone the repository
   ```bash
   git clone https://github.com/yourusername/Copy-Move.git
   cd Copy-Move
