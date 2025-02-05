# Validation and Mean Absolute Error 
MAE - mean absolute error; the average of error margin 

Validation of your model is important because we want to ensure the model is accurate with data it hasn't seen before. 

That is why we split the dataset into two, training data and validation data. 

For example, our model is trying to predict the price of homes given certain characteristics. In the training data, all home with green doors were very expensive. But our validation data doesn't have this pattern, so the prediction of the home prices will be skewed and the MAE will be high. 

### Mean Absolute Error (MAE) Calculation Example

The **Mean Absolute Error (MAE)** is a metric used to evaluate the accuracy of a regression model. It calculates the average of the absolute differences between the predicted values and the actual values.

#### Formula:

MAE = $\frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|$

Where:
- $y_i$ is the actual value for the \(i\)-th observation.
- $\hat{y}_i$ is the predicted value for the ${i}-th observation.
- ${n}$ is the total number of observations.

#### Example:

Suppose you have the following actual and predicted values:

| Observation | Actual Value (\( y_i \)) | Predicted Value (\( \hat{y}_i \)) |
|-------------|--------------------------|-----------------------------------|
| 1           | 3                        | 2.5                               |
| 2           | 4                        | 4.2                               |
| 3           | 5                        | 5.5                               |
| 4           | 6                        | 5.8                               |
| 5           | 7                        | 6.9                               |

##### Step 1: Calculate the absolute errors for each observation.

\[
|y_i - \hat{y}_i|
\]
1. For Observation 1: \( |3 - 2.5| = 0.5 \)
2. For Observation 2: \( |4 - 4.2| = 0.2 \)
3. For Observation 3: \( |5 - 5.5| = 0.5 \)
4. For Observation 4: \( |6 - 5.8| = 0.2 \)
5. For Observation 5: \( |7 - 6.9| = 0.1 \)

##### Step 2: Calculate the mean of the absolute errors.

\[
MAE = \frac{1}{5} (0.5 + 0.2 + 0.5 + 0.2 + 0.1)
\]
\[
MAE = \frac{1}{5} (1.5)
\]
\[
MAE = 0.3
\]

Related:
- MarkDown for Math: https://rpruim.github.io/s341/S19/from-class/MathinRmd.html
- Kaggle Exereince for Model Validation: https://www.kaggle.com/code/jennyzhu1/exercise-model-validation/edit