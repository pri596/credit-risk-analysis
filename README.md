# Credit Risk Analysis and Default Prediction

##  Overview

Loan default prediction is a critical problem for financial institutions. Incorrect lending decisions—especially approving high-risk borrowers—can lead to significant financial losses and broader economic impact.

This project develops a machine learning system to predict whether a borrower is likely to default, with a focus on **reducing high-risk approvals (false negatives)** while maintaining model interpretability and consistency in decision-making.

---

##  Problem Statement

Banks must evaluate loan applications based on multiple financial and personal factors such as income, credit history, and employment status. Manual or rule-based systems often struggle to:

* Handle large volumes of applications consistently
* Capture complex relationships between features
* Avoid bias and inconsistent decision-making

This project addresses these challenges by learning patterns from historical data to support **data-driven, scalable, and consistent credit risk assessment**.

---

##  Impact

Incorrect loan decisions affect:

* Individuals (students, small business owners, farmers)
* Financial institutions (credit losses)
* Broader economic ecosystems (employment and business continuity)

Reducing incorrect approvals directly contributes to **financial stability and better risk management**.

---

##  System Approach

### 🔹 Input

Borrower-level financial and demographic features

### 🔹 Output

Binary prediction:

* `0` → Low risk (no default)
* `1` → High risk (default)

---

##  Modeling Strategy

Multiple models were used to balance **performance and interpretability**:

### Logistic Regression

* Baseline model
* Provides clear, interpretable relationships between features and risk

### Random Forest

* Captures non-linear relationships
* Reduces variance through ensemble learning

### XGBoost

* Gradient boosting model
* Optimized for high predictive performance

---

##  Data Processing

* One-hot encoding for categorical variables (`drop_first=True` to avoid multicollinearity)
* Feature scaling for models sensitive to magnitude (Logistic Regression)
* Stratified train-test split to preserve class distribution

> The dataset exhibits class imbalance, making accuracy alone an unreliable metric.

---

##  Evaluation Strategy

Given the risk-sensitive nature of the problem, evaluation focuses on:

* **ROC-AUC** → overall model discrimination ability
* **Recall** → ability to correctly identify high-risk borrowers
* **Confusion Matrix** → detailed error analysis

###  Key Insight

> False negatives (predicting a risky borrower as safe) are the most costly, as they directly lead to financial loss.

---

##  Model Performance Summary

| Model               | Accuracy | ROC-AUC  | Recall   |
| ------------------- | -------- | -------  | ------   |
| Logistic Regression | 0.665	   | 0.755119 | 0.671429 |
| Random Forest       | 0.720	   | 0.746964 | 0.871429 |
| XGBoost             | 0.730    | 0.739405 | 0.842857 |

> Recall is emphasized as a critical metric for minimizing financial risk.

---

##  Overfitting Analysis

Train vs test ROC-AUC was used to evaluate generalization:

* Tree-based models (Random Forest, XGBoost) show higher training performance, indicating potential overfitting
* Logistic Regression demonstrates more consistent generalization

This highlights the trade-off between **model complexity and stability**

---

##  Model Interpretability (SHAP)

SHAP (SHapley Additive Explanations) was used to understand model predictions:

### Global Insights

* Loan amount, account status, and financial stability are key drivers of risk

### Local Insights

* Higher loan amounts and weaker financial indicators push predictions toward default

> The model’s behavior aligns with financial intuition, increasing confidence in its predictions.

---

##  Model Comparison & Final Decision

* Logistic Regression offers strong interpretability but lower predictive performance
* Random Forest improves performance but lacks transparency
* XGBoost achieves the best overall performance (highest ROC-AUC and recall)

###  Final Model Selection

XGBoost is selected as the final model due to its superior ability to identify high-risk borrowers and minimize costly misclassifications.

---

##  Key Takeaways

* Accuracy alone is insufficient for risk-sensitive problems
* Recall is critical for minimizing financial loss
* There is a trade-off between interpretability and performance
* Explainability tools like SHAP are essential for real-world deployment

---

##  Limitations

* No temporal modeling of borrower behavior
* Limited feature scope
* No extensive hyperparameter tuning
* No fairness/bias analysis

---

## Future Improvements

* Hyperparameter optimization (GridSearch / Bayesian tuning)
* Incorporating time-series financial data
* Deployment as a real-time risk scoring system
* Bias and fairness evaluation in lending

---

##  Tech Stack

* Python
* Pandas, NumPy
* Scikit-learn
* XGBoost
* SHAP
* Matplotlib, Seaborn

---

##  Conclusion

This project demonstrates a complete machine learning pipeline for credit risk prediction, with emphasis on evaluation rigor, interpretability, and real-world applicability rather than just predictive performance.

It reflects a shift from simply building models to making informed, risk-aware decisions using machine learning. The system is designed to support decision-making in real-world lending scenarios by balancing predictive performance with interpretability and risk-awareness
