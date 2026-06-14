# ❤️ Heart Failure Prediction using Deep Learning

## 📌 Project Overview

Heart failure is a serious cardiovascular condition that can lead to life-threatening complications if not detected and monitored properly. This project aims to predict the likelihood of a **death event (DEATH_EVENT)** in heart failure patients using clinical records and deep learning techniques.

The project includes comprehensive data preprocessing, exploratory data analysis (EDA), feature scaling, outlier handling, and the implementation of both **Artificial Neural Network (ANN)** and **Recurrent Neural Network (RNN-LSTM)** models. The best-performing model was deployed using **Gradio** to provide an interactive web application for real-time predictions.

Live : https://900e3e112db7da403f.gradio.live/
<img width="1920" height="1560" alt="image" src="https://github.com/user-attachments/assets/754f62cf-ee25-439d-9ad9-4417871bfb3c" />

---

## 📊 Dataset Information

The dataset contains **299 patient records**, 12 clinical features, and 1 target variable.

### Features

| Feature                  | Description                                       |
| ------------------------ | ------------------------------------------------- |
| age                      | Age of the patient                                |
| anaemia                  | Decrease of red blood cells                       |
| creatinine_phosphokinase | CPK enzyme level in blood                         |
| diabetes                 | Presence of diabetes                              |
| ejection_fraction        | Percentage of blood leaving heart per contraction |
| high_blood_pressure      | Presence of high blood pressure                   |
| platelets                | Platelet count in blood                           |
| serum_creatinine         | Serum creatinine level                            |
| serum_sodium             | Serum sodium level                                |
| sex                      | Gender of patient                                 |
| smoking                  | Smoking status                                    |
| time                     | Follow-up period (days)                           |
| DEATH_EVENT              | Target variable                                   |

---

## 🔍 Exploratory Data Analysis (EDA)

The following analyses were performed:

* Dataset inspection and validation
* Missing value detection
* Target class distribution analysis
* Feature-wise visualization against target labels
* Correlation heatmap generation
* Outlier detection using boxplots
* Feature distribution analysis
* Scaling impact visualization

### Key Findings

* Dataset is moderately imbalanced:

  * No Death: 203 samples
  * Death: 96 samples

* Most correlated features with DEATH_EVENT:

  * Time (0.53)
  * Serum Creatinine (0.29)
  * Ejection Fraction (0.27)

* Significant outliers were observed in:

  * Creatinine Phosphokinase
  * Ejection Fraction
  * Platelets
  * Serum Creatinine
  * Serum Sodium

---

## ⚙️ Data Preprocessing

### Steps Performed

* Train-Test Split (80:20)
* Standardization using StandardScaler
* Outlier treatment using mean replacement
* Feature transformation and normalization
* Visualization of distributions before and after scaling

---

## 🤖 Deep Learning Models

### 1️⃣ Artificial Neural Network (ANN)

#### Architecture

* Dense Layer (32 neurons, ReLU)

* Batch Normalization

* Dropout (0.3)

* Dense Layer (16 neurons, ReLU)

* Batch Normalization

* Dropout (0.3)

* Output Layer (1 neuron, Sigmoid)

#### Training Configuration

* Optimizer: Adam
* Loss Function: Binary Crossentropy
* Metric: Accuracy
* Epochs: 50
* Batch Size: 32
* Validation Split: 20%

#### Performance

The ANN model demonstrated strong learning capability with stable convergence.

* Validation Accuracy: ~81%
* Validation Loss: ~0.43

---

### 2️⃣ Recurrent Neural Network (RNN - LSTM)

#### Architecture

* LSTM Layer (64 units)

* Batch Normalization

* Dropout (0.3)

* LSTM Layer (32 units)

* Batch Normalization

* Dropout (0.3)

* Dense Output Layer (1 neuron, Sigmoid)

#### Training Configuration

* Optimizer: Adam
* Loss Function: Binary Crossentropy
* Metric: Accuracy
* Epochs: 50
* Batch Size: 32
* Validation Split: 20%

#### Test Performance

* Test Accuracy: 58.33%
* Test Loss: 0.6918

#### Observations

The RNN model suffered from class imbalance issues and failed to correctly identify positive death-event cases.

Classification Results:

| Class        | Precision | Recall | F1 Score |
| ------------ | --------- | ------ | -------- |
| No Death (0) | 0.58      | 1.00   | 0.74     |
| Death (1)    | 0.00      | 0.00   | 0.00     |

The confusion matrix showed that the model predicted every sample as "No Death", indicating severe bias toward the majority class.

---

## 🌐 Deployment

The ANN model was deployed using **Gradio** to provide an easy-to-use web interface.

### Features

* Real-time predictions
* User-friendly input fields
* Probability score output
* Interactive clinical decision support

Users can enter patient information and instantly receive:

* Death Event Prediction
* Probability Score

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* TensorFlow / Keras
* Gradio

---

## 📈 Results Summary

| Model      | Accuracy                 | Status            |
| ---------- | ------------------------ | ----------------- |
| ANN        | ~81% Validation Accuracy | ✅ Best Performing |
| RNN (LSTM) | 58.33% Test Accuracy     | ⚠️ Underperformed |

---

## 🎯 Conclusion

This project demonstrates an end-to-end deep learning pipeline for heart failure survival prediction. While the ANN model achieved promising results and was successfully deployed, the RNN model struggled due to class imbalance and failed to generalize effectively on minority-class predictions.

Future improvements may include:

* SMOTE oversampling
* Class weighting
* Hyperparameter tuning
* Ensemble learning
* Advanced deep learning architectures

These enhancements could significantly improve prediction performance and robustness for real-world clinical applications.

---
