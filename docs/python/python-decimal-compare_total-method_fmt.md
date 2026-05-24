# Python | Decimal compare_total()方法

> 原文：`https://www.geeksforgeeks.org/python-decimal-compare_total-method/`

`Decimal.compare_total()`是一种`Decimal`类方法，它使用两个`Decimal`值的抽象表示而不是数值来比较这两个`Decimal`值。

## 语法

```
Decimal.compare_total()
```

**参数：**
`Decimal`值

**返回值：**
- `1` - 如果 a > b
- `-1` - 如果 a < b
- `0` - 如果 a = b

## 代码示例 1：compare_total()方法示例

```py
# Python Program explaining 
# compare_total() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.compare_total() method
print ("\n\nDecimal a with compare_total() method : ", a.compare_total(a))

print ("Decimal a with compare_total() method : ", a.compare_total(b))

print ("Decimal b with compare_total() method : ", b.compare_total(a))
```

**输出：**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with compare_total() method :  0
Decimal a with compare_total() method :  -1
Decimal b with compare_total() method :  1
```

## 代码示例 2：compare_total()方法示例

```py
# Python Program explaining 
# compare_total() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.compare_total() method
print ("\n\nDecimal a with compare_total() method : ", a.compare_total(a))

print ("Decimal a with compare_total() method : ", a.compare_total(b))

print ("Decimal b with compare_total() method : ", b.compare_total(a))
```

**输出：**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with compare_total() method :  0
Decimal a with compare_total() method :  -1
Decimal b with compare_total() method :  1
```