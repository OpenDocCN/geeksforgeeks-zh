# scipy.stats.describe() 函数 | Python

> 原文：[https://www.geeksforgeeks.org/scipy-stats-describe-function-python/](https://www.geeksforgeeks.org/scipy-stats-describe-function-python/)

`scipy.stats.describe(array, axis=0)` 计算沿数组指定轴传递的数组元素的描述性统计。

## 参数

- `array`：输入数组或有元素的对象进行统计计算。
- `axis`：轴，统计数据将沿着该轴计算。默认情况下，`axis=0`。

## 返回

根据设置的参数统计数组元素。

## 代码示例 1

```py
# FInding statistics of data

from scipy import stats

arr1 = [9, 3, 27]

desc = stats.describe(arr1)

print("No. of observations is :\n", desc)
```

**输出：**

> 观测数为:
> descripteresult(nobs = 3，minmax=(3，27)，均值=13.0，方差=156.0，偏斜度=0.5280049792181878，峰度=-1.5)

## 代码示例 2：多维数据

```py
# FInding statistics of data

from scipy import stats

arr1 = [[1, 3, 27],
        [3, 4, 6],
        [7, 6, 3],
        [3, 6, 8]]

desc = stats.describe(arr1, axis = 0)

print("No. of observations at axis = 0 :\n\n", desc)

print("\n\nNo. of observations at axis = 1 :\n\n", desc)
```

**输出：**

> 轴上的观察次数= 0:
> descripteresult(nobs = 4，minmax=(array([1，3，3])，array([ 7，6，27]))，mean=array([ 3.5，4.75，11。])，方差=数组([ 6.33333333，2.25，118。])，偏斜度=数组([ 0.65202366，-0.21383343，1.03055786])，峰度=数组([-0.90304709，-1.72016461，-0.75485971])
>
> 轴上的观察次数= 1:
> descripteresult(nobs = 4，minmax=(array([1，3，3])，array([ 7，6，27]))，mean=array([ 3.5，4.75，11。])，方差=数组([ 6.33333333，2.25，118。])，偏斜度=数组([ 0.65202366，-0.21383343，1.03055786])，峰度=数组([-0.90304709，-1.72016461，-0.75485971])