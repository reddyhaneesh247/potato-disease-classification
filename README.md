# 🥔 Potato Disease Prediction

## Overview

This project uses Deep Learning and Computer Vision techniques to classify potato leaf images into different disease categories. A Convolutional Neural Network (CNN) was trained on the PlantVillage dataset to automatically identify potato leaf diseases and support early disease detection.

## Features

* Potato leaf disease classification using CNN
* Image preprocessing and normalization
* Data augmentation for improved generalization
* Multi-class image classification
* Deep learning model built using TensorFlow/Keras
* Disease prediction from leaf images

## Dataset

The project uses the PlantVillage dataset containing potato leaf images categorized into:

* Potato Early Blight
* Potato Late Blight
* Potato Healthy

Dataset Structure:

```text
PlantVillage/
├── Potato___Early_blight
├── Potato___Late_blight
└── Potato___healthy
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

* Loaded images from the PlantVillage dataset
* Created TensorFlow image datasets
* Applied batching and shuffling
* Split data into training, validation, and testing sets

### 2. Image Preprocessing

Performed:

* Image resizing
* Pixel normalization
* Data augmentation

```python
resize_and_rescale = tf.keras.Sequential([
    layers.Resizing(256, 256),
    layers.Rescaling(1./255)
])
```

### 3. Data Augmentation

Used augmentation techniques to improve model robustness:

* Random Flip
* Random Rotation

### 4. Model Architecture

Built a Convolutional Neural Network (CNN) consisting of:

* Multiple Conv2D Layers
* MaxPooling Layers
* Flatten Layer
* Dense Layers
* Softmax Output Layer

### 5. Model Training

The model was trained using TensorFlow/Keras to classify potato leaf images into three disease categories.

### 6. Model Evaluation

Evaluated performance using:

* Training Accuracy
* Validation Accuracy
* Training Loss
* Validation Loss

## Model Architecture

```text
Input Image
      ↓
Resizing & Rescaling
      ↓
Conv2D + MaxPooling
      ↓
Conv2D + MaxPooling
      ↓
Conv2D + MaxPooling
      ↓
Flatten
      ↓
Dense Layer
      ↓
Softmax Output
```

## Example Prediction

Input:

```text
Potato Leaf Image
```

Output:

```text
Potato___Early_blight
```

or

```text
Potato___Late_blight
```

or

```text
Potato___healthy
```

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/reddyhaneesh247/potato-disease-classification.git
cd potato-disease-classification
```

### 2. Open the Notebook

Open the notebook in Google Colab:

```text
Potato_Disease_Prediction.ipynb
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

* Load and preprocess potato leaf images
* Apply image augmentation
* Train the CNN model
* Evaluate model performance
* Generate disease predictions

### 7. Predict Disease Class

The trained model classifies potato leaves into:

* Potato Early Blight
* Potato Late Blight
* Potato Healthy

### Project Structure

```text
potato-disease-classification/
│
├── Potato_Disease_Prediction.ipynb
├── PlantVillage.zip
├── README.md
└── saved_models/
```
### END
