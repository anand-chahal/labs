# Numpy Slicing Lab

## Questions

1. Create a 1D numpy array of integers from 0 to 9.
2. Extract the first 5 elements from the array.
3. Extract the last 3 elements from the array.
4. Extract every other element from the array.
5. Reverse the array.
6. Create a 2D numpy array with shape (3, 4) using integers from 0 to 11.
7. Extract the first row of the 2D array.
8. Extract the last column of the 2D array.
9. Extract the subarray consisting of the first two rows and the first two columns.
10. Extract the subarray consisting of the last two rows and the last two columns.
11. Create a 3D numpy array with shape (2, 3, 4) using integers from 0 to 23.
12. Extract the first 2D slice of the 3D array (i.e., array[0, :, :]).
13. Extract the last 2D slice of the 3D array (i.e., array[-1, :, :]).
14. Extract the first column of every 2D slice of the 3D array.
15. Extract the last row of every 2D slice of the 3D array.
16. Create a 1D numpy array of 10 random integers between 1 and 100.
17. Extract the elements at indices 2, 4, and 6.
18. Extract the subarray from index 3 to the end.
19. Extract the subarray from the beginning to index 6 (exclusive).
20. Reverse the 1D array of random integers.

## Solutions

1. **Create a 1D numpy array of integers from 0 to 9.**
    ```python
    import numpy as np
    array = np.arange(10)
    print(array)
    ```

2. **Extract the first 5 elements from the array.**
    ```python
    first_five = array[:5]
    print(first_five)
    ```

3. **Extract the last 3 elements from the array.**
    ```python
    last_three = array[-3:]
    print(last_three)
    ```

4. **Extract every other element from the array.**
    ```python
    every_other = array[::2]
    print(every_other)
    ```

5. **Reverse the array.**
    ```python
    reversed_array = array[::-1]
    print(reversed_array)
    ```

6. **Create a 2D numpy array with shape (3, 4) using integers from 0 to 11.**
    ```python
    array_2d = np.arange(12).reshape(3, 4)
    print(array_2d)
    ```

7. **Extract the first row of the 2D array.**
    ```python
    first_row = array_2d[0, :]
    print(first_row)
    ```

8. **Extract the last column of the 2D array.**
    ```python
    last_column = array_2d[:, -1]
    print(last_column)
    ```

9. **Extract the subarray consisting of the first two rows and the first two columns.**
    ```python
    subarray_2x2 = array_2d[:2, :2]
    print(subarray_2x2)
    ```

10. **Extract the subarray consisting of the last two rows and the last two columns.**
    ```python
    subarray_2x2_last = array_2d[-2:, -2:]
    print(subarray_2x2_last)
    ```

11. **Create a 3D numpy array with shape (2, 3, 4) using integers from 0 to 23.**
    ```python
    array_3d = np.arange(24).reshape(2, 3, 4)
    print(array_3d)
    ```

12. **Extract the first 2D slice of the 3D array (i.e., array[0, :, :]).**
    ```python
    first_2d_slice = array_3d[0, :, :]
    print(first_2d_slice)
    ```

13. **Extract the last 2D slice of the 3D array (i.e., array[-1, :, :]).**
    ```python
    last_2d_slice = array_3d[-1, :, :]
    print(last_2d_slice)
    ```

14. **Extract the first column of every 2D slice of the 3D array.**
    ```python
    first_column_3d = array_3d[:, :, 0]
    print(first_column_3d)
    ```

15. **Extract the last row of every 2D slice of the 3D array.**
    ```python
    last_row_3d = array_3d[:, -1, :]
    print(last_row_3d)
    ```

16. **Create a 1D numpy array of 10 random integers between 1 and 100.**
    ```python
    random_array = np.random.randint(1, 101, size=10)
    print(random_array)
    ```

17. **Extract the elements at indices 2, 4, and 6.**
    ```python
    elements = random_array[[2, 4, 6]]
    print(elements)
    ```

18. **Extract the subarray from index 3 to the end.**
    ```python
    subarray_from_3 = random_array[3:]
    print(subarray_from_3)
    ```

19. **Extract the subarray from the beginning to index 6 (exclusive).**
    ```python
    subarray_to_6 = random_array[:6]
    print(subarray_to_6)
    ```

20. **Reverse the 1D array of random integers.**
    ```python
    reversed_random_array = random_array[::-1]
    print(reversed_random_array)
    ```
