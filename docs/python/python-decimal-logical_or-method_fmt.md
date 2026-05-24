# Python `Decimal.logical_or()` 方法

> 原文：[https://www.geeksforgeeks.org/python-decimal-logical_or-method/](https://www.geeksforgeeks.org/python-decimal-logical_or-method/)

`Decimal.logical_or()` 是 `Decimal` 类的一个方法，它返回两个十进制值的按位或运算结果。

## 语法
`Decimal.logical_or()`

## 参数
十进制值。

## 返回
两位（逻辑）十进制值的按位或。

## 代码示例 1：`logical_or()` 方法示例

```py
# Python Program explaining 
# logical_or() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('0')

b = Decimal('1')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_or() method
print ("\n\nDecimal a with logical_or() method : ", a.logical_or(b))

print ("Decimal b with logical_or() method : ", b.logical_or(b))
```

## 输出

```py
Decimal value a :  0
Decimal value b :  1

Decimal a with logical_or() method :  1
Decimal b with logical_or() method :  1
```

## 代码示例 2：`logical_or()` 方法示例

```py
# Python Program explaining 
# logical_or() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('1')

b = Decimal('0')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_or() method
print ("\n\nDecimal a with logical_or() method : ", a.logical_or(a))

print ("Decimal b with logical_or() method : ", a.logical_or(b))
```

## 输出

```py
Decimal value a :  1
Decimal value b :  0

Decimal a with logical_or() method :  1
Decimal b with logical_or() method :  1
```