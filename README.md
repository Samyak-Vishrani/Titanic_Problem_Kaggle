# 🚢 Titanic Survival Prediction – Machine Learning Project

## 📌 Problem Statement

The objective of this project is to build a machine learning model that predicts whether a passenger survived the Titanic disaster based on structured features such as:

* Passenger class (Pclass)
* Sex
* Age
* Fare
* Number of siblings/spouses aboard (SibSp)
* Number of parents/children aboard (Parch)
* Port of embarkation (Embarked)

This is a **binary classification problem**, where the target variable `Survived` takes values:

* `1` → Survived
* `0` → Did Not Survive

The dataset contains both **numerical and categorical features**, along with missing values, requiring appropriate preprocessing before model training.

---

## 📂 Project Structure

```
submission.ipynb      → Baseline implementation
submission_02.ipynb   → Structured ML pipeline with cross-validation
```

---

## 🔹 Approach 1 – Baseline Implementation (`submission.ipynb`)

This notebook implements a straightforward modeling workflow:

* Exploratory Data Analysis (EDA)
* Data cleaning and missing value handling
* Manual encoding of categorical variables
* Basic train-test split
* Model training and prediction
* Submission file generation

This approach establishes a working solution with fundamental preprocessing and evaluation steps.

---

## 🔹 Approach 2 – Structured ML Pipeline (`submission_02.ipynb`)

The workflow was refactored into a more scalable and reproducible pipeline-based implementation.

### Key Components

### 1️⃣ Preprocessing

* `ColumnTransformer` used to handle:

  * Numerical features separately
  * Categorical features separately
* `SimpleImputer`

  * Median strategy for numerical features
  * Most frequent strategy for categorical features
* `OneHotEncoder`

  * Encodes categorical variables
  * Handles unseen categories during inference

---

### 2️⃣ Model Training

* Integrated preprocessing and model inside a single `Pipeline`
* Used classifiers such as:

  * Logistic Regression
  * Random Forest

---

### 3️⃣ Model Evaluation

* Implemented `StratifiedKFold` cross-validation
* Performed hyperparameter tuning using `GridSearchCV`
* Evaluated models using cross-validation scores instead of a single split

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Jupyter Notebook

---

## 📊 Outcome

The final solution:

* Uses an end-to-end preprocessing pipeline
* Prevents data leakage
* Supports structured hyperparameter tuning
* Produces predictions for Kaggle submission format
