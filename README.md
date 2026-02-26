🚗 Vehicle Classification using CNN

Deep Learning Project – ICT 3212
Rajarata University of Sri Lanka

📌 Project Overview

This project implements a Convolutional Neural Network (CNN) to classify vehicle images into four categories:

🚘 Car

🚌 Bus

🚛 Truck

🏍 Motorcycle

The model is built using TensorFlow / Keras and trained from scratch on a labeled vehicle image dataset.

The goal is to develop a model that achieves strong accuracy while maintaining good generalization performance.

🧠 Model Architecture

The CNN consists of:

🔹 4 Convolutional Blocks (32 → 64 → 128 → 256 filters)

🔹 Batch Normalization for training stability

🔹 MaxPooling layers for spatial reduction

🔹 Dropout for regularization

🔹 Fully Connected classifier head

🔹 Softmax output layer (4 classes)

Input Image Size: 128 × 128 × 3

⚙️ Training Configuration
Parameter	Value
Epochs	30
Batch Size	64
Optimizer	Adam
Learning Rate	0.00081
Loss Function	Categorical Crossentropy
📊 Model Performance

✅ Training Accuracy: ~92%

✅ Validation Accuracy: ~86–87%

⚠ Mild Overfitting Observed (~6% gap)

📉 Validation loss stabilised after early spike

The model demonstrates acceptable generalisation for a custom CNN trained from scratch.
