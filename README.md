## Credit Risk Analysis using Machine Learning

This repository contains an exploratory machine learning project focused on
predicting credit risk using structured financial and demographic data.

The project was undertaken as a learning exercise to understand how different
modeling and evaluation choices affect decision quality and interpretability
in high-stakes financial systems.

---

## Problem Context

In credit risk assessment, different types of prediction errors carry unequal
consequences. Incorrectly approving a high-risk applicant can lead to
significant financial loss, whereas incorrectly rejecting a low-risk applicant
primarily affects customer experience.

This project was therefore designed to move beyond accuracy as a single metric
and examine model behaviour under risk-aware evaluation settings.

---

## Data Preparation Decisions

The dataset contains a combination of numerical and categorical attributes.
Categorical features were one-hot encoded to avoid introducing artificial
ordinal relationships between categories such as employment types.

Feature scaling was applied selectively, particularly for models sensitive to
feature magnitude, to ensure stable optimisation behaviour without unnecessarily
transforming tree-based models.

---

## Model Selection Rationale

Logistic Regression was used as an initial baseline model due to its
interpretability, allowing direct inspection of how input features influence
predictions. This was important for understanding model behaviour in a financial
decision-making context.

A Random Forest model was then explored to capture non-linear relationships
present in the data. Comparing these models helped illustrate the trade-off
between transparency and predictive flexibility.

---

## Evaluation Strategy

Rather than optimising for accuracy alone, multiple evaluation metrics were used
to better reflect real-world decision costs. Precision, recall, F1-score, and
ROC-AUC were examined to observe how model performance changes under different
evaluation perspectives.

This approach was intended to highlight the limitations of aggregate metrics
when applied to asymmetric risk settings.

---

## Feature Importance Analysis

Feature importance derived from the Random Forest model was inspected to gain
insight into which attributes most strongly influenced predictions. This step
was included to improve transparency and support interpretability when reasoning
about model outputs.

---

## Limitations and Learning Outcomes

This implementation assumes static borrower behaviour and does not account for
temporal changes in credit patterns. Additionally, no extensive hyperparameter
tuning was performed, as the primary goal was to understand baseline model
behaviour rather than maximise performance.

The project reinforced the importance of aligning evaluation strategies and
model choices with real-world risk considerations, particularly in regulated
domains such as finance.

---

## Tools Used

Python, Pandas, NumPy, scikit-learn, Matplotlib, Seaborn

---

## Note

This project was developed during undergraduate study as part of independent
learning and coursework, with an emphasis on understanding modeling decisions
and evaluation trade-offs rather than building a production-ready system.

