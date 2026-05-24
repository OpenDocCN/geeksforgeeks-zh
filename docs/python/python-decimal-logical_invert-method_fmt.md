# Python Decimal逻辑取反()方法

> 原文：[https://www.geeksforgeeks.org/python-decimal-logical_invert-method/](https://www.geeksforgeeks.org/python-decimal-logical_invert-method/)

`Decimal`类的`logical_invert()`方法返回`Decimal`值的数字反转。

## 语法
`Decimal.logical_invert()`

## 参数
`Decimal`值。

## 返回
`Decimal`值的数字反转。

## 代码示例 1：`logical_invert()`方法示例

```py
# Python Program explaining 
# logical_invert() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('0')
b = Decimal('1')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_invert() method
print ("\n\nDecimal a with logical_invert() method : ", a.logical_invert())
print ("Decimal b with logical_invert() method : ", b.logical_invert())
```

**输出：**

```py
Decimal value a :  0
Decimal value b :  1

Decimal a with logical_invert() method :  1111111111111111111111111111
Decimal b with logical_invert() method :  1111111111111111111111111110
```

## 代码示例 2：`logical_invert()`方法示例

```py
# Python Program explaining 
# logical_invert() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('1')
b = Decimal('0')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_invert() method
print ("\n\nDecimal a with logical_invert() method : ", a.logical_invert())
print ("Decimal b with logical_invert() method : ", a.logical_invert())
```

**输出：**

```py
Decimal value a :  1
Decimal value b :  0

Decimal a with logical_invert() method :  1111111111111111111111111110
Decimal b with logical_invert() method :  1111111111111111111111111110
```