# 使用 NumPy 从均匀分布生成随机数

> 原文: [https://www.geeksforgeeks.org/generate-random-numbers-from-the-uniform-distribution-using-numpy/](https://www.geeksforgeeks.org/generate-random-numbers-from-the-uniform-distribution-using-numpy/)

随机数是逻辑上无法预测的数字。在 NumPy 中，我们被提供了一个叫做 `random` 模块，它允许我们使用随机数。为了从均匀分布生成随机数，我们将使用 `random` 模块的 [`random.uniform()`](https://www.geeksforgeeks.org/numpy-random-uniform-in-python/) 方法。

**语法:**

```py
numpy.random.uniform(low=0.0, high=1.0, size=None)
```

在均匀分布中，样本均匀分布在半开区间 [`low`, `high`] 上，它包括 `low` 但不包括 `high` 区间。

**例 1:**

### Python 3 示例 1

```py
# importing module
import numpy as np

# numpy.random.uniform() method
r = np.random.uniform(size=4)

# printing numbers
print(r)
```

**输出:**

```py
[0.3829765  0.50958636 0.42844207 0.4260992  0.3513896 ]
```

**例 2:**

### Python 3 示例 2

```py
# importing module
import numpy as np

# numpy.random.uniform() method
random_array = np.random.uniform(0.0, 1.0, 5)

# printing 1D array with random numbers
print("1D Array with random values : \n", random_array)
```

**输出:**

```py
1D Array with random values :
[0.2167103  0.07881761 0.89666672 0.31143605 0.31481039]
```