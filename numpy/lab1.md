# Basics
This lab will introduce you to the basics of NumPy, a powerful library for numerical computing in Python. You will learn how to create arrays, perform vectorized operations, and use slicing to manipulate data.

## 1. Creating Arrays
### Task 1.1: Create a NumPy array from a list
Create a one-dimensional NumPy array from a Python list.

### Task 1.2: Create a 2D array
Create a 2D array (matrix) from a list of lists.
### Task 1.3: Create arrays using built-in functions
Create arrays using `np.zeros`, `np.ones`

1. Create a list of 20 zeros
2. Create a list of 100 ones
3. Create a list of 30 9s
4. Create a matrix of 2s of dimension 5x6
5. Create a matrix of 0s of dimension 3x10
6. Create a matrix of 0s of dimension 3x10
7. Create a 10x10 sudoku and fill it with random integers between 0 and 9

## 2. Array Operations
### Reshaping arrays
1. Reshape a 1D array into a 2D array
Given the 1D array arr:

```python
arr = np.arange(12)
```
Task: Reshape arr into a 2D array with 3 rows and 4 columns.

2: Reshape a 1D array into a 3D array
Given the 1D array arr:

```python
arr = np.arange(24)
```
Task: Reshape arr into a 3D array with dimensions 2x3x4.

3: Flatten a 2D array into a 1D array
Given the 2D array matrix:

```python
matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
```
Task: Flatten matrix into a 1D array.

4: Reshape a 2D array into another 2D array with different dimensions
Given the 2D array matrix:

```python
matrix = np.array([[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]])
```
Task: Reshape matrix into a 2D array with 6 rows and 2 columns.

5: Reshape and transpose a 3D array
Given the 3D array tensor:

```python
tensor = np.arange(27).reshape(3, 3, 3)
```
Task: Reshape the above tensor into a 2D array with dimensions 3x9 and then transpose it.

6: Using np.newaxis to add a new dimension
Given the 1D array arr:

```python
arr = np.array([1, 2, 3, 4])
```
Task: Reshape arr into a 2D array with shape (4, 1) using np.newaxis.

7: Reshape a 1D array into a 2D array and back to 1D
Given the 1D array arr:

```python
arr = np.arange(16)
```
Task: Reshape arr into a 2D array with 4 rows and 4 columns, and then flatten it back to a 1D array.

8: Reshape and modify a view
Given the 1D array arr:

```python
arr = np.arange(8)
```
Task: Reshape arr into a 2D array with 2 rows and 4 columns, modify an element in the reshaped array, and observe the change in the original array.
