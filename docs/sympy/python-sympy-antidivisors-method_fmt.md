# Python | sympy.antidivisors() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-antidivisors-method/](https://www.geeksforgeeks.org/python-sympy-antidivisors-method/)

借助 `sympy.antidivisors()` 方法，我们可以默认按照排序顺序找到给定数字的[反除数](https://oeis.org/A066272/a066272a.html)。

## 语法
```python
antidivisors(n, generator=False)
```

## 参数
- `n` – 表示整数。
- `generator` – 如果 `generator` 为 `True`，则返回一个无序的生成器对象，否则返回一个有序的反除数列表。默认情况下为 `False`。

## 返回
返回给定整数的反除数列表。

## 示例 #1
```python
# import antidivisors() method from sympy
from sympy.ntheory.factor_ import antidivisors

n = 24

# Use antidivisors() method 
antidivisors_n = antidivisors(n)

print("The anti-divisors of {} : {}".format(n, antidivisors_n))
```

**输出:**
```
The anti-divisors of 24 : [7, 16]
```

## 示例 #2
```python
# import antidivisors() method from sympy
from sympy.ntheory.factor_ import antidivisors

n = 128

# Use antidivisors() method 
antidivisors_n = antidivisors(n)

print("The anti-divisors of {} : {}".format(n, antidivisors_n))
```

**输出:**
```
The anti-divisors of 128 : [3, 5, 15, 17, 51, 85]
```