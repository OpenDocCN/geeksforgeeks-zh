# Python | Decimal is_signed()方法

> 原文: [https://www.geeksforgeeks.org/python-decimal-is_signed-method/](https://www.geeksforgeeks.org/python-decimal-is_signed-method/)

`Decimal.is_signed()`是`Decimal`类方法，检查`Decimal`值的符号是否为负数。

## 语法
`Decimal.is_signed()`

## 参数
十进制值

## 返回值
`true` – 如果十进制值的符号为负；否则为`false`。

## 代码示例 1: is_signed()方法示例

```py
# Python Program explaining 
# is_signed() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('-inf')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_signed() method
print ("\n\nDecimal a with is_signed() method : ", a.is_signed())

print ("Decimal b with is_signed() method : ", b.is_signed())
```

## 输出

```py
Decimal value a :  -1
Decimal value b :  -Infinity

Decimal a with is_signed() method :  True
Decimal b with is_signed() method :  True
```

## 代码示例 2: is_signed()方法示例

```py
# Python Program explaining 
# is_signed() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e+5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_signed() method
print ("\n\nDecimal a with is_signed() method : ", a.is_signed())

print ("Decimal b with is_signed() method : ", b.is_signed())
```

## 输出

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_signed() method :  True
Decimal b with is_signed() method :  False
```