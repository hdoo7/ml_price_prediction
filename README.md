# Rent Price Prediction Project

## Overview
This project aims to predict rent prices using machine learning models. It involves:
1. Retrieving datasets from Google Drive.
2. Cleaning and engineering features from the data.
3. Training and evaluating multiple regression models.
4. Making price predictions on a test dataset.

## Table of Contents
1. [Getting Started](#getting-started)
2. [Feature Engineering](#feature-engineering)
3. [Model Training](#model-training)
4. [Model Inference](#model-inference)
5. [Results](#results)

---

## Getting Started
To run this project:
1. Install the required Python libraries:
   ```bash
   pip install -r requirements.txt
   ```
2. Clone or download the repository to your local machine.
  ```bash
  git clone https://github.com/hdoo7/ml_tech_assessment.git
  cd ml_tech_assessment
  ```
---

## Feature Engineering
Key steps in preparing the dataset:
1. **Data Cleaning**:
   - Drop rows with missing values in critical columns (`description`, `sqfeet`, and `price`).
   - Log the data size before and after cleaning.
2. **Feature Creation**:
   - `desc_length`: Character count in the `description`.
   - `price_per_sqft`: Price divided by `sqfeet`.
3. **Encoding Categorical Variables**:
   - Convert categorical columns like `region`, `type`, etc., into dummy variables.
4. **Target Transformation**:
   - Use the natural log of the target variable (`price`) to normalize the distribution.

---

## Model Training
Three models are trained and evaluated:
1. **Gradient Boosting Regressor (GB)**.
2. **K-Nearest Neighbors Regressor (KNN)**.
3. **Random Forest Regressor (RF)**.

### Training Steps
1. Split the data into training and validation sets using an 80/20 ratio.
2. Handle missing values with `SimpleImputer`.
3. Scale features using `StandardScaler`.

### Evaluation Metrics
Each model is evaluated on the validation set using the following metrics:
- **Mean Absolute Error (MAE)**.
- **Root Mean Squared Error (RMSE)**.
- **R² Score**.

---

## Model Inference
The trained models are used to predict prices on the test dataset. Key steps:
1. **Clean and Align Test Data**:
   - Apply the same cleaning and feature engineering steps as the training data.
   - Ensure feature alignment between training and test datasets.
2. **Make Predictions**:
   - Predict `price` using each model.
   - Transform predictions back from the log scale.
3. **Evaluate Predictions**:
   - Compare predictions with the ground truth using the same metrics.

---

## Results
Sample predictions and model performance metrics are displayed.

### Sample Test Set Results:
| Model               | MAE    | RMSE        |  R²     |
|---------------------|--------|-------------|---------|
| KNN                 | 71,996 | 14048287.57 |  0.0086 |
| Gradient Boosting   | 71,958 | 14059007.62 |  0.0071 |
| Random Forest       | 71,944 | 14072663.73 |  0.0052 |

---

## Conclusion
This project demonstrates a complete pipeline for predicting rent prices, including data collection, preprocessing, model training, and evaluation. The comparison of multiple models provides insights into their relative performance on the provided datasets.
```
