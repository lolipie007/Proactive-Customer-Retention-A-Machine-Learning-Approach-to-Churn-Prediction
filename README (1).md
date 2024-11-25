# **Customer Churn Prediction Project**

## **Overview**
This project focuses on predicting customer churn using machine learning techniques. The dataset simulates customer behavior, including various features such as months as a customer, total purchases, and support tickets. The goal is to develop a robust churn prediction model and derive actionable business insights to reduce churn.

---

## **Features**
### **Dataset Columns**
| Feature                | Description                                                                              |
|------------------------|------------------------------------------------------------------------------------------|
| `customer_id`          | Unique identifier for each customer                                                     |
| `months_as_customer`   | Number of months the customer has been with the company                                 |
| `total_purchases`      | Total number of purchases made by the customer                                          |
| `avg_order_value`      | Average value of the customer's purchases (some values may be missing)                  |
| `support_tickets`      | Number of support tickets raised by the customer                                        |
| `last_interaction_days`| Days since the customer last interacted with the company                                |
| `churn`                | Target variable (1 for churned customers, 0 for non-churned customers)                  |

---

## **Project Workflow**

### **1. Data Analysis and Preprocessing**
- **Objective:** Load, explore, and clean the dataset for modeling.
- **Steps:**
  1. Handle missing values (`avg_order_value` imputed with the median).
  2. Normalize numerical features using `StandardScaler`.
  3. Split the data into features (`X`) and target (`y`).

---

### **2. Model Development**
- **Objective:** Build a machine learning model to predict churn.
- **Steps:**
  1. Used **Random Forest Classifier** for its robustness and ability to handle mixed data types.
  2. Applied **K-Fold Cross-Validation** to ensure performance generalization.
  3. Evaluated using **ROC-AUC Score**, a metric suitable for imbalanced datasets.

---

### **3. Insights and Recommendations**
- **Objective:** Derive actionable insights to reduce churn.
- **Findings:**
  - Customers with longer tenure (`months_as_customer`) are less likely to churn.
  - Higher support ticket volumes correlate with a higher churn likelihood.
  - Frequent purchases reduce churn probability.
- **Recommendations:**
  1. Improve support systems for customers raising frequent tickets.
  2. Offer loyalty programs to newer customers.
  3. Target campaigns for customers with lower interaction frequency.

---

## **Implementation**
### **Prerequisites**
Install the required libraries:
```bash
pip install -r requirements.txt
```

### **Files**
- `customer_churn_data.csv`: The dataset.
- `churn_prediction.py`: Script for loading, preprocessing, modeling, and generating insights.
- `README.md`: Documentation for the project.
- `requirements.txt`: Dependencies required to run the project.

### **Running the Project**
1. Clone the repository.
2. Run the `churn_prediction.py` script:
   ```bash
   python churn_prediction.py
   ```
3. Review the results, including:
   - Cross-validation scores.
   - Holdout set evaluation.
   - Feature importance and insights.

---

## **Evaluation Metrics**
### **Cross-Validation**
Used 5-fold cross-validation to calculate the average ROC-AUC score:
```
Cross-Validation Scores (ROC-AUC): [0.9971, 0.9986, 0.9981, 0.9999, 0.9958]
Mean ROC-AUC Score: 0.9979
```

### **Holdout Set**
Performance on an unseen holdout set:
```
Holdout ROC-AUC Score: 0.9952
```

---

## **Business Impact**
- **Problem Addressed:** Churn significantly impacts customer lifetime value (CLV).
- **Proposed Solution:** Predict and mitigate churn using targeted actions driven by data insights.
- **Integration:** The churn prediction model can be integrated into CRM systems for real-time customer risk profiling.

---

## **Future Improvements**
1. Test additional models like Gradient Boosting (e.g., XGBoost, LightGBM) for potential performance gains.
2. Explore hyperparameter tuning using `GridSearchCV` or `RandomizedSearchCV`.
3. Incorporate additional features such as customer demographics or interaction channels.

---

This README serves as a complete guide to understanding and replicating the project workflow.
