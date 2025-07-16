# Short Answer Questions

## Section 1: Problem Definition

**Problem:** Predicting student dropout rates

**Objectives:**
1. Identify students at high risk of dropping out early, so interventions can be provided.
2. Improve overall student retention rates for the institution.
3. Allocate support resources more efficiently to students who need them most.

**Stakeholders:**
- School administrators (who need to improve retention and allocate resources)
- Students (who may benefit from targeted support and interventions)

**Key Performance Indicator (KPI):**
- Reduction in the annual student dropout rate (percentage decrease compared to previous years)

---

## Section 2: Data Collection & Preprocessing

**Relevant Data Sources:**
- Student academic records (grades, attendance, participation)
- Socioeconomic background data (family income, parental education, etc.)

**Potential Bias:**
- Socioeconomic bias: If the dataset over-represents students from certain backgrounds, the model may unfairly predict higher dropout risk for those groups, leading to biased interventions.

**Preprocessing Steps:**
1. Imputation of missing values (e.g., filling in missing attendance records)
2. Normalization of numerical features (e.g., scaling grades to a standard range)
3. Encoding categorical variables (e.g., converting parental education level into numerical format)

---

## Section 3: Model Development

**Model Choice and Justification:**
- Random Forest: It handles both numerical and categorical data well, is robust to overfitting, and provides feature importance for interpretability.

**Data Splitting:**
- Split the dataset into 70% training, 15% validation, and 15% test sets. The training set is used to fit the model, the validation set to tune hyperparameters, and the test set to evaluate final performance.

**Hyperparameters to Tune:**
- Number of trees (n_estimators): More trees can improve performance but increase computation time.
- Maximum tree depth (max_depth): Controls model complexity and helps prevent overfitting.

---

## Section 4: Evaluation & Deployment

**Evaluation Metrics:**
- F1-score: Balances precision and recall, important if both false positives and false negatives are costly.
- ROC-AUC: Measures the model’s ability to distinguish between students who will and won’t drop out, regardless of threshold.

**Concept Drift:**
- Concept drift is when the statistical properties of the target variable change over time (e.g., new factors influencing dropout). Monitor by regularly comparing model predictions to actual outcomes and retrain if performance drops.

**Technical Deployment Challenge and Mitigation:**
- Challenge: Scaling the model to handle predictions for thousands of students in real-time.
- Mitigation: Deploy the model as a cloud-based API with autoscaling to handle variable loads.
