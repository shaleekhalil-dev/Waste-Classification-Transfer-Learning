# ♻️ Waste Classification Using Transfer Learning (VGG16)

[![IBM Advanced Deep Learning Specialist](https://img.shields.io/badge/Credential-IBM%20Advanced%20Deep%20Learning%20Specialist-blue)](https://www.coursera.org/)
[![Python](https://img.shields.io/badge/Python-3.12-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.17.0-orange.svg)](https://www.tensorflow.org/)

## 📌 Project Overview
EcoClean and similar waste management systems often rely on manual sorting, which is labor-intensive, error-prone, and leads to the contamination of recyclable materials. 

This project aims to automate the waste classification process using Machine Learning and Computer Vision. By leveraging **Transfer Learning** with a pre-trained **VGG16** model, this system accurately classifies images of waste into two distinct categories:
*   **Organic Waste (O)**
*   **Recyclable Waste (R)**

*This project was completed as the final capstone for the **IBM Advanced Deep Learning Specialist** professional certificate.*

## 🛠️ Technology Stack
*   **Languages:** Python
*   **Deep Learning Framework:** TensorFlow / Keras
*   **Pre-trained Model:** VGG16 (ImageNet weights)
*   **Data Processing & Evaluation:** NumPy, Scikit-learn
*   **Data Visualization:** Matplotlib

## 🧠 Methodology

The project was executed in several stages to ensure optimal model performance:

### 1. Data Preprocessing & Augmentation
*   Used `ImageDataGenerator` to load and augment images on the fly.
*   Applied techniques like rescaling, width/height shifts, and horizontal flipping to make the model robust against varied inputs.

### 2. Phase 1: Feature Extraction
*   Loaded the **VGG16** base model without the top classification layers (`include_top=False`).
*   **Froze** all base model layers to retain the generic visual features learned from ImageNet.
*   Added custom dense layers with Dropout regularization on top.
*   Trained the model using early stopping to prevent overfitting.

### 3. Phase 2: Fine-Tuning
*   To squeeze out more performance, **Fine-Tuning** was applied.
*   Unfroze the last convolutional block of the VGG16 base model (`block5_conv3`).
*   Re-compiled the model with a very low learning rate (`RMSprop(1e-4)`) to subtly adjust the pre-trained weights to our specific waste dataset.

## 📊 Results & Evaluation
Both the Feature Extraction model and the Fine-Tuned model were evaluated on unseen test data.

*   **Training vs. Validation Curves:** Monitored using accuracy and loss plots to ensure the model was generalizing well.
*   **Classification Report:** Generated using `scikit-learn` to calculate Precision, Recall, and F1-score for both classes.

*(Note: Add your `plot_accuracy_curve.png` and `plot_loss_curve.png` in the repository and display them here)*

## 🚀 How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/shaleekhalil-dev/Waste-Classification-Transfer-Learning.git
   ```
2. Install the required dependencies:
   ```bash
   pip install tensorflow==2.17.0 numpy==1.26.4 scikit-learn==1.5.1 matplotlib==3.9.2
   ```
3. Run the Jupyter Notebook `Final Proj-Classify Waste Products Using TL FT.ipynb` to see the step-by-step implementation.

## 👨‍💻 Author
**Shali Khalil** ([@shaleekhalil-dev](https://github.com/shaleekhalil-dev))
