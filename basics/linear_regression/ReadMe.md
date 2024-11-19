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

# Simple Linear Regression (SLR) Derivation

## 1. Mean Squared Error (MSE)
The goal of linear regression is to find the line that minimizes the error between the predicted values and the actual values. The most common loss function used is the Mean Squared Error (MSE), which is given by:

$$
\text{MSE} = \frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2
$$

where:
- \( N \) is the number of data points,
- \( y_i \) is the actual value of the output,
- \( \hat{y}_i \) is the predicted value.

## 2. Minimizing the MSE
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

## 3. Solving for \( m \) and \( b \)
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

# Multiple Linear Regression (MLR) Derivation

Multiple Linear Regression (MLR) is an extension of Simple Linear Regression (SLR) where we predict the target variable \( y \) using more than one feature. The goal is to find the best-fitting hyperplane in a multi-dimensional space that minimizes the error between the actual and predicted values.

In MLR, the model equation is given by:

$$
\hat{y} = m_1 x_1 + m_2 x_2 + \dots + m_n x_n + b
$$

where:
- \( \hat{y} \) is the predicted value of the output,
- \( x_1, x_2, \dots, x_n \) are the input features,
- \( m_1, m_2, \dots, m_n \) are the coefficients (slopes) for each feature,
- \( b \) is the intercept term.

## 1. Objective of Multiple Linear Regression

The goal in MLR is to find the best values for the coefficients \( m_1, m_2, \dots, m_n \) and the intercept \( b \) that minimize the error between the actual output values \( y \) and the predicted output values \( \hat{y} \).

To measure the error, we use the **Mean Squared Error (MSE)**, which is given by:

$$
\text{MSE} = \frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2
$$

where:
- \( N \) is the number of data points,
- \( y_i \) is the actual value of the target variable for the \( i \)-th data point,
- \( \hat{y}_i \) is the predicted value of the target variable for the \( i \)-th data point.

Substituting the MLR model equation into the MSE formula:

$$
\text{MSE} = \frac{1}{N} \sum_{i=1}^{N} \left( y_i - \left( m_1 x_{i1} + m_2 x_{i2} + \dots + m_n x_{in} + b \right) \right)^2
$$

## 2. Minimizing the MSE

To find the values of \( m_1, m_2, \dots, m_n \), and \( b \) that minimize the MSE, we take the partial derivatives of the MSE with respect to each of the coefficients and set them equal to zero.

### 2.1 Partial Derivative with Respect to \( m_j \)

The partial derivative of the MSE with respect to \( m_j \) is:

$$
\frac{\partial \text{MSE}}{\partial m_j} = -\frac{2}{N} \sum_{i=1}^{N} x_{ij} \left( y_i - \left( m_1 x_{i1} + m_2 x_{i2} + \dots + m_n x_{in} + b \right) \right)
$$

### 2.2 Partial Derivative with Respect to \( b \)

The partial derivative of the MSE with respect to \( b \) is:

$$
\frac{\partial \text{MSE}}{\partial b} = -\frac{2}{N} \sum_{i=1}^{N} \left( y_i - \left( m_1 x_{i1} + m_2 x_{i2} + \dots + m_n x_{in} + b \right) \right)
$$

### 2.3 Setting Partial Derivatives Equal to Zero

Now, we set each of these partial derivatives to zero to minimize the error:

$$
\frac{\partial \text{MSE}}{\partial m_j} = 0 \quad \text{for each} \quad j = 1, 2, \dots, n
$$

$$
\frac{\partial \text{MSE}}{\partial b} = 0
$$

These equations form a system of linear equations that can be solved to find the values of \( m_1, m_2, \dots, m_n \), and \( b \).

## 3. Solving the System of Equations

We can express the system of equations in matrix form. Let’s define the following:

- \( \mathbf{X} \) is the \( N * (n+1) \)  matrix of input features, where the first column is a column of 1's (for the intercept term), and the remaining columns are the feature values \( x_1, x_2, \dots, x_n \):

$$
\mathbf{X} =
\begin{bmatrix}
1 & x_{11} & x_{12} & \dots & x_{1n} \\
1 & x_{21} & x_{22} & \dots & x_{2n} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
1 & x_{N1} & x_{N2} & \dots & x_{Nn} \\
\end{bmatrix}
$$

- \( \mathbf{y} \) is the \( N \times 1 \) vector of actual output values:

$$
\mathbf{y} =
\begin{bmatrix}
y_1 \\
y_2 \\
\vdots \\
y_N \\
\end{bmatrix}
$$

- \( \mathbf{w} \) is the \( (n+1) \times 1 \) vector of model parameters (the coefficients \( m_1, m_2, \dots, m_n \) and the intercept \( b \)):

$$
\mathbf{w} =
\begin{bmatrix}
b \\
m_1 \\
m_2 \\
\vdots \\
m_n \\
\end{bmatrix}
$$

Now, the MSE minimization problem can be rewritten as:

$$
\mathbf{X}^T \mathbf{X} \mathbf{w} = \mathbf{X}^T \mathbf{y}
$$

This is a **normal equation** that can be solved for \( \mathbf{w} \) to find the optimal values of the parameters:

$$
\mathbf{w} = (\mathbf{X}^T \mathbf{X})^{-1} \mathbf{X}^T \mathbf{y}
$$

## 4. Final Model Equation

Once the parameters \( \mathbf{w} \) are computed, the model equation can be written as:

$$
\hat{y} = b + m_1 x_1 + m_2 x_2 + \dots + m_n x_n
$$

where \( b \) is the intercept, and \( m_1, m_2, \dots, m_n \) are the coefficients for each feature.

## Conclusion

The goal of Multiple Linear Regression is to find the best coefficients \( m_1, m_2, \dots, m_n \) and intercept \( b \) that minimize the error between the actual and predicted values of the output. This is achieved by solving the normal equation:

$$
\mathbf{w} = (\mathbf{X}^T \mathbf{X})^{-1} \mathbf{X}^T \mathbf{y}
$$

Once the coefficients are found, we can use them to make predictions for new data points.



## What is R² Score?

The **R² score** (coefficient of determination) measures how well a regression model explains the variance in the target variable. It is defined as:

$$
R^2 = 1 - \frac{\text{SS}_{\text{res}}}{\text{SS}_{\text{tot}}}
$$

- SS_res = Σ(yᵢ - ŷᵢ)² (Residual Sum of Squares, error between actual and predicted values).
- SS_tot = Σ(yᵢ - ȳ)² (Total Sum of Squares, total variance in the target variable).

### Key Points:
- \( R^2 = 1 \): Perfect fit (model explains all variance in the data).
- \( R^2 = 0 \): Model performs no better than predicting the mean.
- \( R^2 < 0 \): Model performs worse than predicting the mean.

In scikit-learn, the \( R^2 \) score can be computed using the `r2_score` function.
