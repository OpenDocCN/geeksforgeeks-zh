## `scipy.stats.halfgennorm.median()` 方法

> 原文：[https://www.geeksforgeeks.org/python-scipy-stats-halfgennorm-median-method/](https://www.geeksforgeeks.org/python-scipy-stats-halfgennorm-median-method/)

`scipy.stats.halfgennorm.median()` 方法用于计算半广义正态分布的中位数。

> **语法：** `stats.halfgennorm.median(beta)`
> **返回：** 返回分布的中位数。

### 示例 1

在此示例中，我们将看到如何使用 `stats.halfgennorm.median()` 方法来获取分布的中位数。

```py
# import halfgennorm
from scipy.stats import halfgennorm
beta = 1

# Using stats.halfgennorm.median() method
gfg = halfgennorm.median(beta)

print(gfg)
```

**输出：**

> 0.6931471805599455

### 示例 2

```py
# import halfgennorm
from scipy.stats import halfgennorm
beta = 4

# Using stats.halfgennorm.median() method
gfg = halfgennorm.median(beta)

print(gfg)
```

**输出：**

> 0.4571463442259011