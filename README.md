✈️ Optimizing Air Travel Through Flight Delay Prediction
A Machine Learning Approach for Minimizing Controllable Delays in Air Travel
📌 Project Overview

Air travel is a critical component of today’s global economy, but flight delays cause major inconvenience to passengers and lead to significant operational costs for airlines.
This project focuses on predicting flight delays and identifying controllable delay factors using machine learning and explainable AI techniques.

The goal is not just prediction, but actionable insights that airlines and airports can use to improve operational efficiency and passenger experience.

🎯 Objectives & Motivation
Project Goals

Understand key causes and patterns behind flight delays

Build machine learning models to predict:

Whether a flight will be delayed (Classification)

How long the delay will be (Regression)

Identify controllable delays (e.g., Carrier Delay, Late Aircraft Delay)

Enable operational decision-making through interpretable ML

Why This Matters

Flight delays cost airlines billions due to operational disruptions

Predictive and explainable systems help:

Reduce avoidable delays

Improve scheduling and resource allocation

Enhance passenger satisfaction

📊 Exploratory Data Analysis (EDA) – Key Insights

Seasonality Pattern:
Arrival delays peak between July and December, likely due to holiday traffic and weather conditions. Spring months show relatively lower delays.

Yearly Trends:
Average arrival delays peaked in 2017, dropped sharply in 2020 (pandemic impact), and gradually stabilized to pre-pandemic levels by 2023.

Major Delay Contributors:

Late Aircraft Delay

Carrier Delay
These contribute the most to total delay time, highlighting internal operational bottlenecks.

Lower Impact Factors:

Weather Delay

NAS Delay

Security Delay
These are comparatively smaller, reinforcing the focus on controllable delays.

Class Imbalance:

Target feature is_delayed (1 = delay ≥ 15 minutes, 0 = on-time) was highly imbalanced.

This was addressed during modeling to prevent bias toward the majority class.

🛫 Airport-Level Analysis

The Top 10 airports by average arrival delay are major hubs with heavy traffic and congestion.

These airports can benefit from targeted operational improvements such as better ground crew allocation and congestion monitoring.

🔍 Correlation Analysis

Correlation heatmap showed weak correlations between most features.

Indicates low multicollinearity, allowing features to contribute independently to model predictions.

⚙️ Methodology
1. Data Preprocessing

Handled missing values

Feature encoding

Standard scaling

Removed irrelevant columns

2. Feature Engineering

Created binary target: is_delayed

Ensured only pre-departure features were used for prediction

3. Initial Modeling

Baseline model: Logistic Regression

Found misleadingly high accuracy due to class imbalance

4. Multiple Model Evaluation

Models tested:

Logistic Regression

Decision Tree

Random Forest

Gradient Boosting

⚠️ Initial results showed ~100% accuracy due to data leakage

🚨 Data Leakage Detection & Fix

Leakage features identified:

Actual arrival time

Arrival delay variables (arr_delay, arr_del15)

These features were removed

Models retrained using only information available before departure

🏆 Final Model Selection

Random Forest Classifier emerged as the best model

Key strengths:

Handles non-linear relationships

Robust to outliers

Balanced precision, recall, and AUC-ROC

Model Performance

AUC-ROC ≈ 0.933

Significantly better than Logistic Regression (AUC ≈ 0.84)

Demonstrates strong separation between delayed and on-time flights

🔍 Explainable AI (SHAP)

Applied SHAP (Shapley values) for model interpretability

Identified key drivers:

Scheduled departure time

Carrier

Origin airport

SHAP analysis also helped:

Detect data leakage

Validate the final cleaned model

Ensure transparency and trust in predictions

⏱️ Regression: Delay Duration Prediction

Built a regression model to estimate delay duration (in minutes)

Evaluated using:

MAE

RMSE

🧠 Operational Adjustability Index (OAI)

Introduced Operational Adjustability Index (OAI) to focus on delays that airlines can control

Trained a specialized regression model to minimize controllable delay types

Combined SHAP + OAI to generate actionable insights for operations teams

📈 Actionable Recommendations
Carrier-Level

Optimize crew scheduling

Improve aircraft readiness

Add buffer time for high-risk slots (especially evening departures)

Airport-Level

Allocate additional ground crew at busy hubs

Monitor congestion trends at delay-prone airports

System-Level

Integrate real-time delay and OAI predictions into airline dashboards

Prioritize flights where delays are operationally controllable

Strategic Impact

Reduces avoidable delays

Improves customer satisfaction

Minimizes cascading disruptions

Optimizes airline and airport operations

🧑‍💻 Author

Name: Shikha Bharti
Enrollment No: 21321028

🙌 Thank You

If you find this project useful or interesting, feel free to ⭐ the repository!
