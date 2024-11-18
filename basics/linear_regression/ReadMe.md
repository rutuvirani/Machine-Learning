# Linear Regression Derivation

## 1. Simple Linear Regression (SLR)
In Simple Linear Regression (SLR), we have a single input feature (`x`) and a single output (`y`). The goal is to fit a line of the form:

$$
\hat{y} = mx + b
$$

where:
- \( m \) is the slope,
- \( b \) is the intercept.

## 2. Multiple Linear Regression (MLR)
In Multiple Linear Regression (MLR), we have multiple input features \( x_1, x_2, \dots, x_n \) and a single output \( y \). The model equation is:

$$
\hat{y} = m_1 x_1 + m_2 x_2 + \dots + m_n x_n + b
$$

where:
- \( m_1, m_2, \dots, m_n \) are the slopes for each feature,
- \( b \) is the intercept.

## 3. Mean Squared Error (MSE)
The goal of linear regression is to find the line that minimizes the error between the predicted values and the actual values. The most common loss function used is the Mean Squared Error (MSE), which is given by:

$$
\text{MSE} = \frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2
$$

where:
- \( N \) is the number of data points,
- \( y_i \) is the actual value of the output,
- \( \hat{y}_i \) is the predicted value.

## 4. Minimizing the MSE
To find the optimal values of \( m \) and \( b \), we differentiate the MSE with respect to both parameters and set them to zero.

Substitute the predicted value \( \hat{y}_i = mx_i + b \) into the MSE equation:

$$
\text{MSE} = \frac{1}{N} \sum_{i=1}^{N} \left(y_i - (mx_i + b)\right)^2
$$

Now, we take the partial derivatives of MSE with respect to \( m \) and \( b \):

$$
\frac{\partial \text{MSE}}{\partial m} = -\frac{2}{N} \sum_{i=1}^{N} x_i \left(y_i - (mx_i + b)\right)
$$

$$
\frac{\partial \text{MSE}}{\partial b} = -\frac{2}{N} \sum_{i=1}^{N} \left(y_i - (mx_i + b)\right)
$$

## 5. Solving for \( m \) and \( b \)
Setting the partial derivatives to zero:

$$
\frac{\partial \text{MSE}}{\partial m} = 0 \quad \text{and} \quad \frac{\partial \text{MSE}}{\partial b} = 0
$$

After solving these equations, we get the following formulas for \( m \) and \( b \):

$$
m = \frac{\sum \left( x_i - \bar{x} \right) \left( y_i - \bar{y} \right)}{\sum \left( x_i - \bar{x} \right)^2}
$$

$$
b = \bar{y} - m \bar{x}
$$
