Vehicle Type Detection System using CNN
Project Overview
This repository contains the Final Corrected Version of a vehicle type detection system developed at the Rajarata University of Sri Lanka, Department of Computing. The system utilizes a Deep Convolutional Neural Network (CNN) to classify images into four distinct categories: Bus, Car, Motorcycle, and Truck.

Key Features
Overfitting Mitigation: Implements specific strategies, including Dropout layers and tuned learning rates, to address previous overfitting issues.

Automated Data Preprocessing: Includes scripts for mounting Google Drive, extracting datasets, and cleaning folder structures (e.g., renaming directories for consistency).

Real-time Visualization: Features custom evaluation summaries that display top-3 predictions with confidence percentages and color-coded results.

Deep Learning Architecture: Utilizes a Sequential model with multiple Conv2D blocks, BatchNormalization, and MaxPooling2D layers.

Model Performance
Based on the provided training logs and graphs:

Training Accuracy: Reaches approximately 92% after 30 epochs.

Validation Accuracy: Stabilizes around 86-87%, showing a successful but narrow generalization gap.

Training Dynamics: The model experienced a significant loss spike around Epoch 5 before successfully converging to a lower loss value.

Inference Quality: Individual tests show high confidence scores (e.g., 99.25% for Bus and 99.8% for Motorcycle).

Dataset Structure
The model expects a organized directory structure as follows:

Plaintext
/vehicle_dataset
    ├── train/
    │   ├── bus/
    │   ├── car/
    │   ├── motorcycle/
    │   └── truck/
    └── test/ (organized similarly)
Setup and Usage
Environment: This project is optimized for Google Colab using a T4 GPU.

Data: Place your vehicle_dataset.zip in the root of your Google Drive.

Execution:

Run the initial cells to mount Google Drive and extract the data.

Execute the training block to train the CNN.

Use the visualization cell to view random test image results and bar charts.

Results Example
The system provides a clear evaluation summary for test samples:

1. Motorcycle: Confidence: 99.8% (Correct).

2. Car: Confidence: 97.2% (Correct).

3. Car (True) / Truck (Pred): Confidence: 62.8% (Wrong).
