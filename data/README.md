# Responsible AI Model Audit: Fairness and Explainability in Recidivism Risk Prediction

This project examines the COMPAS recidivism dataset through the lens of responsible AI. Rather than focusing only on predictive performance, this project evaluates subgroup performance, fairness metrics, explainability, model documentation, and ethical deployment risks.

The purpose of this project is educational. It is intended to demonstrate how predictive models can be audited, not to recommend the use of recidivism prediction systems in criminal justice settings.

## Project Purpose

The goal of this project is to demonstrate how a machine learning model can be evaluated beyond aggregate accuracy. The COMPAS dataset is used as a case study to explore how predictive models may produce different error patterns across demographic groups.

This project asks:

- How well does the model perform overall?
- Do false positive and false negative rates differ across groups?
- Which features most strongly influence predictions?
- What limitations should be documented before interpreting model results?
- What ethical risks arise when predictive models are used in high-stakes settings?

## Dataset

This project uses the public COMPAS dataset released by ProPublica. The data is loaded directly from ProPublica’s public GitHub repository and is not stored in this repository.

The primary target variable is `two_year_recid`, which indicates whether a person was charged with a new offense within two years.

## Notebooks

| Notebook | Description |
|---|---|
| [01_data_understanding.ipynb](notebooks/01_data_understanding.ipynb) | Loads the COMPAS dataset, reviews the data structure, and identifies the target variable. |
| [02_exploratory_data_analysis.ipynb](notebooks/02_exploratory_data_analysis.ipynb) | Explores demographic variables, COMPAS scores, target distribution, and initial fairness questions. |
| [03_model_training.ipynb](notebooks/03_model_training.ipynb) | Trains baseline classification models and evaluates aggregate model performance. |
| [04_fairness_evaluation.ipynb](notebooks/04_fairness_evaluation.ipynb) | Audits subgroup performance, false positive rates, and false negative rates. |
| [05_explainability_shap.ipynb](notebooks/05_explainability_shap.ipynb) | Uses logistic regression coefficients and SHAP values to interpret model behavior. |
| [06_model_card_and_ethics_reflection.ipynb](notebooks/06_model_card_and_ethics_reflection.ipynb) | Documents intended use, limitations, ethical risks, and responsible AI takeaways. |

## Report

| Report | Description |
|---|---|
| [model_card.md](reports/model_card.md) | Standalone model card summarizing intended use, limitations, fairness considerations, explainability, and ethical risks. |

## Main Findings

This project shows that aggregate model performance is not enough for responsible AI evaluation. A model may appear reasonable when evaluated with overall metrics, while still producing different error patterns across demographic groups.

The fairness audit examined false positive and false negative rates by race and sex. These error types matter because they have different consequences in a criminal justice context. A false positive may contribute to unnecessary supervision, detention, or harsher treatment, while a false negative may be framed as a public safety concern.

The explainability analysis showed that prior offense history and age were among the strongest drivers of the model’s predictions. However, explainability does not resolve the ethical concerns raised by subgroup performance differences.

## Responsible AI Takeaways

This project demonstrates several responsible AI lessons:

1. Accuracy is only one part of model evaluation.
2. Subgroup error rates are essential for identifying potential harms.
3. Removing protected attributes does not automatically remove bias.
4. Explainability can support model review, but it does not guarantee fairness.
5. Model cards help document intended use, limitations, and risks.
6. Some high-stakes predictive systems may be technically possible but ethically inappropriate for deployment.

## Tools

This project uses:

- Python
- pandas
- matplotlib
- seaborn
- scikit-learn
- SHAP
- Jupyter Notebook / Google Colab
- GitHub

## Responsible AI Framing

This project approaches model development as only one part of responsible AI practice. The emphasis is on auditing model behavior, identifying subgroup-level harms, interpreting model decisions, and documenting limitations clearly.

The project should not be interpreted as a recommendation to deploy recidivism prediction systems. Instead, it is a portfolio and teaching example of how responsible AI audits can combine technical evaluation with ethical reflection.

## Repository Structure

```text
responsible-ai-model-audit/
├── data/
│   └── README.md
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_exploratory_data_analysis.ipynb
│   ├── 03_model_training.ipynb
│   ├── 04_fairness_evaluation.ipynb
│   ├── 05_explainability_shap.ipynb
│   └── 06_model_card_and_ethics_reflection.ipynb
├── reports/
│   └── model_card.md
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore
