# **Coding Lab: Multivariate Linear Regression in Python**

### **Objective**
In this lab, you will:  
- Load and explore a dataset using `pandas`  
- Train a **Multivariate Linear Regression** model using `scikit-learn`  
- Evaluate the model’s performance  
- Visualize results  

### **Step 1: Import Required Libraries**  
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
```

### **Step 2: Create a Synthetic Dataset**  
We simulate a dataset where `y` depends on **two features** `X1` and `X2`.  
```python
np.random.seed(42)

# Generate two independent variables
X1 = 2 * np.random.rand(100, 1)
X2 = 3 * np.random.rand(100, 1)

# Generate the dependent variable with some noise
y = 5 + 2 * X1 + 3 * X2 + np.random.randn(100, 1)

# Create DataFrame
data = pd.DataFrame(np.hstack((X1, X2, y)), columns=['X1', 'X2', 'y'])
```

### **Step 3: Split the Data into Training and Testing Sets**  
```python
X = data[['X1', 'X2']]  # Feature matrix
y = data['y']           # Target variable

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

### **Step 4: Train a Multivariate Linear Regression Model**  
```python
model = LinearRegression()
model.fit(X_train, y_train)

# Model parameters
print(f"Intercept: {model.intercept_}")
print(f"Coefficients: {model.coef_}")
```

### **Step 5: Make Predictions and Evaluate the Model**  
```python
y_pred = model.predict(X_test)

# Compute MSE
mse = mean_squared_error(y_test, y_pred)
print(f"Mean Squared Error: {mse}")
```

### **Step 6: 3D Visualization of the Regression Plane**  
```python
fig = plt.figure(figsize=(10, 7))
ax = fig.add_subplot(111, projection='3d')

ax.scatter(X_test['X1'], X_test['X2'], y_test, color='blue', label='Actual Data')
ax.scatter(X_test['X1'], X_test['X2'], y_pred, color='red', label='Predicted Data')

ax.set_xlabel('Feature X1')
ax.set_ylabel('Feature X2')
ax.set_zlabel('Target y')
ax.set_title('Multivariate Linear Regression')

plt.legend()
plt.show()
```

---

# **Questions**

## **Coding Question**  
1. Implement a function `train_multivariate_regression(X_train, y_train)` that takes training data and returns a trained model.

## **Conceptual Questions**  
2. Why do we need **multiple features** in regression? How does adding more features impact the model?  
3. How does the `LinearRegression` model in `scikit-learn` compute the best-fit coefficients?  
4. What is **multicollinearity**, and how can it affect a linear regression model?  
5. What happens if one of the features in the dataset is completely uncorrelated with the target variable?  
6. If the Mean Squared Error (MSE) is high, what steps can you take to improve the model?  

---

# **Solutions**

## **Solution to Coding Question**
```python
def train_multivariate_regression(X_train, y_train):
    model = LinearRegression()
    model.fit(X_train, y_train)
    return model
```

## **Solution to Conceptual Questions**  

**2. Why do we need multiple features in regression?**  
- Multiple features allow the model to capture more complex relationships in the data, leading to better predictions. Adding **relevant** features improves accuracy, but too many features can cause overfitting.

**3. How does the `LinearRegression` model in `scikit-learn` compute the best-fit coefficients?**  
- It uses **Ordinary Least Squares (OLS)**, minimizing the sum of squared differences between actual and predicted values.

**4. What is multicollinearity, and how can it affect a linear regression model?**  
- **Multicollinearity** occurs when two or more independent variables are highly correlated. This can make it difficult to determine the effect of each individual feature on the target variable, leading to unstable coefficient estimates.

**5. What happens if one of the features in the dataset is completely uncorrelated with the target variable?**  
- The coefficient for that feature will be close to **zero**, indicating it has little impact. Including such features can add noise and reduce model efficiency.

**6. If the Mean Squared Error (MSE) is high, what steps can you take to improve the model?**  
- Check for **irrelevant features** and remove them.  
- Use **feature scaling** if the magnitude of variables is significantly different.  
- Increase the **training data size** if possible.  
- Use **regularization (Ridge/Lasso regression)** to reduce overfitting.