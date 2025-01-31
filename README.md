# Kaggle_sticker_sales_prediction

📌 Project: Sticker Sales Forecasting
🚀 Problem Statement
The objective of this project is to forecast sticker sales across different stores and countries over multiple years. Given historical sales data, the goal is to develop a machine learning model that accurately predicts future sales while considering factors such as:

Seasonality (monthly trends, holidays, weekends)
Store and product interactions
External influences like public holidays and events
The model is evaluated using the Mean Absolute Percentage Error (MAPE), with the aim of minimizing forecasting errors.

🔍 Approaches We Tried
Throughout the project, multiple approaches were tested to improve model performance. Below are the different steps and methods we explored:

1️⃣ Data Preprocessing
Handling missing values in num_sold using grouped median imputation by store-product combinations.
Checked for outliers in sales data and removed extreme values beyond the 99th percentile.
Combined train & test datasets for seamless feature engineering.
2️⃣ Feature Engineering
We extracted meaningful features to improve forecasting accuracy:

Time-Based Features:
day_of_week, month, year
is_weekend (binary feature for Saturdays & Sundays)
Cyclical encoding (sin and cos) for month and day_of_week
Interaction Features:
country_product = country + product
store_product = store + product
Public Holiday Features:
Integrated country-specific holidays (e.g., Christmas, National Day)
Created is_holiday column indicating if the date falls on a public holiday
3️⃣ Model Selection & Training
We experimented with multiple models, comparing their performance:

✅ LightGBM (Best Model) – Fast and handles categorical data well
🛠 Tried but not used in final submission:
XGBoost (slower, similar performance to LightGBM)
LSTM (Deep Learning, but overfitted without more sequential data)
CatBoost (performed well but slightly worse than LightGBM)
🔹 Final Model: LightGBM with hyperparameter tuning.

4️⃣ Hyperparameter Optimization
To further improve results, we tuned key parameters:

learning_rate, max_depth, num_leaves
min_child_samples, reg_alpha, reg_lambda
Used GridSearchCV & Optuna for tuning.
5️⃣ Model Evaluation
Validation MAPE: Achieved ~20%
Leaderboard Score (Kaggle): Continuous improvements with feature refinements.