# Python Decimal logb()方法

> 原文: [https://www.geeksforgeeks.org/python-decimal-logb-method/](https://www.geeksforgeeks.org/python-decimal-logb-method/)

## 方法描述

`Decimal.logb()` 是 `Decimal` 类的方法，返回 `Decimal` 值的调整指数。

**语法：**
```py
Decimal.logb()
```

**参数：**
`Decimal` 值。

**返回：**
`Decimal` 值的调整指数。

### 代码示例 1

```py
# Python Program explaining 
# logb() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('.9932')

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logb() method
print ("\n\nDecimal a with logb() method : ", a.logb())

print ("Decimal b with logb() method : ", b.logb())
```

**输出：**
```py
Decimal value a :  0.9932
Decimal value b :  0.142857

Decimal a with logb() method :  -1
Decimal b with logb() method :  -1
```

### 代码示例 2

```py
# Python Program explaining 
# logb() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logb() method
print ("\n\nDecimal a with logb() method : ", a.logb())

print ("Decimal b with logb() method : ", b.logb())
```

**输出：**
```py
Decimal value a :  3.14
Decimal value b :  3.21E+7

Decimal a with logb() method :  0
Decimal b with logb() method :  7
```