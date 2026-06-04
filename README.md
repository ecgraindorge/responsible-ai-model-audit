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

## Responsible AI Framing

This project approaches model development as only one part of responsible AI practice. The emphasis is on auditing model behavior, identifying subgroup-level harms, interpreting model decisions, and documenting limitations clearly.
