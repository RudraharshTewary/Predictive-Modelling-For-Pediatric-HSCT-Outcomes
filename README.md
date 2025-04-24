# Pediatric HSCT: CD34+ Concentration Analysis

Analysis investigating the effect of CD34+ cell concentration on survival outcomes in pediatric Hematopoietic Stem Cell Transplants (HSCT), using data from the UCI ML Repository.

## Goal

To verify if higher CD34+ cell doses (`CD34kgx10d6`) correlate with improved survival in children undergoing unrelated allogeneic HSCT (UHSCT).

## Dataset

*   **Source:** UCI ML Repository - "Bone Marrow Transplants: Children"
*   **Data:** 187 pediatric patients, 37 features. Analysis focused on the 142 complete records.
*   **Key Variable:** `CD34kgx10d6` (CD34+ cell dose/kg)
*   **Target:** `survival_status` (0=Alive, 1=Dead)

## Methodology

1.  **Preprocessing:** Handled missing values, corrected data types, engineered features for time-to-event variables with non-occurrence codes, one-hot encoded 'Disease'.
2.  **EDA:** Visualized distributions and correlations (see `.Rmd` file).
3.  **Modeling:** Trained Logistic Regression, Decision Tree, and Random Forest models using 10-fold CV on the complete subset to predict `survival_status`. Random Forest performed best (72% accuracy).
4.  **Interpretation:** Used Random Forest Feature Importance and Partial Dependence Plots (PDP) for `CD34kgx10d6`.

## Key Findings

*   `CD34kgx10d6` was the most important feature according to the Random Forest model.
*   PDP analysis showed a **positive correlation between higher CD34+ concentration and survival** (lower probability of death).
*   Model accuracy was limited (72%), likely due to the small dataset size.

---
