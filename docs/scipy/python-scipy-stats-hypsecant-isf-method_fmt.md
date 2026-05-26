# Python Scipy stats.hypsecant.isf() 方法

> 原文: [https://www.geeksforgeeks.org/python-scipy-stats-hypsecant-isf-method/](https://www.geeksforgeeks.org/python-scipy-stats-hypsecant-isf-method/)

借助 `stats.hypsecant.isf()` 方法，我们可以得到生存反函数的值，即逆(1–CDF)。

## 语法

`stats.hypsecant.isf(x, beta)`

## 返回

返回逆生存函数的值。

## 示例 1

在这个例子中我们可以看到，通过使用 `stats.hypsecant.isf()` 方法，我们能够得到逆生存函数值。

```py
# import hypsecant
from scipy.stats import hypsecant
beta = 1

# Using stats.hypsecant.isf() method
gfg = hypsecant.isf(0.3, beta)

print(gfg)
```

输出:

> 1.6742754776268165

## 示例 2

```py
# import hypsecant
from scipy.stats import hypsecant
beta = 4

# Using stats.hypsecant.isf() method
gfg = hypsecant.isf(0.9, beta)

print(gfg)
```

输出:

> 2.1572699652988865