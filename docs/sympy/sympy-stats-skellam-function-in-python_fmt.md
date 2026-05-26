# Python 中的 sympy.stats.skellam() 函数

> 原文: [https://www.geeksforgeeks.org/sympy-stats-skellam-function-in-python/](https://www.geeksforgeeks.org/sympy-stats-skellam-function-in-python/)

借助 `sympy.stats.Skellam()` 方法，我们可以创建一个具有 Skellam 分布的离散随机变量。

Skellam 分布是两个统计上独立的随机变量 `N1` 和 `N2` 的 `N1-N2` 差的分布，每个都是泊松分布的，具有各自的期望值 `mu1` 和 `mu2`。

## 语法

```py
sympy.stats.Skellam(name, mu1, mu2)
```

## 参数

- `mu1`: 一个非负值。
- `mu2`: 一个非负值。

## 返回值

返回一个具有 Skellam 分布的离散随机变量。

## 示例

### 示例 1

```py
# import sympy, Skellam, density, Symbol
from sympy.stats import Skellam, density
from sympy import Symbol

mu1 = Symbol("mu1", positive = True)
mu2 = Symbol("mu2", positive = True)

# using sympy.stats.Skellam() method
X = Skellam("x", mu1, mu2)
skeDist = density(X)(z)

print(skeDist)
```

**输出:**

```py
(mu1/mu2)**(z/2)*exp(-mu1 - mu2)*besseli(z, 2*sqrt(mu1)*sqrt(mu2))
```

### 示例 2

```py
# import sympy, Skellam, density
from sympy.stats import Skellam, density

# using sympy.stats.Skellam() method
X = Skellam("x", 1, 2)
skeDist = density(X)(3)

print(skeDist)
```

**输出:**

```py
sqrt(2)*exp(-3)*besseli(3, 2*sqrt(2))/4
```