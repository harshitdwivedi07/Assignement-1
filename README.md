# Medical Insurance Cost Prediction using Multiple Linear Regression

## Objective
Predict medical insurance charges of customers based on personal and
health-related information using a Multiple Linear Regression model.

## Dataset Link
Medical Cost Personal Insurance Dataset (Kaggle):
https://www.kaggle.com/datasets/mirichoi0218/insurance

## Libraries Used
- pandas
- numpy
- scikit-learn
- matplotlib

## Methodology
1. Loaded the dataset and identified numerical features (age, bmi, children),
   categorical features (sex, smoker, region), and the target variable
   (charges).
2. Checked for missing values (none found), encoded categorical variables
   (label encoding for sex/smoker, one-hot encoding for region), and split
   the data into 80% training and 20% testing sets.
3. Trained a Multiple Linear Regression model using age, sex, bmi, children,
   smoker, and region to predict charges.
4. Evaluated the model using MAE, MSE, and R2 Score, and plotted actual vs
   predicted charges.

## Results
| Metric | Value |
|--------|-------|
| MAE | 4181.19 |
| MSE | 33,596,915.85 |
| R2 Score | 0.7836 |

**Observations:**
1. Smoking status has the strongest positive effect on predicted charges,
   with a coefficient far larger than any other feature.
2. Age and BMI both increase predicted charges, but their effect is much
   smaller than smoking status.
3. The R2 score (0.78) shows the model explains most of the variance in
   charges, but the actual vs predicted plot shows higher error for
   high-charge cases, suggesting a non-linear relationship the model does
   not fully capture.

## Conclusion
This project used Multiple Linear Regression to predict medical insurance
charges from age, sex, BMI, number of children, smoking status, and region.
Smoking status was found to be the strongest driver of charges, followed by
age and BMI, while sex and region had a much smaller influence. The model
achieved a reasonable fit on the test data, with the R2 score indicating that
a large portion of the variance in charges is explained by these features.
However, the relationship between charges and predictors such as BMI and
smoking is not purely linear in reality (e.g., charges rise sharply for
smokers with high BMI), which limits the model's accuracy for such cases.
A key limitation of Linear Regression here is its assumption of linear,
additive relationships between features and the target, which prevents it
from capturing interaction effects (such as smoker x BMI) without manual
feature engineering.
