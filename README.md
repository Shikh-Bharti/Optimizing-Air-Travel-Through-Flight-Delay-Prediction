# Optimizing-Air-Travel-Through-Flight-Delay-Prediction
Flight Delay 
Prediction
A Machine Learning Approach for 
Minimizing Controllable Delays in Air 
Travel
Project Objectives & 
Motivation
• Project Goals:
• Air travel is essential in 
• Understand key causes and 
patterns behind delays
• Build models to predict:
• Whether a flight will be 
delayed (Classification)
• How long the delay will be 
(Regression)
• Highlight controllable delays 
(e.g., Carrier, Late Aircraft)
• Enable operational decision
making via interpretable ML
today’s global economy, 
yet delays disrupt 
passengers and incur 
massive costs to airlines.
• Why This Matters:
Delays cost billions in 
operational disruptions. A 
predictive and explainable 
system improves both 
efficiency and passenger 
experience.
2
Key Insights from EDA
3
Arrival delays peak from 
July to December, likely 
due to holiday traffic and 
adverse weather. Lower 
delays in spring months 
suggest seasonal patterns 
that airlines can leverage 
for better planning.
The average arrival delay 
peaked in 2017 and showed a 
significant drop in 2020, likely 
due to reduced air traffic 
during the pandemic. Delay 
levels have gradually 
increased again post-2020, 
stabilizing around pre
pandemic figures by 2023.
Late Aircraft and Carrier 
delays contribute the most to 
total delay time, indicating 
major operational 
bottlenecks.
In contrast, Weather, NAS, 
and Security delays are 
relatively lower, highlighting 
the potential for controlling 
delays internally.
is_delayed feature (1 for 
delays ≥15 mins, 0 
otherwise) showed a highly 
imbalanced distribution, with 
most flights being not on 
time. This imbalance was 
addressed during modeling 
to ensure the classifier 
doesn’t bias toward the 
majority class. 
4
Top 10 Airport by average arrival delay
• The top 10 airports by average arrival delay reveal 
consistently high delays at major hubs, likely due to heavy 
traffic and congestion.
These airports may benefit from targeted operational 
improvements to reduce arrival bottlenecks.
Correlation Heatmap
• The correlation heatmap shows weak correlations 
between most features, indicating low multicollinearity.
This suggests that each feature contributes 
independently to the delay prediction model.
Methodology & 
Models
Preprocessing
Cleaned missing data, 
feature encoding, standard 
scaling
Feature Engineering
Created is_delayed target 
Removed irrelevant columns
Initial Modeling
Started with Logistic 
Regression as baseline
Found class imbalance 
(most flights on time) 
→ accuracy 
misleadingly high
Tried Multiple Models
Evaluated models:
Logistic Regression, Decision 
Tree, Random Forest, 
Gradient Boosting
All models initially showed 
~100% accuracy due to data 
leakage
Feature Engineering & 
Leakage Handling
Identified and removed 
leakage features (e.g., 
actual arrival time, arrival 
delay itself)
Re-engineered features to 
use only pre-departure 
information
Final Model Selection
Re-trained models 
with cleaned features
Random Forest 
Classifier emerged as 
best performance 
Balanced precision, 
recall, and AUC-ROC
Robust to non-linear 
relationships and 
outliers
SHAP-Based Explainability
Applied SHAP (Shapley values) to 
interpret feature contributions
Found key drivers: scheduled 
departure time, carrier, origin 
airport
Aligned with Operational 
Adjustability focus (controllable 
delays)
Regression for Delay 
Duration
Built a regression model 
to estimate delay in 
minutes
Evaluated using MAE and 
RMSE
OAI-Focused Model
Introduced Operational 
Adjustability Index 
(OAI)
Trained a regressor 
specifically to minimize 
controllable delay types
Combined SHAP + OAI 
to prioritize actionable 
insights
Model Performance & Explainability
Model Evaluation (Random Forest Classifier)
Accuracy: ~100% (initially due to leakage — resolved 
later)
Precision, Recall, F1-score: All balanced post-cleaning
AUC-ROC Score:
Random Forest AUC ≈ 0.933
Significantly higher than Logistic Regression (AUC 
≈ 0.84)
Demonstrates better separability between 
delayed and on-time flights
SHAP (Explainable ML) Analysis
•SHAP summary plot identified top contributors:
•arr_delay, nas_delay, weather_delay, etc.
•High SHAP impact of arr_delay and arr_del15 confirmed data leakage, leading 
to:
•Feature elimination
•Retraining the model with only pre-departure features
•SHAP was also applied on the final cleaned model to ensure transparency & 
trust in predictions
6
Actionable Recommendations
Carrier-Level 
Recommendations:
Optimize crew scheduling 
& aircraft readiness
Implement buffer time 
during high-risk slots 
(evening departures)
System-Level 
Improvements:
Integrate real-time OAI 
delay prediction in airline 
dashboards
Prioritize flights where 
delay cause is actionable
Airport-Level 
Strategies:
Allocate extra ground 
crew at busy hubs
Monitor airport-level 
congestion patterns
Strategic Benefit:
This approach helps 
minimize avoidable delays 
→ enhancing customer 
satisfaction, reducing 
cascading disruptions, 
and optimizing 
operations.
7
Name- Shikha Bharti
Enrolment- 21321028
Thank YOU
8
