# bank-loan-default-logistic-regression
“A beginner-friendly Machine Learning project using Logistic Regression to predict bank loan default risk with applicant financial and credit-related features.”
# 🏦 Bank Loan Default Prediction using Logistic Regression

A beginner-friendly Machine Learning project that uses **Logistic Regression** to predict whether a bank loan applicant is likely to **default or repay a loan**.

The project demonstrates a complete classification workflow, including synthetic data generation, data preparation, feature scaling, model training, evaluation, feature interpretation, and live prediction.

---

## 📌 Project Overview

Loan default prediction is an important application of Machine Learning in banking and financial services.

In this project, a **Logistic Regression** model is developed to classify loan applicants into two categories:

* **0 → Repaid**
* **1 → Defaulted**

Logistic Regression is used because it is relatively simple to understand and provides a coefficient for each feature, making the model easier to interpret.

> **Important:** This project uses a realistic **synthetic dataset** created specifically for this classroom case study. It does not use private or real bank customer data.

---

## 🎯 Objectives

The main objectives of this project are:

* Understand Logistic Regression for classification.
* Predict loan default risk.
* Work with financial and credit-related applicant features.
* Prepare data for Machine Learning.
* Convert categorical data into numerical features.
* Split data into training and testing sets.
* Apply feature scaling.
* Train a Logistic Regression model.
* Evaluate model performance.
* Interpret model coefficients.
* Make predictions for individual applicants.

---

## 📊 Dataset

The notebook creates a synthetic dataset containing **3,000 loan applicants**.

Each row represents one applicant.

### Features

| Feature             | Description                                                      |
| ------------------- | ---------------------------------------------------------------- |
| `annual_income`     | Applicant's annual income in thousands                           |
| `credit_score`      | Credit bureau score ranging from 300–850                         |
| `loan_amount`       | Requested loan amount in thousands                               |
| `debt_to_income`    | Existing monthly debt payments as a percentage of monthly income |
| `employment_years`  | Years at the applicant's current job                             |
| `late_payments_2yr` | Number of late payments during the previous 2 years              |
| `loan_purpose`      | Purpose of loan: Home, Auto, or Personal                         |
| `default`           | Target variable: 0 = Repaid, 1 = Defaulted                       |

These features are defined directly in the notebook.

---

## 🧪 Synthetic Data Generation

Because real bank loan data is private and regulated, the project generates synthetic data using Python.

The dataset includes:

* 3,000 observations
* Income values
* Credit scores
* Loan amounts
* Debt-to-income ratios
* Employment history
* Late-payment history
* Loan purpose
* Default outcome

A simple business-risk rule is used to generate the default label so that the dataset contains meaningful patterns for the Machine Learning model to learn.

---

## 🤖 Machine Learning Model

### Logistic Regression

The project uses:

**Logistic Regression**

It is a classification algorithm used to predict the probability of an outcome.

In this project:

```text
0 → Likely to Repay
1 → Likely to Default
```

The model assigns a coefficient/weight to each feature. Positive weights push the prediction toward default, while negative weights push it toward repayment.

---

## 🔄 Machine Learning Workflow

The project follows this workflow:

```text
Synthetic Dataset
       ↓
Data Exploration
       ↓
One-Hot Encoding
       ↓
Train-Test Split
       ↓
Feature Scaling
       ↓
Logistic Regression
       ↓
Prediction
       ↓
Model Evaluation
       ↓
Feature Interpretation
       ↓
Individual Applicant Prediction
```

---

## 🛠️ Data Preprocessing

### 1. One-Hot Encoding

The `loan_purpose` column contains text categories:

```text
Home
Auto
Personal
```

These categories are converted into numerical variables using **one-hot encoding**.

---

### 2. Train-Test Split

The dataset is divided into:

* **80% training data**
* **20% testing data**

Stratified splitting is used to maintain the distribution of the target variable between the training and testing sets.

---

### 3. Feature Scaling

`StandardScaler` is applied to the numerical features.

Scaling helps prevent features with larger numerical values from dominating the model simply because of their scale.

---

## 📈 Model Evaluation

The trained model is evaluated using:

### Accuracy

Measures the percentage of predictions that are correct.

### Classification Report

The notebook generates a classification report containing metrics for the two classes:

* Repaid
* Defaulted

### Confusion Matrix

The confusion matrix shows:

* Actually repaid → Predicted repay
* Actually repaid → Predicted default
* Actually defaulted → Predicted repay
* Actually defaulted → Predicted default

These evaluation methods are implemented directly in the notebook.

---

## 🔍 Feature Importance through Model Coefficients

One of the useful aspects of Logistic Regression is that its coefficients can be examined.

The notebook creates a table containing:

```text
Feature
Weight
```

The coefficients help explain which variables push the model toward higher or lower default risk.

According to the case-study interpretation:

### Factors increasing default risk

* Lower credit score
* More late payments
* Higher debt-to-income
* Higher loan amount

### Factors reducing default risk

* Higher income
* Longer employment history

The notebook's summary identifies low credit score and late-payment history as important default drivers, while higher income, longer job tenure, and lower debt-to-income reduce predicted risk.

---

## 👤 Live Applicant Prediction

The notebook includes a custom function:

```python
predict_default()
```

This allows a user to enter information about an individual applicant and receive:

* Predicted default probability
* Prediction of likely default or likely repayment

The function uses the trained model and scaler to generate the prediction.

---

## 🧑‍💼 Example Applicants

### Riskier Applicant

The notebook demonstrates an applicant with:

* Lower income
* Lower credit score
* Higher loan amount
* Higher debt-to-income ratio
* Short employment history
* Multiple late payments
* Personal loan purpose

This example is used to demonstrate how the model responds to a higher-risk applicant profile.

### Stronger Applicant

A second example uses:

* Higher income
* Higher credit score
* Smaller loan amount
* Lower debt-to-income ratio
* Longer employment history
* No late payments
* Home loan purpose

This demonstrates the model's prediction for a stronger applicant profile.

---

## 💼 Business Application

A bank could use a similar type of model as part of a credit-risk workflow.

A simplified process could be:

```text
Loan Application
       ↓
Applicant Data
       ↓
Risk Prediction Model
       ↓
Default Risk Estimate
       ↓
Human Underwriting Review
       ↓
Final Lending Decision
```

Applicants identified as higher risk could be routed for additional manual underwriting review or considered for different loan terms, subject to the bank's policies and applicable regulations.

---

## ⚠️ Limitations

This project is designed for **educational purposes**.

### 1. Synthetic Dataset

The model is trained on synthetic data rather than actual bank customer data.

### 2. Classroom Business Rules

The default labels are generated using simplified business rules.

### 3. Real-World Lending Is More Complex

Actual credit-risk systems may involve many additional variables, validation procedures, regulatory requirements, and human review.

### 4. Fairness and Bias

A real lending model would require appropriate fairness and bias testing before deployment.

### 5. Model Should Not Make Decisions Alone

The notebook specifically describes high-risk predictions as candidates for manual underwriting review rather than treating the model as the only decision-maker.

---

## 🧰 Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Scikit-learn**
* **Google Colab / Jupyter Notebook**

The notebook uses `train_test_split`, `LogisticRegression`, `StandardScaler`, `accuracy_score`, `confusion_matrix`, and `classification_report`.

---

## 📁 Project Structure

```text
bank-loan-default-logistic-regression/
│
├── bank_loan_default_logistic_regression.ipynb
│
└── README.md
```

---

## ▶️ How to Run

### Option 1 — Google Colab

1. Open the `.ipynb` notebook.
2. Upload it to Google Colab.
3. Run the cells from top to bottom.
4. Review the generated dataset and visualizations.
5. Train the Logistic Regression model.
6. Check the evaluation metrics.
7. Try different applicant values using `predict_default()`.

### Option 2 — Jupyter Notebook

Install the required libraries:

```bash
pip install numpy pandas matplotlib scikit-learn
```

Then open:

```text
bank_loan_default_logistic_regression.ipynb
```

---

## 🧠 Key Concepts Learned

Through this project, the following concepts are demonstrated:

* Classification
* Logistic Regression
* Synthetic data generation
* Feature engineering
* One-hot encoding
* Train-test split
* Stratified sampling
* Feature scaling
* Model training
* Prediction
* Probability prediction
* Accuracy
* Classification report
* Confusion matrix
* Model coefficients
* Credit-risk prediction
* Business interpretation

---

## 🎓 Academic Context

**Program:** BBA FinTech & AI
**Project Area:** Machine Learning / Financial Technology
**Application:** Banking & Credit Risk
**Model:** Logistic Regression
**Dataset:** Synthetic Loan Applicant Dataset

---

## 💡 Key Learning

This project demonstrates how Machine Learning can be applied to a financial problem such as **loan default prediction**.

The main learning is that a Machine Learning model can identify patterns in applicant information and estimate default risk. Logistic Regression is particularly useful for this classroom example because its coefficients make the model easier to interpret.

---

## ⚖️ Responsible AI Note

A loan-default model can influence important financial decisions, so predictions should be treated as **decision-support information rather than unquestionable decisions**.

A real-world implementation would require appropriate data governance, privacy protection, fairness and bias testing, validation, regulatory compliance, and human oversight. The notebook itself notes that deployment with real data would require fair-lending and privacy considerations and bias testing across protected groups.

---

## 📌 Project Status

**Completed — Educational Machine Learning Project**

This project demonstrates an end-to-end Logistic Regression workflow for predicting bank loan default risk using synthetic applicant data.

---

## 👩‍💻 Author

**Chehak**
BBA FinTech & AI Student
Chitkara University, Punjab
