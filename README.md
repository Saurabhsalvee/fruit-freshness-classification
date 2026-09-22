# 🍎 Fruit Freshness Classification Using Deep Learning

## Overview

This project uses deep learning to classify fruit images based on both **fruit type** and **freshness condition**.

The model classifies images into six categories:

1. **Fresh Apple**
2. **Rotten Apple**
3. **Fresh Banana**
4. **Rotten Banana**
5. **Fresh Orange**
6. **Rotten Orange**

Two deep-learning approaches are implemented and compared:

1. **Custom CNN**
2. **MobileNetV2 with Transfer Learning and Fine-Tuning**

The project also supports prediction on a new uploaded fruit image and displays the predicted fruit, condition, confidence, and probabilities for all six classes.

---

## Project Architecture

### 1. Custom CNN

A convolutional neural network is built from scratch as the baseline model.

**Flow:**

`Input Image → Data Augmentation → Convolution Blocks → Global Average Pooling → Dense Layers → 6-Class Classification`

The CNN uses:

- Conv2D layers
- Batch Normalization
- Max Pooling
- Global Average Pooling
- Dropout
- Dense Softmax output layer

### 2. MobileNetV2

MobileNetV2 pretrained on ImageNet is used for transfer learning.

**Flow:**

`Input Image → Data Augmentation → MobileNetV2 → Global Average Pooling → Dropout → Dense Layer → 6-Class Classification`

The model is trained in two stages:

1. The pretrained MobileNetV2 base is frozen and only the new classification head is trained.
2. The final layers of MobileNetV2 are unfrozen and fine-tuned using a smaller learning rate.

---

## Dataset

This project uses the **Fruits Fresh and Rotten for Classification** dataset from Kaggle.

**Dataset Link:**  
https://www.kaggle.com/datasets/sriramr/fruits-fresh-and-rotten-for-classification

The dataset contains the following six classes:

- Fresh Apple
- Rotten Apple
- Fresh Banana
- Rotten Banana
- Fresh Orange
- Rotten Orange

### Important

The dataset is **not stored in this GitHub repository** because of its large size.

The notebook downloads the dataset automatically using a direct Kaggle download URL.

**No Kaggle API key or `kaggle.json` file is required.**

---

## Data Preprocessing

The notebook performs the following preprocessing steps:

- Resize images to **224 × 224**
- Split training data into **80% training and 20% validation**
- Keep the original test set separate
- Apply data augmentation
- Use batch processing
- Use TensorFlow prefetching for better performance

### Data Augmentation

The following augmentation techniques are applied:

- Horizontal flip
- Random rotation
- Random zoom
- Random contrast adjustment

---

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Pillow
- CNN
- MobileNetV2
- Transfer Learning
- Google Colab
- Kaggle Dataset

---

## Features

- Automatic Kaggle dataset download
- Safe ZIP extraction
- Automatic train/test folder detection
- Dataset class distribution analysis
- Sample image visualization
- Image preprocessing
- Data augmentation
- Custom CNN model
- MobileNetV2 transfer learning
- MobileNetV2 fine-tuning
- Accuracy and loss graphs
- Model comparison
- Accuracy, precision, recall and F1-score
- Classification report
- Confusion matrix
- Final model saving
- New image upload
- Fruit type prediction
- Fresh/Rotten prediction
- Prediction confidence
- Probability for all six classes

---

## Model Results

The models were evaluated on the test dataset.

| Model | Test Accuracy |
|---|---:|
| Custom CNN | **83.91%** |
| Fine-Tuned MobileNetV2 | **99.04%** |

The fine-tuned MobileNetV2 achieved higher accuracy than the custom CNN for this dataset and training configuration.

---

## Evaluation Metrics

The final model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Classification Report
- Confusion Matrix

These metrics help evaluate the model's performance across all six classes.

---

## How to Run in Google Colab

1. Open the notebook in Google Colab.
2. Enable GPU:

   `Runtime → Change runtime type → T4 GPU`

3. Run the cells from top to bottom.
4. The dataset will be downloaded automatically.
5. The dataset will be extracted and verified.
6. Train the Custom CNN model.
7. Train and fine-tune MobileNetV2.
8. View the evaluation results.
9. Upload a fruit image in the prediction section.
10. View the fruit type, freshness condition, confidence, and class probabilities.

---

## Google Colab Notebook

Open the project directly in Google Colab:

https://colab.research.google.com/drive/10kToxJqLEQMGnhwcySX-CMHqy7eWWp0D?usp=sharing

