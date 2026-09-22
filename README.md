# Fruit Freshness Classification Using Deep Learning

## Overview

This project uses deep learning to classify fruit images based on their **fruit type and freshness condition**.

The project classifies images into six categories:

1. **Fresh Apple**
2. **Rotten Apple**
3. **Fresh Banana**
4. **Rotten Banana**
5. **Fresh Orange**
6. **Rotten Orange**

Two deep-learning approaches are implemented and compared:

1. **Custom CNN**
2. **MobileNetV2 with Transfer Learning and Fine-Tuning**

The project also supports prediction on a new uploaded fruit image.

---

## Project Architecture

### 1. Custom CNN

A convolutional neural network is built from scratch as a baseline model.

**Flow:**

`Input Image → Data Augmentation → Convolution Blocks → Global Average Pooling → Dense Layers → 6-Class Classification`

The CNN contains multiple convolutional blocks with:

- Conv2D
- Batch Normalization
- Max Pooling
- Global Average Pooling
- Dropout
- Dense classification layer

### 2. MobileNetV2

MobileNetV2 pretrained on ImageNet is used for transfer learning.

**Flow:**

`Input Image → Data Augmentation → MobileNetV2 → Global Average Pooling → Dropout → Dense Layer → 6-Class Classification`

The MobileNetV2 base is initially frozen while the classification layer is trained. The final layers are then unfrozen and fine-tuned using a small learning rate.

---

## Dataset

This project uses the **Fruits Fresh and Rotten for Classification** dataset from Kaggle.

**Kaggle Dataset:**

https://www.kaggle.com/datasets/sriramr/fruits-fresh-and-rotten-for-classification

The dataset contains six classes:

- Fresh Apple
- Rotten Apple
- Fresh Banana
- Rotten Banana
- Fresh Orange
- Rotten Orange

### Important

The dataset is **not stored in this GitHub repository** because of its large size.

The notebook downloads the dataset directly from Kaggle using a public download URL.

**No Kaggle API key or `kaggle.json` file is required.**

---

## Data Preprocessing

The notebook performs the following preprocessing steps:

- Image resizing to **224 × 224**
- Training/validation split
- Data augmentation
- Batch processing
- TensorFlow prefetching
- Separate test dataset

Data augmentation includes:

- Horizontal flipping
- Rotation
- Zoom
- Contrast adjustment

The original test set is kept separate from the training and validation data.

---

## Models

### Custom CNN

The custom CNN is used as the baseline model.

It learns image features directly from the fruit dataset.

### MobileNetV2

MobileNetV2 uses pretrained ImageNet features.

The model is trained in two stages:

1. Train the new classification head with the pretrained base frozen.
2. Fine-tune the final MobileNetV2 layers using a lower learning rate.

---

## Model Results

The models are evaluated on the test dataset.

| Model | Test Accuracy |
|---|---:|
| Custom CNN | **83.91%** |
| Fine-Tuned MobileNetV2 | **99.04%** |

MobileNetV2 achieved higher test accuracy than the custom CNN for this dataset and training configuration.

---

## Evaluation

The final model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Classification Report
- Confusion Matrix

Predictions are generated for the complete test dataset before calculating the evaluation metrics.

---

## How to Run in Google Colab

1. Open the notebook in Google Colab.
2. Enable GPU from:

   `Runtime → Change runtime type → T4 GPU`

3. Run the cells from top to bottom.
4. The dataset is downloaded automatically.
5. The dataset is extracted and its train/test folders are detected automatically.
6. Train the Custom CNN.
7. Train and fine-tune MobileNetV2.
8. Check the evaluation results.
9. Upload a new fruit image in the prediction section.

### Google Colab Notebook

https://colab.research.google.com/drive/10kToxJqLEQMGnhwcySX-CMHqy7eWWp0D?usp=sharing

---

## Image Prediction

The trained MobileNetV2 model can classify a new uploaded image.

The prediction provides:

- Fruit type
- Freshness condition
- Prediction confidence
- Probability for all six classes
