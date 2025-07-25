Adult Income - Exploratory Data Analysis (EDA) Project
Project Overview
This project focuses on performing a comprehensive Exploratory Data Analysis (EDA) on the "Adult Census Income" dataset from Kaggle. The primary goal is to understand the underlying patterns, relationships, and key insights within the data that could influence an individual's income level, ultimately laying the groundwork for a future predictive modeling (classification) task.

Dataset
The dataset used in this analysis is the "Adult Income" dataset, originally hosted on Kaggle. It contains various features describing individuals and aims to predict whether an individual's income is over $50,000 annually.

Source: Kaggle: Adult Census Income

Key Features: Includes a rich mix of numerical (e.g., age, hours-per-week) and categorical (e.g., education, marital-status, occupation, sex) features, making it ideal for demonstrating various EDA techniques.

Exploratory Data Analysis (EDA) Sections & Key Findings
This EDA was conducted following a structured approach, covering various aspects of data understanding and visualization.

1. Overall Data Structure and Information
The df_adult.head() output shows initial rows with diverse data types. df_adult.info() reveals approximately 48,842 entries and 15 columns, with object types for categorical data and int64/float64 for numerical. df_adult.describe() provides statistics for numerical columns like age and hours-per-week. The missing values summary (from df_adult.isnull().sum()) indicates some columns (e.g., workclass, occupation, native-country) have missing values, often represented as '?' in this dataset.

2. Examining the Target Variable (income)
df_adult['income'].value_counts() shows a significant class imbalance, with the <=50K category having a much higher count than >50K. The bar chart visually confirms this imbalance, illustrating that the majority of individuals in the dataset earn less than or equal to $50,000 annually.



3. Examining Numerical Variables
Histograms and boxplots for age, education-num, and hours-per-week reveal their distributions. age typically shows a right-skew, while education-num might have multiple peaks. capital-gain and capital-loss exhibit extreme right-skewness and many outliers, as most values are zero, visible in their boxplots.



4. Examining Categorical Variables
df_adult[col].value_counts() outputs frequency tables for selected categorical columns like workclass and education. Bar charts visually represent these frequencies, showing the most common categories (e.g., 'Private' for workclass, 'HS-grad' for education). This helps identify dominant groups and potential data quality issues like '?' values if not handled.



5. Examining Correlation Between Numerical Variables
The heatmap of the correlation matrix for numerical features (e.g., age, education-num, hours-per-week) shows their linear relationships. While no extremely strong correlations are typically observed among these, education-num and age might show a weak positive correlation. Scatterplots like age vs. hours-per-week visually confirm these relationships and reveal data density.



6. Examining Relationship Between Categorical Variables and Income
Stacked bar charts, generated from pd.crosstab(df_adult[col], df_adult['income'], normalize='index'), effectively show the proportion of income levels within each category of features like education, occupation, and sex. For instance, these plots clearly demonstrate that individuals with higher education levels or certain occupation types (e.g., 'Exec-managerial', 'Prof-specialty') have a significantly higher percentage of >50K income. The sex plot typically shows a higher proportion of >50K income for males compared to females.



Tools and Technologies
Python: Programming language for data analysis.

Pandas: Data manipulation and analysis library.

NumPy: Numerical computing library.

Matplotlib: Plotting library (used for basic plot configurations).

Seaborn: Statistical data visualization library (used for creating aesthetically pleasing and informative plots).

Google Colab: Cloud-based Jupyter notebook environment for execution.

Author
Omidreza Ahmadi/omidrezaasdev
