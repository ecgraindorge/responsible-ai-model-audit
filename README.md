# Responsible AI Model Audit: Fairness and Explainability in Recidivism Risk Prediction

This project examines the COMPAS recidivism dataset through the lens of responsible AI. Rather than focusing only on predictive performance, this project evaluates subgroup performance, fairness metrics, explainability, and ethical deployment risks.

## Project Purpose

The goal of this project is to demonstrate how a machine learning model can be evaluated beyond aggregate accuracy. The project uses the COMPAS dataset as a case study to explore how predictive models can produce different error patterns across demographic groups.

This project is intended as an educational model audit and should not be interpreted as a recommendation to deploy recidivism prediction systems in criminal justice settings.

## Project Goals

- Explore the COMPAS dataset using responsible data science practices.
- Build a baseline predictive model for two-year recidivism.
- Evaluate model performance across demographic subgroups.
- Compare false positive and false negative rates.
- Use explainability methods to interpret model behavior.
- Create a model card and ethical reflection.

## Dataset

This project uses the public COMPAS dataset released by ProPublica. The data is loaded directly from ProPublica’s public GitHub repository and is not stored in this repository.

## Planned Project Structure

1. Data understanding
2. Exploratory data analysis
3. Baseline model training
4. Fairness evaluation
5. Explainability analysis
6. Model card and ethical reflection

## Tools

This project will use:

- Python
- pandas
- matplotlib
- seaborn
- scikit-learn
- SHAP
- Jupyter Notebook

## Notebooks

| Notebook | Description |
|---|---|
| [01_data_understanding.ipynb](notebooks/01_data_understanding.ipynb) | Loads the COMPAS dataset, reviews the data structure, and identifies the target variable. |
| [02_exploratory_data_analysis.ipynb](notebooks/02_exploratory_data_analysis.ipynb) | Explores demographic variables, COMPAS scores, target distribution, and initial fairness questions. |
| [03_model_training.ipynb](notebooks/03_model_training.ipynb) | Trains baseline classification models and evaluates aggregate model performance. |
| [04_fairness_evaluation.ipynb](notebooks/04_fairness_evaluation.ipynb) | Audits subgroup performance, false positive rates, and false negative rates. |
| [05_explainability_shap.ipynb](notebooks/05_explainability_shap.ipynb) | Uses logistic regression coefficients and SHAP values to interpret model behavior. |
| [06_model_card_and_ethics_reflection.ipynb](notebooks/06_model_card_and_ethics_reflection.ipynb) | Documents intended use, limitations, ethical risks, and responsible AI takeaways. |

## Responsible AI Framing

This project approaches model development as only one part of responsible AI practice. The emphasis is on auditing model behavior, identifying subgroup-level harms, interpreting model decisions, and documenting limitations clearly.

## Key Takeaways

This project demonstrates that responsible AI evaluation requires more than overall model accuracy. A model may perform reasonably well in aggregate while still producing different error patterns across demographic groups.

The project highlights three central lessons:

1. Fairness auditing should examine subgroup-level error rates.
2. Explainability can support model review, but it does not guarantee fairness.
3. Some high-stakes predictive systems may be technically possible but ethically inappropriate for deployment.
