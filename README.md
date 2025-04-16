# NYC Taxi & Limousine Commission (TLC) Data Analysis & Modeling Portfolio Project

## Overview

This repository documents a comprehensive data analysis and machine learning project undertaken as part of the **Google Advanced Data Analytics Certificate**. The project leverages publicly available NYC Taxi & Limousine Commission (TLC) trip record data to derive insights and build predictive models addressing various business questions relevant to the NYC taxi ecosystem.

Working as a consultant for the fictional firm "Automatidata," the project involved multiple phases, including:

1.  **Preliminary Data Exploration & Understanding:** Initial inspection and identification of key variables and potential data quality issues.
2.  **Exploratory Data Analysis (EDA):** In-depth analysis and visualization to uncover patterns, relationships, and anomalies affecting taxi fares.
3.  **Statistical Analysis & A/B Testing:** Investigating the impact of payment methods on total fare amounts through hypothesis testing.
4.  **Regression Modeling:** Building and evaluating a linear regression model to predict taxi fares.
5.  **Machine Learning Classification:** Developing and evaluating classification models (Random Forest, XGBoost) to predict passenger tipping behavior, incorporating crucial **ethical considerations** that led to refining the project's objective.

## Business Problems & Objectives

This project tackled several key objectives for the NYC TLC:

*   **Understand Data Characteristics:** Perform initial exploration to grasp the structure, quality, and potential challenges within the TLC dataset.
*   **Identify Fare Drivers:** Analyze factors influencing taxi fare amounts and build a model to predict fares based on trip characteristics.
*   **Optimize Revenue Streams:** Investigate whether payment type (cash vs. credit card) significantly impacts the total fare amount received by drivers.
*   **Analyze Tipping Behavior:** Understand factors influencing tipping and predict the likelihood of a passenger being a "generous" tipper (>= 20% tip), after ethically reconsidering an initial problematic request to predict non-tippers.

## Data Source

The analysis utilizes publicly available **NYC TLC Trip Record Data**. This dataset contains detailed information about individual taxi trips, including pickup/dropoff times and locations, trip distances, itemized fares, rates, payment types, and passenger counts.

## Methodology & Analysis

The project followed a structured approach, incorporating various data analysis and machine learning techniques:

1.  **Data Exploration & Cleaning (EDA):**
    *   Initial data loading, inspection, and identification of missing values or anomalies (e.g., trips with zero distance but non-zero fares).
    *   Visualizations (Scatter plots, Box plots, Histograms) using tools like Matplotlib, Seaborn, and Tableau to understand distributions and relationships (e.g., `trip_distance` vs. `total_amount`).
    *   Outlier detection and analysis.
    *   Correlation analysis between relevant features.
2.  **Statistical Testing:**
    *   Formulated hypotheses regarding payment type and total fare amount.
    *   Conducted a two-sample t-test to determine statistical significance.
3.  **Regression Modeling (Fare Prediction):**
    *   Feature selection and preprocessing.
    *   Built a Multiple Linear Regression (MLR) model.
    *   Evaluated model performance using R-squared, MAE, MSE, and RMSE.
    *   Checked regression assumptions (e.g., linearity via Actual vs. Predicted plots).
    *   Interpreted model coefficients (feature importance).
4.  **Classification Modeling (Tipping Prediction):**
    *   **Ethical Pivot:** Rejected the initial request to predict non-tippers due to fairness and accessibility concerns. Reframed the objective to predict "generous" tippers (>= 20%).
    *   Feature engineering and selection relevant to tipping behavior.
    *   Implemented and compared Random Forest and XGBoost classifiers.
    *   Utilized cross-validation and evaluated models using Precision, Recall, F1-Score, and Accuracy.
    *   Analyzed feature importances to understand drivers of generous tipping.
5.  **Reporting & Visualization:** Created executive summaries and visualizations to communicate findings and recommendations clearly to stakeholders.

## Key Findings & Insights

*   **Data Quality:** EDA revealed important anomalies (e.g., outliers in fare/distance relationships, zero-distance trips) requiring careful handling during modeling.
*   **Payment Type Impact:** A/B testing showed a statistically significant difference, with credit card payments associated with higher average total fare amounts compared to cash payments.
*   **Fare Prediction:** The MLR model achieved good performance (R² ≈ 0.87) in predicting taxi fares, with ride duration being a surprisingly impactful (though correlated) feature.
*   **Tipping Behavior:** The classification models (Random Forest chosen, F1 ≈ 0.72) provided reasonable predictions for identifying generous tippers. Key factors influencing tips were identified (details likely in the notebooks/feature importance plots). The ethical consideration driving the objective change was a critical outcome.

## Tools & Technologies

*   **Programming Language:** Python
*   **Core Libraries:** Pandas (Data Manipulation), NumPy (Numerical Operations), Scikit-learn (Modeling, Evaluation), Matplotlib & Seaborn (Visualization)
*   **Visualization (Mentioned):** Tableau
*   **Development Environment:** Jupyter Notebooks
*   **Version Control:** Git / GitHub

## Repository Structure

This repository contains the following key components:

*   **`/notebooks` (Suggested Folder):** Jupyter notebooks detailing the code implementation for each project phase (EDA, A/B Testing, Regression, Classification).
*   **`/summaries` (Suggested Folder):** The executive summary PDF/Image files provided.
*   **`/pace_documents` (Suggested Folder):** Completed PACE strategy documents guiding the project lifecycle (if available).
*   **`README.md`:** This file, providing a comprehensive overview of the project.
*   *(Optional: `/data_samples` or links to data source)*

## How to Use This Repository

1.  Review this `README.md` for a high-level understanding of the project scope, methodology, and findings.
2.  Explore the Jupyter notebooks (`/notebooks`) for detailed code implementation and step-by-step analysis.
3.  Refer to the executive summaries (`/summaries`) for concise reports on each phase's outcomes.
4.  Examine the PACE documents (`/pace_documents`) to understand the structured planning and execution process (if included).

## Contact

*   **LinkedIn:** [linkedin.com/in/nikolaosbiniaris](https://linkedin.com/in/nikolaosbiniaris)
*   **GitHub:** [github.com/NickolasB98](https://github.com/NickolasB98)
*   **Email:** nikosbiniaris98@gmail.com

---
