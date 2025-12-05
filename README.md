# 🇬🇧 British Sign Language (BSL) Detection Using Machine Learning  
A lightweight real-time BSL alphabet recognition system built using Convolutional Neural Networks (CNN) and a custom self-created dataset.

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/TensorFlow-Keras-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/OpenCV-Real--time-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge"/>
</p>

---

## 📌 Overview
This project implements a **real-time British Sign Language (BSL) alphabet detector** using a CNN trained on a custom dataset captured using OpenCV.  
The system recognizes **static BSL alphabets A–Z (except H & J)** and runs efficiently on a live webcam feed using lightweight preprocessing.

---

## 📂 Dataset Details
The dataset was fully built manually through live image capture.

- **Resolution:** 48×48 grayscale images  
- **Samples per class:** ~250  
- **Classes:** A–Z (excluding H & J) + Blank → **25 total classes**  
- **Preprocessing Includes:**  
  - Region of interest (ROI) extraction  
  - Grayscale conversion  
  - Image resizing  
  - Normalization (0–1)  
- **Dataset Split:** 80% training, 20% validation  

---

## 🧠 Model Architecture

### **Convolutional Layers**
- Conv2D (128 filters, 3×3) → MaxPooling → Dropout (40%)  
- Conv2D (256 filters) → MaxPooling → Dropout (40%)  
- Conv2D (512 filters) → MaxPooling → Dropout (40%)  
- Conv2D (512 filters) → MaxPooling → Dropout (40%)  

### **Dense Layers**
- Dense (512 neurons) → Dropout (40%)  
- Dense (64 neurons) → Dropout (20%)  
- Dense (256 neurons) → Dropout (30%)  
- Output: Dense (25 neurons, Softmax activation)  

### **Training Settings**
- Optimizer: **Adam**  
- Loss Function: **Categorical Crossentropy**  
- Epochs: **100**  
- Batch Normalization applied  

---

## 🏃‍♂️ Real-Time Detection Pipeline
1. Capture frame from webcam  
2. Extract Region of Interest (ROI)  
3. Convert to grayscale and resize to 48×48  
4. Normalize image data  
5. Predict using trained CNN model  
6. Display predicted letter with confidence score  

---

## 📝 Requirements

Python 3.8+
TensorFlow / Keras
OpenCV
NumPy
Matplotlib
splitfolders

---


Install dependencies:

```bash
pip install -r requirements.txt
```

## ▶️ Running the Project
Run "making_directories" up until the 2nd last cell 
Run "making_and_training_bsl_model_final" or "making_and_training_model_with_augmentation" depending on if you want data augmentation or not.

