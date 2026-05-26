# Python Scipy stats.hypsecant.interval()方法

> 原文: [https://www.geeksforgeeks.org/python-scipy-stats-hypsecant-interval-method/](https://www.geeksforgeeks.org/python-scipy-stats-hypsecant-interval-method/)

借助 `stats.hypsecant.interval()` 方法，我们可以得到包含分布α%范围的端点值。

> **语法:** `stats.hypsecant.interval(alpha)`
> **返回:** 返回分布端点的值。

## 例 1

在这个例子中我们可以看到，通过使用 `stats.hypsecant.interval()` 方法，我们能够得到分布的端点值。

```py
# import hypsecant
from scipy.stats import hypsecant
alpha = 0.1

# Using stats.hypsecant.interval() method
gfg = hypsecant.interval(alpha)

print(gfg)
```

**输出:**

> (-0.15772961019105322, 0.15772961019105325)

## 例 2

```py
# import hypsecant
from scipy.stats import hypsecant
alpha = 1

# Using stats.hypsecant.interval() method
gfg = hypsecant.interval(alpha)

print(gfg)
```

**输出:**

> (-inf, inf)