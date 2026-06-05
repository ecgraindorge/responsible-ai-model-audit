{

&#x20; "cells": \[

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "O3FMZw8sfPb4"

&#x20;     },

&#x20;     "source": \[

&#x20;       "# Model Card and Ethical Reflection\\n",

&#x20;       "\\n",

&#x20;       "This notebook provides a model card and ethical reflection for the COMPAS responsible AI audit.\\n",

&#x20;       "\\n",

&#x20;       "The purpose of this project is not to recommend the use of recidivism prediction systems. Instead, the purpose is to demonstrate how predictive models can be audited for fairness, subgroup performance, explainability, and responsible AI risks."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "5ch8mh2rfYYX"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Project Overview\\n",

&#x20;       "\\n",

&#x20;       "This project examines the COMPAS dataset through the lens of responsible AI.\\n",

&#x20;       "\\n",

&#x20;       "The project includes:\\n",

&#x20;       "\\n",

&#x20;       "1. Data understanding  \\n",

&#x20;       "2. Exploratory data analysis  \\n",

&#x20;       "3. Baseline model training  \\n",

&#x20;       "4. Fairness evaluation  \\n",

&#x20;       "5. Explainability analysis  \\n",

&#x20;       "6. Model card and ethical reflection  \\n",

&#x20;       "\\n",

&#x20;       "The central question guiding the project is:\\n",

&#x20;       "\\n",

&#x20;       "> How can a predictive model be evaluated not only by overall accuracy, but also by subgroup performance, error distribution, explainability, and ethical risk?"

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "c6e71147"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Summary of Main Findings\\n",

&#x20;       "\\n",

&#x20;       "This project demonstrates why responsible AI evaluation should move beyond aggregate model performance.\\n",

&#x20;       "\\n",

&#x20;       "The baseline logistic regression model achieved moderate overall performance:\\n",

&#x20;       "\\n",

&#x20;       "| Metric | Value |\\n",

&#x20;       "|---|---:|\\n",

&#x20;       "| Accuracy | 0.675 |\\n",

&#x20;       "| Precision | 0.662 |\\n",

&#x20;       "| Recall | 0.567 |\\n",

&#x20;       "| F1 Score | 0.611 |\\n",

&#x20;       "| ROC-AUC | 0.722 |\\n",

&#x20;       "\\n",

&#x20;       "However, the fairness audit showed that aggregate performance does not tell the full story. Error rates differed across demographic groups.\\n",

&#x20;       "\\n",

&#x20;       "For example, in the test set:\\n",

&#x20;       "\\n",

&#x20;       "| Group | False Positive Rate | False Negative Rate |\\n",

&#x20;       "|---|---:|---:|\\n",

&#x20;       "| African-American | 0.331 | 0.318 |\\n",

&#x20;       "| Caucasian | 0.166 | 0.591 |\\n",

&#x20;       "| Hispanic | 0.208 | 0.611 |\\n",

&#x20;       "| Male | 0.266 | 0.413 |\\n",

&#x20;       "| Female | 0.145 | 0.534 |\\n",

&#x20;       "\\n",

&#x20;       "The explainability analysis showed that the model was most strongly influenced by prior offense count and age. Higher prior offense counts increased predicted likelihood of two-year recidivism, while higher age generally lowered predicted likelihood.\\n",

&#x20;       "\\n",

&#x20;       "The central finding is that model auditing requires multiple layers of evaluation: overall performance, subgroup error rates, explainability, and ethical reflection."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "MrQS\_xcGfek3"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Intended Use\\n",

&#x20;       "\\n",

&#x20;       "This project is intended for educational and auditing purposes.\\n",

&#x20;       "\\n",

&#x20;       "Appropriate uses include:\\n",

&#x20;       "\\n",

&#x20;       "- Demonstrating responsible AI audit practices.\\n",

&#x20;       "- Teaching fairness and explainability concepts.\\n",

&#x20;       "- Comparing aggregate performance with subgroup-level performance.\\n",

&#x20;       "- Showing how model documentation can support responsible review.\\n",

&#x20;       "\\n",

&#x20;       "This project should not be used to support actual criminal justice decisions."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "dkObsYuMflBv"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Out-of-Scope Uses\\n",

&#x20;       "\\n",

&#x20;       "This project should not be used to:\\n",

&#x20;       "\\n",

&#x20;       "- Recommend detention, sentencing, parole, bail, or supervision decisions.\\n",

&#x20;       "- Rank individuals by risk in a real criminal justice setting.\\n",

&#x20;       "- Replace human judgment or legal due process.\\n",

&#x20;       "- Claim that recidivism can be predicted in a fully objective or neutral way.\\n",

&#x20;       "- Treat model outputs as causal explanations of human behavior."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "8CQuoA8ZfoLY"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Dataset\\n",

&#x20;       "\\n",

&#x20;       "The project uses the public COMPAS dataset released by ProPublica.\\n",

&#x20;       "\\n",

&#x20;       "The dataset contains 7,214 rows and 53 columns. For this project, the target variable is `two\_year\_recid`, which indicates whether a person was charged with a new offense within two years.\\n",

&#x20;       "\\n",

&#x20;       "In the full dataset, approximately 45.1% of individuals had `two\_year\_recid = 1`, while approximately 54.9% had `two\_year\_recid = 0`.\\n",

&#x20;       "\\n",

&#x20;       "Key variables used in the baseline model include:\\n",

&#x20;       "\\n",

&#x20;       "- Age\\n",

&#x20;       "- Age category\\n",

&#x20;       "- Juvenile felony count\\n",

&#x20;       "- Juvenile misdemeanor count\\n",

&#x20;       "- Juvenile other offense count\\n",

&#x20;       "- Prior offense count\\n",

&#x20;       "- Charge degree\\n",

&#x20;       "\\n",

&#x20;       "Race and sex were not used as model features in the baseline model. However, they were retained for fairness auditing.\\n",

&#x20;       "\\n",

&#x20;       "This distinction is important because removing protected attributes from a model does not necessarily remove bias. Other features may still reflect structural inequities or act as proxies."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "cNGuxiZKfvcq"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Model Summary\\n",

&#x20;       "\\n",

&#x20;       "The project trained baseline classification models to predict two-year recidivism.\\n",

&#x20;       "\\n",

&#x20;       "Two models were compared:\\n",

&#x20;       "\\n",

&#x20;       "- Logistic regression\\n",

&#x20;       "- Random forest\\n",

&#x20;       "\\n",

&#x20;       "Logistic regression was selected as the primary audit model because it performed better than the random forest model on the main aggregate metrics in this analysis and is relatively interpretable compared with more complex models.\\n",

&#x20;       "\\n",

&#x20;       "The logistic regression model achieved:\\n",

&#x20;       "\\n",

&#x20;       "- Accuracy: 0.675\\n",

&#x20;       "- Precision: 0.662\\n",

&#x20;       "- Recall: 0.567\\n",

&#x20;       "- F1 score: 0.611\\n",

&#x20;       "- ROC-AUC: 0.722\\n",

&#x20;       "\\n",

&#x20;       "These metrics suggest moderate predictive performance. However, these aggregate values do not show whether the model distributes errors differently across groups. For that reason, the project evaluates false positive and false negative rates by race and sex in the fairness audit."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "ZPhI-KMMfzMY"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Fairness Considerations\\n",

&#x20;       "\\n",

&#x20;       "The fairness evaluation focused on whether model errors differed across demographic groups.\\n",

&#x20;       "\\n",

&#x20;       "Particular attention was given to:\\n",

&#x20;       "\\n",

&#x20;       "- False positive rates by race\\n",

&#x20;       "- False negative rates by race\\n",

&#x20;       "- False positive rates by sex\\n",

&#x20;       "- False negative rates by sex\\n",

&#x20;       "\\n",

&#x20;       "The subgroup analysis showed that error rates were not evenly distributed.\\n",

&#x20;       "\\n",

&#x20;       "For race, the African-American subgroup had a higher false positive rate than the Caucasian subgroup in this test set. The African-American false positive rate was approximately 0.331, compared with approximately 0.166 for the Caucasian subgroup. This is significant because false positives represent individuals predicted to recidivate who did not recidivate.\\n",

&#x20;       "\\n",

&#x20;       "At the same time, the Caucasian and Hispanic subgroups had higher false negative rates than the African-American subgroup. This shows why fairness evaluation is complex in the fact that different groups may experience different types of error.\\n",

&#x20;       "\\n",

&#x20;       "For sex, the male subgroup had a higher false positive rate than the female subgroup, while the female subgroup had a higher false negative rate than the male subgroup.\\n",

&#x20;       "\\n",

&#x20;       "These results should be interpreted alongside subgroup sample sizes. The African-American and Caucasian groups had larger sample sizes in the test set, while the Asian and Native American groups had very small sample sizes. Small groups can produce unstable error-rate estimates, so fairness conclusions should avoid overinterpreting metrics for very small subgroups."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "1d8d0095"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Why Error Type Matters\\n",

&#x20;       "\\n",

&#x20;       "False positives and false negatives have different ethical consequences.\\n",

&#x20;       "\\n",

&#x20;       "A false positive means the model predicts recidivism when the person does not recidivate. In a criminal justice context, this type of error could contribute to unnecessary supervision, detention, or harsher treatment.\\n",

&#x20;       "\\n",

&#x20;       "A false negative means the model predicts no recidivism when the person does recidivate. This type of error may be framed as a public safety concern.\\n",

&#x20;       "\\n",

&#x20;       "Because these errors carry different consequences, responsible AI auditing should examine both types of error separately instead of relying only on overall accuracy."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "ReKO8Y\_Cf1zr"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Explainability Considerations\\n",

&#x20;       "\\n",

&#x20;       "The explainability notebook used logistic regression coefficients and SHAP values to examine which features influenced model predictions.\\n",

&#x20;       "\\n",

&#x20;       "The global explainability analysis showed that prior offense count and age were the most influential features in the model.\\n",

&#x20;       "\\n",

&#x20;       "- Higher values of `priors\_count` pushed predictions toward a higher likelihood of two-year recidivism.\\n",

&#x20;       "- Higher age generally pushed predictions toward a lower likelihood of two-year recidivism.\\n",

&#x20;       "- Juvenile offense counts, age category, and charge degree had smaller effects compared with prior offense count and age.\\n",

&#x20;       "\\n",

&#x20;       "The local SHAP waterfall example showed how individual features can push a single prediction higher or lower. For that example, age pushed the prediction upward toward class `1`, while prior offense count pushed it downward toward class `0`.\\n",

&#x20;       "\\n",

&#x20;       "Explainability can help identify which variables are driving predictions, but explainability alone does not make a model fair, valid, or ethically appropriate. A model can be explainable and still produce harmful outcomes."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "ysT0B7x6f4T5"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Key Limitations\\n",

&#x20;       "\\n",

&#x20;       "This project has several important limitations:\\n",

&#x20;       "\\n",

&#x20;       "1. The dataset reflects historical criminal justice data, which may contain structural inequities.\\n",

&#x20;       "2. The target variable, two-year recidivism, is based on observed charges and may reflect policing, surveillance, and charging patterns rather than behavior alone.\\n",

&#x20;       "3. The model is a simplified educational baseline and is not optimized for real-world use.\\n",

&#x20;       "4. Fairness metrics can conflict with one another, so no single metric fully determines whether a model is fair.\\n",

&#x20;       "5. Subgroup metrics can be unstable for smaller groups.\\n",

&#x20;       "6. Explainability methods describe model behavior, but they do not establish causality.\\n",

&#x20;       "7. The project does not include stakeholder input from affected communities.\\n",

&#x20;       "8. The project does not evaluate legal, procedural, or institutional safeguards that would be necessary in any high-stakes decision-making context."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "lamU9vEvf6YB"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Ethical Risk Assessment\\n",

&#x20;       "\\n",

&#x20;       "This project highlights several ethical risks associated with high-stakes predictive modeling:\\n",

&#x20;       "\\n",

&#x20;       "- Models may reproduce historical inequities.\\n",

&#x20;       "- Aggregate accuracy can hide subgroup-level harms.\\n",

&#x20;       "- Risk scores can appear more objective than they actually are.\\n",

&#x20;       "- Users may over-rely on model outputs.\\n",

&#x20;       "- Explanations may create a false sense of transparency.\\n",

&#x20;       "- Technical fairness metrics may not capture lived experience or institutional harm.\\n",

&#x20;       "\\n",

&#x20;       "In sensitive domains such as criminal justice, responsible AI requires more than model performance. It requires critical evaluation of whether the system should be built or deployed at all."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "d03f16fa"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Model Card Summary\\n",

&#x20;       "\\n",

&#x20;       "| Category | Documentation |\\n",

&#x20;       "|---|---|\\n",

&#x20;       "| Model type | Logistic regression baseline classifier |\\n",

&#x20;       "| Target variable | `two\_year\_recid` |\\n",

&#x20;       "| Intended use | Educational responsible AI audit |\\n",

&#x20;       "| Out-of-scope use | Any real criminal justice decision-making |\\n",

&#x20;       "| Key performance result | Moderate aggregate performance, ROC-AUC approximately 0.722 |\\n",

&#x20;       "| Key fairness result | Error rates differed across race and sex groups |\\n",

&#x20;       "| Key explainability result | Prior offense count and age were the most influential features |\\n",

&#x20;       "| Primary limitation | Historical criminal justice data may encode structural inequities |\\n",

&#x20;       "| Responsible AI conclusion | The model should be treated as an audit artifact, not a deployable system |"

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "Unda7VTIf9Qo"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Responsible AI Takeaways\\n",

&#x20;       "\\n",

&#x20;       "This project demonstrates several responsible AI lessons:\\n",

&#x20;       "\\n",

&#x20;       "1. Model accuracy is only one part of evaluation.\\n",

&#x20;       "2. Subgroup error rates are essential for identifying potential harms.\\n",

&#x20;       "3. Removing protected attributes does not automatically remove bias.\\n",

&#x20;       "4. Explainability is useful, but it is not the same as fairness.\\n",

&#x20;       "5. Model cards can help document intended use, limitations, and risks.\\n",

&#x20;       "6. Some AI systems may be technically possible but ethically inappropriate for deployment."

&#x20;     ]

&#x20;   },

&#x20;   {

&#x20;     "cell\_type": "markdown",

&#x20;     "metadata": {

&#x20;       "id": "vCD7vfnwf\_X2"

&#x20;     },

&#x20;     "source": \[

&#x20;       "## Conclusion\\n",

&#x20;       "\\n",

&#x20;       "This project demonstrates how a responsible AI audit can move beyond traditional model evaluation.\\n",

&#x20;       "\\n",

&#x20;       "The baseline model achieved moderate aggregate performance, but the fairness audit showed that subgroup error rates varied by race and sex. The explainability analysis showed that the model relied most heavily on prior offense count and age.\\n",

&#x20;       "\\n",

&#x20;       "These findings reinforce the importance of asking more than whether a model performs well overall. Responsible AI evaluation should also ask:\\n",

&#x20;       "\\n",

&#x20;       "- Who experiences the model's errors?\\n",

&#x20;       "- What kinds of errors are most consequential?\\n",

&#x20;       "- Which features drive predictions?\\n",

&#x20;       "- What limitations should be documented?\\n",

&#x20;       "- Should a model like this be used in a high-stakes setting?\\n",

&#x20;       "\\n",

&#x20;       "The primary contribution of this project is not the predictive model itself, but the audit framework used to evaluate it. In sensitive contexts such as criminal justice, technical performance must be considered alongside fairness, explainability, institutional context, and ethical risk."

&#x20;     ]

&#x20;   }

&#x20; ],

&#x20; "metadata": {

&#x20;   "colab": {

&#x20;     "provenance": \[]

&#x20;   },

&#x20;   "kernelspec": {

&#x20;     "display\_name": "Python 3",

&#x20;     "name": "python3"

&#x20;   },

&#x20;   "language\_info": {

&#x20;     "name": "python"

&#x20;   }

&#x20; },

&#x20; "nbformat": 4,

&#x20; "nbformat\_minor": 0

}

