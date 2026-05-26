# Python | Pandas Series.plot()方法

> 原文: [https://www.geeksforgeeks.org/python-pandas-series-plot-method/](https://www.geeksforgeeks.org/python-pandas-series-plot-method/)

借助`Series.plot()`方法，我们可以利用`Series.plot()`方法得到熊猫系列的剧情。

## 语法

`Series.plot()`

## 返回

返回系列的剧情。

## 示例 1

在这个示例中，我们可以看到通过使用`Series.plot()`方法，我们能够获得pandas系列的绘图。

```py
# import Series and matplotlib
import pandas as pd
import matplotlib.pyplot as plt

# using Series.plot() method
gfg = pd.Series([0.1, 0.4, 0.16, 0.3, 0.9, 0.81])

gfg.plot()
plt.show()
```

**输出:**

![](img/fbfdd153af94fa52c315000174ebee60.png)

## 示例 2

```py
# import Series and matplotlib
import pandas as pd
import matplotlib.pyplot as plt

# using Series.plot() method
gfg = pd.Series([10, 9.9, 9.8, 7.8, 6.7, 19, 5.5])

gfg.plot()
plt.show()
```

**输出:**

![](img/1c8fe822bc8bc19fc171db66bd3fc888.png)