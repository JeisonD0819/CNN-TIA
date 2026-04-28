# 🏭 Quality Classification of Ceramic Tiles using Deep Learning (DNN & CNN)

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

To design and compare deep learning models that can accurately classify tile quality using process data, optimizing their performance through hyperparameter tuning.

---

## 📊 Dataset

- Source: `Ceramic_process_QC.xlsx`
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

*(You can include exact metrics here if desired)*

---

## 📂 Repository Structure

- `Proyecto Final.ipynb` → Full implementation (EDA, preprocessing, models, evaluation)  
- `Ceramic_process_QC.xlsx` → Raw dataset  
- `Informe_Final.pdf` → Detailed technical report  

---

## 🚀 How to Run

1. Open the notebook in Google Colab or Jupyter Notebook  
2. Install required libraries:
   - pandas  
   - numpy  
   - tensorflow / keras  
   - scikit-learn  
   - matplotlib / seaborn  

---

## 📎 Conclusions

- Industrial process variables contain meaningful patterns for quality prediction  
- Deep learning models can successfully model these relationships  
- Temporal structuring (time windows) plays an important role in performance  
- CNN architectures can outperform traditional dense networks in structured data scenarios  

---

## 👨‍💻 Authors

- Jeison Nicolas Diaz Arciniegas  
- David Santiago Nagles Barajas  
- Miguel Antonio Parrado Pardo  

**Course:** Artificial Intelligence Techniques  
**Professor:** Jorge Ivan Sofrony  
**Universidad Nacional de Colombia**
