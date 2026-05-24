# Python cmath.asinh() 函数

> 原文: [https://www.geeksforgeeks.org/python-cmath-asinh-function/](https://www.geeksforgeeks.org/python-cmath-asinh-function/)

`cmath` 模块包含许多用于复数数学运算的函数。`cmath.asinh()` 函数返回复数的反双曲正弦值。该函数传递的值可以是整数、浮点数或复数。

> **语法:** `cmath.asinh(x)`
>
> **参数:** 此方法只接受单个参数。
> *   **x:** 该参数是传递给 `asinh()` 的值。
>
> **返回:** 该函数返回一个复数的反双曲正弦值。

下面的例子说明了上述功能的使用:

## 示例 1

在本例中，我们可以通过使用 `cmath.asinh()` 方法，传递任何值给它来获得反双曲正弦的值。

```py
# Python code to implement
# the asinh()function

# importing "cmath"
# for mathematical operations   
import cmath

# using cmath.asinh() method 
val = cmath.asinh(3)

print(val)
```

**输出:**

```
(1.8184464592320668+0j)
```

## 示例 2

```py
# Python code to implement
# the asinh()function

# importing "cmath"
# for mathematical operations   
import cmath

# using cmath.asinh() method 
val = cmath.asinh(2 + 5j)

print(val)
```

**输出:**

```
(2.37054853731792+1.184231684275022j)
```