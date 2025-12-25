# A Clustered Regression Analysis of Global Inequality Drivers

**Author:** Vineeth Maryada  
---

## 📖 Project Overview
Rising income inequality is a critical global issue, but debates on how to solve it are often driven by ideology rather than empirical evidence. This project aims to develop an interpretable statistical model to quantify the impact of key national factors on inequality.

By utilizing **unsupervised clustering (K-Means)** and **Multiple Linear Regression**, this analysis moves beyond simple correlation to determine if "one size fits all" economic policies work, or if different economies require different interventions.

## 📊 Data Sources
Two disparate datasets were merged using SQL-style inner joins on country and year keys. Both datasets were sourced from Kaggle:

1.  **World Bank Development Indicators:** Provided independent variables such as GDP per capita, Tax revenue, and Corruption estimates.
2.  **World Inequality Database (WID):** Provided dependent variables, specifically Pre-tax and Post-tax Gini coefficients.

## 🛠️ Methodology & Techniques

### Data Preprocessing
* **Feature Engineering:** Created a `GDP per capita` variable by dividing Total GDP by population for better data spread.
* **Handling Missing Data:** Replaced "Mean Imputation" with **Dropping NaNs**. Experiments showed imputation reduced standard deviation and created unrealistic spikes; dropping missing values preserved a realistic spread.
* **Standardization:** All numerical features were standardized to prevent large-scale variables (like GDP) from disproportionately influencing model coefficients.

### Modeling Strategy
1.  **K-Means Clustering:** Used to segment countries into groups based on economic similarity.
2. **Multiple Linear Regression:** Applied to each cluster to interpret the relationship between policy levers (Tax, Education, Health) and the Post-Tax Gini coefficient.

## 🔍 Key Findings
The analysis proved that the development stage dictates policy effectiveness, identifying three distinct clusters:

### 1. Cluster 1: Wealthy Democracies (Strong Fit)
* **$R^2 \approx 0.57$** 
* **Insight:** Validates standard economic theory. Strong institutions (Corruption Control coefficient: -0.057) and Education spending (-0.016) successfully reduce inequality.

### 2. Cluster 2: Emerging Markets (Moderate Fit)
* **$R^2 \approx 0.34$** 
* **Insight:** Results were paradoxical. Health spending reduced inequality, but Education spending correlated with *higher* inequality (+0.008).

### 3. Cluster 0: Developing Nations (Poor Fit)
* **$R^2 \approx 0.06$** 
* **Insight:** Fiscal policy levers had little to no effect. Inequality here is likely driven by structural factors (war, geography, political instability) rather than tax policy, rendering standard economic prescriptions ineffective.

## 🚀 Conclusion & Future Work
This project demonstrates that there is no "one size fits all" solution for inequality[cite: 298]. [cite_start]While textbook rules apply to wealthy nations, they break down in the poorest nations.

**Future Directions:**
To better model **Cluster 0 (Developing Nations)**, future work should incorporate non-fiscal variables such as:
* Political Stability 
* Access to Electricity 
* Shadow Economy Size

---
*Data Sources: [World Bank Indicators](https://www.kaggle.com/datasets/nicolasgonzalezmunoz/world-bank-world-development-indicators) | [Gini Coefficient](https://www.kaggle.com/datasets/willianoliveiragibin/gini-coefficient/data)* 
