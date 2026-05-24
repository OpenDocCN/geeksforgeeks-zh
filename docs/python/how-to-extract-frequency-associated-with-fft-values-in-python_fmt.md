# 如何在 Python 中提取与 fft 值关联的频率？

> 原文: [https://www.geeksforgeeks.org/how-to-extract-frequency-associated-with-fft-values-in-python/](https://www.geeksforgeeks.org/how-to-extract-frequency-associated-with-fft-values-in-python/)

在本文中，我们将从快速傅立叶变换中找出提取的频率值。我们可以从执行快速傅立叶变换（即 Python 中的 `fft`）后获得的一组复数中获得频率的大小。频率可以通过计算复数的大小得到。所以每个复数上的简单 `abs(x)` 应该返回频率。

## 所需方法

为了提取与 `fft` 值相关的频率，我们将使用 [`numpy`](https://www.geeksforgeeks.org/numpy-in-python-set-1-introduction/) 模块的 `fft()` 和 `fftfreq()` 方法。

*   `numpy.fft.fft()`: 用优化的 `fft` 即快速傅里叶变换算法计算一维 n 点 `DFT` 即离散傅里叶变换。

> **语法:** `numpy.fft.fft(a, axis=-1)`
>
> **参数:**
>
> *   `a`: 输入数组可以是复杂的。
> *   `axis`: 计算快速傅立叶变换的轴。如果没有给出，则使用最后一个轴。
>
> **返回:** 截断或零填充的输入，沿轴指示的轴变换，如果未指定轴，则返回最后一个。

*   `numpy.fft.fftfreq()`: 它计算与系数相关的频率。

> **语法:** `numpy.fft.fftfreq(n, d=1.0)`
>
> *   `n`: 窗长。
> *   `d`: 采样间隔（采样速率的倒数）。默认为 1。
>
> **返回:** 长度数组 `n` 包含采样频率。

## 分步方法

### 步骤 1: 导入所需模块

```py
# import module
import numpy as np
```

### 步骤 2: 使用 NumPy 创建一个数组

```py
# assign data
x = np.array([1,2,1,0,1,2,1,0])
```