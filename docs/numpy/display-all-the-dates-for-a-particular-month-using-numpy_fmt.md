# 使用 NumPy 显示特定月份的所有日期

> 原文: [https://www.geeksforgeeks.org/display-all-the-dates-for-a-particular-month-using-numpy/](https://www.geeksforgeeks.org/display-all-the-dates-for-a-particular-month-using-numpy/)

在 NumPy 中，为了显示特定月份的所有日期，我们可以在 `numpy.array()` 的帮助下完成，传递第一个参数特定月份和第二个参数下个月，第三个参数是数据类型 `datetime64[D]`。它将返回特定月份的所有日期。

> **语法:** `numpy.array(*start*, *stop*, *step*, *dtype=None*)`
>
> **参数:**
>
> `start`: 开始间隔
>
> `stop`: 间隔结束
>
> `step`: 值之间的间距
>
> `dtype`: 输出数组的类型。如果没有给出 [`dtype`](https://numpy.org/doc/stable/reference/generated/numpy.dtype.html#numpy.dtype)，从其他输入参数中推断数据类型。
>
> **返回:**
>
> `ndarray`

**例 1:**

## Python 3

```py
import numpy as np

# dates of july  2020
print(np.arrange('2012-07', '2020-08',
                 dtype='datetime64[D]'))
```