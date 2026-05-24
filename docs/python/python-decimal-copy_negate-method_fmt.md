# Python Decimal copy_negate() 方法

> 原文：[https://www.geeksforgeeks.org/python-decimal-copy_negate-method/](https://www.geeksforgeeks.org/python-decimal-copy_negate-method/)

`copy_negate()` 是 `Decimal` 类的一个方法，用于返回 `Decimal` 值的相反数。

> **语法：** `decimal.copy_negate()`
>
> **参数：** 十进制值
>
> **返回：** 十进制值的相反数

## 代码示例 1：copy_negate() 方法示例

```py
# Python Program explaining 
# copy_negate() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.copy_negate() method
print ("\n\nDecimal a with copy_negate() method : ", a.copy_negate())

print ("Decimal b with copy_negate() method : ", b.copy_negate())
```

**输出：**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with copy_negate() method :  1
Decimal b with copy_negate() method :  -0.142857
```

## 代码示例 2：copy_negate() 方法示例

```py
# Python Program explaining 
# copy_negate() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e+5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.copy_negate() method
print ("\n\nDecimal a with copy_negate() method : ", a.copy_negate())

print ("Decimal b with copy_negate() method : ", b.copy_negate())
```

**输出：**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with copy_negate() method :  3.14
Decimal b with copy_negate() method :  -3.21E+7
```