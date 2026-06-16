# Customer Churn Prediction with Machine Learning

A multi-notebook data analytics and machine learning project that analyzes telecom customer churn, identifies high-risk customer segments, trains churn prediction models, and translates the results into business recommendations.

## Project Overview

Customer churn is a major business problem for subscription-based companies. This project uses the Telco Customer Churn dataset to answer three main questions:

1. Which customer groups are most likely to churn?
2. Can machine learning predict customers at risk of leaving?
3. What actions should the business take to improve retention?

The project is organized as a four-notebook workflow, moving from data cleaning to business recommendations.

## Notebook Workflow

| Notebook | Purpose |
|---|---|
| `customer-churn-eda.ipynb` | Cleans the dataset, creates churn features, and explores major churn patterns |
| `customer-churn-insights.ipynb` | Builds customer segments and identifies high-risk churn groups |
| `customer-churn-modeling.ipynb` | Trains and compares churn prediction models |
| `customer-churn-recommendations.ipynb` | Combines segment and model findings into business recommendations |

## Dataset

This project uses the Telco Customer Churn dataset, which contains customer demographics, account information, service subscriptions, billing details, and churn status.

The original raw dataset is not included directly in this repository. See `data/README.md` for dataset source information and local setup instructions.

## Key Findings

The overall churn rate was **26.54%**.

Several customer groups had much higher churn risk:

| Segment | Churn Rate |
|---|---:|
| Customers with all 5 risk factors | 71.85% |
| Combined high-risk profile | 71.16% |
| Fiber optic + electronic check customers | 53.23% |
| Month-to-month + 0-12 months tenure customers | 51.35% |
| No online security + no tech support customers | 48.96% |

The analysis showed that churn risk increases sharply when multiple risk factors appear together.

## Modeling Results

The modeling notebook compared a dummy baseline, Logistic Regression, Random Forest, and Gradient Boosting.

The final selected model was **Logistic Regression with a 0.55 prediction threshold**.

| Metric | Score |
|---|---:|
| Accuracy | 75.30% |
| Precision | 52.43% |
| Recall | 75.13% |
| F1-score | 61.76% |
| ROC-AUC | 84.16% |

Logistic Regression was selected because churn prediction is focused on identifying customers likely to leave. In this context, recall and F1-score were more important than accuracy alone.

## Business Recommendations

Based on the analysis, the company should:

1. Prioritize new month-to-month customers with early retention offers or proactive check-ins.
2. Target fiber optic customers using electronic checks for billing and service satisfaction follow-up.
3. Promote online security and tech support bundles to customers missing both services.
4. Use churn model scores to rank customers for retention outreach.
5. Create 30-day, 60-day, and 90-day onboarding follow-ups for first-year customers.

## Repository Structure

```text
customer-churn-prediction/
├── notebooks/
│   ├── customer-churn-eda.ipynb
│   ├── customer-churn-insights.ipynb
│   ├── customer-churn-modeling.ipynb
│   └── customer-churn-recommendations.ipynb
├── data/
│   └── README.md
├── outputs/
│   ├── README.md
│   ├── churn_recommendations.csv
│   ├── final_model_summary.csv
│   ├── key_churn_segments.csv
│   ├── model_comparison_results.csv
│   └── other generated output files
├── README.md
├── requirements.txt
└── .gitignore
```

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- scikit-learn
- Jupyter Notebook
- Kaggle

## Skills Demonstrated

- Data cleaning
- Exploratory data analysis
- Customer segmentation
- Feature preparation
- Classification modeling
- Model evaluation
- Threshold tuning
- Business recommendation development
- Portfolio-ready notebook organization

## How to Run

Clone this repository:

```bash
git clone https://github.com/anav24/customer-churn-prediction.git
cd customer-churn-prediction
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Download the Telco Customer Churn dataset and place the raw CSV here:

```text
data/WA_Fn-UseC_-Telco-Customer-Churn.csv
```

Run the notebooks in this order:

```text
notebooks/customer-churn-eda.ipynb
notebooks/customer-churn-insights.ipynb
notebooks/customer-churn-modeling.ipynb
notebooks/customer-churn-recommendations.ipynb
```

Each notebook saves its generated CSV files to the `outputs/` folder when run locally. On Kaggle, outputs are saved to `/kaggle/working`.

## Next Improvements

Possible future improvements include:

- Hyperparameter tuning
- Cross-validation
- Feature importance analysis
- SHAP model interpretation
- Retention campaign simulation
- Dashboard version of the final recommendations

## Project Summary

This project demonstrates an end-to-end churn analysis workflow, including data cleaning, exploratory data analysis, customer segmentation, classification modeling, threshold tuning, and business recommendation development.

The main takeaway is that churn is not random. Customers with short tenure, month-to-month contracts, fiber optic service, electronic check payments, and missing support services are much more likely to leave. By identifying these customers earlier, the business can focus retention efforts where they are most likely to matter.
