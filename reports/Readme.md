**Happiness Ordination \- Project Report Suggested Structure**

You are working as a junior policy analyst for the United Nations Sustainable Development Solutions Network (SDSN). The SDSN advises governments and international organizations on policies that promote human well-being and sustainable development. One of your current responsibilities is to help interpret global happiness data in a way that supports evidence-based policy discussions.

You have been provided with a dataset containing international happiness indicators. Your task is to use principal component analysis (PCA) to make sense of this multivariate dataset and to uncover the main dimensions that structure global happiness. The SDSN is particularly interested in understanding whether happiness is dominated by a single underlying gradient or whether multiple, distinct dimensions can be identified. They are also interested in how different happiness-related factors relate to one another, which factors tend to go together, and which appear to reflect separate aspects of well-being.

In addition, the SDSN would like to know how different world regions compare within this reduced-dimensional “happiness space.” Are countries from certain regions characterized by similar combinations of economic, social, and institutional factors? Are there regions that consistently score high or low along particular dimensions revealed by the PCA? Are there countries that stand out as unusual compared to others in their region?

You are asked to prepare a short analytical report aimed at international policy advisors and diplomats. The audience is familiar with global development issues but not with advanced statistical methods. Your report should therefore focus on clear interpretation and meaningful patterns rather than technical details. Use visualizations where appropriate to support your interpretations, and explain what the PCA reveals about global happiness in a way that informs policy-oriented discussions about well-being, inequality, and development priorities.

**Important:** Think about how you want to structure the report yourself. Don’t forget to add the author contributions and AI disclaimer. Do **not** include code in the report. All code and data analysis belong in your Jupyter notebook. 
   
   
   
1\. **Dataset Overview**

| Item | Description |
| :---- | :---- |
| Dataset name | Happy.csv |
| Number of rows |  156 |
| Number of columns |  9 |
| Format file (.csv, .txt, etc) |  csv |
| Authors of the dataset |  Wanja |
| Source (name) |  Github |
| Source (link) | https://github.com/datagus/ASDA2025/tree/main/datasets/homework\_week10 |

   
   
2\. **Dataset Structure**

| Feature/variable | Data type | Description | Number of Unique values | Example values |
| :---- | :---- | :---- | :---- | :---- |
| Overall rank |  int64 |  ranks of different countries from 1 to 156 |  156 |  7.632, 7.594, 7.555, 7.495 |
| Country or region |  object |  names of different countries | 156 |  'Finland', 'Norway', 'Denmark', 'Iceland' |
| Score |  float64 |  happiness scores of different countries | 154 |  7.632, 7.594, 7.555, 7.495 |
| GDP per capita | float64 | GDP per capita score | 147 | 1.305, 1.456, 1.351, 1.343 |
| Social support | float64 | social support | 146 | 1.592, 1.582, 1.59, 1.644 |
| Healthy life expectancy | float64 | healthy life expectancy | 143 | 0.874, 0.861, 0.868, 0.914 |
| Freedom to make life choices | float64 | score of perception | 136 | 0.681, 0.686, 0.683, 0.677 |
| Generosity | float64 | quality of being kind and generous | 122 | 0.202, 0.286, 0.284, 0.353 |
| Perceptions of corruption | float64 | score of the perception of corruption | 111 | 0.393, 0.34, 0.408, 0.138 |

 

3\. **Data cleaning**

| Issue | Names of Columns affected | Description of the Issue | Action Taken |
| :---- | :---- | :---- | :---- |
| Inconsistent column labeling |  N/A |   |   |
| Wrong data types |  N/A |   |   |
| Missing values |  N/A |   |   |
| Duplicates |  N/A |   |   |
| Inconsistent categories |  N/A |   |   |
| Other | N/A |   |   |

 

 

 

4\. **Descriptive statistics**  
Numeric columns  
 

|   | count | mean | std | min | 25% | 50% | 75% | max |
| ----: | ----: | ----: | ----: | ----: | ----: | ----: | ----: | ----: |
| Overall rank | 156.0 | 78.500000 | 45.177428 | 1.000 | 39.75000 | 78.5000 | 117.25000 | 156.000 |
| Score | 156.0 | 5.375917 | 1.119506 | 2.905 | 4.45375 | 5.3780 | 6.16850 | 7.632 |
| GDP per capita | 156.0 | 0.891449 | 0.391921 | 0.000 | 0.61625 | 0.9495 | 1.19775 | 2.096 |
| Social support | 156.0 | 1.213237 | 0.302372 | 0.000 | 1.06675 | 1.2550 | 1.46300 | 1.644 |
| Healthy life expectancy | 156.0 | 0.597346 | 0.247579 | 0.000 | 0.42225 | 0.6440 | 0.77725 | 1.030 |
| Freedom to make life choices | 156.0 | 0.454506 | 0.162424 | 0.000 | 0.35600 | 0.4870 | 0.57850 | 0.724 |
| Generosity | 156.0 | 0.181006 | 0.098471 | 0.000 | 0.10950 | 0.1740 | 0.23900 | 0.598 |
| Perceptions of corruption | 156.0 | 0.112449 | 0.096343 | 0.000 | 0.05100 | 0.0820 | 0.13900 | 0.457 |

   
Category columns

|   | Country or region |
| :---- | :---- |
| Count |  156 |
| Number of unique values |  156 |
| Most frequent value |  1 |
| Most frequent value (frequency) |  1 |
| Least frequent value |  1 |
| Least frequent value (frequency) |  1 |

 

**5\. Analysis \- Research question**

This project analyses the key drivers of national happiness using the World Happiness dataset. The objective is to understand which economic, social, health, and institutional factors explain happiness levels, how these relationships behave across countries, and how reliably happiness can be predicted using a reduced set of variables.

 

The analysis follows a structured pipeline:

1\. 	Exploratory Data Analysis (EDA)

2\. 	Relationship & Interaction Analysis

3\. 	Distribution & Variability Analysis

4\. 	Predictive Modelling & Stability

5\. 	Feature Sufficiency Evaluation

 

## 1\. Exploratory Data Analysis (EDA)

### 1.1 Strongest Drivers of Happiness

Initial correlation analysis shows that happiness is not driven by income alone. While GDP per capita has a strong positive association with happiness, several non-economic factors show equal or stronger relationships.

Key observations:

·   	Social support and healthy life expectancy exhibit correlations comparable to GDP per capita.

·   	Perceptions of corruption show a strong negative relationship with happiness.

·   	Generosity shows weak and inconsistent association.

 

<img width="401" height="245" alt="image" src="https://github.com/user-attachments/assets/5e815354-a609-43bc-b336-257dee52f50a" />



### 1.2 GDP Sufficiency vs Non-Economic Factors

Comparative correlation analysis reveals that GDP per capita alone is not sufficient to explain happiness. Social and health-related variables add substantial explanatory value, indicating that happiness is a multi-dimensional outcome.

<img width="452" height="270" alt="image" src="https://github.com/user-attachments/assets/8e9e3bea-dfd9-4b2a-8619-46848acf3476" />


### 1.3 Social Support vs GDP

Social support demonstrates:

·   	A strong independent association with happiness

·   	An amplifying effect on GDP, where similar income levels yield higher happiness when social support is stronger

This suggests that economic prosperity translates into happiness more effectively in socially cohesive societies.

<img width="452" height="270" alt="image" src="https://github.com/user-attachments/assets/93bb6c7c-e04e-4915-a6e9-87dfb9941ada" />


### 1.4 Corruption and Happiness

Perceptions of corruption have a statistically significant negative relationship with happiness.

·   	Pearson correlation indicates a strong negative association

·   	p-value ≈ 1.21 × 10⁻⁷, confirming high statistical significance

<img width="395" height="245" alt="image" src="https://github.com/user-attachments/assets/9fa4740c-f0c3-493b-abe2-3ef1b7954499" />


## 2\. Relationship & Interaction Analysis

### 2.1 Rank vs Happiness Score

The relationship between overall rank and happiness score is clearly non-linear.

·   	Sharp score differences among top-ranked countries

·   	Flattening in mid-ranked countries

·   	Steeper decline again at the bottom ranks

This pattern arises because rank is derived from the happiness score itself, causing compression at the top and dispersion at the bottom.

 

<img width="452" height="270" alt="image" src="https://github.com/user-attachments/assets/09759f99-150b-412c-9bdc-c5ccdbd2cc88" />


### 2.2 Top 10 Countries: Marginal Differences

Happiness scores among the top 10 countries are tightly clustered:

·   	Small score range

·   	Low standard deviation

This indicates that minor score differences can lead to noticeable rank changes at the top.

<img width="394" height="245" alt="image" src="https://github.com/user-attachments/assets/976550ff-0c6a-4ec8-ac2c-bbb085b056ad" />


### 2.3 Structural Drivers of Low Happiness

Bottom-ranked countries consistently show:

·   	Low GDP per capita

·   	Weak social support

·   	Poor health outcomes

·   	Limited freedom

·   	High perceived corruption

These factors appear structural, not random.

<img width="444" height="245" alt="image" src="https://github.com/user-attachments/assets/d405b9c6-7e2c-43db-97a0-b11fd783e4ba" />

### 2.4 Freedom × Corruption Interaction (EDA)

Exploratory grouping shows that:

·   	High freedom leads to higher happiness only when corruption is low

·   	High corruption suppresses happiness even in relatively free societies

This indicates an interaction pattern, where institutional trust conditions the benefits of freedom.

<img width="373" height="295" alt="image" src="https://github.com/user-attachments/assets/257771b6-e9a2-41dc-aec8-daeffa99e093" />


##  

## 3\. Distribution & Variability Analysis

### 3.1 Distribution of Happiness Scores

The happiness score distribution is approximately normal:

·   	Skewness ≈ 0.015

·   	No meaningful left or right skew

This supports the use of mean-based comparisons and linear models later.

<img width="452" height="270" alt="image" src="https://github.com/user-attachments/assets/e942041c-bdfd-4ad4-831e-f66ca639e82d" />


### 3.2 Variance Compression at the Top

Top-ranked countries show lower variance in happiness scores due to:

·   	Shared structural strengths

·   	Ceiling effects in happiness

·   	Limited room for upward differentiation

·   	 

### 3.3 High Volatility Among Low-Ranked Countries

Low-ranked countries exhibit higher volatility because:

·   	They fail on different dimensions (income, health, institutions, freedom)

·   	Structural weaknesses vary widely

·   	No ceiling effects constrain dispersion

<img width="395" height="195" alt="image" src="https://github.com/user-attachments/assets/312822f3-2076-483c-85b6-4d8b2e56822d" />


## 4\. Predictive Modelling & Stability

### 4.1 Model Comparison

Four models were evaluated:

·   	Linear Regression

·   	Random Forest Regression

·   	Linear Regression \+ PCA

·   	Random Forest \+ PCA

Out-of-sample evaluation was used to avoid data leakage and overfitting.

Key findings:

·   	Random Forest captures non-linear relationships better

·   	PCA improves linear model stability but does not benefit tree-based models

·   	Performance differences between full and reduced models are modest

 

<img width="452" height="224" alt="image" src="https://github.com/user-attachments/assets/48d98b42-0ced-47e6-9f9d-67ce722476f2" />


### 4.2 Out-of-Sample Variable Stability

Stability analysis across multiple train–test splits show:

·   	Most stable variables:

GDP per capita, social support

·   	Moderately stable:

Healthy life expectancy, Freedom, Corruption perception

·   	Most unstable:

Generosity

Generosity’s effect varies widely across samples, indicating limited robustness.

 

<img width="452" height="269" alt="image" src="https://github.com/user-attachments/assets/dc446b0d-bf62-4a0e-a840-40a3b1df9dab" />


## 5\. Minimum Sufficient Feature Set

Exhaustive evaluation of all three-variable combinations shows that the following set achieves near-maximum predictive power:

### Minimum sufficient set

·   	GDP per capita

·   	Social support

·   	Healthy life expectancy

This trio captures the economic, social, and health dimensions of happiness while remaining stable and interpretable.

## Final Conclusion

Happiness is a multi-dimensional outcome driven by the interaction of economic security, social cohesion, health, and institutional trust. While income matters, social support and health outcomes are equally critical, and institutional factors such as corruption significantly shape how freedom and prosperity translate into happiness.

From a predictive perspective, a small, well-chosen subset of variables can explain most of the variation in happiness, while unstable factors like generosity contribute little robust signal.

This analysis demonstrates the value of combining EDA, structural reasoning, and predictive validation to derive reliable and interpretable insights.

6\. AI Disclaimer

AI is used for some visuals and organizing   the report writing.

