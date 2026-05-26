# Python | Pandas `index.slice_locs()`

> 原文: [https://www.geeksforgeeks.org/python-pandas-index-slice_locs/](https://www.geeksforgeeks.org/python-pandas-index-slice_locs/)

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 python 包的奇妙生态系统。`Pandas` 就是其中一个包，让导入和分析数据变得容易多了。

`Pandas` 的 `Index.slice_locs()` 功能计算输入标签的切片位置。它将开始和结束标签作为参数，并返回与这些值对应的整数值。

## 语法

`index.slice_locs(start=None, end=None, step=None, kind=None)`

**参数:**
- `start`: 如果为 `None`，默认为开始。
- `end`: 如果为 `None`，默认为结束。
- `step`: 如果为 `None`，默认为 1。
- `kind`: `{'ix', 'loc', 'getitem'}` 或 `None`。

**返回:** `start`, `end`: int

## 示例

### 示例 #1

使用 `Index.slice_locs()` 功能查找输入值的切片标签。

```python
# importing pandas as pd
import pandas as pd

# Creating the index
idx = pd.Index(['Beagle', 'Pug', 'Labrador', 'Sephard',
                'Mastiff', None, 'Husky'])

# Print the index
idx
```

**输出:**
![](img/8efade14bc8348beb3205ff0ddc0154b.png)

现在我们将找到“Pug”和“Mastiff”的切片标签。

```python
# finding the slice labels for the input value.
idx.slice_locs(start='Pug', end='Mastiff')
```

**输出:**
![](img/c512698077a20b12856e4a99794371fc.png)

正如我们在输出中看到的，该函数已经返回了输入标签的切片位置。

### 示例 #2

使用 `Index.slice_locs()` 函数在日期时间基准索引中查找切片标签。

```python
# importing pandas as pd
import pandas as pd

# Creating the index
idx = pd.date_range('1/1/2018', periods=5, freq='MS')

# Print the index
idx
```

**输出:**
![](img/f7a9b69082e4e7d4cf9842d255f2f356.png)

现在，我们将找到输入标签的切片标签。

```python
# finding the slice labels
idx.slice_locs(start='2018-02-01', end='2018-04-01')
```

**输出:**
![](img/6d027df07a74802bb557bfdf26b8e169.png)

正如我们在输出中看到的，函数返回了包含输入切片标签值的范围值。