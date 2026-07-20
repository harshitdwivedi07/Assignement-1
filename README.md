# Medical Insurance Cost Prediction using Multiple Linear Regression
**Harshit Dwivedi**
## Objective
Build a Multiple Linear Regression model that estimates a customer's medical
insurance charges from their personal and health-related details.

## Dataset Link
Medical Cost Personal Insurance Dataset (Kaggle):
https://www.kaggle.com/datasets/mirichoi0218/insurance

## Libraries Used
- pandas
- numpy
- scikit-learn
- matplotlib

## Methodology
1. Loaded the dataset and separated it into numerical columns (age, bmi,
   children), categorical columns (sex, smoker, region), and the target
   column (charges).
2. Verified there were no missing values, converted the categorical columns
   into numeric form (label encoding for sex and smoker, one-hot encoding
   for region), then split the data 80/20 into training and test sets.
3. Fit a Multiple Linear Regression model on age, sex, bmi, children,
   smoker, and region to predict charges, and generated predictions on the
   test set.
4. Assessed performance using MAE, MSE, and R2 Score, and visualized the
   fit with an actual vs predicted scatter plot.

## Results
| Metric | Value |
|--------|-------|
| MAE | 4181.19 |
| MSE | 33,596,915.85 |
| R2 Score | 0.7836 |

**Observations:**
1. Smoker status carries by far the largest coefficient, making it the
   single biggest factor pushing charges up.
2. Age and bmi also push charges higher, though their impact is noticeably
   smaller than smoking.
3. An R2 of 0.78 means the model captures most of the variation in charges,
   but the scatter plot reveals larger errors at the high end, pointing to a
   non-linear pattern the model can't fully represent.

## Conclusion
This project applied Multiple Linear Regression to estimate medical
insurance charges using age, sex, bmi, children, smoker status, and region.
Smoker status emerged as the dominant factor behind higher charges, with age
and bmi contributing to a lesser extent, while sex and region played only a
minor role. The resulting model fit the test data reasonably well, and its
R2 score confirms that these variables account for a large share of the
variation in charges. That said, real-world charge patterns — such as the
sharp jump seen when high bmi combines with smoking — are not strictly
linear, so the model's predictions lose accuracy in those cases. This points
to a core limitation of Linear Regression: it assumes purely linear, additive
relationships and therefore cannot capture interaction effects like
smoker x bmi unless they are engineered into the feature set manually.
