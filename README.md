# Customer Churn Prediction & Retention Analytics

## Project Overview

This project develops an end-to-end customer churn analytics solution for a fictional B2B SaaS company, **InsightFlow Analytics Ltd**.

The objective is to understand customer churn behaviour, identify the factors associated with customer attrition, predict customers at risk of churning, quantify potential revenue exposure, and communicate actionable retention insights through Power BI.

The project combines **Python, SQL, Machine Learning and Power BI** to demonstrate a complete data analytics workflow.

---

## Business Scenario

**Company:** InsightFlow Analytics Ltd
**Industry:** B2B SaaS / Subscription Services

The company is experiencing customer churn and wants to understand:

* Which customers are most likely to churn?
* What behavioural and service factors are associated with churn?
* How much revenue is exposed to churn risk?
* Which customers should the retention team prioritise?
* What insights can management use to improve customer retention?

---

## Business Objectives

The project aims to:

* Analyse customer demographics, engagement and subscription behaviour
* Identify patterns associated with customer churn
* Analyse customer support and satisfaction indicators
* Use SQL to answer business questions from a relational database
* Build machine learning models to predict churn probability
* Segment customers according to predicted churn risk
* Estimate revenue at risk
* Create an interactive Power BI dashboard for business users
* Translate analytical findings into practical retention recommendations

---

## Dataset

The project uses a **synthetic B2B SaaS customer dataset** containing 10,000 customers and 16 analytical features.

The dataset includes information relating to:

* Customer demographics
* Region
* Subscription type
* Monthly revenue
* Customer tenure
* Login frequency
* Session duration
* Product feature usage
* Recency of customer activity
* Complaints
* Support response time
* Support resolution time
* Customer satisfaction
* Churn status

Because the data is synthetic, the project is intended to demonstrate analytical methodology rather than represent real-world company performance.

---

## Project Workflow

```text
Data Generation & Preparation
            ↓
Exploratory Data Analysis
            ↓
SQL Business Analysis
            ↓
Machine Learning
            ↓
Customer Risk Prediction
            ↓
Revenue-at-Risk Analysis
            ↓
Power BI Dashboard
            ↓
Business Recommendations
```

---

## Analytical Work

### Data Preparation

The first stage prepares the customer data for analysis and modelling.

Key activities include:

* Data generation
* Data validation
* Data type handling
* Missing-value checks
* Feature preparation
* Dataset validation
* Export of the final analytical dataset

Final dataset:

**10,000 rows × 16 columns**

---

### Exploratory Data Analysis

The EDA stage investigates customer behaviour and relationships with churn.

Areas analysed include:

* Churn distribution
* Customer demographics
* Subscription behaviour
* Customer engagement
* Login frequency
* Product feature usage
* Customer satisfaction
* Complaints
* Support response times
* Revenue impact
* Tenure

### Key EDA Findings

Overall churn rate:

**15.04%**

Customers:

* **8,496 retained**
* **1,504 churned**

Total monthly revenue:

**£733,000**

Revenue associated with churned customers:

**£110,416**

The analysis indicates that customer engagement, product usage, support experience and satisfaction are important areas to investigate when assessing churn risk.

---

## SQL Business Analysis

A SQLite database is included in the repository:

`customer_churn_analytics.db`

The SQL analysis investigates:

* Customer overview
* Customer revenue
* Revenue by subscription type
* Customer behaviour
* Customer engagement
* Support interactions
* Churn patterns
* Business-level customer segments

This demonstrates the ability to move beyond Python analysis and work with a relational database using SQL.

---

## Machine Learning

Three classification models were developed to predict customer churn:

* Logistic Regression
* Random Forest
* Gradient Boosting

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC

### Logistic Regression

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 93.85% |
| Precision | 85.89% |
| Recall    | 70.76% |
| F1 Score  | 77.60% |
| ROC-AUC   | 97.36% |

Random Forest and Gradient Boosting achieved extremely high scores on this synthetic dataset.

The **Random Forest** model was selected for customer risk ranking and feature-importance analysis.

> **Important:** The unusually high model performance should not be interpreted as evidence that the model would achieve the same performance on real-world customer data. The dataset is synthetic and contains strong generated relationships between behavioural features and churn.

---

## Key Churn Drivers

The Random Forest feature-importance analysis identified the following major predictors:

| Feature                     | Importance |
| --------------------------- | ---------: |
| Features Used               |     25.13% |
| Monthly Login Count         |     22.91% |
| Last Login Days Ago         |     18.31% |
| Complaint Count             |     16.23% |
| Customer Satisfaction Score |     13.22% |

The results suggest that **product engagement and customer activity** are particularly important signals of churn risk.

---

## Customer Risk Segmentation

The machine learning model generates a churn probability for each customer.

Customers are classified using the following thresholds:

| Risk Category | Churn Probability |
| ------------- | ----------------: |
| Low Risk      |            < 0.30 |
| Medium Risk   |         0.30–0.69 |
| High Risk     |            ≥ 0.70 |

### Risk Results

| Risk Category | Customers |
| ------------- | --------: |
| Low Risk      |     8,496 |
| Medium Risk   |         1 |
| High Risk     |     1,503 |

---

## Revenue at Risk

The analysis identifies **1,503 high-risk customers**.

Estimated monthly revenue associated with these high-risk customers:

**£110,337**

This provides a financial perspective for prioritising customer retention activity.

Instead of treating every customer equally, the business can focus retention resources on customers with both **high churn probability and meaningful revenue exposure**.

---

## Power BI Dashboard

The final stage of the project is an interactive Power BI report designed to communicate the analytical results to business stakeholders.

The planned report contains six analytical pages:

### Executive Overview

Provides a management-level summary including:

* Total customers
* Churn rate
* Churned customers
* Monthly revenue
* Revenue at risk
* High-risk customers
* Churn distribution
* Regional and subscription insights

### Customer Insights

Explores:

* Customer demographics
* Subscription mix
* Tenure
* Engagement
* Satisfaction
* Customer profiles

### Churn Analysis

Investigates:

* Churn by tenure
* Churn by satisfaction
* Churn by subscription
* Churn by engagement
* Churn trends
* Key churn patterns

### Risk Analysis

Focuses on:

* High-risk customers
* Risk categories
* Churn probability
* Risk by region
* Risk by subscription
* Feature importance

### Revenue Impact

Examines:

* Revenue at risk
* Revenue associated with churn
* Revenue by region
* Revenue by subscription
* High-value customers at risk

### Model Insights

Communicates:

* Model comparison
* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Feature importance
* Model limitations

---

## Business Recommendations

Based on the analysis, the company could consider the following retention strategies:

### Increase Product Engagement

Customers showing declining login frequency or low feature adoption could receive targeted onboarding, product education and feature-usage campaigns.

### Prioritise High-Risk Customers

Customers with a high predicted churn probability should be prioritised by the retention team.

### Monitor Customer Activity

A reduction in login frequency or increasing inactivity can be used as an early-warning signal.

### Improve Customer Support

Customers experiencing complaints, slower response times or lower satisfaction may require proactive support intervention.

### Combine Risk With Customer Value

Retention resources should consider both:

**Probability of churn × Financial value**

This helps the business prioritise customers where intervention could have the greatest financial impact.

---

## Tools & Technologies

| Tool                 | Purpose                                      |
| -------------------- | -------------------------------------------- |
| Python               | Data preparation, EDA and machine learning   |
| Pandas               | Data manipulation                            |
| NumPy                | Numerical analysis                           |
| Matplotlib / Seaborn | Data visualisation                           |
| Scikit-learn         | Machine learning                             |
| SQLite               | Relational database and SQL analysis         |
| SQL                  | Business analysis                            |
| Power BI             | Interactive dashboard and business reporting |
| Jupyter Notebook     | Analytical workflow                          |
| GitHub               | Version control and portfolio presentation   |

---

## Key Skills Demonstrated

This project demonstrates practical experience with:

* Data cleaning
* Exploratory data analysis
* Business analysis
* SQL
* Relational databases
* Data visualisation
* Feature engineering
* Classification modelling
* Model evaluation
* Feature importance
* Customer segmentation
* Risk scoring
* Revenue-at-risk analysis
* Power BI dashboard development
* Business storytelling
* Translating analytical findings into recommendations

---

## Project Limitations

Several limitations should be considered.

The dataset is synthetic and therefore does not represent real customer behaviour.

The extremely high machine-learning performance, particularly from tree-based models, may indicate strong relationships built into the generated dataset.

A production churn model would require:

* Real historical customer data
* Out-of-time validation
* Careful leakage checks
* Model monitoring
* Regular retraining
* Calibration of predicted probabilities
* Business validation
* A/B testing of retention interventions

Therefore, the model should be viewed as a demonstration of the analytical workflow rather than a production-ready churn prediction system.

---

## Project Outcome

This project demonstrates an end-to-end analytics workflow:

**Raw customer data → Data preparation → EDA → SQL → Machine Learning → Risk prediction → Revenue impact → Power BI → Business recommendations**

The final solution provides both **descriptive insight** into historical churn and **predictive insight** into customers who may require retention intervention.

---

## Author

**Neelam Singh**

United Kingdom
