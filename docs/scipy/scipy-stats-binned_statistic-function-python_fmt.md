# scipy.stats.binned_statistic() 函数 | Python

> 原文: [https://www.geeksforgeeks.org/scipy-stats-binned_statistic-function-python/](https://www.geeksforgeeks.org/scipy-stats-binned_statistic-function-python/)

`stats.binned_statistic(x, values, statistic='mean', bins=10, range=None)` 函数计算给定数据（数组元素）的分箱统计值。
工作原理类似于[直方图](https://www.geeksforgeeks.org/scipy-stats-histogram-function-python/)功能。直方图功能创建面元并计算每个面元中的点数；而该函数计算每个箱的值的总和、平均值、中值、计数或其他统计数据。

## 参数

- `arr`: 【array_like】输入待分箱数组。
- `values`: 【array_like】要计算哪个属性。
- `statistic`: 统计计算方式 {均值(`mean`)、计数(`count`)、中值(`median`)、和(`sum`), 函数}。默认是均值(`mean`)。
- `bins`: 【int 或 scalars】如果 `bins` 为 `int`，则定义给定范围内等宽箱的数量（默认为 10）。如果 `bins` 是一个序列，它定义箱的边缘。
- `range`: (float, float) 箱柜的上下范围，如果没有提供，范围从 `x.max()` 到 `x.min()`。

## 返回值

各仓统计值；箱边缘；箱号。

## 代码示例 #1

```py
# stats.binned_statistic() method
import numpy as np
from scipy import stats

# 1D array
arr = [20, 2, 7, 1, 34]
print("\narr : \n", arr)

# median
print("\nbinned_statistic for median : \n", stats.binned_statistic(
        arr, np.arange(5), statistic='median', bins=4))
```

**输出:**

```py
arr :
 [20, 2, 7, 1, 34]

binned_statistic for median :
 BinnedStatisticResult(statistic=array([ 2., nan,  0.,  4.]),
bin_edges=array([ 1.,  9.25, 17.5, 25.75, 34.  ]),
binnumber=array([3, 1, 1, 1, 4], dtype=int64))
```

## 代码示例 #2

```py
# stats.binned_statistic() method
import numpy as np
from scipy import stats

# mean
arr = [20, 2, 7, 1, 34]
print("\nbinned_statistic for mean : \n", stats.binned_statistic(
        arr, np.arange(5), statistic='mean', bins=2))
```

**输出:**

```py
binned_statistic for mean :
 BinnedStatisticResult(statistic=array([2., 2.]),
bin_edges=array([ 1., 17.5, 34. ]),
binnumber=array([2, 1, 1, 1, 2], dtype=int64))
```