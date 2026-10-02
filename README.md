# CNN-Based Multi-Class Flower Recognition

A Convolutional Neural Network (CNN) project for identifying and classifying flowers from the **ColoredFlowersBD** dataset.

## Project Overview

This project uses a custom Convolutional Neural Network to classify images into **13 different flower classes** found in the ColoredFlowersBD dataset.

The complete workflow includes:

* Dataset download and extraction
* Exploratory Data Analysis (EDA)
* Image checking and cleaning
* Duplicate image detection
* Train, validation, and test splitting
* Image resizing and normalization
* Data augmentation
* CNN model development
* Model training with EarlyStopping
* Model evaluation
* Classification report
* Confusion matrix
* Accuracy and loss visualization

## Dataset

The project uses the **ColoredFlowersBD** dataset(https://www.kaggle.com/datasets/jocelyndumlao/colored-flowers-in-bangladesh), which contains flower images from Bangladesh.

The dataset contains 13 flower classes:

1. Chandramallika
2. Cosmos Phul
3. Gada
4. Golap
5. Jaba
6. Kagoj Phul
7. Noyontara
8. Radhachura
9. Rangan
10. Salvia
11. Sandhyamani
12. Surjomukhi
13. Zinnia

Dataset source:

**Kaggle:** Colored Flowers in Bangladesh

## Data Preprocessing

The following preprocessing steps were used:

* Images were resized to **224 × 224 pixels**.
* Pixel values were normalized from **0–255 to 0–1**.
* The dataset was divided into:

  * **80% Training**
  * **10% Validation**
  * **10% Testing**
* Training data used data augmentation.
* Validation and test data were not augmented.
* A random seed of **42** was used for reproducibility.

### Data Augmentation

The training data uses:

* Random horizontal flipping
* Random rotation
* Random zoom

## CNN Architecture

A custom CNN architecture was developed using TensorFlow/Keras.

```text
Input: 224 × 224 × 3
        ↓
Conv2D: 32 filters
        ↓
MaxPooling
        ↓
Conv2D: 64 filters
        ↓
MaxPooling
        ↓
Conv2D: 128 filters
        ↓
MaxPooling
        ↓
Global Average Pooling
        ↓
Dense: 128 neurons
        ↓
Dropout: 0.5
        ↓
Dense: 13 classes
        ↓
Softmax
```

### Model Configuration

* **Optimizer:** Adam
* **Loss function:** Sparse Categorical Cross-Entropy
* **Metric:** Accuracy
* **Epochs:** Up to 20
* **EarlyStopping:** Used with validation loss
* **Input size:** 224 × 224 × 3
* **Output classes:** 13

## Model Evaluation

The model was evaluated using the test dataset.

The following evaluation methods were used:

* Test accuracy
* Test loss
* Classification report
* Confusion matrix
* Training and validation accuracy curves
* Training and validation loss curves

## Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab
* Kaggle Dataset

## Project Structure

```text
flower-classification-cnn/
│
├── flower_classification_cnn.ipynb
├── README.md
└── .gitignore
```

## How to Run

### 1. Open the notebook

Open:

```text
flower_classification_cnn.ipynb
```

using **Google Colab** or Jupyter Notebook.

### 2. Install the required libraries

The notebook uses TensorFlow, NumPy, Matplotlib, Seaborn, PIL, and Scikit-learn.

### 3. Download the dataset

The notebook downloads the ColoredFlowersBD dataset from Kaggle.

### 4. Run the notebook

Run the cells sequentially to:

1. Download the dataset
2. Extract and inspect the dataset
3. Perform preprocessing
4. Split the data
5. Create the CNN
6. Train the model
7. Evaluate the model
8. Generate the classification report
9. Generate the confusion matrix

## Future Improvements

Possible future improvements include:

* Hyperparameter tuning
* Transfer learning using pretrained CNN models
* Comparing different CNN architectures
* Improving model accuracy
* Deploying the trained model as a web application
* Adding an image-upload interface for real-time flower prediction

## Author

**Tuhin**

This project was developed as a CNN learning and image-classification project.
