# Python Decimal.is_snan() 方法

> 原文：[https://www.geeksforgeeks.org/python-decimal-is_snan-method/](https://www.geeksforgeeks.org/python-decimal-is_snan-method/)

## 方法介绍

`Decimal.is_snan()` 是 `Decimal` 类的一个方法，用于检查 `Decimal` 值是否为信号 NaN。

> **语法：** `Decimal.is_snan()`
>
> **参数：** 十进制值
>
> **返回：** `true` – 如果十进制值是信号 NaN，否则为 `false`

## 代码示例 1

```py
# Python Program explaining 
# is_snan() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('nan')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_snan() method
print ("\n\nDecimal a with is_snan() method : ", a.is_snan())

print ("Decimal b with is_snan() method : ", b.is_snan())
```

**输出：**

```py
Decimal value a :  -1
Decimal value b :  -NaN

Decimal a with is_snan() method :  False
Decimal b with is_snan() method :  False
```

## 代码示例 2

```py
# Python Program explaining 
# is_snan() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_snan() method
print ("\n\nDecimal a with is_snan() method : ", a.is_snan())

print ("Decimal b with is_snan() method : ", b.is_snan())
```

**输出：**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_snan() method :  False
Decimal b with is_snan() method :  False
```