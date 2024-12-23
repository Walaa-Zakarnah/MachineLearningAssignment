# PPV Value Prediction using PyCaret

This project employs PyCaret, a low-code machine learning library, to predict PPV (Peak Particle Velocity) values. The workflow begins with analyzing feature correlations and progresses to building and comparing machine learning models.

## Project Overview

### Dataset Information
- **Original Data Shape:** (5270, 4)
- **Transformed Data Shape:** (5270, 4)
- **Train Set Shape:** (4216, 4)
- **Test Set Shape:** (1054, 4)

### Key Features
- **Numeric Features:** 3
- **Target Variable:** PPV
- **Preprocessing:** Enabled
  - **Numeric Imputation:** Mean
  - **Categorical Imputation:** Mode

### Cross-Validation
- **Fold Generator:** KFold
- **Number of Folds:** 10
- **CPU Jobs:** -1
- **GPU Usage:** Disabled

## Feature Correlations

- **PPV with Gender:** -0.02
- **PPV with Age:** -0.57
- **PPV with Duration:** 0.98

## Models and Performance Metrics

The following table lists the models used and their respective performance metrics:

| Model                      | MAE    | MSE    | RMSE   | R²     | RMSLE  | MAPE   | TT (Sec) |
|----------------------------|--------|--------|--------|--------|--------|--------|----------|
| Extra Trees Regressor      | 0.0103 | 0.0006 | 0.0249 | 1.0000 | 0.0019 | 0.0007 | 0.5240   |
| Light Gradient Boosting    | 0.0334 | 0.0042 | 0.0648 | 0.9999 | 0.0044 | 0.0026 | 0.6550   |
| Extreme Gradient Boosting  | 0.0296 | 0.0029 | 0.0541 | 0.9999 | 0.0037 | 0.0022 | 0.0820   |
| Random Forest Regressor    | 0.0329 | 0.0036 | 0.0593 | 0.9999 | 0.0046 | 0.0025 | 0.6440   |
| Decision Tree Regressor    | 0.0472 | 0.0078 | 0.0879 | 0.9998 | 0.0057 | 0.0032 | 0.0250   |
| Gradient Boosting Regressor| 0.0795 | 0.0184 | 0.1348 | 0.9996 | 0.0119 | 0.0082 | 0.1670   |
| K Neighbors Regressor      | 0.1572 | 0.0492 | 0.2216 | 0.9990 | 0.0352 | 0.0235 | 0.0250   |
| AdaBoost Regressor         | 0.5513 | 0.4250 | 0.6516 | 0.9915 | 0.0973 | 0.0786 | 0.1630   |
| Least Angle Regression     | 1.1116 | 1.7733 | 1.3307 | 0.9644 | 0.1963 | 0.1859 | 0.0190   |
| Bayesian Ridge             | 1.1116 | 1.7733 | 1.3306 | 0.9644 | 0.1963 | 0.1859 | 0.0200   |
| Ridge Regression           | 1.1116 | 1.7733 | 1.3307 | 0.9644 | 0.1963 | 0.1859 | 0.0190   |
| Linear Regression          | 1.1116 | 1.7733 | 1.3307 | 0.9644 | 0.1963 | 0.1859 | 0.6800   |
| Elastic Net                | 1.1196 | 1.7944 | 1.3385 | 0.9640 | 0.2004 | 0.1906 | 0.0200   |
| Lasso Regression           | 1.1216 | 1.7971 | 1.3395 | 0.9639 | 0.2019 | 0.1924 | 0.0200   |
| Huber Regressor            | 1.0857 | 1.8156 | 1.3460 | 0.9636 | 0.2086 | 0.1972 | 0.0460   |

## Metrics Description

| Metric | Description |
|--------|-------------|
| MAE    | Measures average error magnitude. Lower values are better. |
| MSE    | Captures average squared error. Sensitive to outliers. |
| RMSE   | Provides error in the same unit as the target variable. |
| R²     | Explains how well the model predicts the target. Ranges from 0 to 1. |
| RMSLE  | Focuses on proportional differences, less sensitive to large errors. |
| MAPE   | Percentage-based error, useful for interpretability. |
| TT     | Training time for the model in seconds. |

## Installation

1. Clone the repository.
   ```bash
   git clone <repository-url>
   ```

2. Navigate to the project directory.
   ```bash
   cd <project-directory>
   ```

3. Install the required dependencies.
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Run the Jupyter Notebook or Python script for data preprocessing and model training.
   ```bash
   jupyter notebook
   ```

2. Evaluate model performance using the metrics provided.

## Contributing

Contributions are welcome! Please create an issue or submit a pull request for major changes.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
