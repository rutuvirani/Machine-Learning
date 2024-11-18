# Linear Regression

Linear regression is a fundamental technique used to fit a line through data points in order to predict further data. The goal is to find a line that minimizes the **Mean Squared Error (MSE)**.

---

## Types of Linear Regression

1. **Simple Linear Regression (SLR)**: One input column and one output column.
2. **Multiple Linear Regression (MLR)**: Multiple input columns and one output column.

---

## Objective

We aim to find the parameters \( m \) (slope) and \( b \) (intercept) such that the MSE is minimized.

### Mean Squared Error (MSE) Formula:
\[
\text{MSE} = \frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2
\]

---

## Closed Form Solution

### Formula for \( m \) (slope):
\[
m = \frac{\sum \left( x - \bar{x} \right) \left( y - \bar{y} \right)}{\sum \left( x - \bar{x} \right)^2}
\]

### Formula for \( b \) (intercept):
\[
b = \bar{y} - m \bar{x}
\]

---

## Derivation of \( m \) and \( b \)

The predicted line equation is:
\[
\hat{y} = m x + b
\]

Substitute \( \hat{y} \) into the MSE:
\[
\text{MSE} = \frac{1}{N} \sum_{i=1}^{N} \left(y_i - (m x_i + b)\right)^2
\]

To minimize MSE, take partial derivatives of the equation with respect to \( m \) and \( b \), and set them to zero:

### Partial Derivatives:

1. With respect to \( m \):
\[
\frac{\partial \text{MSE}}{\partial m} = -\frac{2}{N} \sum_{i=1}^{N} x_i \left(y_i - (m x_i + b)\right)
\]

2. With respect to \( b \):
\[
\frac{\partial \text{MSE}}{\partial b} = -\frac{2}{N} \sum_{i=1}^{N} \left(y_i - (m x_i + b)\right)
\]

Setting these derivatives to zero and solving for \( m \) and \( b \), we arrive at the closed-form solutions shown above.

---
