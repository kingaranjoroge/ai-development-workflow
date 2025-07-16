# Critical Thinking

## Ethics & Bias

**How biased training data could negatively impact patient care:**
- If the training data contains historical biases (e.g., underrepresentation of certain demographic groups or past unequal treatment), the AI model may learn and perpetuate these biases.
- This can result in unfair predictions, such as systematically underestimating readmission risk for certain groups, leading to inadequate care or missed interventions.
- Biased models can erode trust in AI systems and exacerbate existing healthcare disparities.

**Strategy to reduce or detect bias:**
- Implement fairness-aware learning: Use algorithms and evaluation metrics that explicitly measure and mitigate bias (e.g., demographic parity, equalized odds).
- Regularly audit model predictions across different demographic groups to detect disparities.
- Resample or reweight the training data to ensure balanced representation of all groups.

---

## Trade-offs

**Model interpretability vs. accuracy in healthcare:**
- Highly accurate models (e.g., deep neural networks) may be less interpretable, making it difficult for clinicians to understand or trust predictions.
- Interpretable models (e.g., logistic regression, decision trees) may be slightly less accurate but allow for transparency and easier validation by healthcare professionals.
- In healthcare, interpretability is often prioritized to ensure accountability, regulatory compliance, and clinician acceptance.

**Influence of limited hospital resources on model choice and deployment:**
- Limited resources may necessitate choosing simpler, less computationally intensive models that are easier to deploy and maintain.
- Deployment decisions may favor solutions that integrate smoothly with existing IT infrastructure and require minimal ongoing support.
- Resource constraints may also limit the frequency of model retraining and monitoring, so robust, low-maintenance models are preferred.
