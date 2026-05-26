# Pandas `Series.pct_change()` 方法

> 原文: [https://www.geeksforgeeks.org/python-pandas-series-pct_change/](https://www.geeksforgeeks.org/python-pandas-series-pct_change/)

Pandas `pct_change()` 方法应用于具有数字数据的 Series，以计算 n 个元素后的百分比变化。默认情况下，它计算当前元素相对于前一个元素的百分比变化：`(当前 - 以前) / 以前 * 100`。
首先，n（`periods`）个值始终为 `NaN`，因为没有之前的值可用于计算变化。

## 语法

`Series.pct_change(periods=1, fill_method='pad', limit=None)`

## 参数

- `periods`：定义当前值和上一个值之间的差距。默认值为 1。
- `fill_method`：定义用于处理空值的方法。
- `limit`：停止前要填充的连续 `NaN` 值的数量。

## 返回类型

百分比变化的数值序列。

## 示例 1

在该方法中，使用 `pandas.Series()` 从 Python 列表中创建一个 Series。该序列不包含任何空值，因此直接调用 `pct_change()` 方法，默认值为 `periods` 参数，即 1。

```py
# importing pandas module
import pandas as pd

# importing numpy module
import numpy as np

# creating list
list = [10, 14, 20, 25, 12.5, 13, 0, 50]

# creating series
series = pd.Series(list)

# calling method
result = series.pct_change()

# display
result
```

**输出:**

```py
0         NaN
1    0.400000
2    0.428571
3    0.250000
4   -0.500000
5    0.040000
6   -1.000000
7         inf
dtype: float64
```

如输出所示，前 n 个值始终等于 `NaN`。其余值等于旧值的百分比变化，并存储在与调用者 Series 相同的位置。
**注意:** 由于倒数第二个值为 0，百分比变化为 `inf`。`inf` 代表无限。
使用公式，`pct_change = (x - 0) / 0 = inf`。

## 示例 2：处理空值

在本例中，一些空值也是使用 Numpy 的 `np.nan` 方法创建的，并传递给列表。`fill_method` 传递为 `'bfill'`。`'bfill'` 代表反向填充，并将在下一个位置用值填充空值。

```py
# importing pandas module
import pandas as pd

# importing numpy module
import numpy as np

# creating list
list = [10, np.nan, 14, 20, 25, 12.5, 13, 0, 50]

# creating series
series = pd.Series(list)

# calling method
result = series.pct_change(fill_method='bfill')

# display
result
```

**输出:**

```py
0         NaN
1    0.400000
2    0.000000
3    0.428571
4    0.250000
5   -0.500000
6    0.040000
7   -1.000000
8         inf
dtype: float64
```

从输出中可以看出，位置 1 的值是 0.4，因为 `NaN` 被 14 代替。因此，`(14 - 10) / 10 * 100 = 40`。下一个值是 0，因为 14 和 14 中的百分比变化是 0。