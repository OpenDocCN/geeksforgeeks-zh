# Python Decimal min_mag()方法

> 原文：[https://www.geeksforgeeks.org/python-decimal-min_mag-method/](https://www.geeksforgeeks.org/python-decimal-min_mag-method/)

`Decimal.min_mag()`是一个`Decimal`类方法，它比较两个`Decimal`值并返回绝对值最小的那个，忽略它们的符号。

语法：
```python
Decimal.min_mag()
```

参数：`Decimal`值

返回：两者中绝对值较小者，忽略其符号。

## 代码示例 1：`min_mag()`方法示例

```python
# Python Program explaining 
# min_mag() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.min_mag() method
print ("\n\nDecimal a with min_mag() method : ", a.min_mag(a))

print ("Decimal a with min_mag() method : ", a.min_mag(b))

print ("Decimal b with min_mag() method : ", b.min_mag(a))
```

输出：
```python
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with min_mag() method :  -1
Decimal a with min_mag() method :  0.142857
Decimal b with min_mag() method :  0.142857
```

## 代码示例 2：`min_mag()`方法示例

```python
# Python Program explaining 
# min_mag() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e+5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.min_mag() method
print ("\n\nDecimal a with min_mag() method : ", a.min_mag(a))

print ("Decimal a with min_mag() method : ", a.min_mag(b))

print ("Decimal b with min_mag() method : ", b.min_mag(a))
```

输出：
```python
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with min_mag() method :  -3.14
Decimal a with min_mag() method :  -3.14
Decimal b with min_mag() method :  -3.14
```