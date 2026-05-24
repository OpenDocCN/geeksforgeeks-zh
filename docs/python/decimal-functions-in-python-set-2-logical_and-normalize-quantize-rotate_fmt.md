# Python 中的十进制函数

## 集合 2：逻辑与、归一化、量化、旋转等函数

> 原文：[https://www.geeksforgeeks.org/decimal-functions-in-python-set-2-logical_and-normalize-quantize-rotate/](https://www.geeksforgeeks.org/decimal-functions-in-python-set-2-logical_and-normalize-quantize-rotate/)

一些十进制函数已经在下面的集合 1 中讨论过了：[Python 中的十进制函数 | 集合 1](https://www.geeksforgeeks.org/decimal-functions-python-set-1/)。

本文将讨论更多的函数。

### 1. `logical_and()`
该函数按数字计算数字的逻辑“与”运算。数字只能有值 `0` 或 `1`。

### 2. `logical_or()`
该函数计算数字的数字方式逻辑“或”运算。数字只能有值 `0` 或 `1`。

### 3. `logical_xor()`
该函数计算数字的数字方式逻辑“xor”运算。数字只能有值 `0` 或 `1`。

### 4. `logical_invert()`
该函数计算数字的数字方式逻辑“反相”运算。数字只能有值 `0` 或 `1`。

```python
# Python code to demonstrate the working of
# logical_and(), logical_or(), logical_xor()
# and logical_invert()

# importing "decimal" module to use decimal functions
import decimal

# Initializing decimal number
a = decimal.Decimal(1000)

# Initializing decimal number
b = decimal.Decimal(1110)

# printing logical_and of two numbers
print ("The logical_and() of two numbers is : ",end="")
print (a.logical_and(b))

# printing logical_or of two numbers
print ("The logical_or() of two numbers is : ",end="")
print (a.logical_or(b))

# printing exclusive or of two numbers
print ("The exclusive or of two numbers is : ",end="")
print (a.logical_xor(b))

# printing logical inversion of number
print ("The logical inversion of number is : ",end="")
print (a.logical_invert())
```

输出：

```text
The logical_and() of two numbers is : 1000
The logical_or() of two numbers is : 1110
The exclusive or of two numbers is : 110
The logical inversion of number is : 1111111111111111111111110111
```

### 5. `next_plus()`
该函数返回可表示的最小数，大于给定数的。

### 6. `next_minus()`
这个函数返回可以表示的最大的数，比给定的数小。

```python
# Python code to demonstrate the working of
# next_plus() and next_minus()

# importing "decimal" module to use decimal functions
import decimal

# Initializing decimal number
a = decimal.Decimal(101.34)

# printing the actual decimal number
print ("The original number is : ",end="")
print (a)

# printing number after using next_plus()
print ("The smallest number larger than current number : ",end="")
print (a.next_plus())

# printing number after using next_minus()
print ("The largest number smaller than current number : ",end="")
print (a.next_minus())
```

输出：

```text
The original number is : 101.340000000000003410605131648480892181396484375
The smallest number larger than current number : 101.3400000000000034106051317
The largest number smaller than current number : 101.3400000000000034106051316
```

### 7. `next_toward()`
该函数返回第二个参数方向上最接近第一个参数的数。如果两个数字相等，则返回带有第一个数字符号的第二个数字。

### 8. `normalize()`
该函数在删除数字中所有最右边的尾随零后打印数字。

```python
# Python code to demonstrate the working of
# next_toward() and normalize()

# importing "decimal" module to use decimal functions
import decimal

# Initializing decimal number
a = decimal.Decimal(101.34)

# Initializing decimal number
b = decimal.Decimal(-101.34)

# Initializing decimal number
c = decimal.Decimal(-58.68)

# Initializing decimal number
d = decimal.Decimal(14.010000000)

# printing the number using next_toward()
print ("The number closest to 1st number in direction of second number : ")
print (a.next_toward(c))

# printing the number using next_toward()
# when equal
print ("The second number with sign of first number is : ",end="")
print (b.next_toward(a))

# printing number after erasing rightmost trailing zeroes
print ("Number after erasing rightmost trailing zeroes : ",end="")
print (d.normalize())
```

输出：

```text
The number closest to 1st number in direction of second number : 
101.3400000000000034106051316
The second number with sign of first number is : -101.3400000000000034106051316
Number after erasing rightmost trailing zeroes : 14.01
```

### 9. `quantize()`
此函数返回第一个参数，小数部分（指数）中的位数缩短为第二个参数小数部分（指数）中的位数。

### 10. `same_quantum()`
如果两个数的指数不同，则此函数返回 `0`，如果两个数的指数相同，则返回 `1`。

```python
# Python code to demonstrate the working of
# quantize() and same_quantum()

# importing "decimal" module to use decimal functions
import decimal

# Initializing decimal number
a = decimal.Decimal(20.76548)

# Initializing decimal number
b = decimal.Decimal(12.25)

# Initializing decimal number
c = decimal.Decimal(6.25)

# printing quantized first number
print ("The quantized first number is : ",end="")
print (a.quantize(b))

# checking if both number have same exponent
if (b.same_quantum(c)):
       print ("Both the numbers have same exponent")
else : print ("Both numbers have different exponent")
```

输出：

```text
The quantized first number is : 20.77
Both the numbers have same exponent
```

### 11. `rotate()`
此功能将第一个参数旋转第二个参数中提到的量。如果第二个参数的符号为正，则旋转向左，否则旋转向右。第一个参数的符号不变。

### 12. `shift()`
此功能将第一个参数移动第二个参数中提到的数量。如果第二个参数的符号是正，则换挡是向左的，否则换挡是向右的。第一个参数的符号不变。数字移位后被 `0` 代替。

```python
# Python code to demonstrate the working of
# rotate() and shift()

# importing "decimal" module to use decimal functions
import decimal

# Initializing decimal number
a = decimal.Decimal(2343509394029424234334563465)

# using rotate() to rotate the first argument
# rotates to right by 2 positions
print ("The rotated value is : ",end="")
print (a.rotate(-2))

# using shift() to shift the first argument
# rotates to left by 2 positions
print ("The shifted value is : ",end="")
print (a.shift(2))
```

输出：

```text
The rotated value is : 6523435093940294242343345634
The shifted value is : 4350939402942423433456346500
```

### 13. `remainder_near()`
返回值“`第 1 –( n *第 2)`”，其中 `n` 是最接近 `第 1/2` 次结果的整数值。如果两个整数具有完全相似的接近度，则选择一个。

### 14. `scaleb()`
此函数将第一个数字的指数移动第二个参数的值。

```python
# Python code to demonstrate the working of
# remainder_near() and scaleb()

# importing "decimal" module to use decimal functions
import decimal

# Initializing decimal number
a = decimal.Decimal(23.765)

# Initializing decimal number
b = decimal.Decimal(12)

# Initializing decimal number
c = decimal.Decimal(8)

# using remainder_near to compute value
print ("The computed value using remainder_near() is : ",end="")
print (b.remainder_near(c))

# using scaleb() to shift exponont
print ("The value after shifting exponent : ",end="")
print (a.scaleb(2))
```

输出：

```text
The computed value using remainder_near() is : -4
The value after shifting exponent : 2376.500000000000056843418861
```

本文由 [**曼吉特·辛格**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。