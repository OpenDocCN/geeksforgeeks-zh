# Python | Pandas TimedeltaIndex.slice_locs()

> 原文: [https://www.geeksforgeeks.org/python-pandas-timedeltaindex-slice_locs/](https://www.geeksforgeeks.org/python-pandas-timedeltaindex-slice_locs/)

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 python 包的奇妙生态系统。`pandas` 就是其中一个包，让导入和分析数据变得容易多了。

## TimedeltaIndex.slice_locs() 函数

`TimedeltaIndex.slice_locs()` 函数计算输入标签的切片位置，并步进一个有序的时间增量索引对象。该函数假设数据已排序。

> **语法:** `TimedeltaIndex.slice_locs(start=None, end=None, step=None, kind=None)`
>
> **参数:**
> - **start:** (标签，默认 `None`) 如果 `None`，默认开始。
> - **end:** (标签，默认 `None`) 如果 `None`，默认结束。
> - **step:** (int，默认 `None`) 如果 `None`，默认 1。
> - **kind:** {'ix', 'loc', 'getitem'} 或 `None`。
>
> **返回:** `start`, `end`: int

## 示例 1

使用 `TimedeltaIndex.slice_locs()` 函数计算给定时间增量索引对象中传递的标签的切片位置。

```py
# importing pandas as pd
import pandas as pd

# Create the TimedeltaIndex object
tidx = pd.TimedeltaIndex(start ='11 days 22:14:12.001124', periods = 5, freq ='T')

# Print the TimedeltaIndex object
print(tidx)
```

**输出:**
![](img/856277f2e6ae685a7306e94f999507c9.png)

现在我们将使用 `TimedeltaIndex.slice_locs()` 函数为传递的标签找到切片位置值。

```py
# find the slice location for the passed label
tidx.slice_locs('11 days 22:15:20.001124')
```

**输出:**
![](img/fec96b8fd29b8f581d93f0fd1a39721a.png)

正如我们在输出中看到的那样，`TimedeltaIndex.slice_locs()` 函数已经返回了 `tidx` 对象中切片的开始位置和结束位置。

## 示例 2

使用 `TimedeltaIndex.slice_locs()` 函数计算给定时间增量索引对象中传递的标签的切片位置。

```py
# importing pandas as pd
import pandas as pd

# Create the TimedeltaIndex object
tidx = pd.TimedeltaIndex(start ='03 days 09:22:56', periods = 5, freq ='H')

# Print the TimedeltaIndex object
print(tidx)
```

**输出:**
![](img/ef5db482e0443064fbdb081652a92b7c.png)

现在我们将使用 `TimedeltaIndex.slice_locs()` 函数为传递的标签找到切片位置值。

```py
# find the slice location for the passed label
tidx.slice_locs('3 days 12:20:56')
```

**输出:**
![](img/4e06f758635dc1bb485226a2c63d087b.png)

正如我们在输出中看到的，`TimedeltaIndex.slice_locs` 函数已经返回了 `tidx` 对象中切片的开始位置和结束位置。