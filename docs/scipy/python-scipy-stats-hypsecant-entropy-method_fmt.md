# Python | Scipy stats.hypsecant.entropy()方法

> 原文: [https://www.geeksforgeeks.org/python-scipy-stats-hypsecant-entropy-method/](https://www.geeksforgeeks.org/python-scipy-stats-hypsecant-entropy-method/)

借助`stats.hypsecant.entropy()`方法，我们可以得到随机变量的熵值。

> **语法:** `stats.hypsecant.entropy(beta)`
> **返回:** 返回随机变量的熵值。

## 例 1

在这个例子中我们可以看到，通过使用`stats.hypsecant.entropy()`方法，我们能够得到随机变量的熵值。

```py
# import hypsecant
from scipy.stats import hypsecant
beta = 2

# Using stats.hypsecant.entropy() method
gfg = hypsecant.entropy(beta)

print(gfg)
```

**输出:**

> 1.8378770664093453

## 例 2

```py
# import hypsecant
from scipy.stats import hypsecant
beta = 4

# Using stats.hypsecant.entropy() method
gfg = hypsecant.entropy(beta)

print(gfg)
```

**输出:**

> 1.8378770664093453