# Python Decimal `is_zero()` 方法

> 原文: [https://www.geeksforgeeks.org/python-decimal-is_zero-method/](https://www.geeksforgeeks.org/python-decimal-is_zero-method/)

`Decimal.is_zero()` 是 `Decimal` 类的方法，用于检查 `Decimal` 值是否为零值。

## 语法

```
Decimal.is_zero()
```

**参数：** `Decimal` 值。

**返回值：**
- `true` - 如果 `Decimal` 值是零值；
- 否则返回 `false`。

## 代码示例 1

```py
# Python Program explaining 
# is_zero() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal(0)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_zero() method
print ("\n\nDecimal a with is_zero() method : ", a.is_zero())

print ("Decimal b with is_zero() method : ", b.is_zero())
```

**输出：**

```
Decimal value a :  -1
Decimal value b :  0

Decimal a with is_zero() method :  False
Decimal b with is_zero() method :  True
```

## 代码示例 2

```py
# Python Program explaining 
# is_zero() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-0)

b = Decimal('321e+5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_zero() method
print ("\n\nDecimal a with is_zero() method : ", a.is_zero())

print ("Decimal b with is_zero() method : ", b.is_zero())
```

**输出：**

```
Decimal value a :  0
Decimal value b :  3.21E+7

Decimal a with is_zero() method :  True
Decimal b with is_zero() method :  False
```