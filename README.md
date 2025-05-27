# Task 2 – Exploratory Data Analysis on Titanic Dataset 

This repository contains Task 2 of the AI & ML Internship: Exploratory Data Analysis (EDA) using the Titanic Dataset.

- Objective: Visually and statistically explore the Titanic dataset to uncover patterns, trends, anomalies, and key features relevant to survival.

## Project Contents

- `Titanic-Dataset.csv` — Original dataset  
- `Task_2_EDA.ipynb` — Python script for all preprocessing + visualizations  
- `Visual Images` — Folder containing all visual plots  
- `README.md` — This documentation
- 'task2.pdf' — The Given task Assigned by Elevate Labs

## Tools Used
- Python, Pandas, NumPy, Seaborn, Matplotlib

## Data Preparation Summary

- Missing values in Age and Embarked were filled using median and mode.
- Cabin column dropped due to high missingness.
- New features created:
  - `FamilySize = SibSp + Parch + 1`
  - `Title` extracted from Name
- Rare titles grouped into a single 'Rare' category.

##  Exploratory Data Analysis (EDA)

###  1. Basic Distributions

####  Survival Count
- Most passengers did not survive (label = 0).![Survival count](https://github.com/user-attachments/assets/7906336e-8574-4753-871f-9f36b7dc26d8)


####  Passenger Class Count
- Most passengers were in 3rd class.![Passenger class count](https://github.com/user-attachments/assets/afb185b1-245b-4436-97d6-d5ae1daa1c6f)


### 2. Univariate Numeric Distributions

####  Age Distribution
- Majority of passengers were aged 20–40.
- Age distribution is slightly right-skewed.
- There are several children and elderly.![Age distribution](https://github.com/user-attachments/assets/414208ba-45ef-495f-b194-c895964a6a66)


####  Fare Distribution
- Fare is highly right-skewed.
- A few passengers paid extremely high fares (outliers).![Fare distribution](https://github.com/user-attachments/assets/2d081f4a-6cf0-453a-a935-ffdb27dd123c)


####  Family Size
- Most passengers were either alone or had small family sizes.
- Medium family sizes (3–4) are relatively rare but important.![Family Size Distribution](https://github.com/user-attachments/assets/2ccd1d14-6d54-4910-90d5-8f391511c54b)


### 3. Boxplots (Outlier Detection)

- Fare has extreme outliers beyond 300.![Boxplot Fare](https://github.com/user-attachments/assets/97964593-fbcd-4729-bfc7-1f5cf9a0b8b4)

- Age and FamilySize distributions show mild outliers.![Boxplot Age](https://github.com/user-attachments/assets/af8ee53f-f88e-4e10-b9a7-18ea91255caa) ![Boxplot Family Size](https://github.com/user-attachments/assets/f7e25020-2e35-49cf-bfa1-a68ff9aa97ba)


- Boxplots help reveal potential anomalies and distribution spread.

### 4. Bivariate Analysis – Survival vs Features

#### Age by Survival
- Survivors tend to be slightly younger.
- More non-survivors are seen in the middle-aged group.![Age distribution by Survival](https://github.com/user-attachments/assets/ef3c2cc6-1521-4602-8b54-4bd6b9510c78)


#### Fare by Survival
- Survivors generally paid higher fares.
- Indicates wealth/class could have impacted survival.![Fare distribution by Survival](https://github.com/user-attachments/assets/89013671-4d33-49e4-9bf0-94cfebe03e38)


###  5. Grouped Survival Rates (Categorical)

#### By Sex
- Females had much higher survival rates.![Survival rate by Sex](https://github.com/user-attachments/assets/9197a235-d983-4ec9-a513-532ee068efe6)


#### By Pclass
- 1st class passengers survived more.
- 3rd class had the lowest survival.![Survival rate by passenger class](https://github.com/user-attachments/assets/6f5886c5-96f6-49cc-9005-28f308490bdc)


#### By Embarked
- Port 'C' (Cherbourg) had the best survival outcomes.
- Most people embarked from 'S', but survival was lower there.![Survival rate by Embarked Port](https://github.com/user-attachments/assets/ac64f3e8-681f-4443-bca1-047f1daf7095)


#### By Family Size
- Passengers with 3–4 family members had the highest survival rate.
- Large families and solo travelers had worse outcomes.![Survival rate by Family size](https://github.com/user-attachments/assets/ea0ebee3-233a-4bd7-ada6-2959ec2681ef)


#### By Title
- Miss, Mrs, and Master had better survival rates.
- Rare titles (military or nobility) had poor survival rates.![Survival rate by Title](https://github.com/user-attachments/assets/e3719e5b-7724-4fa8-b629-42c56e01ebf9)


###  6. Feature Relationships

#### Correlation Heatmap
- Fare positively correlated with survival.
- Pclass negatively correlated (as class increases numerically, survival drops).
- FamilySize has low but slightly negative correlation.![Correlation Matrix](https://github.com/user-attachments/assets/fff81740-ba48-4b7a-a20b-2352953a9426)


#### Pairplot
- Shows separability in Fare and Age between survivors and non-survivors.
- Highlights potential feature importance for modeling.![Pairplot of Numeric Features by Survival](https://github.com/user-attachments/assets/eb3aca3c-704c-4972-86b3-2e88411ec8e0)

##  Key Insights, Patterns & Anomalies

###  Insights
- Females, younger passengers, and 1st class travelers had the highest survival.
- Fare and Title are important indicators of social class, which impacted survival.

###  Patterns
- Strong survival pattern by sex and class.
- Medium-sized families (3–4 members) had better outcomes.
- Passengers who embarked at Cherbourg survived more often.

###  Anomalies
- Fare distribution has major outliers.
- Some passengers with high fares still did not survive — possible anomalies.
- A few solo travelers survived despite low survival odds.

##  Summary Table

| Feature     | Insight |
|-------------|---------|
| Sex         | Strongest indicator of survival; females prioritized |
| Pclass      | 1st class passengers had best survival chances |
| Age         | Children and young adults more likely to survive |
| Fare        | Higher fare correlates with better outcomes |
| FamilySize  | Medium-sized families had the best odds |
| Embarked    | Port 'C' had best survival rates |
| Title       | Social class and gender reflected in title influenced survival |

---

##  Conclusion

This analysis helps identify meaningful features for predictive modeling. It also highlights the importance of class, gender, and family size in survival outcomes.

