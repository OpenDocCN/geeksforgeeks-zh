# Python 中的 sympy.stats.BetaBinomial()函数

> 原文: [https://www.geeksforgeeks.org/sympy-stats-betabinomial-function-in-python/](https://www.geeksforgeeks.org/sympy-stats-betabinomial-function-in-python/)

借助 `sympy.stats.BetaBinomial()` 方法，我们可以创建一个能够表示β二项分布的随机变量。

**语法:**
`sympy.stats.BetaBinomial(name, n, alpha, beta)`

**参数:**
- `name` – 它给一个分布命名。
- `n` – 正整数，`n` 次试验次数。
- `alpha` – 实正数。
- `beta` – 实正数。

**示例 #1:**
在这个示例中，我们可以看到，通过使用 `sympy.stats.BetaBinomial()` 方法，我们能够创建表示β-二项式分布的随机变量。

```py
# Import Sympy and BetaBinomial
from sympy.stats import BetaBinomial, density

# Using sympy.stats.BetaBinomial() method
X = BetaBinomial('X', 2, 3, 1)
gfg = density(X).dict

print(gfg)
```

**输出:**
> {0: 3*beta(3, 3), 1: 6*beta(4, 2), 2: 3/5}

**示例 2:**

```py
# Import Sympy and BetaBinomial
from sympy.stats import BetaBinomial, density

# Using sympy.stats.BetaBinomial() method
X = BetaBinomial('X', 5, 3, 4)
gfg = density(X).dict

print(gfg)
```

**输出:**
> {0: beta(3, 9)/beta(3, 4), 1: 5*beta(4, 8)/beta(3, 4), 2: 10*beta(5, 7)/beta(3, 4), 3: 10*beta(6, 6)/beta(3, 4), 4: 5*beta(7, 5)/beta(3, 4), 5: beta(8, 4)/beta(3, 4)}