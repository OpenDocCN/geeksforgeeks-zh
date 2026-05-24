# Python cmath.asin() 函数

> 原文: [https://www.geeksforgeeks.org/python-cmath-asin-function/](https://www.geeksforgeeks.org/python-cmath-asin-function/)

`cmath` 模块包含许多用于复数数学运算的函数。`cmath.asin()` 函数返回复数的反正弦值。该函数传递的值可以是整数、浮点数和复数。

> **语法:** `cmath.asin(x)`
>
> **参数:** 此方法只接受单个参数。
> *   **x:** 该参数是传递给 `asin()` 的值
>
> **返回:** 该函数返回一个复数的反正弦值。

下面的例子说明了上述功能的使用:

**示例 #1:** 在本例中，我们可以通过使用 `cmath.asin()` 方法，向其传递任何值来获得反正弦的值。

## Python 3

```py
# Python code to implement
# the asin()function

# importing "cmath"
# for mathematical operations   
import cmath

# using cmath.asin() method 
val = cmath.asin(3)

print(val)
```

**输出:**

```py
(1.5707963267948966+1.762747174039086j)
```

**例 2:**

## Python 3

```py
# Python code to implement
# the asin()function

# importing "cmath"
# for mathematical operations   
import cmath

# using cmath.asin() method 
val = cmath.asin(2 + 5j)

print(val)
```

**输出:**

```py
(0.374670804825527+2.3830308809003258j)
```