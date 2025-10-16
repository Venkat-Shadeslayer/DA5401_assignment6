# DA5401_assignment6  (July–Nov 2025)

Author: Venkata Sai Vishwesvar SV
Roll number: BE22B042
Github username : Venkat-Shadeslayer 

## Overview
This repository contains my work for Assignment 6 of the DA5401 course. 

## Executive Summary

This project explores various strategies for **handling missing data** in the **UCI Credit Card Default dataset**, with a focus on understanding how different imputation methods impact downstream model performance. Missing data is a ubiquitous problem in real-world datasets, and the choice of imputation strategy can profoundly influence the accuracy and reliability of predictive models.

### Objective
The objective was to evaluate and compare multiple imputation techniques ,ranging from simple to model-based , and determine which method produces the most accurate imputations and the best-performing classification model for predicting credit card default.

### Methodology Overview
1. **Data Simulation:** Artificially introduced Missing At Random (MAR) values (8%) into two continuous features — `AGE` and `BILL_AMT1`.  
2. **Imputation Strategies Evaluated:**
   - **Strategy 0 (Gold Standard):** Original complete data.  
   - **Strategy 1:** Median Imputation (Baseline).  
   - **Strategy 2:** Linear Regression Imputation.  
   - **Strategy 3a:** K-Nearest Neighbors (KNN) Regression Imputation.  
   - **Strategy 3b:** Decision Tree Regression Imputation.  
   - **Strategy 4:** Iterative Imputation (MICE).  
   - **Strategy 5:** Listwise Deletion (Control).  
3. **Evaluation Metrics:**  
   - **Imputation Accuracy:** Measured using **Mean Squared Error (MSE)** between true and imputed values.  
   - **Downstream Model Performance:** Assessed using a **Logistic Regression classifier**, focusing on **F1-score** and **Recall**.  

### Key Findings
- While the **F1-scores were nearly identical** across most imputation strategies, a deeper analysis using **Mean Squared Error (MSE)** revealed meaningful differences in imputation quality.  
- The **Decision Tree Regression Imputation** method achieved the **lowest MSE**, indicating the most accurate reconstruction of missing values.  
- This improvement translated into a downstream classifier with the **highest recall (0.71)** — demonstrating its effectiveness in correctly identifying defaults while maintaining stable overall performance.  
- The **Iterative Imputer (MICE)** performed competitively but required more computation and offered only marginal gains relative to its complexity.  

### Final Recommendation
**Decision Tree Regression Imputation** is recommended as the optimal strategy for this dataset.  
It combines:
- **High imputation accuracy (lowest MSE)**  
- **Strong recall performance** in the downstream classifier  
- **Conceptual robustness** due to its ability to capture non-linear relationships  

### Conclusion
This study reaffirms that while simple approaches like median imputation provide quick fixes, **model-based imputation techniques** — particularly non-linear ones — can yield substantial improvements.  
The analysis also highlights the importance of evaluating imputation methods not just by downstream metrics like F1-score, but also by **direct imputation accuracy (MSE)** to make informed, data-driven decisions.  
In essence, **investing in a more context-aware imputation strategy** is a reliable way to maximize both data integrity and model performance in any real-world machine learning pipeline.

