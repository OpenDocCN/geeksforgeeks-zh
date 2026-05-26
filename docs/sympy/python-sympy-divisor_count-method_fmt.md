# Python | sympy.divisor_count()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-divisor_count-method/](https://www.geeksforgeeks.org/python-sympy-divisor_count-method/)

借助 `sympy.divisor_count()` 方法，我们可以统计给定整数的除数。

## 语法
`divisor_count(n, modulus=1)`

## 参数
- `n` – 表示整数。
- `modulus` – 默认设置为 1。如果 `modulus` 不是 1，那么只计算那些能被 `modulus` 整除的。

## 返回
返回给定数的除数。

## 示例#1

```py
# import divisor_count() method from sympy
from sympy import divisor_count

n = 84

# Use divisor_count() method 
divisor_count_n = divisor_count(n)

print("The number of divisors of {} : {}".format(n, divisor_count_n))
```

**输出:**

```py
The number of divisors of 84 : 12
```

## 例 2

```py
# import divisor_count() method from sympy
from sympy import divisor_count

n = 12

# Use divisor_count() method 
divisor_count_n = divisor_count(n, modulus = 2)

print("The number of divisors of {} : {}".format(n, divisor_count_n))
```

**输出:**

```py
The number of divisors of 12 : 4
```