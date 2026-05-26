# scipy.stats.tmean()

> 参考: https://www.geeksforgeeks.org/scipy-stats-tmean-python/

`scipy.stats.tmean(array, limits=None, inclusive=(True, True))` 计算沿数组指定轴的数组元素的修剪平均值。

公式如下：
![](img/a66fab605678af4a57b07c619882c187.png)

> **参数:**
> **`array`**: 输入具有计算修剪平均值的元素的数组或对象。
> **`axis`**: 轴，沿该轴计算修剪平均值。默认情况下，`axis=0`。
> **`limits`**: 数组的下限和上限要考虑，小于下限或大于上限的值将被忽略。如果`limits`为`None`[默认值]，则使用所有值。
> **`inclusive`**: 一个由两个布尔值组成的元组，用于指定边界是否包含在内。
>
> **返回:** 基于设置参数的数组元素的修剪平均值。

**代码#1:**

```py
# Trimmed Mean

from scipy import stats
import numpy as np

# array elements ranging from 0 to 19
x = np.arange(20)

print("Trimmed Mean :", stats.tmean(x))

print("\nTrimmed Mean by setting limit : ",
      stats.tmean(x, (2, 10)))
```

**输出:**

```py
Trimmed Mean : 9.5

Trimmed Mean by setting limit :  6.0
```

**代码#2:** 多维数据，`axis`参数工作示例

```py
# Trimmed Mean

from scipy import stats
import numpy as np

arr1 = [[1, 3, 27],
        [5, 3, 18],
        [17, 16, 333],
        [3, 6, 82]]

# using axis = 1
print("\nTrimmed Mean is with axis = 1 : \n",
      stats.tmean(arr1, axis = 1))
```

**输出:**

```py
Trimmed Mean is with axis = 1 :
 [10.33333333  8.66666667 88.66666667 30.33333333]
```