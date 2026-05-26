# scipy.stats.signaltonoise() 函数 | Python

> 原文: [https://www.geeksforgeeks.org/scipy-stats-signaltonoise-function-python/](https://www.geeksforgeeks.org/scipy-stats-signaltonoise-function-python/)

`scipy.stats.signaltonoise(arr, axis=0, ddof=0)` 函数计算输入数据的信噪比。

**其公式:**
![](img/7fd56a788d81841a4136671781ad232f.png)

## 参数

- `arr`: 【array_like】输入具有计算信噪比元素的数组或对象。
- `axis`: 计算平均值的轴。默认情况下，`axis=0`。
- `ddof`: 标准差的自由度修正。

## 结果

均值与标准差之比，即信噪比。

## 代码示例

### 代码 #1: 工作

```py
# stats.signaltonoise() method
import numpy as np
from scipy import stats

arr1 = [[20, 2, 7, 1, 34],
        [50, 12, 12, 34, 4]]

arr2 = [50, 12, 12, 34, 4]

print("\narr1 : ", arr1)
print("\narr2 : ", arr2)

print("\nsignaltonoise ratio for arr1 : ",
      stats.signaltonoise(arr1, axis=0, ddof=0))

print("\nsignaltonoise ratio for arr1 : ",
      stats.signaltonoise(arr1, axis=1, ddof=0))

print("\nsignaltonoise ratio for arr2 : ",
      stats.signaltonoise(arr2, axis=0, ddof=0))
```

**输出:**

> arr1 : [[20, 2, 7, 1, 34], [50, 12, 12, 34, 4]]
>
> arr2 : [50, 12, 12, 34, 4]
>
> signaltonoise ratio for arr1 : [2.33333333 1.4 3.8 1.06060606 1.26666667]
>
> signaltonoise ratio for arr1 : [1.01779811 1.3142934]
>
> signaltonoise ratio for arr2 : 1.5886088888888861

### 代码 #2: 如何实现

```py
def signaltonoise(a, axis, ddof):
    a = np.asanyarray(a)
    m = a.mean(axis)
    sd = a.std(axis=axis, ddof=ddof)
    return np.where(sd == 0, 0, m / sd)

print("\nsignaltonoise ratio for arr1 : ",
      signaltonoise(arr1, axis=0, ddof=0))

print("\nsignaltonoise ratio for arr1 : ",
      signaltonoise(arr1, axis=1, ddof=0))

print("\nsignaltonoise ratio for arr2 : ",
      signaltonoise(arr2, axis=0, ddof=0))
```

**输出:**

> signaltonoise ratio for arr1 : [2.33333333 1.4 3.8 1.06060606 1.26666667]
>
> signaltonoise ratio for arr1 : [1.01779811 1.3142934]
>
> signaltonoise ratio for arr2 : 1.5886088888888861