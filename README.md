A Clustered Regression Analysis of Global Inequality Drivers
📖 Project Overview

Rising income inequality is a critical global issue, yet policy debates are often driven by ideology rather than empirical evidence. This project aims to develop an interpretable statistical model to quantify the impact of key national factors on inequality.

By utilizing unsupervised clustering (K-Means) combined with Multiple Linear Regression, this analysis challenges the "one-size-fits-all" economic policy approach. It investigates whether specific economic levers (such as education spending, tax revenue, and corruption control) are equally effective across different economic contexts.

🎯 Problem Statement

Policymakers often struggle to identify which economic levers effectively reduce the Gini coefficient (an indicator of inequality). This project addresses the question: Do standard economic policies work universally, or do different economies require different interventions?

📊 Data Sources

The analysis merges two distinct datasets using SQL-style inner joins on country and year keys (covering the period 2000–2022):

    World Bank Development Indicators: Provided independent variables such as GDP per capita, Tax Revenue, and Corruption estimates.

World Inequality Database (WID): Provided dependent variables, specifically Pre-tax and Post-tax Gini coefficients.

Both datasets were sourced from Kaggle.

🛠️ Methodology & Tech Stack

Technologies Used: Python, Pandas, Scikit-Learn, Matplotlib, Seaborn.
1. Data Preprocessing

    Feature Engineering: Created a GDP per capita variable by dividing Total GDP by population.

Handling Missing Data: Conducted experiments comparing "Mean Imputation" vs. "Dropping NaNs." Analysis showed that imputation distorted the standard deviation, so rows with missing values were dropped to maintain a realistic spread.

Standardization: All numerical features were standardized to ensure variables with large scales (like GDP) did not disproportionately influence the model.

2. Algorithms

    K-Means Clustering: Used to segment countries into specific groups based on economic similarity.

Multiple Linear Regression: Applied within each cluster to interpret the relationships between national factors and the Post-Tax Gini coefficient.

🔍 Key Findings

The analysis revealed a fundamental policy disconnect across global economies, visualized through three distinct clusters:

Cluster 1: Wealthy Democracies (R2≈0.57)

    Result: The model performed well, confirming standard economic theory.

    Insights: Strong institutions (Corruption Control) and Education spending successfully reduced inequality.

Cluster 2: Emerging Markets (R2≈0.34)

    Result: Moderate model fit with paradoxical findings.

    Insights: Health spending reduced inequality, but Education spending correlated with higher inequality. Surprisingly, corruption estimates in this cluster showed a correlation with decreased inequality.

Cluster 0: Developing Nations (R2≈0.06)

    Result: The model failed to predict inequality.

    Insights: Standard fiscal policy levers (tax and spending) had little to no effect. Inequality in these regions is likely driven by structural factors (e.g., war, geography) rather than fiscal policy, indicating that one-size-fits-all prescriptions are ineffective here.

🚀 Future Work

To improve the model's performance for Cluster 0 (Developing Nations), future iterations should incorporate non-fiscal variables, such as:

    Political Stability

    Access to Electricity

    Shadow Economy Size

These variables may better explain the drivers of inequality in the world's poorest nations where standard fiscal metrics fall short.

📝 Author

    Vineeth Maryada
