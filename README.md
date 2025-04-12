# California Housing Price Prediction

This project predicts the median house value in California using machine learning models. It demonstrates data preprocessing, normality testing, and regression modeling.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Code Explanation](#code-explanation)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/eddythemachine/linear_regression_learning/your-project-name.git
   ```
2. Install dependencies:
   ```bash
!pip install pandas
!pip install numpy 
!pip install matplotlib.pyplot 
   ```
3. (Optional) Set up a virtual environment:
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows use `env\Scripts\activate`
   ```

## Usage

1. Load the dataset and check for missing values:
   ```python
   import pandas as pd
   df = pd.read_csv("housing.csv")
   print(df.head())
   ```
2. Train a machine learning model:
   ```bash
   python train_model.py --input data.csv
   ```
3. For a detailed explanation of the regression analysis, see the notebook: [notebooks/regression_analysis.ipynb](notebooks/regression_analysis.ipynb).

## Features
- Predict median housing prices based on various demographic features.
- Visualize data distributions and correlation between features.
- Test normality of the target variable using statistical tests.

## Code Explanation

1. **Data Preprocessing**:
   - The data is first cleaned by removing any missing values.
   - A log transformation is applied to the target variable to stabilize variance.

2. **Model Training**:
   - The data is split into training and testing sets.
   - A Random Forest Regressor is trained to predict the target variable.

3. **Normality Testing**:
   - We use D'Agostino's K-squared test to check if the target variable follows a normal distribution.

## Contributing

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.



## Acknowledgments

- Thank you to the developers of the **California Housing dataset** available on [Kaggle](https://www.kaggle.com/camnugent/train).
- Inspired by the book "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.

---

### Importance of Normality Testing

Normality testing is crucial in statistical analysis and machine learning for several reasons:

- **Assumption Verification**: Many statistical methods, including linear regression, assume that the residuals (errors) are normally distributed. Normality testing helps verify this assumption, ensuring the validity of the results.

- **Model Performance**: Non-normality can lead to biased estimates, affecting the performance of models. For instance, if the target variable is skewed, it may lead to inefficient parameter estimates and unreliable predictions.

- **Statistical Inference**: Normality is essential for conducting hypothesis tests and constructing confidence intervals. If the data is not normally distributed, the results of these tests may not be valid.

- **Outlier Detection**: Normality tests can help identify outliers in the data, which can significantly impact the results of statistical analyses and model performance.

### Using D'Agostino's K-squared Test

D'Agostino's K-squared test is a popular method for assessing normality because:

- **Combines Skewness and Kurtosis**: The test evaluates both skewness (asymmetry of the distribution) and kurtosis (tailedness of the distribution) to determine how much the distribution deviates from normality.

- **Robustness**: It is robust to sample size and can be applied to small and large datasets.

- **Statistical Output**: The test provides a K-squared statistic and a p-value, allowing for hypothesis testing. A low p-value (typically < 0.05) indicates that the null hypothesis (that the data is normally distributed) can be rejected.

### Normalization Techniques

To address non-normality, several transformation techniques can be applied:

1. **Log Transformation**:
   - **Purpose**: Reduces right skewness in the data.
   - **How it Works**: By applying the logarithm, large values are compressed, making the distribution more symmetric.
   - **Use Case**: Effective for data with exponential growth patterns or when the target variable has a long right tail.

2. **Square Root Transformation**:
   - **Purpose**: Reduces right skewness, similar to log transformation but less aggressive.
   - **How it Works**: Takes the square root of each value, which can help stabilize variance.
   - **Use Case**: Useful for count data or when the data is moderately skewed.

3. **Box-Cox Transformation**:
   - **Purpose**: A family of power transformations that can stabilize variance and make the data more normal.
   - **How it Works**: It applies a power transformation based on a parameter that is estimated from the data.
   - **Use Case**: Suitable for positive data and can adapt to different types of skewness.

### Conclusion

Normality testing and transformation techniques are essential for ensuring the validity of statistical analyses and improving model performance. By using D'Agostino's K-squared test, along with transformations like log, square root, and Box-Cox, you can effectively address non-normality in your data, leading to more reliable and interpretable results in your analyses.
