# customer-churn-milestone-2
Customer churn prediction project using Python and machine learning, covering exploratory analysis, classification models, imbalanced-data evaluation, churn-risk analysis, and business recommendations.

## Project Overview

This project develops a machine learning solution for predicting customer churn.

The analysis examines customer behaviour and identifies patterns associated with churn. Four classification models were developed and evaluated using multiple performance measures appropriate for an imbalanced churn dataset.

The project focuses on using customer behaviour to identify customers who may be at higher risk of churn and how these predictions can support a customer-retention decision.

---

## Business Problem

Customer churn can reduce revenue and customer lifetime value. A business needs a way to identify customers who may be at higher risk of leaving so that retention efforts can be prioritised.

The objective of this project is to build a classification model that can identify potential churners using available customer behaviour data.

---

## Dataset

The dataset contains **20,000 customer records** and the following variables:

- `MonthsActive` – length of time the customer has been active
- `AvgOrderValue` – average customer order value
- `NumOrdersLastQuarter` – number of orders placed during the last quarter
- `DaysSinceLastOrder` – number of days since the customer's most recent order
- `SupportTicketsFiled` – number of support tickets filed
- `Churned` – target variable indicating whether the customer churned

The target variable is imbalanced, with approximately **7.8% of customers classified as churned**.

---

## Analysis

The analysis included:

- Dataset and data-quality inspection
- Target distribution analysis
- Descriptive statistics
- Customer behaviour analysis
- Exploratory data analysis
- Feature engineering
- Stratified train/validation/test splitting
- Feature scaling
- Imbalanced-class handling
- Classification model development
- Model evaluation
- Business interpretation

---

## Models Developed

Four classification models were developed:

1. Logistic Regression
2. Random Forest
3. Gradient Boosting
4. K-Nearest Neighbors (KNN)

Different approaches to class imbalance were applied where appropriate, including class weighting, balanced sample weighting, and minority-class oversampling.

---

## Model Evaluation

Because churn represents a minority of the dataset, accuracy was not used as the only measure of model performance.

The models were evaluated using:

- Confusion Matrix
- Precision
- Recall
- F1-Score
- Accuracy
- ROC-AUC
- PR-AUC
- Top-K risk ranking
- Lift
- Baseline comparisons
- Training versus validation performance
- Classification threshold analysis
- Final test-set evaluation

---

## Key Findings

The analysis identified **`DaysSinceLastOrder`** as the clearest behavioural signal associated with churn.

Customers with longer periods since their last order showed substantially higher observed churn rates.

`SupportTicketsFiled` provided a secondary signal, while ordering activity and customer tenure showed weaker relationships with churn. `AvgOrderValue` showed limited variation in churn across customer groups.

The analysis also showed that recency alone contained a substantial amount of the predictive signal available in the dataset.

---

## Final Model

**Logistic Regression** was selected as the final model based on its combination of predictive performance, generalisation, and interpretability.

### Final Test Performance

| Metric | Result |
|---|---:|
| Precision | 0.19 |
| Recall | 0.62 |
| F1-Score | 0.29 |
| Accuracy | 0.76 |
| ROC-AUC | 0.76 |
| PR-AUC | 0.31 |

The validation and test results were broadly consistent, indicating stable performance on unseen data.

---

## Business Decision

The final model can be used as a **churn-risk decision-support tool**.

Customers can be ranked according to predicted churn probability, allowing a retention team to prioritise higher-risk customers for review and possible intervention.

The model should not be treated as proof that a customer will churn. A predicted risk score is an indicator that can support further customer review.

The classification threshold should be determined according to the business's available retention capacity and the relative cost of false positives and false negatives.

---

## Project Structure

```text
customer-churn-milestone-2/
├── .gitignore
├── README.md
├── dataset/
│   └── milestone-2-customer-churn.csv
├── notebook/
│   └── customer_churn_analysis.ipynb
└── presentation/
    └── presentation.pptx
```

## Technologies and Libraries

The analysis was developed using:

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

---

## How to Run

1. Clone or download the repository.
2. Open the `notebook` folder.
3. Open the customer churn analysis notebook.
4. Ensure the dataset is located in the `dataset` folder.
5. Run the notebook cells in order.

The notebook loads the dataset using the project-relative path:

    data = pd.read_csv('../dataset/milestone-2-customer-churn.csv')

---

## Project Deliverables

- Customer churn analysis notebook
- Customer churn dataset
- Presentation
- Project documentation

## Author

**Oluwaseun Bamigbele**

Customer Churn Prediction – Milestone 2
