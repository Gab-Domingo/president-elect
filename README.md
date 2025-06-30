# 🗳️ Presidential Election Predictor (Logistic Regression)

This project uses logistic regression to predict whether a presidential candidate would win or lose based on historical features such as education, experience, and public profile. It serves as a practice project for applying machine learning techniques to real-world decision-making scenarios.

---

## 📂 Project Overview

Using a dataset of past Philippine presidential candidates, this project:

- Preprocesses a mix of categorical and numeric features
- Trains a logistic regression model for binary classification (Win vs Not Win)
- Accepts new candidate profiles to simulate outcomes
- Calculates both binary predictions and win probabilities
- Simulates competitive elections by normalizing probabilities to vote shares

---

## 📈 Features Used

- `sex` (binary: 1 = Male, 0 = Female)
- `alma_mater` (ordinal-coded)
- `last_college_attended` (categorical)
- `degree_obtained` (categorical)
- `hi_educ_attain` (categorical)
- `last_job` (categorical: e.g., Senator, Vice President, Mayor)
- `no_of_govt_positions_served` (int)
- `served_in_gov't` (binary)
- `years_of_service` (float)

---

## 🔍 Model

- **Algorithm**: Logistic Regression
- **Pipeline**:
  - Missing value imputation
  - One-hot and ordinal encoding
  - Scaling numeric features
- **Performance**: Achieved ~91% accuracy on validation data

---

## 📊 Usage Example

Input a new candidate profile:

```python
possible_candidate = pd.DataFrame([
    {
        "sex": 1,
        "alma_mater": 2,
        "last_college_attended": "San Beda College",
        "degree_obtained": "Law",
        "hi_educ_attain": "College",
        "last_job": "Mayor",
        "no_of_govt_positions_served": 5,
        "served_in_gov't": 1,
        "years_of_service": 30
    }
])

prediction = pipeline.predict(possible_candidate)
probability = pipeline.predict_proba(possible_candidate)[:, 1]
