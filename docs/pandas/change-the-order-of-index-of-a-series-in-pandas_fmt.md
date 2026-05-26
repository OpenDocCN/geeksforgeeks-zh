# 更改Pandas Series的索引顺序

> 原文：[https://www.geeksforgeeks.org/change-the-order-of-index-of-a-series-in-pandas/](https://www.geeksforgeeks.org/change-the-order-of-index-of-a-series-in-pandas/)

假设我们想要改变Series索引的顺序，那么我们必须使用pandas模块的`Series.reindex()`方法来执行这个任务。

**Series**，这是一个一维标记的数组，可以保存任何数据。

> **语法：** `pandas.Series(data, index, dtype, copy)`
>
> **参数：**
>
> *   `data`：取ndarrays，list，常量。
> *   `index`：值。
> *   `dtype`：数据类型。
> *   `copy`：数据，默认为False。

想了解更多关于Pandas Series的内容，[点击这里](https://www.geeksforgeeks.org/python-pandas-series/)。

`Series.reindex()`方法在索引的基础上改变数据。

> **语法：** `Series.reindex(labels=None, index=None, columns=None, axis=None, method=None, copy=True, level=None, fill_value=nan, limit=None, tolerance=None)`

想了解更多关于Pandas `Series.reindex()`方法的内容，[点击这里](https://www.geeksforgeeks.org/python-pandas-dataframe-reindex/)。

让我们创建一个Series：

## 示例代码

```py
# import required library
import pandas as pd
import numpy as np

# create numpy array
data = np.array(["Android dev",
                 "content writing",
                 "competetive coding"])
#create a series
total_series = pd.Series(data,
                         index = [1, 2, 3])

# show the series
total_series
```

**输出：**

![Series](img/8e28983c87783fc50b33570c705c48b8.png)

**例1：**

## 示例代码

```py
# import required library
import pandas as pd
import numpy as np

# create numpy array
data = np.array(["Android dev",
                 "content writing",
                 "competetive coding"])
# create a series
total_series = pd.Series(data,
                         index = [1, 2, 3])
# reindexing of series
total_series = total_series.reindex(index 
                                    = [3, 2, 1])
# show the series
total_series
```

**输出：**

![Reindexing on series](img/3b94cbd9ce2140a9bce9f7c78f752d7f.png)

**例2：**

## 示例代码

```py
# import required library
import pandas as pd
import numpy as np

# create numpy array
data = np.array(["Android dev",
                 "content writing",
                 "competetive coding"])
# create a series
total_series = pd.Series(data,
                         index = [1, 2, 3])
# reindexing of series
total_series = total_series.reindex([2, 3, 1])

# show the series
total_series
```

**输出：**

![Reindexing on series-2](img/e3b346f320fc4b0a9ea800f5dfb08f8b.png)