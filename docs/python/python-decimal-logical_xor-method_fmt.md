# Python Decimal logic_xor() 方法

> 原文: [https://www.geeksforgeeks.org/python-decimal-logical_xor-method/](https://www.geeksforgeeks.org/python-decimal-logical_xor-method/)

`Decimal.logic_xor()` 是 `Decimal` 类的一个方法，返回两个 `Decimal` 值的数字异或。

## 语法
`decimal.logic_xor()`

## 参数
十进制值。

## 返回
两位（逻辑）十进制值的数字和。

## 代码示例 1：`logic_xor()` 方法示例

```py
# Python Program explaining 
# logical_xor() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('0')
b = Decimal('1')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_xor() method
print ("\n\nDecimal a with logical_xor() method : ", a.logical_xor(b))
print ("Decimal b with logical_xor() method : ", b.logical_xor(b))
```

**输出：**

```py
Decimal value a :  0
Decimal value b :  1

Decimal a with logical_xor() method :  1
Decimal b with logical_xor() method :  0
```

## 代码示例 2：`logic_xor()` 方法示例

```py
# Python Program explaining 
# logical_xor() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('1')
b = Decimal('0')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_xor() method
print ("\n\nDecimal a with logical_xor() method : ", a.logical_xor(a))
print ("Decimal b with logical_xor() method : ", a.logical_xor(b))
```

**输出：**

```py
Decimal value a :  1
Decimal value b :  0

Decimal a with logical_xor() method :  0
Decimal b with logical_xor() method :  1
```