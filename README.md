# 📚 Predicting Library Usage

A Machine Learning project that analyzes student library borrowing behavior and predicts whether a student is a **Frequent Library User** or **Non-Frequent Library User**.

## 🎯 Project Objective

The goal of this project is to use historical library transaction and student information to identify students who are likely to be frequent library users.

This can help educational institutions understand library usage patterns and support better library resource planning.

## 📊 Dataset

The original dataset contains:

* **52,394 records**
* **22 columns**
* Student information
* Book information
* Borrowing and return information
* Academic information
* Library transaction information

Important features include:

* Membership Number
* Book ID
* Borrow Duration
* Borrow Date
* Return Date
* Department Code
* Cumulative GPA
* Total Credits
* Gender
* Academic Year
* Program Code
* Author
* Publisher
* Location Code
* Borrowed status

## 🧹 Data Preprocessing

The project performs several preprocessing steps:

* Duplicate removal
* Missing-value analysis
* Missing-value handling
* Date conversion
* Date feature engineering
* Student-level aggregation
* Numerical feature processing
* Categorical feature encoding
* Feature scaling

After cleaning:

* Duplicate rows: **0**
* Remaining missing values: **476**
* Final transaction dataset: **52,389 rows**

## 👨‍🎓 Student-Level Dataset

The transaction-level data was transformed into a student-level dataset containing **14,148 students**.

Student-level features include:

* Total transactions
* Total books borrowed
* Average borrow duration
* Total borrow duration
* Average GPA
* Total credits
* Gender
* Place of birth
* Academic year
* Program code
* Department code
* Unique authors
* Unique publishers
* Unique subjects
* First borrow date
* Last borrow date
* Total borrowed

## 🎯 Target Variable

A student is classified as a **Frequent Library User** when their number of transactions reaches the 75th-percentile threshold.

**Transaction threshold:** `4.0`

### Target Distribution

| Category          | Students | Percentage |
| ----------------- | -------: | ---------: |
| Non-Frequent User |   10,217 |     72.22% |
| Frequent User     |    3,931 |     27.78% |

## 🔍 Exploratory Data Analysis

The project performs EDA to understand library usage patterns.

Analysis includes:

* Frequent vs Non-Frequent users
* Distribution of student-level features
* Correlation heatmap
* Library usage by academic program
* Library usage by academic year
* Library usage by gender
* Borrowing duration analysis
* Number of books borrowed
* GPA analysis
* Borrowing trends by year
* Borrowing trends by month

## 🤖 Machine Learning

The target variable is:

```text
frequent_library_user
```

### Train-Test Split

The dataset is divided using:

* **80% Training**
* **20% Testing**
* `random_state = 42`
* Stratified split

## ⚙️ Preprocessing Pipeline

### Numerical Features

* Median imputation
* Standard scaling

### Categorical Features

* Most-frequent imputation
* One-hot encoding
* Unknown categories handled safely

The preprocessing is implemented using `ColumnTransformer` and `Pipeline`.

## 🌳 Model 1 — Decision Tree

The project uses a `DecisionTreeClassifier` with:

* Criterion: `gini`
* Maximum depth: `6`
* Minimum samples split: `10`
* Minimum samples leaf: `5`
* Class weight: `balanced`
* Random state: `42`

### Performance

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 1.0000 |
| Precision | 1.0000 |
| Recall    | 1.0000 |
| F1-Score  | 1.0000 |
| ROC-AUC   | 1.0000 |

## 🔵 Model 2 — SVM

The project also evaluates a Support Vector Machine classifier.

### Performance

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 0.9972 |
| Precision | 0.9937 |
| Recall    | 0.9962 |
| F1-Score  | 0.9949 |
| ROC-AUC   | 1.0000 |

## 🏆 Model Comparison

| Model         | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
| ------------- | -------: | --------: | -----: | -------: | ------: |
| Decision Tree |   1.0000 |    1.0000 | 1.0000 |   1.0000 |  1.0000 |
| SVM           |   0.9972 |    0.9937 | 0.9962 |   0.9949 |  1.0000 |

Based on the notebook's reported test metrics, the **Decision Tree performed best** among the evaluated models.

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

## 📁 Project Structure

```text
Predicting-Library-Usage/
│
├── README.md
├── Untitled(1).ipynb
└── dataset/
    └── library_data.csv
```

> Rename the notebook and dataset files according to the actual files in your repository.

## 🔄 Machine Learning Workflow

```text
Raw Library Data
       ↓
Data Cleaning
       ↓
Date Feature Engineering
       ↓
Student-Level Aggregation
       ↓
Target Variable Creation
       ↓
Exploratory Data Analysis
       ↓
Feature Selection
       ↓
Train-Test Split
       ↓
Preprocessing
       ↓
Model Training
       ↓
Model Evaluation
       ↓
Model Comparison
       ↓
Best Model
```

## 💡 Key Learning Outcomes

Through this project, the following Machine Learning concepts were implemented:

* Data cleaning
* Missing-value handling
* Feature engineering
* Aggregation
* Exploratory Data Analysis
* Classification
* Train-test splitting
* One-hot encoding
* Feature scaling
* Pipelines
* ColumnTransformer
* Decision Trees
* Support Vector Machines
* Classification metrics
* Confusion Matrix
* ROC-AUC
* Model comparison

## 🚀 Future Improvements

Possible improvements include:

* Hyperparameter tuning
* Cross-validation
* Testing additional classification algorithms
* Feature importance analysis
* Model explainability using SHAP
* Deployment using Flask or FastAPI
* Creating a web interface for predictions
* Monitoring model performance after deployment

## 👨‍💻 Author

**Raj**

MCA — Artificial Intelligence & Machine Learning

---

⭐ If you found this project useful, consider giving the repository a star!
