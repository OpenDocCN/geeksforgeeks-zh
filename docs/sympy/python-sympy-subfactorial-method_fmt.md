# Python | sympy.subfactorial()方法

> 原文: `https://www.geeksforgeeks.org/python-sympy-subfactorial-method/`

借助`sympy.subfactorial()`方法，我们可以在 SymPy 中找到一个数的[subfactorial](https://en.wikipedia.org/wiki/Subfactorial)。一个数的子因子由以下公式定义：

![ !n = \begin{cases} 1 & n = 0 \\ 0 & n = 1 \\ (n-1)(!(n-1) + !(n-2)) & n > 1 \end{cases}  ](img/90ab2fc1545fe7a70bd7b5d2d33630a6.png "Rendered by QuickLaTeX.com")

## 语法

`subfactorial(n)`

## 参数

- **n** – 表示要计算其子阶乘的数字。

## 返回值

返回数字的子阶乘，即 `!n`。

## 示例

### 示例 1

```py
# import sympy 
from sympy import *

n = 4
print("Value of n = {}".format(n))

# Use sympy.subfactorial() method 
subfactorial_n = subfactorial(n)

print("Subfactorial of n : {}".format(subfactorial_n))  
```

**输出:**

```py
Value of n = 4
Subfactorial of n : 9
```

### 示例 2

```py
# import sympy 
from sympy import *

n = 9
print("Value of n = {}".format(n))

# Use sympy.subfactorial() method 
subfactorial_n = subfactorial(n)

print("Subfactorial of n : {}".format(subfactorial_n))  
```

**输出:**

```py
Value of n = 9
Subfactorial of n : 133496
```