# 如何对代表图像的 NumPy 数组进行重采样？

> 原文: [https://www.geeksforgeeks.org/how-to-resample-numpy-array-representing-an-image/](https://www.geeksforgeeks.org/how-to-resample-numpy-array-representing-an-image/)

在本文中，我们将对代表图像的 NumPy 数组进行重采样。为此，我们使用 `scipy` 包。`scipy` 包附带了 `ndimage.zoom()` 方法，该方法通过使用给定顺序的样条插值放大 NumPy 数组来为我们实现这一点。默认值为 3 阶（也称为立方）。

对于包含虚部的输入，`ndimage.zoom` 独立缩放实部和虚部。

> **语法:** `scipy.ndimage.zoom(input, zoom, output=None, order=3, mode='constant', cval=0.0, prefilter=True, *grid_mode=False)`
>
> **参数:**
>
> *   `input`: 定义数组。
> *   `zoom`: 既可以取一个序列，也可以取一个数字。如果是一个数字，则表示在所有轴上应用相同值的缩放；如果提供了序列，则按照给定的顺序应用到 x, y, z…等。
> *   `output`: 默认情况下会创建相同输入数据类型的输出。
> *   `order`: 样条插值，必须在 [0, 5] 之间（含 0, 5）。
> *   `mode`: 最重要的参数之一，决定插值必须如何进行。对于边界像素，它可以从这个列表中取值：`['reflect', 'constant', 'nearest', 'mirror', 'wrap']`。
> *   `prefilter`: 取布尔值，判断输入数组在插值前是否需要用样条滤波进行预滤波。
>
> **返回:** 标准缩放输入。

## 例子

为了完成缩放任务，我们将首先创建一个如下所示的数组：

```python
import numpy as np
import scipy.ndimage

ndarray = np.array([[11, 12, 13, 14],
                    [21, 22, 23, 24],
                    [31, 32, 33, 34],
                    [41, 42, 43, 44]])
print(ndarray)
```

**输出:**

```py
[[11 12 13 14]
 [21 22 23 24]
 [31 32 33 34]
 [41 42 43 44]]
```

**例 1:** 在本例中，我们将通过：

*   `ndarray` 作为输入数组。
*   `zoom`: 2（用值缩放）。
*   `order`: 0（样条插值）。

由于 `order = 0`，`zoom = 2`，所以缩放是在具有相同值的轴上进行的。

```python
print(scipy.ndimage.zoom(
  ndarray, 2, order = 0))
```