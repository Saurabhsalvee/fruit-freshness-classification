# 🍎 Fruit Freshness Classification Using Deep Learning

A deep learning project that classifies fruit images into six categories:

- Fresh Apple
- Rotten Apple
- Fresh Banana
- Rotten Banana
- Fresh Orange
- Rotten Orange

## Technologies

- Python
- TensorFlow / Keras
- CNN
- MobileNetV2
- Transfer Learning
- Google Colab
- Kaggle Dataset

## Models

The project compares:

1. Custom CNN
2. MobileNetV2 with Transfer Learning and Fine-Tuning

## Features

- Dataset automatically downloaded from Kaggle
- Data augmentation
- Training and validation
- Model evaluation
- Classification report
- Confusion matrix
- Accuracy, precision, recall and F1-score
- New image upload and prediction
- Fruit type + freshness prediction
- Prediction confidence

## Dataset

**Kaggle Dataset:**  
https://www.kaggle.com/datasets/sriramr/fruits-fresh-and-rotten-for-classification

The dataset is downloaded automatically by the notebook, so no Kaggle API key is required.

## How to Run

1. Open the `.ipynb` file in Google Colab.
2. Enable GPU:  
   `Runtime → Change runtime type → T4 GPU`
3. Run the cells from top to bottom.
4. Upload a fruit image in the prediction section.

## Output

The model predicts the fruit type, freshness condition, and confidence.

## Results

The final MobileNetV2 model achieved **99.04% test accuracy**, outperforming the custom CNN, which achieved **83.91%**.

| Model | Test Accuracy |
|---|---:|
| Custom CNN | 83.91% |
| MobileNetV2 | 99.04% |

### Example Prediction

```text
Fruit: Apple
Condition: Rotten
Confidence: 99.74%
