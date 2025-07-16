# Case Study – Predicting Patient Readmission

## Problem Scope

**Problem Statement:**  
Develop an AI system to predict the risk of a patient being readmitted to the hospital within 30 days of discharge.

**Objectives:**
1. Identify patients at high risk of readmission to enable early intervention.
2. Reduce overall hospital readmission rates and associated costs.
3. Improve patient outcomes by providing targeted post-discharge care.

**Stakeholders:**
- Hospital administrators (concerned with costs and quality metrics)
- Patients (who benefit from better care and reduced readmission risk)
- Healthcare providers (doctors, nurses, care coordinators)

---

## Data Strategy

**Proposed Data Sources:**
- Electronic Health Records (EHR): Demographics, diagnoses, procedures, medications, previous admissions.
- Lab Results: Blood tests, imaging reports, vital signs.

**Ethical Issues:**
1. Patient privacy: Ensuring all data is de-identified and compliant with regulations (e.g., HIPAA).
2. Algorithmic bias: Risk of the model performing worse for certain demographic groups, leading to unequal care.

**Preprocessing Pipeline:**
1. Missing Value Treatment: Impute missing lab results using median values or flag as missing.
2. Feature Engineering: Create features such as “number of admissions in past year,” “average length of stay,” and “comorbidity count.”
3. Normalization/Scaling: Standardize numerical features (e.g., age, lab values) for model compatibility.
4. Encoding Categorical Variables: One-hot encode diagnosis codes, discharge disposition, etc.

---

## Model Development

**Model Choice and Justification:**  
Logistic Regression: Chosen for its interpretability, which is crucial in healthcare settings. It allows clinicians to understand which factors contribute most to readmission risk.

**Simulated Confusion Matrix and Precision/Recall Calculation:**
Suppose, on a test set of 100 patients, the model produces the following results:

|                | Predicted Readmit | Predicted No Readmit |
|----------------|------------------|----------------------|
| Actual Readmit |        18        |         7            |
| Actual No Readmit |     10        |        65            |

- **Precision:**  
  Precision = TP / (TP + FP) = 18 / (18 + 10) = 0.643
- **Recall:**  
  Recall = TP / (TP + FN) = 18 / (18 + 7) = 0.720

**Role of Class Imbalance:**
In hospital readmission prediction, the number of patients who are readmitted is often much lower than those who are not (class imbalance). This can cause the model to be biased toward predicting “no readmission.” Addressing this may require resampling techniques or using metrics like precision/recall instead of accuracy.

---

## Deployment & Optimization

**Steps to Deploy the Model in a Hospital IT System:**
1. Package the trained model as a REST API (e.g., using Flask or FastAPI).
2. Integrate the API with the hospital’s EHR system for real-time predictions.
3. Ensure secure authentication and logging for all API requests.
4. Monitor model performance and update as needed.

**Strategies for Healthcare Compliance:**
- Ensure all data handling and storage comply with HIPAA or relevant regulations.
- Use encryption for data in transit and at rest.
- Maintain audit logs for all model predictions and data access.

**Method to Address Overfitting:**
- Cross-validation: Use k-fold cross-validation during training to ensure the model generalizes well to unseen data.
