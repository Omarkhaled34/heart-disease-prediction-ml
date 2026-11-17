# ❤️ Heart Disease Prediction Using Machine Learning

## 📌 Project Overview

This project focuses on predicting the presence of heart disease using Machine Learning classification algorithms.

The main objective is to explore and compare different tree-based classification models, understand how hyperparameter tuning affects model performance, and evaluate their ability to classify patients based on medical and clinical features.

Three machine learning algorithms are implemented:

- Decision Tree Classifier
- Random Forest Classifier
- XGBoost Classifier

The project covers the complete basic machine learning workflow, including data preprocessing, categorical feature encoding, dataset splitting, model training, hyperparameter experimentation, and performance evaluation.

## 🎯 Project Objectives

- Explore and prepare the heart disease dataset.
- Convert categorical variables into numerical representations using One-Hot Encoding.
- Separate input features from the target variable.
- Split the dataset into training and validation sets.
- Train and evaluate three classification algorithms.
- Experiment with different hyperparameters.
- Compare training and validation accuracy.
- Understand the impact of model complexity on prediction performance.

## 📊 Dataset Description

The project uses a Heart Disease dataset containing 918 patient records.

The dataset includes the following features:

| Feature | Description |
|---|---|
| Age | Patient's age |
| Sex | Patient's sex |
| ChestPainType | Type of chest pain |
| RestingBP | Resting blood pressure |
| Cholesterol | Serum cholesterol level |
| FastingBS | Fasting blood sugar |
| RestingECG | Resting electrocardiogram results |
| MaxHR | Maximum heart rate achieved |
| ExerciseAngina | Exercise-induced angina |
| Oldpeak | ST depression |
| ST_Slope | Slope of the peak exercise ST segment |

**Target Variable:**

- `HeartDisease`
  - 0: No heart disease
  - 1: Heart disease

## 🛠️ Technologies and Libraries

The project is implemented using Python and the following libraries:

- **NumPy:** Numerical computing.
- **Pandas:** Data manipulation and analysis.
- **Matplotlib:** Data visualization.
- **Scikit-learn:** Machine learning algorithms, dataset splitting, and evaluation.
- **XGBoost:** Gradient boosting classification.

## ⚙️ Project Workflow

### 1. Data Loading

The dataset is loaded into a Pandas DataFrame for exploration and preprocessing.

### 2. Categorical Feature Encoding

Categorical variables are converted into numerical representations using One-Hot Encoding.

The following features are encoded:

- Sex
- ChestPainType
- RestingECG
- ExerciseAngina
- ST_Slope

This transformation allows the machine learning algorithms to process categorical information.

### 3. Feature and Target Separation

The dataset is divided into:

- **X:** Independent variables (input features).
- **y:** Dependent variable (HeartDisease).

### 4. Train-Validation Split

The dataset is divided using `train_test_split()`:

- Training set: 80% (734 records).
- Validation set: 20% (184 records).

A `random_state` of 42 is used to make the split reproducible.

### 5. Decision Tree Classifier

A Decision Tree model is trained to identify patterns in the dataset.

Hyperparameter experimentation includes:

- `min_samples_split`: Controls the minimum number of samples required to split an internal node.
- `max_depth`: Controls the maximum depth of the decision tree.

Different values are tested, and training and validation accuracy are compared to investigate model complexity and overfitting.

The selected configuration in the notebook is:

- `min_samples_split = 30`
- `max_depth = 4`

### 6. Random Forest Classifier

Random Forest is implemented as an ensemble learning algorithm that combines multiple decision trees to improve predictive performance.

The following hyperparameters are investigated:

- `min_samples_split`
- `max_depth`
- `n_estimators`

The `n_estimators` parameter determines the number of decision trees in the forest.

The final configuration used in the notebook is:

- `n_estimators = 100`
- `max_depth = 16`
- `min_samples_split = 10`

### 7. XGBoost Classifier

XGBoost is implemented using gradient boosting, where successive trees are trained to improve the predictions of the previous ensemble.

The model uses:

- `n_estimators = 500`
- `learning_rate = 0.1`
- `early_stopping_rounds = 10`
- `random_state = 42`

Early stopping is used with a separate evaluation subset from the training data to determine when additional boosting iterations no longer improve performance.

The recorded best iteration is 29.

### 8. Model Evaluation

The models are evaluated using classification accuracy on the training and validation datasets.

Accuracy is calculated as:

Accuracy = Correct Predictions / Total Predictions

Training and validation accuracy are compared to understand how well each model fits the training data and generalizes to unseen validation samples.

## 📈 Results

The following results are recorded in the notebook:

| Model | Training Accuracy | Validation Accuracy |
|---|---:|---:|
| Decision Tree | 87.06% | 86.96% |
| Random Forest | 92.78% | 88.04% |
| XGBoost | 93.87% | 86.96% |

### Results Interpretation

**Decision Tree:**
Achieved similar training and validation accuracy, suggesting a relatively consistent fit on the two datasets.

**Random Forest:**
Achieved the highest validation accuracy among the three models, with 88.04%.

**XGBoost:**
Achieved the highest training accuracy, but its validation accuracy was lower than Random Forest.

Based on the recorded validation accuracy, Random Forest achieved the best result in this experiment.

These results are specific to the current dataset split and model configurations. They do not establish clinical reliability or prove that one model will perform best on other datasets.

## 📁 Repository Structure

```text
heart-disease-prediction-ml/
│
├── heart_failure.ipynb
│
├── heart.csv
│
├── README.md
│
└── requirements.txt
```

## 🚀 Installation and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/heart-disease-prediction-ml.git
```

### 2. Navigate to the Project Directory

```bash
cd heart-disease-prediction-ml
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Notebook

```bash
jupyter notebook heart_failure.ipynb
```

Make sure `heart.csv` is located in the same directory as the notebook.

## 📦 Requirements

The project requires the following Python libraries:

```text
numpy
pandas
matplotlib
scikit-learn
xgboost
jupyter
```

## 🔍 Future Improvements

Potential improvements to extend this project include:

- Perform more comprehensive hyperparameter optimization.
- Evaluate models using Precision, Recall, F1-score, and ROC-AUC.
- Generate confusion matrices and ROC curves.
- Analyze feature importance.
- Apply cross-validation for more reliable model comparison.
- Investigate class imbalance and its impact on model performance.
- Save the trained models for future predictions.
- Build an interactive prediction interface.

## ⚠️ Disclaimer

This project is developed for educational and machine learning practice purposes only.

It is not a clinically validated diagnostic system and must not be used to make medical decisions.

## 👨‍💻 Author

**YOUR NAME**

Machine Learning | Data Science | Python

GitHub: https://github.com/YOUR_USERNAME
