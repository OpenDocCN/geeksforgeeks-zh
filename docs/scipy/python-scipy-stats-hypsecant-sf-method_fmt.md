# Python Scipy stats.hypsecant.sf() 方法

> 原文: [https://www.geeksforgeeks.org/python-scipy-stats-hypsecant-sf-method/](https://www.geeksforgeeks.org/python-scipy-stats-hypsecant-sf-method/)

借助 `stats.hypsecant.sf()` 方法，我们可以得到生存函数值，即 **1–CDF**。

## 语法
`stats.hypsecant.sf(x, beta)`

## 返回
返回生存函数的值。

### 例 1
在这个例子中我们可以看到，通过使用 `stats.hypsecant.sf()` 方法，我们能够得到生存函数值。

```py
# import hypsecant
from scipy.stats import hypsecant
beta = 1

# Using stats.hypsecant.sf() method
gfg = hypsecant.sf(0.3, beta)

print(gfg)
```

**输出:**
> 0.7065742294890258

### 例 2

```py
# import hypsecant
from scipy.stats import hypsecant
beta = 4

# Using stats.hypsecant.sf() method
gfg = hypsecant.sf(0.9, beta)

print(gfg)
```

**输出:**
> 0.9713401642619637