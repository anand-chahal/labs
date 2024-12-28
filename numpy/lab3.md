# NumPy Boolean Indexing and Fancy Indexing Lab

## Objective
This lab will help you understand and practice boolean indexing and fancy indexing operations in NumPy. These techniques allow for advanced and efficient data manipulation.

### Boolean Indexing

### Exercise 1: Boolean indexing on a 1D array

Given the 1D array `arr`:
```python
arr = np.array([5, 10, 15, 20, 25, 30])
```

**Task:** Extract elements greater than 15.

### Exercise 2: Boolean indexing on a 2D array

Given the 2D array `matrix`:
```python
matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
```

**Task:** Extract elements greater than 4.

### Exercise 3: Boolean condition with logical AND

Given the 1D array `arr`:
```python
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
```

**Task:** Extract elements that are greater than 3 and less than 8.

### Exercise 4: Boolean condition with logical OR

Given the 1D array `arr`:
```python
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
```

**Task:** Extract elements that are less than 3 or greater than 8.

### Exercise 5: Modify elements using boolean indexing

Given the 1D array `arr`:
```python
arr = np.array([10, 20, 30, 40, 50])
```

**Task:** Set elements greater than 25 to 0.

### Exercise 6: Boolean indexing with complex condition

Given the 2D array `matrix`:
```python
matrix = np.array([[5, 10, 15], [20, 25, 30], [35, 40, 45]])
```

**Task:** Extract elements that are multiples of 10.

### Exercise 7: Count elements satisfying a condition

Given the 1D array `arr`:
```python
arr = np.array([3, 6, 9, 12, 15, 18])
```

**Task:** Count elements that are divisible by 3.

### Exercise 8: Extract elements using boolean array

Given the 1D array `arr` and a boolean array `bool_arr`:
```python
arr = np.array([10, 20, 30, 40, 50])
bool_arr = np.array([True, False, True, False, True])
```

**Task:** Extract elements where `bool_arr` is `True`.

### Exercise 9: Replace elements satisfying a condition

Given the 1D array `arr`:
```python
arr = np.array([5, 10, 15, 20, 25])
```

**Task:** Replace elements less than 15 with -1.

### Exercise 10: Select elements from two arrays based on condition

Given two 1D arrays `a` and `b`, and a condition array `cond`:
```python
a = np.array([1, 2, 3, 4, 5])
b = np.array([10, 20, 30, 40, 50])
cond = np.array([True, False, True, False, True])
```

**Task:** Select elements from `a` where `cond` is `True` and from `b` where `cond` is `False`.

### Fancy Indexing

### Exercise 11: Fancy indexing on a 1D array

Given the 1D array `arr`:
```python
arr = np.array([10, 20, 30, 40, 50])
```

**Task:** Extract elements at indices 0, 2, and 4.

### Exercise 12: Fancy indexing on a 2D array

Given the 2D array `matrix`:
```python
matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
```

**Task:** Extract elements at positions (0, 1), (1, 2), and (2, 0).

### Exercise 13: Fancy indexing with repeated indices

Given the 1D array `arr`:
```python
arr = np.array([10, 20, 30, 40, 50])
```

**Task:** Extract elements at indices 0, 0, 1, 1, 2, 2.

### Exercise 14: Modify elements using fancy indexing

Given the 1D array `arr`:
```python
arr = np.array([1, 2, 3, 4, 5])
```

**Task:** Double the elements at indices 1, 3, and 4.

### Exercise 15: Extract rows and columns using fancy indexing

Given the 2D array `matrix`:
```python
matrix = np.array([[10, 20, 30], [40, 50, 60], [70, 80, 90]])
```

**Task:** Extract rows 0 and 2 and columns 1 and 2.

### Exercise 16: Fancy indexing with negative indices

Given the 1D array `arr`:
```python
arr = np.array([100, 200, 300, 400, 500])
```

**Task:** Extract elements at indices -1, -3, and -5.

### Exercise 17: Using fancy indexing to rearrange elements

Given the 1D array `arr`:
```python
arr = np.array([10, 20, 30, 40, 50])
```

**Task:** Rearrange the elements in the order of indices [4, 2, 0, 1, 3].

### Exercise 18: Extract diagonal elements using fancy indexing

Given the 2D array `matrix`:
```python
matrix = np.array([[10, 20, 30], [40, 50, 60], [70, 80, 90]])
```

**Task:** Extract the diagonal elements.

### Exercise 19: Fancy indexing with boolean array

Given the 1D array `arr`:
```python
arr = np.array([5, 10, 15, 20, 25])
```

**Task:** Extract elements where the boolean array `[True, False, True, False, True]` is `True`.

### Exercise 20: Combining boolean and fancy indexing

Given the 2D array `matrix`:
```python
matrix = np.array([[10, 20, 30], [40, 50, 60], [70, 80, 90]])
```

**Task:** Extract elements from columns 0 and 2 where the corresponding elements in the first row are greater than 15.

---

## Solutions

### Boolean Indexing

### Exercise 1: Boolean indexing on a 1D array
```python
result = arr[arr > 15]
print(result)  # Output: [20 25 30]
```

### Exercise 2: Boolean indexing on a 2D array
```python
result = matrix[matrix > 4]
print(result)  # Output: [5 6 7 8 9]
```

### Exercise 3: Boolean condition with logical AND
```python
result = arr[(arr > 3) & (arr < 8)]
print(result)  # Output: [4 5 6 7]
```

### Exercise 4: Boolean condition with logical OR
```python
result = arr[(arr < 3) | (arr > 8)]
print(result)  # Output: [ 1  2  9 10]
```

### Exercise 5: Modify elements using boolean indexing
```python
arr[arr > 25] = 0
print(arr)  # Output: [10 20  0  0  0]
```

### Exercise 6: Boolean indexing with complex condition
```python
result = matrix[matrix % 10 == 0]
print(result)  # Output: [10 20 30 40]
```

### Exercise 7: Count elements satisfying a condition
```python
count = np.sum(arr % 3 == 0)
print(count)  # Output: 6
```

### Exercise 8: Extract elements using boolean array
```python
result = arr[bool_arr]
print(result)  # Output: [10 30 50]
```

### Exercise 9: Replace elements satisfying a condition
```python
arr[arr < 15] = -1
print(arr)  # Output: [-1 -1 15 20 25]
```

### Exercise 10: Select elements from two arrays based on condition
```python
result = np.where(cond, a, b)
print(result)  # Output: [ 1 20  3 40  5]
```

### Fancy Indexing

### Exercise 11: Fancy indexing on a 1D array


```python
indices = [0, 2, 4]
result = arr[indices]
print(result)  # Output: [10 30 50]
```

### Exercise 12: Fancy indexing on a 2D array
```python
result = matrix[[0, 1, 2], [1, 2, 0]]
print(result)  # Output: [2 6 7]
```

### Exercise 13: Fancy indexing with repeated indices
```python
indices = [0, 0, 1, 1, 2, 2]
result = arr[indices]
print(result)  # Output: [10 10 20 20 30 30]
```

### Exercise 14: Modify elements using fancy indexing
```python
indices = [1, 3, 4]
arr[indices] *= 2
print(arr)  # Output: [ 1  4  3  8 10]
```

### Exercise 15: Extract rows and columns using fancy indexing
```python
rows = [0, 2]
cols = [1, 2]
result = matrix[rows][:, cols]
print(result)  # Output: [[20 30]
               #          [80 90]]
```

### Exercise 16: Fancy indexing with negative indices
```python
indices = [-1, -3, -5]
result = arr[indices]
print(result)  # Output: [500 300 100]
```

### Exercise 17: Using fancy indexing to rearrange elements
```python
indices = [4, 2, 0, 1, 3]
result = arr[indices]
print(result)  # Output: [50 30 10 20 40]
```

### Exercise 18: Extract diagonal elements using fancy indexing
```python
result = matrix[[0, 1, 2], [0, 1, 2]]
print(result)  # Output: [10 50 90]
```

### Exercise 19: Fancy indexing with boolean array
```python
bool_arr = np.array([True, False, True, False, True])
result = arr[bool_arr]
print(result)  # Output: [ 5 15 25]
```

### Exercise 20: Combining boolean and fancy indexing
```python
result = matrix[:, [0, 2]][matrix[0] > 15]
print(result)  # Output: [[40 60]
               #          [70 90]]
```