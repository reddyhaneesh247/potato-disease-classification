# Bell Pepper Disease Classification

## Overview

This project uses Deep Learning and Computer Vision techniques to classify bell pepper leaf images as either healthy or affected by bacterial spot. A Convolutional Neural Network (CNN) was trained on the bell pepper subset of the PlantVillage dataset to automatically identify leaf diseases and support early disease detection.

## Features

* Bell pepper leaf disease classification using CNN
* Image preprocessing and normalization
* Data augmentation for improved generalization
* Binary image classification (2 classes)
* Deep learning model built using TensorFlow/Keras
* Disease prediction with confidence score from leaf images

## Dataset

The project uses the bell pepper images from the PlantVillage dataset (1,157 images) categorized into:

* Pepper Bell Bacterial Spot
* Pepper Bell Healthy

Dataset Structure:

```text
PlantVillage/
├── Pepper__bell___Bacterial_spot
└── Pepper__bell___healthy
```

## Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Matplotlib
* Google Colab

## Project Workflow

### 1. Data Preparation

* Loaded images from the PlantVillage dataset using `image_dataset_from_directory`
* Image size 256x256, batch size 32
* Applied caching, shuffling and prefetching
* Split data into training (80%), validation (10%), and testing (10%) sets

### 2. Image Preprocessing

Performed:

* Image resizing
* Pixel normalization

```python
resize_and_rescale = tf.keras.Sequential([
    layers.Resizing(256, 256),
    layers.Rescaling(1./255)
])
```

### 3. Data Augmentation

Used augmentation techniques on the training set to improve model robustness:

* Random Flip (horizontal and vertical)
* Random Rotation (0.2)

### 4. Model Architecture

Built a Convolutional Neural Network (CNN) consisting of:

* Resizing and Rescaling layers
* 6 Conv2D layers (32 filters, then 64 filters) with ReLU activation
* MaxPooling layer after each Conv2D layer
* Flatten Layer
* Dense Layer (64 units, ReLU)
* Softmax Output Layer (2 units)

### 5. Model Training

The model was trained using TensorFlow/Keras with the Adam optimizer and sparse categorical crossentropy loss for 5 epochs to classify bell pepper leaf images into two categories: bacterial spot and healthy.

### 6. Model Evaluation

Evaluated performance using:

* Training Accuracy
* Validation Accuracy
* Training Loss
* Validation Loss
* Test Accuracy and Loss

| Metric   | Training | Validation | Test   |
|----------|----------|------------|--------|
| Accuracy | 0.8690   | 0.9271     | 0.8500 |
| Loss     | 0.1983   | 0.1498     | 0.1907 |

## Model Architecture

```text
Input Image (256 x 256 x 3)
      ↓
Resizing & Rescaling
      ↓
Conv2D (32) + MaxPooling
      ↓
Conv2D (64) + MaxPooling  (repeated 5 times)
      ↓
Flatten
      ↓
Dense Layer (64)
      ↓
Softmax Output (2 classes)
```

## Example Prediction

Input:

```text
Bell Pepper Leaf Image
```

Output:

```text
Pepper__bell___Bacterial_spot
```

or

```text
Pepper__bell___healthy
```

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/reddyhaneesh247/bell-pepper-disease-classification.git
cd bell-pepper-disease-classification
```

### 2. Open the Notebook

Open the notebook in Google Colab:

```text
Bell_Pepper_Disease_Classification.ipynb
```

### 3. Install Required Libraries

```python
!pip install tensorflow numpy matplotlib
```

### 4. Upload the Dataset

Upload:

```text
PlantVillage.zip
```

to Google Colab.

### 5. Extract the Dataset

```python
import zipfile

with zipfile.ZipFile("PlantVillage.zip", "r") as zip_ref:
    zip_ref.extractall("/content/")
```

### 6. Run All Cells

Execute all notebook cells sequentially to:

* Load and preprocess bell pepper leaf images
* Apply image augmentation
* Train the CNN model
* Evaluate model performance
* Generate disease predictions

### 7. Predict Disease Class

The trained model classifies bell pepper leaves into:

* Pepper Bell Bacterial Spot
* Pepper Bell Healthy

### Project Structure

```text
bell-pepper-disease-classification/
│
├── Bell_Pepper_Disease_Classification.ipynb
├── PlantVillage.zip
└── README.md
```

## Future Improvements

* Train for more epochs and add early stopping
* Handle class imbalance and report precision, recall and F1-score
* Use transfer learning (MobileNetV2, EfficientNet) for higher accuracy
* Save the trained model and deploy it with FastAPI or Streamlit
* Extend to other PlantVillage crops and diseases
