# Python `Decimal.shift()` 方法

> 原文：[https://www.geeksforgeeks.org/python-decimal-shift-method/](https://www.geeksforgeeks.org/python-decimal-shift-method/)

`Decimal.shift()` 是 `Decimal` 类的一个方法，返回 `x` 移位 `y` 次后的副本。

> **语法：** `Decimal.shift()`
>
> **参数：** 十进制值
>
> **返回：** `x` 移位 `y` 次后的副本

## 代码示例 1：`shift()` 方法示例

```py
# Python Program explaining 
# shift() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(1)
b = Decimal(2)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.shift() method
print ("\n\nDecimal a with shift() method : ", a.shift(b))
print ("Decimal b with shift() method : ", b.shift(b))
```

**输出：**

```py
Decimal value a :  1
Decimal value b :  2

Decimal a with shift() method :  100
Decimal b with shift() method :  200
```

## 代码示例 2：`shift()` 方法示例

```py
# Python Program explaining 
# shift() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(300)
b = Decimal(15)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.shift() method
print ("\n\nDecimal a with shift() method : ", a.shift(b))
print ("Decimal b with shift() method : ", b.shift(b))
```

**输出：**

```py
Decimal value a :  300
Decimal value b :  15

Decimal a with shift() method :  300000000000000000
Decimal b with shift() method :  15000000000000000
```