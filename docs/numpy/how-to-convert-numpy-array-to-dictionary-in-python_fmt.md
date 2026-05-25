# Python 中 NumPy 数组如何转换成字典？

> 原文：[https://www.geeksforgeeks.org/how-to-convert-numpy-array-to-dictionary-in-python/](https://www.geeksforgeeks.org/how-to-convert-numpy-array-to-dictionary-in-python/)

下面的文章解释了如何在 Python 中将 `numpy 数组`转换为`字典`。Numpy 中的 `Array` 是一个元素表（通常是数字），所有元素都是相同的类型，由一组正整数索引。在 Numpy 中，数组的维数称为数组的秩。给出数组沿每个维度的大小的整数元组称为数组的形状。Numpy 中的数组类称为 `数组`。Numpy 数组中的元素通过使用方括号来访问，并且可以通过使用嵌套的 Python 列表来初始化。

## 方法

要将 `numpy 数组`转换为`字典`，以下程序使用 `dict(enumerate(array.flat(), 1))`，这正是它的作用：

*   `array.flat`：此函数用于获取给定数组的副本并将其折叠为一维。
*   [`Enumeration`](https://www.geeksforgeeks.org/enumerate-in-python/)：枚举方法为列表中的每个项目提供自动计数器/索引。第一个索引值将从 0 开始。
*   [`dict`](https://www.geeksforgeeks.org/python-dictionary/)：此函数用于将任何对象转换为字典。

### 例 1：

```py
# importing required libraries
import numpy as np

# creating a numpy array
array = np.array([['a', 'b', 'c'],
                  ['d', 'e', 'f'],
                  ['g', 'h', 'i']])

# convert numpy array to dictionary
d = dict(enumerate(array.flatten(), 1))

# print numpy array
print(array)
print(type(array))

# print dictionary
print(d)
print(type(d))
```