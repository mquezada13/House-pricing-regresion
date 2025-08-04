# Machine Learning Project: House Price Prediction

## Overview

This project focuses on predicting house prices using various regression and machine learning techniques. The main goal was to explore different modeling approaches and preprocessing strategies to achieve the best possible prediction accuracy.

---

## Data Preparation

- **Dataset:** `general_data` containing house features and sale prices.
- **Feature selection:** A subset of relevant features named `selected_features` was used.
- **Handling missing values:**  
  - Numeric features imputed using mean values.  
  - Categorical features imputed using the most frequent value.  
- **Categorical encoding:** One-hot encoding applied to categorical variables.
- **Scaling:** Numeric features were scaled using `StandardScaler` to normalize data ranges.

---

## Modeling Approaches Explored

### Linear Ridge Regression

- Used Ridge regression with varying regularization strengths (`alpha`) to control overfitting.
- Evaluated model performance using Mean Squared Error (MSE) and R² score.
- Tested multiple alpha values to find an optimal balance between bias and variance.

### Polynomial Ridge Regression

- Applied `PolynomialFeatures` (degree 2 to 6) to capture nonlinear relationships.
- Combined polynomial feature expansion, scaling, and Ridge regression in a pipeline.
- Compared models of different polynomial degrees to determine the best complexity.
- Found degree 4 with appropriate regularization to provide the best performance.

### Log Transformation of Target

- Applied `log1p` transformation to the target variable (`SalePrice`) to stabilize variance and reduce skewness.
- Trained models on the log-transformed target and back-transformed predictions for evaluation.
- Compared performance with models trained on the original scale.

### Random Forest Regression

- Tested Random Forest as a nonlinear, ensemble-based method.
- Random Forest handled missing values and categorical variables better without explicit preprocessing.
- Showed improvement over linear models but still had some prediction errors.
- Used as a benchmark for model performance comparison.

---

## Results and Insights

- Polynomial Ridge regression with degree 4 and proper regularization consistently outperformed linear Ridge and Random Forest models in terms of accuracy and residual behavior.
- Regularization strength (`alpha`) was critical to control model complexity, especially for polynomial models, preventing overfitting.
- Residual and prediction plots helped visualize model performance and identify the best modeling approach.
- Feature-wise comparisons showed how actual and predicted prices relate across key variables.

---

## Next Steps

- Fine-tune hyperparameters including `alpha` and polynomial degree using grid or randomized search.
- Explore advanced ensemble methods such as Gradient Boosting (XGBoost, LightGBM, CatBoost).
- Perform more extensive feature engineering to improve input data representation.
- Incorporate cross-validation for more reliable model evaluation.
- Analyze feature importances and model interpretability.

---

## Code and Tools

- Data preprocessing using `ColumnTransformer` to separately handle numeric and categorical variables.
- Models implemented with scikit-learn's `Ridge`, `PolynomialFeatures`, `RandomForestRegressor`, and pipelines.
- Visualizations created with matplotlib and seaborn.
- Results saved and analyzed with pandas DataFrames.

---

## Contact

For questions or collaboration, feel free to reach out.

---

*This README summarizes the data exploration, modeling efforts, and conclusions of the house price prediction project.*

