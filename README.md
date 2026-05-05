# 🧠 Fake Job Detection System (NLP + Machine Learning)

## 📌 Overview

This project is an end-to-end **Fake Job Detection System** that uses **Natural Language Processing (NLP)** and **Machine Learning** to classify job postings as **Fraudulent** or **Genuine**.

The system analyzes job descriptions and identifies deceptive patterns to help protect job seekers from scams.

---

## 📂 Dataset

The dataset used is the **EMSCAD (Employment Scam Aegean Dataset)**, commonly available on Kaggle as:

> **"Real or Fake: Fake Job Postings Prediction"**

* Total records: ~17,000 job postings
* Target variable:

  * `0` → Genuine Job
  * `1` → Fraudulent Job

### 🧾 Key Features

* Text Data: `title`, `description`, `requirements`, `benefits`, `company_profile`
* Metadata: `location`, `industry`, `employment_type`, etc.

---

## ⚙️ Project Pipeline

### 1️⃣ Data Preprocessing

* Removed irrelevant columns (`job_id`, `salary_range`)
* Handled missing values
* Merged multiple text fields into a single column
* Cleaned text:

  * Lowercasing
  * Removing HTML tags, URLs, punctuation
  * Stopword removal
  * Lemmatization

---

### 2️⃣ Feature Engineering

* Converted text into numerical features using **TF-IDF Vectorization**
* Limited features to top 5000 terms for efficiency

---

### 3️⃣ Model Building

Three models were trained and compared:

| Model               | Purpose                        |
| ------------------- | ------------------------------ |
| Logistic Regression | Baseline model                 |
| Random Forest       | Ensemble learning              |
| XGBoost             | Boosting-based optimized model |

* Used **GridSearchCV** for hyperparameter tuning
* Focused on improving **precision and recall**

---

### 4️⃣ Model Evaluation

Evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

---

### 5️⃣ Feature Importance

* Extracted top contributing words using Random Forest
* Visualized most influential features

---

### 6️⃣ Deployment Ready

* Saved trained model using **Joblib**
* Saved TF-IDF vectorizer
* Built a prediction function for real-time inference

---

## 🚀 How It Works

1. Input: Raw job posting text
2. Text preprocessing & cleaning
3. TF-IDF transformation
4. Model prediction
5. Output:

   * ✅ Genuine Job
   * ❌ Fraudulent Job

---

## 🧪 Example

```python
predict_job("Earn money quickly with no experience required!!!")
```

**Output:**

```
Fraudulent Job
```

---

## 🛠️ Tech Stack

* Python
* Pandas, NumPy
* NLTK
* Scikit-learn
* XGBoost
* Matplotlib, Seaborn
* Joblib

---

## 📊 Results

* Achieved high classification performance (~97% accuracy)
* Improved fraud detection precision using ensemble models
* XGBoost and Random Forest outperformed baseline model

---

## 🔍 Challenges & Solutions

### ⚠️ Class Imbalance

* Fraudulent jobs are fewer than real jobs
* Solution: Used `class_weight='balanced'`

---

### ⚠️ Noisy Text Data

* Handled using robust preprocessing techniques

---

## 🌍 Real-World Applications

* Job portals (LinkedIn, Indeed)
* Recruitment platforms
* Freelance marketplaces
* HR analytics systems

---

## 🔮 Future Improvements

* Use **BERT / Transformer models** for better contextual understanding
* Deploy using **Flask / FastAPI**
* Integrate real-time job scraping
* Add anomaly detection for new fraud patterns

---

## 📌 Conclusion

This project demonstrates the ability to:

* Build an end-to-end NLP pipeline
* Handle real-world noisy text data
* Compare multiple ML models effectively
* Optimize and deploy machine learning solutions

---

## 🤝 Contributing

Feel free to fork this repository and improve the model or add deployment features.

---

## 📜 License

This project is open-source and available under the MIT License.
