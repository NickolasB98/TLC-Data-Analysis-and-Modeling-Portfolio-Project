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

*   **`/notebooks`:** Jupyter notebooks detailing the code implementation for each project phase (EDA, A/B Testing, Regression, Classification).
*   **`/summaries`:** The executive summary PDF/Image files provided.
*   **`/pace_documents`:** Completed PACE strategy documents guiding the project lifecycle (if available).
*   **`README.md`:** This file, providing a comprehensive overview of the project.

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

## Final Part Modeling Results

### Overview 

The goal of this project was to create a multiple linear regression and random forest model to predict high rider gratuity or not. This project utilized yellow taxi trips taken in New York City during 2017. The final random forest model performed with 86% accuracy and 72% precision determining what features were most important in separating low tippers from high tippers. Based on the model, the duration, distance, and cost of the trip were most influential in determining a generous tipper (>20%) vs a non-generous one (<20%). 

### Business Understanding 

According to salary.com the average salary for a New York Taxi Driver is around $45,000. This salary is significantly low compared to a median rent value of $6,500 per month. It is important to understand what factors encourage riders to leave tips in order to help drivers obtain a livable wage. 

### Data Understanding

The NYC Taxi and Limousine Commission data came from [NYC.gov](NYC.gov). The data consisted of approximately 408k unique trips and 18 features. The features included information on trip duration and destination, vendor used, toll information, and payment type. The bar chart below shows the breakdown of how many generous tippers (>20%) versus non-generous tippers that exist in the data set. 

<img width="572" alt="image" src="https://github.com/user-attachments/assets/77f8e726-feb2-4415-a188-24fd1292cda9" />

Graph shows the percentage of Non-Generous and Generous Tippers.

In connection to this, a feature was engineered to represent if a ride was taken during rush hour or not. Multiple redundant columns were dropped and reformatted into the proper data type.  

### Modeling and Evaluation 

A random forest model comprising 100 decision trees was used to determine feature importance in who would tip generously or not. The below plot shows that trip duration, distance, and the cost of a fare were the Top 3 most important factors in determining a generous tipper from a non-generous one. The overall model performed with 86% accuracy and 72% precision. 

<img width="749" alt="image" src="https://github.com/user-attachments/assets/3d27eb53-9396-4bd6-a360-4f0b1808e1ab" />

Horizontal bar chart showing feature importance of random forest model.

### Conclusion

This model can benefit Taxi Drivers in knowing if they will be tipped generously or not; however, running a parametric model to determine how much each variable will influence the actual price of the tip. In the future, adding more information on a rider’s past tipping behavior may also be beneficial in helping the stakeholder address their business problem. 
