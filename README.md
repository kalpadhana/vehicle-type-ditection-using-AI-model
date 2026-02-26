# 🚗 Vehicle Type Detection Using Image Classification (CNN)

**ICT 3212 – Rajarata University of Sri Lanka | Department of Computing**

A Convolutional Neural Network (CNN) built with TensorFlow/Keras to classify vehicle images into 4 categories: **Car, Bus, Truck, and Motorcycle**.

---

## 📋 Project Overview

This project implements a custom CNN model trained on a labelled vehicle image dataset. The model applies data augmentation, batch normalization, dropout regularization, and learning rate scheduling to achieve strong generalization with minimal overfitting.

### Final Results

| Metric | Value |
|---|---|
| Test Accuracy | **81.38%** |
| Best Validation Accuracy | **86.62%** |
| Training Accuracy | **91.69%** |
| Train/Val Gap | 5.06% *(Mild – acceptable)* |
| Epochs Trained | 30 / 30 |

### Per-Class Test Accuracy

| Class | Correct / Total | Accuracy |
|---|---|---|
| Car | 143 / 200 | 71.5% |
| Bus | 196 / 200 | 98.0% |
| Truck | 141 / 200 | 70.5% |
| Motorcycle | 171 / 200 | 85.5% |

---

## 🏗️ Model Architecture

- **Input:** 128×128 RGB images
- **3 Convolutional Blocks** – each with Conv2D + BatchNorm + MaxPooling + Dropout
- **Dense Head** – Flatten → Dense(256) + BatchNorm + Dropout(0.40) → Softmax(4)
- **Optimizer:** Adam (initial lr = 0.0008)
- **Loss:** Categorical Cross-Entropy

### Overfitting Fixes Applied

| Parameter | Before | After |
|---|---|---|
| Batch size | 32 | **64** |
| Dropout (blocks 1 & 2) | 0.25 | **0.20** |
| Dropout (head) | 0.50 | **0.40** |
| Learning rate | 0.0005 | **0.0008** |
| Augmentation ranges | Higher | **Reduced** |
| EarlyStopping patience | 8 | **7** |
| ReduceLROnPlateau patience | 4 | **3** |

---

## 📁 Repository Structure

```
├── Vehicle_Type_Detection_Using_Image_Classification_implementation_1.ipynb
│       Main notebook – data setup, model training, evaluation
├── output_log.txt
│       Full training output log (all cell outputs)
├── requirements.txt
│       Python dependencies
├── .gitignore
│       Files excluded from version control
└── README.md
        This file
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/vehicle-type-detection.git
cd vehicle-type-detection
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Dataset Setup

The notebook expects a `vehicle_dataset.zip` stored in Google Drive at:
```
/content/drive/MyDrive/vehicle_dataset.zip
```

The dataset should contain `train/` and `test/` splits with subdirectories for each class:
```
vehicle_dataset/
├── train/
│   ├── car/
│   ├── bus/
│   ├── truck/
│   └── motorcycle/
└── test/
    ├── car/
    ├── bus/
    ├── truck/
    └── motorcycle/
```

### 4. Run the Notebook

Open the notebook in **Google Colab** for best results (GPU recommended):

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

---

## 📊 Training Configuration

| Parameter | Value |
|---|---|
| Image size | 128 × 128 |
| Batch size | 64 |
| Max epochs | 30 |
| Validation split | 20% |
| Number of classes | 4 |

### Data Augmentation (Training Only)

- Rotation: ±15°
- Width/Height shift: ±15%
- Shear: 10%
- Zoom: ±15%
- Horizontal flip: Yes
- Brightness: [0.85, 1.15]
- Channel shift: 15.0

---

## 📈 Training Progress (Key Epochs)

| Epoch | Train Acc | Val Acc |
|---|---|---|
| 1 | 49.3% | 25.0% |
| 10 | 86.2% | 48.5% |
| 15 | 85.9% | 81.4% |
| 19 | 87.9% | 85.5% |
| 30 | 91.5% | **86.6%** |

---

## 🛠️ Technologies Used

- Python 3.12
- TensorFlow / Keras
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- Google Colab + Google Drive

---

## 📄 License

This project is for academic purposes – **ICT 3212**, Rajarata University of Sri Lanka.
