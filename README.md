# 🦠 Malaria Cell Image Classification with CNN

A deep learning image classification project for distinguishing **Parasitized** and **Uninfected** malaria cell images using a Convolutional Neural Network (CNN).

The project demonstrates a complete image classification workflow, from image loading and preprocessing to CNN training, validation, and model saving.

## Project Objective

The objective of this project is to classify microscopic cell images into two categories:

- **Parasitized** — cells containing malaria parasites
- **Uninfected** — healthy cells without malaria parasites

The dataset contains approximately **27,558 cell images**.

## 🔬 Dataset

The project uses the NIH malaria cell image dataset, which is also available through public mirrors such as Kaggle.

The dataset itself is not included in this repository.

The notebook was developed in **Google Colab**, with the image dataset accessed through Google Drive.

## Project Workflow

```text
Malaria Cell Images
        ↓
Image Loading
        ↓
Label Encoding
        ↓
Image Resizing
        ↓
Normalization
        ↓
CNN Model
        ↓
Training & Validation
        ↓
Classification Results
```

## Image Preprocessing

Before training, the images are prepared as follows:

- Images are read using OpenCV
- Images are resized to **32 × 32 pixels**
- Pixel values are normalized by dividing by `255.0`
- Class labels are encoded numerically
- Processed images and labels are converted into NumPy arrays

Class encoding:

```text
Parasitized = 0
Uninfected  = 1
```

## 🧠 CNN Architecture

The model is built using TensorFlow / Keras with a Sequential CNN architecture.

```text
Input Image (32 × 32 × 3)
        ↓
Conv2D — 32 filters, 3×3, ReLU
        ↓
MaxPooling2D
        ↓
Conv2D — 64 filters, 3×3, ReLU
        ↓
MaxPooling2D
        ↓
Flatten
        ↓
Dense — 128 units, ReLU
        ↓
Dropout — 0.5
        ↓
Dense — 2 units, Softmax
```

The model is compiled with:

```text
Optimizer: Adam
Loss: Sparse Categorical Crossentropy
Metric: Accuracy
```

## Training

The CNN was trained with:

- **Epochs:** 10
- **Batch Size:** 32
- **Validation Split:** 20%

## Results

After 10 training epochs, the model achieved:

| Metric | Result |
| --- | ---: |
| Training Accuracy | **96.79%** |
| Validation Accuracy | **96.50%** |
| Training Loss | **0.0899** |
| Validation Loss | **0.1195** |

The results show that the CNN was able to learn useful visual patterns for distinguishing parasitized and uninfected cell images.

These values are based on the notebook's validation split and should be interpreted as project-level results rather than clinical performance.

## Technologies

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- OpenCV
- Matplotlib
- Jupyter Notebook / Google Colab
- Convolutional Neural Networks

## Project Structure

```text
deep-learning-malaria-detection/
│
├── malaria_cnn_image_classification.ipynb
└── README.md
```

### `malaria_cnn_image_classification.ipynb`

Contains the complete workflow including:

- Dataset access
- Image visualization
- Data preparation
- Label encoding
- Image preprocessing
- CNN construction
- Model training
- Validation
- Model saving

## Model Output

The trained model is saved in the notebook as:

```text
my_m_cnn_model.h5
```

## Project Purpose

This project demonstrates practical experience with:

- Deep Learning
- Medical Image Classification
- Convolutional Neural Networks
- Image Preprocessing
- TensorFlow / Keras
- Model Training and Validation
- Computer Vision workflows

It was developed as an educational and portfolio project.

## Disclaimer

This project is intended for **educational and demonstration purposes only**.

It is not a medical diagnostic system and should not be used for clinical decision-making.

---

*From microscopic cell images to meaningful patterns — this project shows how deep learning can turn visual data into structured predictions.*
