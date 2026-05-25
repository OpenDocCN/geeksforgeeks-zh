# 如何删除 Numpy 数组中包含非数值的行？

> 原文：`https://www.geeksforgeeks.org/how-to-remove-rows-in-numpy-array-that-contains-non-numeric-values/`

很多时候，我们在 `NumPy` 数组中有非数值。这些值需要删除，这样数组就不会有这些不必要的值，看起来更体面。可以使用**位非运算符**和 `isnan()` 功能删除所有包含 `NaN` 值的行。

## 例 1

### Python 3

```py
# Importing Numpy module
import numpy as np

# Creating 2X3 2-D Numpy array
n_arr = np.array([[10.5, 22.5, 3.8],
                  [41, np.nan, np.nan]])

print("Given array:")
print(n_arr)

print("\nRemove all rows containing non-numeric elements")
print(n_arr[~np.isnan(n_arr).any(axis=1)])
```