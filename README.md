# A/B Testing Analysis for a Marketing Campaign

## 📊 Project Overview

This project presents a comprehensive analysis of an A/B test conducted to evaluate the effectiveness of a new marketing ad campaign. The primary objective is to determine whether the new ad (`ad` group) leads to a higher conversion rate compared to the existing public service announcement (`psa` group). The analysis involves data cleaning, exploratory data analysis (EDA), and statistical hypothesis testing to derive actionable insights.

---

## Dataset

The dataset used for this analysis is `marketing_AB.csv`, which contains user-level data from the A/B test. The key columns include:

* **user id**: Unique identifier for each user.
* **test group**: The group the user was assigned to ('ad' or 'psa').
* **converted**: A boolean indicating whether the user made a purchase (True) or not (False).
* **total ads**: The total number of ads the user saw.
* **most ads day**: The day of the week the user saw the most ads.
* **most ads hour**: The hour of the day the user saw the most ads.

---

## ⚙️ Methodology

The analysis was conducted in a Jupyter Notebook and follows these steps:

1.  **Data Cleaning**:
    * Loaded the dataset using pandas.
    * Checked for and handled duplicate entries.
    * Dropped irrelevant columns (`Unnamed: 0`, `user id`) to prepare the data for analysis.

2.  **Exploratory Data Analysis (EDA)**:
    * **Univariate Analysis**: Analyzed the distribution of each variable individually. This included plotting count plots and pie charts for categorical data (`test group`, `converted`, `most ads day`, `most ads hour`) and histograms and boxplots for numerical data (`total ads`).
    * **Bivariate Analysis**: Investigated the relationship between each feature and the target variable (`converted`) to uncover initial trends. This was done using stacked bar charts and comparative boxplots.

3.  **Statistical Hypothesis Testing**:
    * **Chi-Squared Test**: Applied to determine if there is a statistically significant association between the categorical variables (`test group`, `most ads day`, `most ads hour`) and the conversion outcome.
    * **T-test / Mann-Whitney U Test**:
        * Checked the assumptions of normality (using the **Shapiro-Wilk test**) and equality of variances (using **Levene's test**) for the `total ads` variable between the converted and non-converted groups.
        * Since the assumptions for a t-test were not met, the **Mann-Whitney U test** (a non-parametric alternative) was performed to determine if there was a statistically significant difference in the number of ads shown to users who converted versus those who did not.

---

## 📈 Key Findings

The analysis yielded several key insights:

* **Test Group Performance**: The `ad` group achieved a conversion rate of **2.55%**, while the `psa` group had a conversion rate of **1.79%**. The Chi-Squared test confirmed that this difference is **statistically significant** (p-value < 0.05).
* **Impact of Ad Timing**: Conversion rates varied significantly by both the day of the week and the hour of the day. For instance, **Mondays** showed the highest conversion rates.
* **Ad Exposure**: The median number of ads seen by users who converted was significantly higher than for those who did not. The Mann-Whitney U test confirmed this observation is **statistically significant** (p-value = 0.0), suggesting that repeated ad exposure is correlated with a higher likelihood of conversion.

---

## 🛠️ Technologies Used

* **Python 3**
* **pandas**: For data manipulation and analysis.
* **numpy**: For numerical operations.
* **matplotlib & seaborn**: For data visualization.
* **scipy**: For statistical hypothesis testing.
* **Jupyter Notebook**: For interactive analysis and reporting.

---
