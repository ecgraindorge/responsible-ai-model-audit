# Model Card: COMPAS Responsible AI Audit

## Model Overview

This project uses a baseline logistic regression model to examine responsible AI auditing practices using the public COMPAS dataset.

The goal of this model is educational. It is used to demonstrate fairness evaluation, subgroup error analysis, and explainability techniques.

This model should not be used for real criminal justice decisions.

## Intended Use

Appropriate uses include:

- Teaching responsible AI model auditing
- Demonstrating fairness metrics
- Comparing aggregate and subgroup performance
- Exploring explainability tools
- Supporting discussion about high-stakes AI systems

## Out-of-Scope Use

This model should not be used to:

- Make bail, sentencing, parole, detention, or supervision decisions
- Rank individuals by risk in a real-world legal setting
- Replace legal judgment or due process
- Claim objective or neutral prediction of human behavior
- Support deployment of recidivism prediction systems

## Dataset

The project uses the public COMPAS dataset released by ProPublica.

The target variable is `two_year_recid`, which indicates whether a person was charged with a new offense within two years.

The baseline model uses:

- Age
- Age category
- Juvenile felony count
- Juvenile misdemeanor count
- Juvenile other offense count
- Prior offense count
- Charge degree

Race and sex are not used as model features, but they are retained for fairness auditing.

## Main Findings

The model’s predictions were most strongly influenced by prior offense history and age.

The fairness audit showed that aggregate performance metrics are not enough. Subgroup-level false positive and false negative rates varied across demographic groups, which means responsible AI evaluation must examine who experiences model errors and what consequences those errors may have.

## Fairness Considerations

The project evaluates whether model errors differ across demographic groups.

The audit focuses on:

- False positive rates by race
- False negative rates by race
- False positive rates by sex
- False negative rates by sex

A key lesson from this project is that removing protected attributes does not automatically remove bias. Other variables may still reflect historical inequities or act as proxies.

## Explainability

The project uses logistic regression coefficients and SHAP values to examine which features influence predictions.

Explainability helps describe model behavior, but it does not prove that a model is fair, valid, or appropriate for deployment.

## Limitations

This project has several limitations:

1. The dataset reflects historical criminal justice data.
2. The target variable may reflect policing, charging, and surveillance patterns.
3. The model is a simplified educational baseline.
4. Fairness metrics may conflict with one another.
5. Subgroup metrics can be unstable for small groups.
6. Explainability methods do not establish causality.
7. The project does not include stakeholder input from affected communities.

## Ethical Summary

This project is best understood as a responsible AI audit, not a deployment-ready predictive system.

The main contribution is the audit framework: evaluating model performance, subgroup error rates, explainability, limitations, and ethical risk.
