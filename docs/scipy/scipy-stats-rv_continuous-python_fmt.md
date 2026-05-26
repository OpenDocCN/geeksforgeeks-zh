# scipy.stats.rv_continuous()

> 原文: [https://www.geeksforgeeks.org/scipy-stats-rv_continuous-python/](https://www.geeksforgeeks.org/scipy-stats-rv_continuous-python/)

`scipy.stats.rv_continuous()` 是一个连续的随机变量类，用于子类化。它是从连续随机变量构造特定分布的基类。这个类不能直接用作分布。

## 参数

- **momtype**: 【int】时刻计算使用：0 为 `pdf`，1 为 `ppf`。默认值= 1
- **a**: 【float】分配下限。默认值为 -ve infinity。
- **b**: 【float】分布上限。默认值为 +ve 无穷大。
- **xtol**: 【float】`ppf` 定点计算公差
- **name**: 【str】实例名称。用于构造默认值，例如对于分布
- **badvalue**: 【object】默认值是 `np.nan`。结果数组中的值，表示违反了某些参数限制的值。
- **longname**: 【str】用作文档字符串第一行的一部分。
- **extradoc**: 【str】用作文档字符串的最后一部分
- **shapes**: 【str】形状的分布。

## 返回

连续随机变量分布。

## 代码示例

### 代码#1：使用 `rv_continuous` 类

```py
def sample(self, size = 1, random_state = None):
    """
        Return a sample from PDF - Probability Distribution Function.
        calling - rv_continuous class.
    """
    return self._rv.rvs(size = size, random_state = random_state)
```

### 代码#2：从 `rv_continuous` 创建高斯分布

```py
from scipy.stats import rv_continuous
import numpy as np

class gaussian_gen(rv_continuous):
    '''Gaussian distribution'''
    def _pdf(self, x):
        return np.exp(-x**2 / 2.) / np.sqrt(2.0 * np.pi)

gaussian = gaussian_gen(name = 'gaussian')

x = 2.0
gaussian._pdf(x)
```

### 输出

```py
0.05399096651318806
```