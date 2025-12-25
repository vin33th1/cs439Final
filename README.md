# A Clustered Regression Analysis of Global Inequality Drivers

[cite_start]**Author:** Vineeth Maryada [cite: 1]  
[cite_start]**Links:** [GitHub Repository](https://github.com/vin33th1/cs439Final) [cite: 2] | [cite_start][Video Walkthrough](https://drive.google.com/file/d/1OtqJamzLTbzDhzyalAWYG1619RicZ6gh/view?usp=sharing) [cite: 3]

---

## 📖 Project Overview
[cite_start]Rising income inequality is a critical global issue, but debates on how to solve it are often driven by ideology rather than empirical evidence[cite: 7]. [cite_start]This project aims to develop an interpretable statistical model to quantify the impact of key national factors on inequality[cite: 9].

[cite_start]By utilizing **unsupervised clustering (K-Means)** and **Multiple Linear Regression**, this analysis moves beyond simple correlation to determine if "one size fits all" economic policies work, or if different economies require different interventions[cite: 10, 15].

## 📊 Data Sources
[cite_start]Two disparate datasets were merged using SQL-style inner joins on country and year keys[cite: 13]. [cite_start]Both datasets were sourced from Kaggle[cite: 37]:

1.  [cite_start]**World Bank Development Indicators:** Provided independent variables such as GDP per capita, Tax revenue, and Corruption estimates[cite: 34, 35].
2.  [cite_start]**World Inequality Database (WID):** Provided dependent variables, specifically Pre-tax and Post-tax Gini coefficients[cite: 36].

## 🛠️ Methodology & Techniques

### Data Preprocessing
* [cite_start]**Feature Engineering:** Created a `GDP per capita` variable by dividing Total GDP by population for better data spread[cite: 129, 131].
* **Handling Missing Data:** Replaced "Mean Imputation" with **Dropping NaNs**. [cite_start]Experiments showed imputation reduced standard deviation and created unrealistic spikes; dropping missing values preserved a realistic spread[cite: 86, 87].
* [cite_start]**Standardization:** All numerical features were standardized to prevent large-scale variables (like GDP) from disproportionately influencing model coefficients[cite: 131, 132].

### Modeling Strategy
1.  [cite_start]**K-Means Clustering:** Used to segment countries into groups based on economic similarity[cite: 15, 125].
2.  [cite_start]**Multiple Linear Regression:** Applied to each cluster to interpret the relationship between policy levers (Tax, Education, Health) and the Post-Tax Gini coefficient[cite: 15, 137].

## 🔍 Key Findings
[cite_start]The analysis proved that development stage dictates policy effectiveness, identifying three distinct clusters[cite: 264]:

### 1. Cluster 1: Wealthy Democracies (Strong Fit)
* [cite_start]**$R^2 \approx 0.57$** [cite: 262]
* **Insight:** Validates standard economic theory. [cite_start]Strong institutions (Corruption Control coefficient: -0.057) and Education spending (-0.016) successfully reduce inequality[cite: 253].

### 2. Cluster 2: Emerging Markets (Moderate Fit)
* [cite_start]**$R^2 \approx 0.34$** [cite: 262]
* **Insight:** Results were paradoxical. [cite_start]Health spending reduced inequality, but Education spending correlated with *higher* inequality (+0.008)[cite: 255].

### 3. Cluster 0: Developing Nations (Poor Fit)
* [cite_start]**$R^2 \approx 0.06$** [cite: 263]
* [cite_start]**Insight:** Fiscal policy levers had little to no effect[cite: 258]. [cite_start]Inequality here is likely driven by structural factors (war, geography, political instability) rather than tax policy, rendering standard economic prescriptions ineffective[cite: 258, 267].

## 🚀 Conclusion & Future Work
[cite_start]This project demonstrates that there is no "one size fits all" solution for inequality[cite: 298]. [cite_start]While textbook rules apply to wealthy nations, they break down in the poorest nations[cite: 300].

**Future Directions:**
To better model **Cluster 0 (Developing Nations)**, future work should incorporate non-fiscal variables such as:
* [cite_start]Political Stability [cite: 305]
* [cite_start]Access to Electricity [cite: 305]
* [cite_start]Shadow Economy Size [cite: 305]

---
*Data Sources: [World Bank Indicators](https://www.kaggle.com/datasets/nicolasgonzalezmunoz/world-bank-world-development-indicators) | [cite_start][Gini Coefficient](https://www.kaggle.com/datasets/willianoliveiragibin/gini-coefficient/data)* [cite: 308, 309]
