# **Coding Lab: Simple Linear Regression in Python**

### **Objective**
In this lab, you will:
- Load and explore a dataset using `pandas`
- Use `numpy` to perform basic data transformations
- Train a **Linear Regression** model using `scikit-learn`
- Visualize the results using `plotly`

### **Step 1: Import Required Libraries**
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
```

### **Step 2: Create a Synthetic Dataset**
We will simulate a dataset with a linear relationship between `X` and `y`.

```python
# Set random seed for reproducibility
np.random.seed(42)

# Generate synthetic data
X = 2 * np.random.rand(100, 1)  # Feature variable
y = 4 + 3 * X + np.random.randn(100, 1)  # Linear relation with noise

# Convert to pandas DataFrame
data = pd.DataFrame(np.hstack((X, y)), columns=['X', 'y'])
```

### **Step 3: Visualizing the Data**
```python
plt.scatter(data['X'], data['y'], color='blue', label='Data Points')
plt.xlabel('Feature X')
plt.ylabel('Target y')
plt.title('Scatter Plot of Generated Data')
plt.legend()
plt.show()
```

### **Step 4: Split the Data into Training and Testing Sets**
```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

### **Step 5: Train a Linear Regression Model**
```python
# Create and train the model
model = LinearRegression()
model.fit(X_train, y_train)

# Get model parameters
print(f"Intercept: {model.intercept_[0]}")
print(f"Coefficient: {model.coef_[0][0]}")
```

### **Step 6: Make Predictions and Evaluate the Model**
```python
# Make predictions on the test set
y_pred = model.predict(X_test)

# Calculate mean squared error
mse = mean_squared_error(y_test, y_pred)
print(f"Mean Squared Error: {mse}")
```

### **Step 7: Visualize the Regression Line**
```python
plt.scatter(X_test, y_test, color='blue', label='Actual Data')
plt.plot(X_test, y_pred, color='red', linewidth=2, label='Regression Line')
plt.xlabel('Feature X')
plt.ylabel('Target y')
plt.title('Linear Regression Model')
plt.legend()
plt.show()
```

---

# **Questions**
1. **Understanding Data Generation**: What is the purpose of adding random noise to the target variable `y` when generating synthetic data?
   
2. **Model Training**: How does the `LinearRegression.fit()` method determine the best-fitting line for the data?

3. **Model Evaluation**: What does the **Mean Squared Error (MSE)** tell us about the model's performance?

4. **Visual Interpretation**: If the regression line does not fit the data well, what could be the possible reasons?

5. **Feature Engineering**: How would the model change if we added another feature (e.g., `X^2` for a quadratic relationship)?

---

This lab provides hands-on experience with **Linear Regression** and its implementation in Python while reinforcing theoretical concepts. Would you like any modifications or additional explanations?

---

### **1. Understanding Data Generation**  
**Q:** What is the purpose of adding random noise to the target variable `y` when generating synthetic data?  
**A:** Random noise helps simulate real-world scenarios where data is not perfectly linear due to measurement errors, variability in processes, or unknown factors. It prevents overfitting and makes the model more robust.

---

### **2. Model Training**  
**Q:** How does the `LinearRegression.fit()` method determine the best-fitting line for the data?  
**A:** The `fit()` method uses the **Ordinary Least Squares (OLS)** method to minimize the sum of squared residuals (the differences between actual and predicted values). It finds the optimal **intercept** and **coefficient(s)** that minimize the error.

---

### **3. Model Evaluation**  
**Q:** What does the **Mean Squared Error (MSE)** tell us about the model's performance?  
**A:** MSE measures the average squared difference between actual and predicted values. A lower MSE indicates that the model's predictions are closer to the actual values, meaning better performance.

---

### **4. Visual Interpretation**  
**Q:** If the regression line does not fit the data well, what could be the possible reasons?  
**A:** Possible reasons include:
   - The relationship between `X` and `y` is **non-linear**.
   - There are **outliers** affecting the model.
   - The dataset has **insufficient or irrelevant features**.
   - **High variance** in the data leading to overfitting.

---

### **5. Feature Engineering**  
**Q:** How would the model change if we added another feature (e.g., `X^2` for a quadratic relationship)?  
**A:** Adding `X^2` as a feature would make the model a **polynomial regression** instead of simple linear regression. This could better capture non-linear patterns in the data. Instead of a straight line, the regression model could fit a **curve**.