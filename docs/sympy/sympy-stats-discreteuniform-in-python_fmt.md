# SymPy 统计：离散均匀分布

> 原文：[https://www.geeksforgeeks.org/sympy-stats-discreteuniform-in-python/](https://www.geeksforgeeks.org/sympy-stats-discreteuniform-in-python/)

借助 `sympy.stats.DiscreteUniform()` 方法，我们可以通过该方法获得一个代表离散均匀分布的随机变量。

## 语法

`sympy.stats.DiscreteUniform(list/tuple)`

## 返回

返回离散均匀分布的随机变量。

## 示例 #1

在这个示例中，我们可以看到，通过使用 `sympy.stats.DiscreteUniform()` 方法，我们能够获得表示离散均匀值的随机变量。

```python
# Import sympy and DiscreteUniform
from sympy.stats import DiscreteUniform, density
from sympy import symbols

# Using stats.DiscreteUniform() method
X = DiscreteUniform('X', symbols('g f g'))
gfg = density(X).dict

print(gfg)
```

**输出：**

> {g: 1/3, f: 1/3}

## 示例 #2

```python
# Import sympy and DiscreteUniform
from sympy.stats import DiscreteUniform, density
from sympy import symbols

# Using stats.DiscreteUniform() method
Y = DiscreteUniform('Y', list(range(5)))
gfg = density(Y).dict

print(gfg)
```

**输出：**

> {0: 1/5, 1: 1/5, 2: 1/5, 3: 1/5, 4: 1/5}