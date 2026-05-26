# Python | sympy.reduced_totient()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-reduced_totient-method/](https://www.geeksforgeeks.org/python-sympy-reduced_totient-method/)

借助`sympy.reduced_totient()`方法，我们可以在 SymPy 中找到 [Carmichael reduced totient function 或 lambda(n)](https://en.wikipedia.org/wiki/Carmichael_function)。`reduced_totient(n)`或 $\lambda(n)$ 是最小的 $m > 0$，使得所有与 $n$ 互质的 $k$ 满足 $k^m \equiv 1 \mod n$。

> **语法:** `reduced_totient(n)`
>
> **参数:**
> **n** – 表示整数。
>
> **返回:** 返回最小整数 $m > 0$，使得对于所有与 $n$ 互质的 $k$，$k^m \% n$ 都等于 1。

**示例#1:**

```py
# import reduced_totient() method from sympy
from sympy.ntheory import reduced_totient

n = 8

# Use reduced_totient() method
reduced_totient_n = reduced_totient(n)

print("lambda({}) =  {} ".format(n, reduced_totient_n))
# 1 ^ 2 = 1 (mod 8), 3 ^ 2 = 9 = 1 (mod 8),
# 5 ^ 2 = 25 = 1 (mod 8) and 7 ^ 2 = 49 = 1 (mod 8)
```

**输出:**

```py
lambda(8) =  2
```

**例 2:**

```py
# import reduced_totient() method from sympy
from sympy.ntheory import reduced_totient

n = 30

# Use reduced_totient() method
reduced_totient_n = reduced_totient(n)

print("lambda({}) =  {} ".format(n, reduced_totient_n))
```

**输出:**

```py
lambda(30) =  4
```