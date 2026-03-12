# Image Classification with Custom CNN and MobileNetV2

This project implements image classification using two approaches:

- A manually designed CNN (`CNN manual`)
- Transfer learning with `MobileNetV2`

Both models are trained with TensorFlow/Keras and exported to multiple deployment formats.

## Course Context

This project was developed for Dicoding's **Belajar Fundamental Deep Learning untuk Pemula**.

## Features

- Custom CNN model architecture
- MobileNetV2 transfer learning pipeline
- Performance comparison between both models
- Early stopping to reduce overfitting
- Exported models for TensorFlow, TensorFlow.js, and TensorFlow Lite

## Model Architectures

### 1) Custom CNN

```text
Conv2D -> BatchNorm -> MaxPooling
Conv2D -> BatchNorm -> MaxPooling
Conv2D -> BatchNorm -> MaxPooling
Conv2D -> BatchNorm -> MaxPooling
Conv2D -> BatchNorm -> MaxPooling
Flatten
Dense -> Dropout
Dense -> Dropout
Softmax
```

### 2) MobileNetV2 (Transfer Learning)

```text
MobileNetV2 (frozen base)
GlobalAveragePooling
Dense(512)
Dropout
Dense(256)
Dropout
Softmax
```

## Results

| Model | Training Acc | Validation Acc | Test Acc |
| --- | ---: | ---: | ---: |
| Custom CNN | 91.79% | 87.29% | **87.53%** |
| MobileNetV2 | 84.47% | **88.85%** | 86.96% |

Both models perform similarly, with the custom CNN slightly higher on test accuracy.

## Training Strategy

Early stopping is used to stop training when validation loss does not improve:

```python
EarlyStopping(
    monitor="val_loss",
    patience=7,
    restore_best_weights=True,
)
```

## Exported Formats

| Format | Location | Purpose |
| --- | --- | --- |
| TensorFlow SavedModel | `savedmodel/` | Standard TensorFlow deployment |
| TensorFlow.js | `tf-js/` | Browser-based inference |
| TensorFlow Lite | `tf-lite/` | Mobile/edge deployment |

## Project Structure

```text
.
├── notebook.ipynb
├── README.md
├── requirements.txt
├── savedmodel/
│   ├── CNN manual/
│   └── MobileNetV2/
├── tf-js/
│   ├── CNN manual/
│   └── MobileNetV2/
└── tf-lite/
    ├── CNN manual/
    └── MobileNetV2/
```

## How to Run

1. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

2. Open and run the notebook:

   - `notebook.ipynb`

3. Use exported models from:

   - `savedmodel/` for TensorFlow
   - `tf-js/` for TensorFlow.js
   - `tf-lite/` for TensorFlow Lite

## Notes

- `requirements.txt` may include many packages from a broader environment (e.g., Colab).
- For lightweight local setup, you can create a smaller dependency list later if needed.

## Author

Nur Rahmawati (Dicoding deep learning project)