# Python | Decimal ln()方法

> 原文: [https://www.geeksforgeeks.org/python-decimal-ln-method/](https://www.geeksforgeeks.org/python-decimal-ln-method/)

## 方法描述

`Decimal.ln()` 是 `Decimal` 类的方法，返回 `Decimal` 值的自然对数（以 e 为底）。

## 语法

```python
Decimal.ln()
```

## 参数

十进制值。

## 返回值

十进制值的自然对数（以 e 为底）。

## 代码示例 1

```py
# Python Program explaining 
# ln() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('.9932')

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.ln() method
print ("\n\nDecimal a with ln() method : ", a.ln())

print ("Decimal b with ln() method : ", b.ln())
```

**输出:**

```py
Decimal value a :  0.9932
Decimal value b :  0.142857

Decimal a with ln() method :  -0.006823225348125508334064182053
Decimal b with ln() method :  -1.945911149055813305438686327
```

## 代码示例 2

```py
# Python Program explaining 
# ln() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.ln() method
print ("\n\nDecimal a with ln() method : ", a.ln())

print ("Decimal b with ln() method : ", b.ln())
```

**输出:**

```py
Decimal value a :  3.14
Decimal value b :  3.21E+7

Decimal a with ln() method :  1.144222799920161998805694448
Decimal b with ln() method :  17.28436658810024428478960133
```