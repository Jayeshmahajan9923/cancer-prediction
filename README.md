🧠 Cancer Prediction using Machine Learning

📌 About the Project

This project focuses on predicting whether a tumor is malignant (cancerous) or benign (non-cancerous) using machine learning techniques.

The main goal was not just to build a model, but to understand how machine learning can assist in real-world medical decision making, where even small mistakes can have serious consequences.

---

📊 Dataset

I used the Breast Cancer dataset which contains features like:

- Radius
- Texture
- Area
- Perimeter
- Smoothness, etc.

The target variable is:

- M (Malignant) → Cancer
- B (Benign) → Non-cancer

---

⚙️ Technologies Used

- Python
- Pandas & NumPy
- Scikit-learn
- Matplotlib / Seaborn

---

🤖 Models Implemented

- Random Forest Classifier ✅
- Support Vector Machine (SVM)

I experimented with multiple models to understand which works better for this problem.

---

📈 Results & Observations

🔹 Random Forest

- Accuracy: 96.5%
- False Negatives: 3

🔹 SVM

- Accuracy: 94.7%
- False Negatives: 6

👉 Even though both models performed well, Random Forest gave better results, especially in reducing false negatives.

---

🧠 Key Learning

One of the biggest takeaways from this project:

«In medical applications, reducing false negatives is more important than just achieving high accuracy.»

Missing a cancer case can be dangerous, so model evaluation should focus on recall, not just accuracy.

---

## 🔗 View Notebook

You can view the complete notebook with outputs here:

https://nbviewer.org/github/Jayeshmahajan9923/cancer-prediction/blob/main/cancer_prediction%20%281%29.ipynb

---

▶️ How to Run

1. Clone the repository

git clone https://github.com/jayeshmahajan9923/cancer-prediction.git

2. Open the notebook in Jupyter

3. Run all cells step by step

---

🚀 Future Improvements

- Hyperparameter tuning using GridSearchCV
- Feature importance analysis
- Building a simple web app (Flask/Streamlit)

---

👨‍💻 Author

JAYESH MAHAJAN

---

🙌 Final Note

This project helped me understand not just machine learning algorithms, but also how to think critically about model performance in real-world scenarios.

