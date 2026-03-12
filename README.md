# 🖼️ Image Classification using CNN and MobileNetV2

This project implements an **image classification system** using two deep learning approaches:

- Custom **Convolutional Neural Network (CNN)**
- **Transfer Learning** using MobileNetV2

The goal of this project is to compare the performance between a manually designed CNN architecture and a pretrained deep learning model.

Both models were trained using **TensorFlow/Keras** and exported into multiple formats for deployment.

---

## 📚 Course Information

This project was developed as part of the course:

**Belajar Fundamental Deep Learning untuk Pemula** by **Dicoding**

The course introduces fundamental concepts of deep learning, including:

- Convolutional Neural Networks (CNN)
- Transfer Learning
- Image Classification
- Model evaluation
- Model deployment

---

## ✨ Features

- Custom CNN architecture built from scratch  
- Transfer learning using **MobileNetV2**  
- Model performance comparison  
- Early stopping training strategy  
- Model export to multiple formats  
- Cross-platform deployment support  

---

# 🧠 Models

## 1️⃣ Custom CNN

The CNN model is manually designed using multiple convolutional layers followed by batch normalization, pooling layers, and fully connected layers.

### Architecture Overview


Conv2D → BatchNorm → MaxPooling
Conv2D → BatchNorm → MaxPooling
Conv2D → BatchNorm → MaxPooling
Conv2D → BatchNorm → MaxPooling
Conv2D → BatchNorm → MaxPooling
Flatten
Dense → Dropout
Dense → Dropout
Softmax Output


### Performance

| Metric | Score |
|------|------|
| Training Accuracy | **91.79%** |
| Validation Accuracy | **87.29%** |
| Test Accuracy | **87.53%** |

---

## 2️⃣ MobileNetV2 (Transfer Learning)

MobileNetV2 pretrained on **ImageNet** is used as a feature extractor.

The base layers are frozen while additional dense layers are added on top for classification.

### Architecture


MobileNetV2 (Frozen)
GlobalAveragePooling
Dense (512)
Dropout
Dense (256)
Dropout
Softmax Output


### Performance

| Metric | Score |
|------|------|
| Training Accuracy | **84.47%** |
| Validation Accuracy | **88.85%** |
| Test Accuracy | **86.96%** |

---

## 📊 Model Comparison

| Model | Test Accuracy |
|------|------|
| Custom CNN | **87.53%** |
| MobileNetV2 | **86.96%** |

Both models achieved **similar performance**, with the custom CNN slightly outperforming MobileNetV2 on the test dataset.

---

## ⚙️ Training Strategy

To prevent overfitting and improve training efficiency, the following callbacks were used:

### Early Stopping

Training stops when validation loss stops improving.

```python
EarlyStopping(
    monitor='val_loss',
    patience=7,
    restore_best_weights=True
)
📦 Model Export

To support different deployment environments, the trained models were exported into multiple formats.

Format	Purpose
TensorFlow SavedModel	Standard TensorFlow deployment
TensorFlow.js	Web browser inference
TensorFlow Lite	Mobile and edge device inference

Both Custom CNN and MobileNetV2 models are available in these formats.

🛠️ Technologies Used

Python

TensorFlow / Keras

NumPy

Matplotlib

Google Colab

📂 Project Structure
image-classification
│
├── models
│   ├── cnn_manual
│   └── mobilenetv2
│
├── notebooks
│   └── training.ipynb
│
├── dataset_sample
│
├── requirements.txt
└── README.md
🎯 Learning Outcomes

Through this project, the following concepts were implemented:

Building a custom CNN architecture

Applying transfer learning with MobileNetV2

Evaluating model performance

Exporting models for cross-platform deployment

👨‍💻 Author

Developed as part of a deep learning learning project from Dicoding.