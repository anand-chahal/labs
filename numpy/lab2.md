## Objective
This lab will help you understand and practice slicing operations in NumPy. Slicing is a powerful technique to access and manipulate subarrays within an array.

### Exercise 1: Slice a 1D array

Given the 1D array `arr`:
```python
arr = np.array([10, 20, 30, 40, 50])
```

**Task:** Extract a subarray from index 1 to index 3 (inclusive).

### Exercise 2: Slice a 2D array

Given the 2D array `matrix`:
```python
matrix = np.array([[10, 20, 30], [40, 50, 60], [70, 80, 90]])
```

**Task:** Extract a submatrix containing the first two rows and the last two columns.

### Exercise 3: Slice with step

Given the 1D array `arr`:
```python
arr = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
```

**Task:** Extract every second element from the array.

### Exercise 4: Reverse a 1D array using slicing

Given the 1D array `arr`:
```python
arr = np.array([1, 2, 3, 4, 5])
```

**Task:** Reverse the array using slicing.

### Exercise 5: Slice and modify a subarray

Given the 1D array `arr`:
```python
arr = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
```

**Task:** Change the elements from index 3 to index 6 to 99.

### Exercise 6: Slice a 3D array

Given the 3D array `tensor`:
```python
tensor = np.arange(27).reshape(3, 3, 3)
```

**Task:** Extract a subarray containing the last two planes along the first dimension.

### Exercise 7: Boolean slicing

Given the 2D array `matrix`:
```python
matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
```

**Task:** Extract all elements greater than 4.

### Exercise 8: Combining slicing and indexing

Given the 2D array `matrix`:
```python
matrix = np.array([[10, 20, 30], [40, 50, 60], [70, 80, 90]])
```

**Task:** Extract the element at row index 1 and column index 2.

### Exercise 9: Slice using negative indices

Given the 1D array `arr`:
```python
arr = np.array([10, 20, 30, 40, 50])
```

**Task:** Extract the last three elements using negative indices.

### Exercise 10: Multi-dimensional slicing

Given the 3D array `tensor`:
```python
tensor = np.arange(27).reshape(3, 3, 3)
```

**Task:** Extract a 2x2 subarray from the first plane (first slice along the third dimension).

---

## Solutions

### Exercise 1: Slice a 1D array
```python
sub_arr = arr[1:4]
print(sub_arr)  # Output: [20 30 40]
```

### Exercise 2: Slice a 2D array
```python
sub_matrix = matrix[:2, 1:]
print(sub_matrix)  # Output: [[20 30]
                   #          [50 60]]
```

### Exercise 3: Slice with step
```python
sub_arr = arr[::2]
print(sub_arr)  # Output: [0 2 4 6 8]
```

### Exercise 4: Reverse a 1D array using slicing
```python
reversed_arr = arr[::-1]
print(reversed_arr)  # Output: [5 4 3 2 1]
```

### Exercise 5: Slice and modify a subarray
```python
arr[3:7] = 99
print(arr)  # Output: [ 0  1  2 99 99 99 99  7  8  9]
```

### Exercise 6: Slice a 3D array
```python
sub_tensor = tensor[1:, :, :]
print(sub_tensor)
# Output: [[[ 9 10 11]
#           [12 13 14]
#           [15 16 17]]
#
#          [[18 19 20]
#           [21 22 23]
#           [24 25 26]]]
```

### Exercise 7: Boolean slicing
```python
cond = matrix > 4
filtered_elements = matrix[cond]
print(filtered_elements)  # Output: [5 6 7 8 9]
```

### Exercise 8: Combining slicing and indexing
```python
element = matrix[1, 2]
print(element)  # Output: 60
```

### Exercise 9: Slice using negative indices
```python
sub_arr = arr[-3:]
print(sub_arr)  # Output: [30 40 50]
```

### Exercise 10: Multi-dimensional slicing
```python
sub_tensor = tensor[0, :2, :2]
print(sub_tensor)
# Output: [[0 1]
#          [3 4]]
```