# 🧠 Cancer Prediction using Machine Learning

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge&logo=github&logoColor=white)](https://opensource.org/licenses/MIT)

## 📌 Project Overview
This repository contains a production-grade machine learning classification pipeline to predict whether breast cancer tumors are **malignant** (cancerous, `1`) or **benign** (non-cancerous, `0`).

In clinical machine learning applications, a simple focus on raw accuracy can be dangerous. Missing a cancer diagnosis (**False Negative**) has severe consequences for patient outcomes. Therefore, this project implements a rigorous diagnostic classification workflow that tunes models specifically to prioritize **Recall** and **Area Under the ROC Curve (ROC-AUC)**, ensuring maximum patient safety while maintaining high overall precision.

---

## 🛠️ Key Production Features

* **Data Leakage Protection**: Data preprocessing and feature scaling (`StandardScaler`) are applied post train-test split, fitting strictly on training subsets.
* **Stratified K-Fold Cross Validation**: A 5-fold Stratified cross-validation framework preserves minority and majority class distributions across validation folds.
* **Hyperparameter Tuning via GridSearchCV**: Automated parameter sweeps optimize hyperparameters for multiple classifiers (Random Forest & SVM).
* **Clinical Safety Scoring**: Models are optimized against `recall` and `roc_auc` scoring criteria to minimize false negatives.
* **Advanced Multi-Panel Visualization**: Automatically plots and evaluates models using:
  * Confusion Matrix heatmaps.
  * Receiver Operating Characteristic (ROC) curve & Area Under the Curve (AUC).
  * Precision-Recall (PR) curve & Average Precision (AP) score.
  * Feature Importance analysis (top 10 diagnostic indicators).
* **Model Serialization**: Uses `joblib` to bundle the optimized classifier and the fitted scaler into a single deployable asset.

---

## 📁 Repository Structure
```
cancer-prediction/
├── .gitignore                          # Standard git exclusions for Python/Jupyter
├── README.md                           # Professional project documentation
├── cancer_prediction (1).ipynb         # Production ML pipeline notebook
├── cancer_prediction_pipeline.joblib   # Serialized scaler and model file
└── data (1).csv                        # Breast Cancer Wisconsin (Diagnostic) Dataset
```

---

## ⚙️ Setup & Installation

### 1. Prerequisites
Make sure you have **Python 3.8+** installed.

### 2. Clone the Repository
```bash
git clone https://github.com/jayeshmahajan9923/cancer-prediction.git
cd cancer-prediction
```

### 3. Install Dependencies
Install the required packages using pip:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn joblib
```

---

## 🚀 Usage

1. Launch Jupyter Notebook or JupyterLab:
   ```bash
   jupyter notebook
   ```
2. Open [cancer_prediction (1).ipynb](file:///C:/Users/jayes/Documents/GitHub/cancer-prediction/cancer_prediction%20%281%29.ipynb).
3. Run all cells sequentially.
4. The pipeline will:
   * Perform scaling and encoding.
   * Run GridSearchCV to optimize models.
   * Render diagnostic heatmaps and performance curves.
   * Export the serialized pipeline to `cancer_prediction_pipeline.joblib`.

---

## 📊 Model Comparison & Results

Both models were tuned using 5-fold Stratified K-Fold Cross Validation and evaluated on an independent 20% test subset.

| Classifier | Test Accuracy | Test Precision | Test Recall (Sensitivity) | Test F1-Score | ROC-AUC |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Random Forest (Tuned)** | **97.37%** | **100.00%** | **92.86%** | **96.30%** | **99.50%** |
| **SVM (Tuned)** | **97.37%** | **100.00%** | **92.86%** | **96.30%** | **99.27%** |

### Key Clinical Observations
* **Random Forest** achieved the highest overall **ROC-AUC (99.50%)** and successfully identified 39 out of 42 malignant cases in the test set (92.86% Recall) with 0 false positives (100% Precision).
* **SVM** (once scaled and optimized via GridSearchCV with RBF kernel: `C=10`, `gamma='scale'`) matched the performance of the Random Forest model on the test split, proving the value of feature scaling.

---

## 🚀 Future Enhancements

* **Web Application**: Build a Streamlit or Flask dashboard to let clinicians upload diagnosis metrics and obtain real-time predictions.
* **Deep Learning Model**: Experiment with a Multi-Layer Perceptron (MLP) using PyTorch/TensorFlow.
* **Feature Selection**: Apply recursive feature elimination (RFE) or L1-regularization to reduce model complexity and enhance interpretability.

---

## 👨‍💻 Author
**Jayesh Mahajan**
* GitHub: [@Jayeshmahajan9923](https://github.com/Jayeshmahajan9923)

---

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
