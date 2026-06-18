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
