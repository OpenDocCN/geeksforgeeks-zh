# `scipy.stats.binned_statistic_2d()` 函数

> 原文：[https://www.geeksforgeeks.org/scipy-stats-binned_statistic_2d-function-python/](https://www.geeksforgeeks.org/scipy-stats-binned_statistic_2d-function-python/)

`stats.binned_statistic_2d(arr1, arr2, values, statistic='mean', bins=10, range=None)` 函数计算给定二维数据的分箱统计值。其工作原理类似于二维直方图功能，制作面元并计算每个面元中的点数；该函数计算每个箱的值的总和、平均值、中值、计数或其他统计数据。

## 参数

- `arr1`：【array_like】输入数组，沿第一维分箱。
- `arr2`：【array_like】输入数组，沿第二维分箱。
- `values`：【array_like】要计算其统计量的值。
- `statistic`：统计计算方式，可选 `{'mean', 'count', 'sum', 'std'}` 等。默认是 `mean`。
- `bins`：【int 或 scalars】如果 `bins` 为 int，则定义给定范围内等宽箱的数量（默认为 10）。如果 `bins` 是一个序列，它定义箱的边界。
- `range`：(float, float) 箱柜的上下范围。如果没有提供，范围从 `x.max()` 到 `x.min()`。

## 结果

- 各箱统计值。
- 沿第一维和第二维的分箱边界。
- 箱号。

## 代码示例

**代码#1：**

```py
# stats.binned_statistic_2d() method 
import numpy as np
from scipy import stats

x = np.random.rand(10)
y = np.random.rand(10)

z = np.arange(10)

print ("x : \n", x)
print ("\ny : \n", y)
print ("\nz : \n", z)

# count
print ("\nbinned_statistic_2d for count : ", 
       stats.binned_statistic_2d(x, y, values = z, 
                statistic ='count', bins = [5, 5]))
```

**输出：**

```
x: 
 [0.31218238 0.86791445 0.42763346 0.79798587 0.91361299 0.09005856
 0.54419846 0.18973948 0.67016378 0.8083121]

y: 
 [0.35959238 0.69265819 0.18751529 0.98863414 0.97810927 0.24054104
 0.76764562 0.60635485 0.6151806 0.638472]

z: 
 [0 1 2 3 4 5 6 7 8 9]

binned_statistic_2d for count :  BinnedStatistic2DResult(statistics=array([[1., 0., 1., 0., 0.],
       [0., 1., 0., 0., 0.],
       [1., 0., 0., 1., 0.],
       [0., 0., 1., 0., 0.],
       [0., 0., 1., 1., 2.]]), x_edge=array([0.09005856, 0.25476945, 0.41948033, 0.58419122, 0.74890211,
       0.91361299]), y_edge=array([0.18751529, 0.3473906 , 0.50796283, 0.666668196...
```

**代码#2：**

```py
# stats.binned_statistic_2d() method 
import numpy as np
from scipy import stats

x = np.random.rand(10)
y = np.random.rand(10)
z = np.arange(10)

# mean
print ("\nbinned_statistic_2d for mean : ", 
       stats.binned_statistic_2d(x, y, values = z,
                   statistic ='mean', bins = [5, 5])) 
```

**输出：**

```
binned_statistic_2d for mean :  BinnedStatistic2DResult(statistics=array([[5. , 7. , nan, nan, nan],
       [nan, 0. , nan, nan, nan],
       [2. , nan, nan, 6. , nan],
       [nan, nan, 8. , nan, nan],
       [nan, nan, 9. , 1. , 3.5]]), x_edge=array([0.09005856, 0.25476945, 0.41948033, 0.58419122, 0.74890211,
       0.91361299]), y_edge=array([0.18751529, 0.3473906 , 0.50796283, 0.66...
```