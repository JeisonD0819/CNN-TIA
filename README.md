# 🏭 Quality Classification of Ceramic Tiles using Deep Learning (DNN & CNN)

![Python](https://img.shields.io/badge/Python-3.x-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-ML-green)
![CNN](https://img.shields.io/badge/Model-CNN-orange)
![DNN](https://img.shields.io/badge/Model-DNN-yellow)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Overview

This project was developed as the final assignment for the course **Artificial Intelligence Techniques** at Universidad Nacional de Colombia.

The objective is to build a classification system capable of predicting the quality of ceramic tiles based on industrial process variables from three production stages:

- Pressing
- Drying
- Baking (kiln)

Each data sample is labeled as:

- **First (Primera)** → meets quality standards  
- **Scrap (Retal)** → does not meet quality standards  

---

## 🎯 Objective

The objective of this project is to develop a classifier system for the quality of ceramic tiles, from three different
operation variables in three industrial process stages. This stages are Pressing, Drying and Baking. The data given contains
measurements of each stage in a time frame of hours, with an additional register of the batch quality divided in two
categories: First and Scrap. 

Getting more in depth, the first step taken was to do an Exploratory Data Analysis [EDA], followed by the modeling
of two Neural Networks; a Dense Neural Network (DNN) and a Convolutional Neural Network (CNN). These models
would be optimized by a given set of HyperParameters, and then evaluated by performance, comparing the best metrics
obtained by each network.

---

## 📊 Dataset

- Source: [`Ceramic_process_QC.xlsx`](./Ceramic_process_QC.xlsx)
- Sheets included:
  - `prensas`
  - `secadero`
  - `horno`
  - `calidad`

### 🧹 Data Preprocessing

The preprocessing pipeline included:

- Removal of non-informative time-related columns  
  (`fecha`, `hora`, `hora_sensor`)
  
- Frequency unification:
  - Some variables were recorded every **30 minutes**
  - Others every **hour**
  - Data was aggregated to a consistent hourly resolution

- Construction of **time windows** to capture temporal behavior of the process

- Feature normalization to improve model performance

---

## 🔍 Exploratory Data Analysis (EDA)

The dataset was analyzed to:

- Understand variable distributions  
- Identify correlations between process variables  
- Detect relevant features influencing product quality  

---

## 🤖 Models

### 🧠 Dense Neural Network (DNN)

A fully connected neural network was implemented and optimized by tuning:

- Number of hidden layers  
- Number of neurons per layer  
- Learning rate  

---

### 🧩 Convolutional Neural Network (CNN)

A CNN was designed to capture structured patterns in the data using:

- Convolutional layers with different kernels  
- Pooling strategies (Max / Average pooling)  
- Fully connected layers  
- Learning rate tuning  

> The CNN leverages the structured representation of process data to extract higher-level features.

---

## 📈 Evaluation

Both models were evaluated using:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- Confusion Matrix  

Additionally:

- **3-fold cross-validation** was applied to ensure robustness

---

## 📊 Results

The models were compared based on their classification performance.

- The **CNN showed better capability** in capturing complex patterns in the process data  
- Hyperparameter tuning significantly improved both models  

### 🔍 Model Comparison

| Metric     | DNN Model 1 | DNN Model 2 |
|------------|------------|------------|
| Accuracy   | 0.9470     | 0.9545     |
| Precision  | 0.9470     | 0.9545     |
| Recall     | 1.0000     | 1.0000     |
| F1-score   | 0.9728     | 0.9542     |

### 📌 Key Observations

- Both models achieved **perfect recall (1.0)**, meaning all positive samples were correctly identified.
- The second model slightly improved **accuracy and precision**.
- The first model achieved a higher **F1-score**, indicating a slightly better balance between precision and recall.
  
---

## 📂 Repository Structure

- 📓 [`Proyecto Final.ipynb`](./Proyecto%20Final.ipynb) → Full implementation (EDA, preprocessing, models, evaluation)  
- 📊 [`Ceramic_process_QC.xlsx`](./Ceramic_process_QC.xlsx) → Raw dataset  
- 📄 [`Informe_Final.pdf`](./Informe_Final.pdf) → Detailed technical report  

---

## 🚀 How to Run

1. Open the notebook in Google Colab or Jupyter Notebook  
2. Install required libraries:
   - torch  
   - numpy  
   - scikit-learn  
   - matplotlib  
   - seaborn  

---

## 📎 Conclusions

- Data quality proved to be a decisive factor in model performance. The results confirmed that predictions are strongly influenced by how the data are distributed and represented.

- Due to class imbalance in the dataset, the models showed a tendency to classify most samples as **first-class**, which is consistent with the predominance of this category in the training data.

- The assumption used to define classes (tiles with more than 50% of their surface in good condition classified as first-class) introduced additional bias. By not clearly separating *second-class* and *retal*, relevant information was lost, and this bias was propagated during prediction.

- Improving dataset quality and achieving better class balance would likely lead to more accurate and reliable models.

- From a training perspective, the use of **cross-entropy loss** was appropriate for the classification task, allowing effective measurement of the difference between predicted and true labels.

- The **Adam optimizer** contributed to stable and efficient convergence by dynamically adjusting the learning rate, improving overall training performance.

- In terms of model comparison, the **CNN achieved performance comparable to the DNN**. This is consistent with the nature of the data, as temporal dependencies between consecutive samples allowed the CNN to capture structured patterns.

- However, the difference in performance between both models was not significant, indicating that both approaches are valid for this type of problem.
---

## 👨‍💻 Authors

- Jeison Nicolas Diaz Arciniegas  
- David Santiago Nagles Barajas  
- Miguel Antonio Parrado Pardo  

**Course:** Artificial Intelligence Techniques  
**Professor:** Jorge Ivan Sofrony  
**Universidad Nacional de Colombia**
