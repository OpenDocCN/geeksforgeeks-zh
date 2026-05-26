# scipy.stats.bayes_mvs()函数 | Python

> 原文: [https://www.geeksforgeeks.org/scipy-stats-bayes_mvs-function-python/](https://www.geeksforgeeks.org/scipy-stats-bayes_mvs-function-python/)

## scipy.stats.bayes_mvs()函数

`scipy.stats.bayes_mvs(arr, alpha)` 函数计算给定贝叶斯置信区间内的均值、方差和标准差。

### 参数

- `arr`: 【array_like】输入数据可以是多维的，但使用前会被展平。
- `alpha`: 返回的置信区间包含真参数的概率。

### 结果

给定贝叶斯置信区间内的均值、方差和标准差。

### 代码示例

```py
# stats.bayes_mvs() method
import numpy as np
from scipy import stats

arr1 = [[20, 2, 7, 1, 34],
        [50, 12, 12, 34, 4]]

arr2 = [50, 12, 12, 34, 4]

print("\narr1 : ", arr1)
print("\narr2 : ", arr2)

mean, var, std = stats.bayes_mvs(arr1, 0.9)

print("\nMean of array1 : ", mean)
print("\nvar of array1 : ", var)
print("\nstd of array1 : ", std)

mean, var, std = stats.bayes_mvs(arr2, 0.5)

print("\nMean of array2 : ", mean)
print("\nvar of array2 : ", var)
print("\nstd of array2 : ", std)
```

### 输出

> arr1 : [[20, 2, 7, 1, 34], [50, 12, 12, 34, 4]]
>
> arr2 : [50, 12, 12, 34, 4]
>
> Mean of array1 : Mean(statistic=17.6, minmax=(7.9921252273964, 27.00888888888886))
>
> var of array1 : Variance(statistic=353.2, minmax=(146.176149159307, 560.223850840693))
>
> std of array1 : Std_dev(statistic=18.136411760663574, minmax=(12.08849707316974, 23.66904837125068))
>
> Mean of array2 : Mean(statistic=22.4, minmax=(16.09058241339323, 28.70941758660677))
>
> var of array2 : Variance(statistic=725.6, minmax=(269.5888888888889, 1181.6111111111113))
>
> std of array2 : Std_dev(statistic=23.872262300862655, minmax=(16.415719844632576, 34.37457067532965))