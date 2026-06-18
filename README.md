# Automated-Waste-Classification-using-CNN

## Overview

This project implements a Convolutional Neural Network (CNN) for automated waste classification. The model is trained to categorize waste images into six classes, enabling efficient waste sorting and supporting recycling and waste management initiatives.

The system leverages TensorFlow and Keras for model development, training, and inference, and is designed to classify waste materials from images with high accuracy.

---

## Objectives

- Automate waste classification using deep learning.
- Reduce manual effort in waste sorting processes.
- Improve recycling efficiency through accurate material identification.
- Demonstrate the application of computer vision in environmental sustainability.

---

## Dataset

The model is trained on an image dataset containing six waste categories:

| Class |
|---------|
| Cardboard |
| Glass |
| Metal |
| Paper |
| Plastic |
| Trash |

Dataset images are automatically loaded and split into training and validation sets using TensorFlow's dataset utilities.

---

## Model Architecture

The classification model is built using a Convolutional Neural Network (CNN) architecture implemented with TensorFlow and Keras.

Key components include:

- Convolutional layers for feature extraction
- Pooling layers for dimensionality reduction
- Regularization techniques to reduce overfitting
- Dense layers for classification
- Softmax output layer for multi-class prediction

The model is trained on resized images of:

```text
256 × 256 pixels
```

---

## Technologies Used

### Programming Language

- Python

### Deep Learning Frameworks

- TensorFlow
- Keras

### Image Processing

- OpenCV
- NumPy

### Development Environment

- Google Colab
- Jupyter Notebook

---

## Project Structure

```text
.
├── CNN_AWS.ipynb
├── final_model.keras
├── train/
│   ├── Cardboard/
│   ├── Glass/
│   ├── Metal/
│   ├── Paper/
│   ├── Plastic/
│   └── trash/
└── predb/
    └── test_images
```

---

## Training Pipeline

### 1. Dataset Loading

Images are loaded from the training directory using TensorFlow's image dataset API.

```python
tf.keras.utils.image_dataset_from_directory()
```

Features:

- Automatic label generation
- Batch processing
- Train-validation split
- Efficient data loading

---

### 2. Image Preprocessing

The dataset undergoes preprocessing including:

- Image resizing to 256 × 256
- Batch creation
- Data normalization
- Dataset shuffling

---

### 3. Model Training

The model is trained using:

- Early Stopping
- Learning Rate Reduction
- Validation monitoring

Callbacks used:

```python
EarlyStopping
ReduceLROnPlateau
```

These techniques help improve generalization and prevent overfitting.

---

### 4. Model Saving

After training, the model is saved in Keras format:

```text
final_model.keras
```

This allows the trained model to be reused for inference without retraining.

---

## Inference Pipeline

The trained model can classify new waste images by:

1. Loading the saved model.
2. Reading input images.
3. Preprocessing images.
4. Performing predictions.
5. Returning the predicted waste category.

Example prediction classes:

```python
class_names = [
    'Cardboard',
    'Glass',
    'Metal',
    'Paper',
    'Plastic',
    'trash'
]
```

---

## Running the Project

### Clone the Repository

```bash
git clone https://github.com/yourusername/waste-classification-cnn.git

cd waste-classification-cnn
```

### Install Dependencies

```bash
pip install tensorflow
pip install opencv-python
pip install numpy
```

### Train the Model

Run the notebook:

```bash
jupyter notebook CNN_AWS.ipynb
```

Execute all cells to train and save the model.

---

## Making Predictions

Load the trained model:

```python
from tensorflow.keras.models import load_model

model = load_model("final_model.keras")
```

Predict on new images:

```python
prediction = model.predict(image)
```

The output corresponds to one of the predefined waste categories.

---

## Applications

### Smart Waste Management

Automated classification of waste materials before disposal.

### Recycling Facilities

Improved sorting efficiency for recyclable materials.

### Environmental Monitoring

Support sustainable waste handling practices.

### Educational Projects

Demonstrate practical applications of computer vision and deep learning.

---

## Future Improvements

- Expand dataset size for improved accuracy.
- Introduce additional waste categories.
- Deploy as a web application.
- Develop a mobile application for real-time classification.
- Integrate object detection for multiple waste items in a single image.
- Deploy the model using cloud services for scalable inference.

---

## Results

The trained CNN successfully classifies waste images into six categories:

- Cardboard
- Glass
- Metal
- Paper
- Plastic
- Trash

The system demonstrates the effectiveness of deep learning techniques for automated waste classification and sustainable waste management solutions.

---

## License

This project is licensed under the MIT License.

---

## Author

Developed as a deep learning project for image-based waste classification using TensorFlow and Keras.
