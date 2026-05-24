# Python Decimal.radix() 方法

> 原文: [https://www.geeksforgeeks.org/python-decimal-radix-method/](https://www.geeksforgeeks.org/python-decimal-radix-method/)

`Decimal.radix()` 是一个 `Decimal` 类方法，返回基数值 10，因为这是 `Decimal`。

## 语法
`Decimal.radix()`

## 参数
十进制值

## 返回
基数值 10，因为这是十进制。

## 代码示例 1
```py
# Python Program explaining 
# radix() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.radix() method
print ("\n\nDecimal a with radix() method : ", a.radix())

print ("Decimal b with radix() method : ", b.radix())
```

**输出:**
```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with radix() method :  10
Decimal b with radix() method :  10
```

## 代码示例 2
```py
# Python Program explaining 
# radix() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14545454')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.radix() method
print ("\n\nDecimal a with radix() method : ", a.radix())

print ("Decimal b with radix() method : ", b.radix())
```

**输出:**
```py
Decimal value a :  -3.14545454
Decimal value b :  3.21E+7

Decimal a with radix() method :  10
Decimal b with radix() method :  10
```