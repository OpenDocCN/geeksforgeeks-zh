# Python | sympy.factorial2() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-factorial2-method/](https://www.geeksforgeeks.org/python-sympy-factorial2-method/)

借助 `factorial2()` 方法，我们可以找到[双阶乘](https://en.wikipedia.org/wiki/Double_factorial)。数字的双阶乘由以下公式定义：

![ n!! = \begin{cases} 1 & n = 0 \\ n(n-2)(n-4) \cdots 1 & n\ \text{positive odd} \\ n(n-2)(n-4) \cdots 2 & n\ \text{positive even} \\ (n+2)!!/(n+2) & n\ \text{negative odd} \end{cases}  ](img/b88876273781e706a0e983f4766f968e.png "Rendered by QuickLaTeX.com")

## 语法
`factorial2(n)`

## 参数
- `n` – 表示要计算双阶乘的数。

## 返回
返回数字的双阶乘，即 `n`。

### 示例 #1
```py
# import sympy 
from sympy import *

n = 10
print("Value of n = {}".format(n))

# Use sympy.factorial2() method 
factorial2_n = factorial2(n)

print("Double factorial of n : {}".format(factorial2_n))  
```

**输出:**
```py
Value of n = 10
Double factorial of n : 3840
```

### 示例 #2
```py
# import sympy 
from sympy import *

n = -3
print("Value of n = {}".format(n))

# Use sympy.factorial2() method 
factorial2_n = factorial2(n)

print("Double factorial of n : {}".format(factorial2_n))  
```

**输出:**
```py
Value of n = -3
Double factorial of n : -1
```