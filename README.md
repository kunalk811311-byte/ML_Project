# 📊 Customer Churn Prediction & Customer Segmentation using Machine Learning

## 📌 Project Overview

Customer churn is one of the biggest challenges for subscription-based businesses. This project predicts whether a customer is likely to leave the company (Churn Prediction) and further segments customers into different business groups using clustering techniques.

The project follows a complete Machine Learning pipeline starting from data preprocessing and exploratory data analysis (EDA) to model building, evaluation, optimization, and customer segmentation.

---

# 🎯 Objectives

- Analyze customer behavior using Exploratory Data Analysis (EDA)
- Clean and preprocess the dataset
- Build a Machine Learning model to predict customer churn
- Improve model performance using different optimization techniques
- Perform Customer Segmentation using K-Means Clustering
- Identify high-risk customers for better business decision-making

---

# 📂 Dataset

Dataset Used:
**Telco Customer Churn Dataset**

The dataset contains customer information such as:

- Customer Demographics
- Tenure
- Monthly Charges
- Total Charges
- Contract Type
- Internet Service
- Payment Method
- Tech Support
- Churn Information

Target Variable:

- **Churn Value**
    - 1 = Customer Churned
    - 0 = Customer Retained

---

# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Imbalanced-Learn (SMOTE)

---

# 📋 Project Workflow

## 1. Data Loading

- Loaded Telco Customer Churn dataset
- Inspected dataset structure
- Checked data types
- Explored missing values

---

## 2. Exploratory Data Analysis (EDA)

Performed detailed visual analysis including:

### Numerical Analysis

- Tenure Distribution
- Monthly Charges Distribution
- Boxplots for:
  - Tenure vs Churn
  - Monthly Charges vs Churn

### Categorical Analysis

- Contract Type
- Internet Service
- Payment Method
- Tech Support

### Statistical Analysis

- Correlation Matrix
- Crosstab Analysis
- Average Tenure by Churn Status
- Descriptive Statistics

---

# 🧹 Data Cleaning

The following preprocessing steps were performed:

### Converted Data Types

- Converted **Total Charges** to numeric format.

### Missing Value Handling

- Missing values in **Total Charges** were replaced with 0.

### Removed Unnecessary Columns

Dropped columns such as:

- CustomerID
- Count
- Country
- State
- Zip Code
- Latitude
- Longitude
- Lat Long
- Churn Label
- Churn Score
- CLTV
- Churn Reason

### Encoding

Applied One-Hot Encoding using:

```python
pd.get_dummies(drop_first=True)
```

Removed the high-cardinality **City** column before final encoding.

---

# 🤖 Machine Learning Model

Model Used:

## Random Forest Classifier

Initial Parameters:

- n_estimators = 100
- random_state = 42

---

# ✂ Train-Test Split

Dataset was divided into:

- 80% Training
- 20% Testing

Using:

```python
train_test_split()
```

---

# 📈 Model Evaluation

Evaluated using:

- Accuracy Score
- Confusion Matrix
- Classification Report

Metrics:

- Accuracy
- Precision
- Recall
- F1 Score

---

# 🚀 Model Improvements

Several approaches were implemented to improve model performance.

---

## 1️⃣ Handling Class Imbalance

Used:

```python
class_weight='balanced'
```

This improved recall for minority class predictions.

---

## 2️⃣ Hyperparameter Tuning

Optimized Random Forest using:

- n_estimators = 300
- max_depth = 10

---

## 3️⃣ SMOTE (Synthetic Minority Oversampling)

Applied:

```python
SMOTE()
```

to balance the training dataset before model training.

---

## 4️⃣ Feature Importance Analysis

Extracted feature importance from the trained Random Forest model.

Less important features were identified and removed to simplify the model.

---

## 5️⃣ Feature Selection

Dropped low-importance features such as:

- Phone Service
- Multiple Lines

Retrained the model and compared performance.

---

## 6️⃣ Model Comparison

Compared multiple Random Forest configurations using:

- Different number of trees
- Different tree depths

Metrics compared:

- Accuracy
- Precision
- Recall
- F1 Score

---

## 7️⃣ Cross Validation

Performed **5-Fold Cross Validation**.

Calculated:

- Mean Accuracy
- Mean Recall

to evaluate model stability.

---

# 📊 ROC-AUC Analysis

Calculated:

- ROC Curve
- AUC Score

Used prediction probabilities to evaluate classification performance.

---

# 👥 Customer Segmentation

After churn prediction, customers were segmented using:

## K-Means Clustering

### Features Used

- Tenure Months
- Monthly Charges
- Total Charges
- Churn Probability



## Data Scaling

Applied:

```python
StandardScaler()
```

before clustering.



## Optimal Number of Clusters

Used the **Elbow Method (WCSS)** to determine the optimal number of clusters.

Selected:

```
K = 3
```


# 📌 Customer Segments

Customers were grouped into three business-friendly segments:

### 🟢 Budget Loyal Customers

- Low monthly charges
- Lower churn probability
- Long-term customers



### 🔴 High Risk New Customers

- Higher churn probability
- Short tenure
- Require retention strategies

### 🔵 Loyal Premium Customers

- High spending customers
- Long tenure
- Valuable customers for the business


# 📈 Data Visualization

The project includes visualizations such as:

- Histogram
- Boxplots
- Countplots
- Correlation Matrix
- ROC Curve
- Elbow Curve
- Cluster Scatter Plots

Scatter plots were created using:

- Monthly Charges vs Churn Probability
- Tenure vs Churn Probability
- Total Charges vs Churn Probability


# 📁 Project Structure

```
├── Customer_Churn_Project.ipynb
├── Telco_customer_churn.xlsx
├── README.md
```


# 💼 Business Impact

This project helps businesses:

- Predict customers likely to churn
- Improve customer retention
- Identify valuable customers
- Design targeted marketing campaigns
- Reduce revenue loss
- Improve customer lifetime value


# 📚 Machine Learning Concepts Covered

- Exploratory Data Analysis
- Data Cleaning
- Feature Engineering
- One-Hot Encoding
- Train-Test Split
- Random Forest Classification
- Class Imbalance Handling
- SMOTE
- Hyperparameter Tuning
- Feature Importance
- Cross Validation
- ROC-AUC Analysis
- Probability Prediction
- Customer Segmentation
- Standardization
- K-Means Clustering


# 🚀 Future Improvements

Possible enhancements include:

- XGBoost Classifier
- LightGBM
- CatBoost
- GridSearchCV
- RandomizedSearchCV
- SHAP Explainability
- Model Deployment using Flask/FastAPI
- Streamlit Dashboard
- Power BI Dashboard Integration


# 👨‍💻 Author

**Kishore Kunal**

Aspiring Data Scientist | Machine Learning Enthusiast


## ⭐ If you found this project helpful, don't forget to star the repository!
