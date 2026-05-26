# sciPy stats.trim1()函数 | Python

> 原文: [https://www.geeksforgeeks.org/scipy-stats-trim1-function-python/](https://www.geeksforgeeks.org/scipy-stats-trim1-function-python/)

`scipy.stats.trim1(a, proportiontocut, tail='right')` 函数从传递的数组分布的一端切下数组中的部分元素。

## 参数

- `arr`: 【`array_like`】输入要修剪的数组或对象。
- `tail`: 【可选】{ `'left'`, `'right'` } 默认为 `'right'`。
- `proportiontocut`: 每端要修剪的数据比例（在 0-1 范围内）。

## 结果

按照给定的比例从两端修剪数组元素。

## 代码示例

```py
# stats.trim1() method
import numpy as np
from scipy import stats

arr1 = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

print("\narr1 : ", arr1)

print("\nclipped arr1 : \n",
      stats.trim1(arr1, proportiontocut=.3, tail='right'))

print("\nclipped arr1 : \n",
      stats.trim1(arr1, proportiontocut=.3, tail='left'))

print("\nclipped arr1 : \n",
      stats.trim1(arr1, proportiontocut=.1, tail='left'))

print("\nclipped arr1 : \n",
      stats.trim1(arr1, proportiontocut=.1, tail='right'))
```

## 输出

```py
arr1 :  [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

clipped arr1 :
 [0 2 1 3 4 5 6]

clipped arr1 :
 [3 4 6 5 7 8 9]

clipped arr1 :
 [1 3 2 4 5 6 7 8 9]

clipped arr1 :
 [0 2 1 3 4 5 6 7 8]
```