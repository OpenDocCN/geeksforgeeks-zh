# Python 中的 `sympy.stats.Hypergeometric()` 函数

> 原文: [https://www.geeksforgeeks.org/sympy-stats-hypergeometric-function-in-python/](https://www.geeksforgeeks.org/sympy-stats-hypergeometric-function-in-python/)

**超几何分布**是一种离散概率分布，定义了抽奖成功的概率。借助 `sympy.stats.Hypergeometric()` 方法，可以得到表示超几何分布值的有限随机变量。

## 语法
`sympy.stats.Hypergeometric(名称, N, m, N)`

## 参数
- `名称` – 它用来表示分布。
- `N` – 总种群大小。
- `m` – 成功状态的数量。
- `N` – 抽样次数。

## 返回
返回超几何分布。

## 示例 #1
在本例中，我们可以看到，通过使用 `sympy.stats.Hypergeometric()` 方法，我们能够获得表示超几何分布的随机变量。

```py
# Import sympy and hypergeometric
from sympy.stats import Hypergeometric, density

# Using sympy.stats.Hypergeometric() method
# Taking 10 marbles, 5 white(success), 3 draws
X = Hypergeometric('X', 10, 5, 3) 
gfg = density(X).dict

print(gfg)
```

输出:

```py
{0: 1/12, 1: 5/12, 2: 5/12, 3: 1/12}
```

## 示例 2

```py
# Import sympy and hypergeometric
from sympy.stats import Hypergeometric, density

# Using sympy.stats.Hypergeometric() method
X = Hypergeometric('X', 2, 1, 1)
gfg = density(X).dict

print(gfg)
```

输出:

```py
{0: 1/2, 1: 1/2}
```