# Linear Regression Introduction

This Jupyter Notebook provides an introduction to linear regression, including importing libraries, loading data, checking for missing values, and dropping missing values. It also covers normality tests, including the Shapiro-Wilk test and the D'Agostino's K-squared test.

## Table of Contents

* [Importing Libraries](#importing-libraries)
* [Loading Data](#loading-data)
* [Checking for Missing Values](#checking-for-missing-values)
* [Dropping Missing Values](#dropping-missing-values)
* [Normality Tests](#normality-tests)
* [Shapiro-Wilk Test](#shapiro-wilk-test)
* [D'Agostino's K-squared Test](#dagostinos-k-squared-test)

## Importing Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

Loading Data
df = pd.read_csv("housing.csv")
Checking for Missing Values


missing_values_sum = df.isnull().sum()
print(f"The total number of missing values in the DataFrame is: {missing_values_sum}")
Dropping Missing Values


df.dropna(inplace=True)
Normality Tests
Shapiro-Wilk Test


from scipy.stats import shapiro
statistic, pvalue = shapiro(df.target.values)
print(f"pvalue: {pvalue:.5f}")
D'Agostino's K-squared Test


from scipy.stats.mstats import normaltest
statistic, pvalue = normaltest(df.target.values)
print(f"pvalue: {pvalue:.5f}")
Conclusion
This notebook provides a basic introduction to linear regression and normality tests. It covers the Shapiro-Wilk test and D'Agostino's K-squared test, which are used to determine if a dataset follows a normal distribution. The notebook also includes code for loading and manipulating data, as well as visualizing the distribution of the target variable.


Contributors
Eddythemachine

Acknowledgments
This notebook was created using Jupyter Notebook.
The data used in this notebook is from the California Housing dataset.


Let me know if you'd like further edits!
