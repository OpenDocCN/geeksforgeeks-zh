# `cmath.nanj` 常数

> 原文链接: https://www.geeksforgeeks.org/python-cmath-nanj-constant/

**cmath 模块**包含许多用于复数数学运算的函数。**常数 `nanj` 用来得到复数 nan（不是数字）。**

> **语法:** `cmath.nanj`
>
> **返回:** 返回复数 nan 值。

下面的例子说明了上述功能的使用：

## 示例 1

```py
# Python code to implement
# the cmath.nanj constant

# importing "cmath"
# for mathematical operations
import cmath

# Print the value of nanj
val = cmath.nanj
print(val)
```

**输出:**

```py
nanj
```

## 示例 2

```py
# Python code to implement
# the cmath.nanj constant

# importing "cmath"
# for mathematical operations
import cmath

# use of cmath.nanj
val = type(cmath.nanj)
print(val)
```

**输出:**

```py
<class 'complex'>
```