# Capstone-Project-Off.Madison.Avenue

Predictive Behavioral Analytics Using LighthousePE Geolocation Data
  
🧠Overview
This project was completed in collaboration with Off Madison Ave (OMA), a behavioral‑science‑driven creative agency. The goal was to transform multi‑year LighthousePE geolocation data into a predictive system capable of forecasting:

- When a customer will return
- Which location they will visit next

The solution supports personalized engagement, churn prevention, cross‑promotion, and real‑time marketing activation for casino and travel clients.

🎯 Objectives
- Predict customer revisit timing.
- Predict the next location a customer is likely to visit.
- Enable proactive engagement using predictive analytics.
- Support personalized targeting and retention strategies.
- Validate the prediction pipeline on real OMA end‑users.

Assess cross‑domain model portability across casino and travel clients.

🧩 Business Problem
Businesses collect massive amounts of behavioral and mobility data but struggle to convert it into timely, actionable insight.
OMA needed a scalable, interpretable system that could:

- Use historical mobility patterns
- Predict future customer movement
- Integrate seamlessly into marketing workflows
- Improve targeting and engagement timing

🔄 Workflow
The full pipeline included:
1. Exploratory Analysis
2. Cohort Construction
3. Feature Engineering
4. Predictive Modeling
5. Performance Evaluation
6. Prediction Target Creation

🛠️ Technical Approach
1. Time‑Aware Data Split
To avoid temporal leakage, we used a chronological train‑validation‑test split, ensuring models learned only from past behavior.

2. Feature Engineering
Created rich behavioral and temporal features, including:
- Recency & frequency metrics (7/30/90‑day windows)
- Dwell‑time changes
- Visit intervals
- Sessionization
- Temporal patterns (hour‑of‑day, day‑of‑week)

3. Prediction Targets
We engineered two supervised learning targets:
- Revisit timing (Very Soon, Soon, Later, Much Later)
- Next location (Top‑K ranking)

4. Modeling
Models used:
- XGBoost
- Random Forest
- Markov baseline for comparison

Evaluation metrics included:
- Log‑MAE
- RMSE
- R²
- Top‑K accuracy
- AUC & PR‑AUC
- Precision & Recall

📊 Key Results
1. Top predictors included recency, dwell‑time changes, and 7/30/90‑day visit frequencies.
2. Most users revisited within 0–2 hours, showing strong short‑term engagement.
3. Twin Pine Casino & Hotel and Twin Pine Vicinity captured most predicted revisits.

Random Forest achieved:
AUC: 0.90
PR‑AUC: 0.95
Precision: 92.7%
Recall: 79.8%

Next‑Location Prediction (XGBoost)
Model	Score
Markov Baseline	0.65
XGBoost Top‑1	0.73
XGBoost Top‑3	0.92
XGBoost Accuracy (Revisit Timing)	0.55
XGBoost F1 (Revisit Timing)	0.55

🔍 Engagement Behavior Insights
Models accurately captured when and where users return.
1. Short revisit intervals indicate strong real‑time engagement potential.
2. Strong Top‑3 next‑location accuracy confirms the ability to rank user intent.
3. Behavioral probability patterns support segmentation and retention strategies.

The system converts historical movement into forward‑looking predictions, validating readiness for operational use.

📁 Project Deliverables
1. SQL Queries
Reusable scripts for:
Data extraction
Transformation
Time‑aware splits
Cohort creation

2. Cleaned Datasets
Model‑ready datasets for:
Casino clients
Travel clients

3. Python Code Pipeline
End‑to‑end workflow including:
Data ingestion
Cleaning
Feature engineering
Sessionization
Modeling
Evaluation

4. Power BI Dashboard
Interactive dashboards showing:
Revisit timing predictions
Next‑location patterns
Engagement insights
Model performance
