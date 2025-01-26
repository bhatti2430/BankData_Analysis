* # Bank Dataset Analysis with Pandas

This Python performs various data analysis operations on a **bank dataset** (`bank.csv`). It uses the **pandas** library to perform tasks such as data loading, cleaning, analysis, and visualization.

## Table of Contents
- [Table of Contents](#table-of-contents)
- [Libraries Used](#libraries-used)
- [Data Loading](#data-loading)
- [Data Analysis](#data-analysis)
- [Data Cleaning](#data-cleaning)
- [Data Visualization](#data-visualization)
- [Grouping Data](#grouping-data)

## Libraries Used

- `pandas`: For data manipulation and analysis.
  
Make sure you have **pandas** installed. You can install it using pip:

     `pip install pandas`

## Data Loading
- import pandas as pd
- df = pd.read_csv("bank.csv")
- df
  
## Data Analysis
- Checking the Shape of Data
  - df.shape

- Viewing First Rows
  - df.head()

- Viewing Last Rows 
  - df.tail()
  
- Sampling Random Rows
  - df.sample()
  
- Getting Information about the Dataset
  - df.info()
  
- Descriptive Statistics (For Numeric Columns)
  - df.describe()
  
- Descriptive Statistics (For All Columns)
  - df.describe(include="all")

- Checking the Count of Unique Values
  - df['balance'].value_counts()
  
- Filtering Data Base
  - df[df['balance'] > 50000 & (df['education'] == 'NAN')]
  
- Checking Missing Values
  - df.isnull().sum()
  

## Data Cleaning
- Handling Missing Values
  - df["final_balance"] = df['balance'].fillna(df["balance"].mean())
  - df[df['balance'].isnull()]
   
- Dropping Columns 
  - df.drop(['job', 'day'], axis=1, inplace=True)
  - df_cleaned = df.dropna()


## Data Visualization
- Bar Plot
  - df['campaign'].value_counts().plot(kind="bar")

- Pie Chart
  - df['balance'].value_counts().plot(kind="pie")

- Box Plot
  - df[['age']].plot(kind="box")

- Line Plot
  - df['final_balance'].plot(kind="line", title="final_balance", color="green")

- Histogram
  - df['campaign'].plot(kind='hist', bins=5, title='campaign')
  

## Grouping Data
- Grouping by Column
  - df.groupby("campaign").describe()
