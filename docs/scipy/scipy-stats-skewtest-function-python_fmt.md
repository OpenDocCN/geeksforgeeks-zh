# scipy.stats.skewtest() 函数

> 原文: [https://www.geeksforgeeks.org/scipy-stats-skewtest-function-python/](https://www.geeksforgeeks.org/scipy-stats-skewtest-function-python/)

`scipy.stats.skewtest(array, axis=0)` 函数用于测试数据的偏斜度是否与正态分布有显著差异。该函数检验的零假设是：抽样总体的偏度与相应正态分布的偏度相同。

**其公式：**
![](img/8f05ec50d85b90b45acc7e42ad84dfb4.png)

## 参数

- `array`: 输入数组或包含元素的对象。
- `axis`: 沿着该轴计算偏斜度检验。默认情况下，`axis=0`。

## 返回值

返回数据集假设检验的 Z 值（统计值）和 P 值。

## 代码示例

### 代码 #1

```py
# Performing skewtest
from scipy.stats import skewtest
import numpy as np
import pylab as p

x1 = np.linspace( -5, 5, 1000 )
y1 = 1./(np.sqrt(2.*np.pi)) * np.exp( -.5*(x1)**2  )

p.plot(x1, y1, '*')

print( '\nSkewness test for given data :\n', skewtest(y1))
```

**输出：**

```py
Skewness test for given data :
 SkewtestResult(statistic=11.874007880556805, pvalue=1.6153913086650964e-32)
```

### 代码 #2

```py
# Performing skewtest
from scipy.stats import skewtest
import numpy as np
import pylab as p

x1 = np.linspace( -5, 12, 1000 )
y1 = 1./(np.sqrt(2.*np.pi)) * np.exp( -.5*(x1)**2  )

p.plot(x1, y1, '.')

print( '\nSkewness for data :\n', skewtest(y1))
```

**输出：**

```py
Skewness for data :
 SkewtestResult(statistic=16.957642860709516, pvalue=1.689888374767126e-64)
```