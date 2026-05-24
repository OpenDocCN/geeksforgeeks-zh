# 连分式分解算法

> 原文：[https://www.geeksforgeeks.org/continued-fraction-factorization-algorithm/](https://www.geeksforgeeks.org/continued-fraction-factorization-algorithm/)

`CFRAC`（连分式因式分解法）是一种对整数有效的通用因式分解算法。它计算给定整数的因子，而不考虑其唯一性。它的运行时间低于指数。1931 年由 D. H. Lehmer 和 R. E. Powers 首次描述，后来在 1975 年由迈克尔 A. 莫里森和约翰·布里尔哈特开发成计算机算法。

## 连分式

一个可以表示为以下形式的表达式：

(1)
$$
X=a_{0}+\frac{b_{1}}{a_{1}+\frac{b_{2}}{a_{2} \ldots+\frac{b_{n-1}}{a_{n-1}+\frac{b_{n}}{a_{n}}}}}
$$
被称为连分式，其中 $a_i$ 和 $b_i$ 是所有 $i \ge 0$ 的实值或复值。当所有 $b_i$ 的值都为 1 时，则称之为简单连分式。

简单连分式可以表示为：

(2)
$$
\left[a_{0} ; a_{1}, a_{2} \ldots a_{n}\right]=a_{0}+\frac{1}{a_{1}+\frac{1}{a_{2} \ldots+\frac{1}{a_{n-1}+\frac{1}{a_{n}}}}}
$$
其中 $C_k = [a_0; a_1, a_2, \ldots, a_k]$（$k \le n$）代表简单连分式的第 $k$ 次收敛。
无限连分数 $[a_0; a_1, a_2, \ldots, a_k, \ldots]$ 定义为收敛器 $C_k = [a_0; a_1, a_2, \ldots, a_k]$。

## 算法

该算法利用 $(mn)^{1/2}$ 的连分式中产生的余数对某个 $m$ 产生一个平方数。

该算法求解数学方程：

(3)
$$
x^{2} \equiv y^{2} \pmod{n}
$$
通过计算 $m$ 的值求解该方程，使得 $m^2 \pmod{n}$ 具有最小上界。

`CFRAC` 算法的时间复杂度为：

(4)
$$
O\left(e^{\sqrt{2 \log n \log \log n}}\right)
$$

## 示例

### 示例 1

```py
Input: continued_fraction((10/7))
Output: [1, 2, 3]
Explanation:
```

(5)
$$
[1,2,3]=1+\frac{1}{2+\frac{1}{3}}=1+\frac{1}{\frac{7}{3}}=1+\frac{3}{7}=\frac{10}{7}
$$

### 示例 2

```py
Input: list(continued_fraction_convergents([0, 2, 1, 2]))
Output: [0, 1/2, 1/3, 3/8]
Explanation:
```

(6)
$$
\begin{array}{c}
{[0,2,1,2]=0+\frac{1}{2+\frac{1}{1+\frac{1}{2}}}} \\
c_{1}=0, c_{2}=0+\frac{1}{2}=\frac{1}{2}, c_{3}=0+\frac{1}{2+\frac{1}{1}}=\frac{1}{3}, c_{4}=0+\frac{1}{2+\frac{1}{1+\frac{1}{2}}}=0+\frac{1}{2+\frac{1}{\frac{3}{2}}}=0+\frac{1}{2+\frac{2}{3}}=0+\frac{1}{\frac{8}{3}}=\frac{3}{8}
\end{array}
$$

### 示例 3

```py
Input: continued_fraction_reduce([1, 2, 3, 4, 5])
Output: 225/157
Explanation:
```

(7)
$$
1+\frac{1}{2+\frac{1}{3+\frac{1}{4+\frac{1}{5}}}}=1+\frac{1}{2+\frac{1}{3+\frac{1}{\frac{21}{5}}}}=1+\frac{1}{2+\frac{1}{3+\frac{5}{21}}}=1+\frac{1}{2+\frac{1}{\frac{68}{21}}}=1+\frac{1}{2+\frac{21}{68}}=1+\frac{1}{\frac{157}{68}}=1+\frac{68}{157}=\frac{225}{157}
$$

## 实现

### 代码 1：将分数转换为连分数表示

```py
# using sympy module
from sympy.ntheory.continued_fraction import continued_fraction
from sympy import sqrt

# calling continued_fraction method
continued_fraction(10/7)
```

**输出：**

```py
[1, 2, 3]
```

### 代码 2：将连分数转换为分数

```py
# using sympy module
from sympy.ntheory.continued_fraction import continued_fraction_reduce

# calling continued_fraction_reduce method
continued_fraction_reduce([1, 2, 3, 4, 5])
```

**输出：**

```py
225/157
```

### 代码 3：从一个连分式中获取一个收敛子列表

```py
# using sympy module
from sympy.core import Rational, pi
from sympy import S
from sympy.ntheory.continued_fraction import continued_fraction_convergents, continued_fraction_iterator

# calling continued_fraction_convergents method and
# passing it as a parameter to a list
list(continued_fraction_convergents([0, 2, 1, 2]))
```

**输出：**

```py
[0, 1/2, 1/3, 3/8]
```