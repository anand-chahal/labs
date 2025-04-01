# **Coding Lab: Polynomial Regression in Python**  

### **Objective**  
In this lab, you will:  
- Understand when polynomial regression is needed  
- Generate non-linear data  
- Train a **Polynomial Regression** model using `scikit-learn`  
- Compare it with Linear Regression  
- Visualize the results  

---

## **Step 1: Import Required Libraries**  
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
```

---

## **Step 2: Create a Non-Linear Dataset**  
We generate data where `y` follows a **quadratic relationship** with `X`.  
```python
np.random.seed(42)

# Generate feature variable
X = 6 * np.random.rand(100, 1) - 3  # Values in range [-3, 3]

# Generate non-linear target variable
y = 1 + 2 * X + 3 * X**2 + np.random.randn(100, 1) * 2  # Quadratic relationship with noise

# Convert to DataFrame
data = pd.DataFrame(np.hstack((X, y)), columns=['X', 'y'])
```

---

## **Step 3: Visualizing the Data**  
```python
plt.scatter(data['X'], data['y'], color='blue', label='Data Points')
plt.xlabel('Feature X')
plt.ylabel('Target y')
plt.title('Scatter Plot of Non-Linear Data')
plt.legend()
plt.show()
```

---

## **Step 4: Split the Data into Training and Testing Sets**  
```python
X_train, X_test, y_train, y_test = train_test_split(data[['X']], data['y'], test_size=0.2, random_state=42)
```

---

## **Step 5: Train a Linear Regression Model**  
First, we train a **Linear Regression** model to see why it struggles with non-linear data.  
```python
lin_model = LinearRegression()
lin_model.fit(X_train, y_train)

y_pred_lin = lin_model.predict(X_test)

# Compute error
mse_lin = mean_squared_error(y_test, y_pred_lin)
print(f"Linear Regression MSE: {mse_lin}")
```

---

## **Step 6: Train a Polynomial Regression Model**  
Now, we transform the feature `X` to include polynomial terms and fit a model.  
```python
# Transform feature into polynomial features (degree = 2)
poly = PolynomialFeatures(degree=2)
X_train_poly = poly.fit_transform(X_train)
X_test_poly = poly.transform(X_test)

# Train polynomial regression model
poly_model = LinearRegression()
poly_model.fit(X_train_poly, y_train)

y_pred_poly = poly_model.predict(X_test_poly)

# Compute error
mse_poly = mean_squared_error(y_test, y_pred_poly)
print(f"Polynomial Regression MSE: {mse_poly}")
```

---

## **Step 7: Visualizing the Results**  
```python
# Sort values for smooth curve
X_sorted = np.linspace(-3, 3, 100).reshape(-1, 1)
X_sorted_poly = poly.transform(X_sorted)
y_sorted_poly = poly_model.predict(X_sorted_poly)

plt.scatter(X_test, y_test, color='blue', label='Actual Data')
plt.plot(X_sorted, y_sorted_poly, color='red', linewidth=2, label='Polynomial Fit')
plt.xlabel('Feature X')
plt.ylabel('Target y')
plt.title('Polynomial Regression Model')
plt.legend()
plt.show()
```

---

# **Questions**

## **Coding Question**  
1. Implement a function `train_polynomial_regression(X_train, y_train, degree)` that trains a polynomial regression model and returns the trained model.  

## **Conceptual Questions**  
2. Why does **Linear Regression** fail for this dataset?  
3. How does the `PolynomialFeatures` transformer work in `scikit-learn`?  
4. What are the risks of choosing a **high-degree polynomial** for regression?  
5. How can we determine the best polynomial degree for a given dataset?  
6. If polynomial regression is still performing poorly, what preprocessing steps can help improve the model?  

---

# **Solutions**  

## **Solution to Coding Question**  
```python
def train_polynomial_regression(X_train, y_train, degree):
    poly = PolynomialFeatures(degree=degree)
    X_train_poly = poly.fit_transform(X_train)
    
    model = LinearRegression()
    model.fit(X_train_poly, y_train)
    
    return model, poly
```

---

## **Solution to Conceptual Questions**  

**2. Why does Linear Regression fail for this dataset?**  
- Linear regression assumes a straight-line relationship, but this dataset has a **quadratic** relationship, making it a poor fit.  

**3. How does the `PolynomialFeatures` transformer work in `scikit-learn`?**  
- It transforms the original feature `X` into higher-degree features, such as `X²`, `X³`, etc., allowing a linear model to fit non-linear relationships.  

**4. What are the risks of choosing a high-degree polynomial for regression?**  
- High-degree polynomials can lead to **overfitting**, where the model captures noise instead of the underlying trend. This makes the model perform well on training data but poorly on new data.  

**5. How can we determine the best polynomial degree for a given dataset?**  
- We can use **cross-validation** to compare model performance for different degrees and select the one with the lowest error on validation data.  

**6. If polynomial regression is still performing poorly, what preprocessing steps can help improve the model?**  
- **Feature scaling**: If feature values have different ranges, normalization helps.  
- **Outlier removal**: Noise in the data can distort polynomial fits.  
- **Regularization**: Lasso or Ridge regression can prevent overfitting.