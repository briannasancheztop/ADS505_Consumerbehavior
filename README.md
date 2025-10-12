# Adapting Retail to Shifting Consumer Behavior: Insights from Shopping Data

This project is a part of the ADS-505 course in the Applied Data Science Program at the University of San Diego.

**Project Status:** Completed

---

## Installation

### Requirements
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy dmba

**Usage**

Clone this repository:
git clone https://github.com/briannasancheztop/ADS505_Consumerbehavior.git

Download the dataset from Kaggle and place shopping_behavior_updated.csv in the project directory
Open and run the Jupyter Notebook sequentially
All visualizations and model outputs will generate automatically

Project Intro/Objective
The primary objective of this project is to analyze the shift from in-store to online retail purchasing and predict high-value customers (top 25% by purchase amount). Retailers face declining foot traffic as consumer preferences evolve toward e-commerce. This analysis aims to provide actionable insights to optimize omnichannel strategies, improve resource allocation, and inform store footprint decisions. By identifying patterns in demographic, loyalty, and purchasing data, the project seeks to guide targeted marketing efforts and strengthen customer retention strategies.

Partner(s)/Contributor(s)
Team 10 Members:

Brianna Sanchez (Team Leader)
Alexander Zhuk

GitHub Repository: https://github.com/briannasancheztop/ADS505_Consumerbehavior

Methods Used

Exploratory Data Analysis (EDA)
Data Visualization
Statistical Hypothesis Testing (Chi-square, t-tests)
Feature Engineering
Data Preprocessing & Transformation
Predictive Modeling (Classification)
Machine Learning (Logistic Regression, Random Forest)
Model Evaluation & Validation
Correlation Analysis
Data Manipulation

Technologies

Python 3.12
Libraries:

Data Processing: pandas, numpy
Visualization: matplotlib, seaborn
Machine Learning: scikit-learn
Statistical Analysis: scipy
Business Analytics: dmba


Environment: Jupyter Notebook / Google Colab
Version Control: Git/GitHub

Project Description
Dataset Overview

Source: Kaggle - Consumer Behavior and Shopping Habits Dataset
Size: 3,900 transactions × 18 features
Format: CSV file (shopping_behavior_updated.csv)

Research Questions & Hypotheses
Primary Question:
Can demographic and transactional features predict high-value customers (top 25% by purchase amount)?
Hypotheses Tested:

Online vs. in-store channel preference differs by age group
Subscription/loyalty status correlates with higher spending
Review ratings predict repeat purchase behavior
Promotional discounts increase average order value
Demographic features (age, gender) significantly impact spending patterns

Research Questions & Hypotheses
Primary Question:
Can demographic and transactional features predict high-value customers (top 25% by purchase amount)?
Hypotheses Tested:

Online vs. in-store channel preference differs by age group
Subscription/loyalty status correlates with higher spending
Review ratings predict repeat purchase behavior
Promotional discounts increase average order value
Demographic features (age, gender) significantly impact spending patterns

Analysis & Modeling Approach
1. Exploratory Data Analysis

Distribution analysis of purchase amounts, age, and categories
Channel preference visualization across demographics
Correlation heatmaps for numeric features
Cross-tabulation of categorical variables

2. Feature Engineering

Created binary target variable: high_value (1 = top 25% spenders, 0 = others)
One-hot encoded categorical variables (gender, category, size, season, payment method, shipping type)
Mapped purchase frequency to ordinal scale
Derived Channel feature from shipping type (Store Pickup = In-Store, else = Online)

3. Statistical Testing

Chi-square tests for categorical associations (age × channel, category × channel, promo × channel)
Independent t-tests for spending differences (subscribers vs. non-subscribers, discount vs. no discount)
Correlation analysis for numeric predictors

4. Predictive Modeling

Train/Validation/Test Split: 60% / 20% / 20%
Models Evaluated:

Logistic Regression with L2 regularization (5-fold CV, class weighting)
Random Forest Classifier (400 trees, max_depth=3, class_weight={0:1, 1:3})


Evaluation Metrics: Accuracy, Precision, Recall, F1-Score, Confusion Matrix, Gains/Lift Charts

Key Findings
Channel Behavior:

83% of revenue comes from online purchases (17% in-store)
Average transaction value identical across channels (~$60)
All age cohorts show 80%+ online preference, contradicting traditional retail assumptions

Critical Insight:
26% precision means the model incorrectly identifies high-value customers 75% of the time, making it unreliable for practical targeting.
Statistical Evidence:

No significant differences in spending across age, gender, subscription status, or discount usage (all p > 0.26)
Near-zero correlations between numeric features and high-value status (r ≈ 0.02–0.04)
Promotions drive transaction volume but not order value ($60.13 without discount vs. $59.28 with)

Roadblocks & Challenges

Homogeneous Spending Patterns: All customer segments spend approximately $60/transaction, making differentiation extremely difficult
Lack of Temporal Data: Dataset lacks purchase recency, seasonality trends, and customer lifetime value metrics
Weak Feature Signals: Demographic and behavioral features show minimal predictive power
Class Imbalance: Top 25% threshold creates natural imbalance (75% vs. 25% split)
Limited Model Performance: Even with ensemble methods and class weighting, precision remained below acceptable thresholds for business use

Business Recommendations

Prioritize Digital Investment: Focus 83% of resources on e-commerce optimization
Scale Back Physical Footprint: 17% in-store revenue suggests aggressive store consolidation
Avoid Demographic Segmentation: No statistical evidence supports age/gender-based targeting
Enhance Data Collection: Implement tracking for purchase recency, CLV, and time-series behavior
Use Promotions for Acquisition Only: Discounts don't increase order size—reserve for customer acquisition campaigns


License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgments

University of San Diego - ADS-505 Applied Data Science course
Kaggle - For providing the Consumer Behavior and Shopping Habits Dataset
Course Instructors - For guidance on statistical modeling and business analytics
dmba Library Contributors - For classification evaluation tools (gains/lift charts)
scikit-learn Community - For comprehensive machine learning documentation
