# Python sympy binomial_coefficients_list()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-binomial_coefficients_list-method/](https://www.geeksforgeeks.org/python-sympy-binomial_coefficients_list-method/)

借助`binomial_coefficients_list()`方法，我们可以将二项式系数作为帕斯卡三角形的行。

> **语法:** `binomial_coefficients_list(n)`
>
> **参数:**
> `n` – 表示整数。
>
> **返回:** 以帕斯卡三角形的行形式返回二项式系数列表。

**示例#1:**

```py
# import binomial_coefficients_list() method from sympy
from sympy.ntheory import binomial_coefficients_list

n = 6

# Use binomial_coefficients_list() method
binomial_coefficients_list_n = binomial_coefficients_list(n)

print("{}th row of Pascal's Triangle = {} ".format(n, binomial_coefficients_list_n))
```

**输出:**

```py
6th row of Pascal's Triangle = [1, 6, 15, 20, 15, 6, 1]
```

**例 2:**

```py
# import binomial_coefficients_list() method from sympy
from sympy.ntheory import binomial_coefficients_list

n = 9

# Use binomial_coefficients_list() method
binomial_coefficients_list_n = binomial_coefficients_list(n)

print("{}th row of Pascal's Triangle = {} ".format(n, binomial_coefficients_list_n))
```

**输出:**

```py
9th row of Pascal's Triangle = [1, 9, 36, 84, 126, 126, 84, 36, 9, 1]
```