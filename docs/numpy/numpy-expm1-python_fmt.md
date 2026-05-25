# numpy.expm1() 用法详解

## 函数描述

`numpy.expm1(array, out=None, where=True, casting='same_kind', order='K', dtype=None)`：这个数学函数帮助用户计算所有元素的指数，从所有输入数组元素中减去 1。

## 参数

```py
array    : [array_like] Input array or object whose elements, we need to test.
out      : [ndarray, optional] Output array with same dimensions as Input array, 
           placed with result.
**kwargs : allows you to pass keyword variable length of argument to a function. 
           It is used when we want to handle named argument in a function.
where    : [array_like, optional] True value means to calculate the universal 
           functions(ufunc) at that position, False value means to leave the 
           value in the output alone.
```

## 返回值

```py
An array with exponential(all elements of input array) - 1.
```

## 代码示例 1：基本工作

```py
# Python program explaining
# expm1() function

import numpy as np

in_array = [1, 3, 5]
print ("Input array : \n", in_array)

exp_values = np.exp(in_array)
print ("\nExponential value of array element : "
       "\n", exp_values)

expm1_values = np.expm1(in_array)
print ("\n(Exponential value of array element) - (1) "
       ": \n", expm1_values)
```

**输出:**

```py
Input array : 
 [1, 3, 5]

Exponential value of array element : 
 [   2.71828183   20.08553692  148.4131591 ]

(Exponential value of array element) - (1) : 
 [   1.71828183   19.08553692  147.4131591 ]
```

## 代码示例 2：图形表示

```py
# Python program showing
# Graphical representation of 
# expm1() function

import numpy as np
import matplotlib.pyplot as plt

in_array = [1, 1.2, 1.4, 1.6, 1.8, 2]
out_array = np.expm1(in_array)

print("out_array : ", out_array)

y = [1, 1.2, 1.4, 1.6, 1.8, 2]
plt.plot(in_array, y, color = 'blue', marker = "*")

# red for numpy.expm1()
plt.plot(out_array, y, color = 'red', marker = "o")
plt.title("numpy.expm1()")
plt.xlabel("X")
plt.ylabel("Y")
plt.show()
```

**输出:**

```py
out_array :  [1.71828183 2.32011692 3.05519997 3.95303242 5.04964746 6.3890561]
```

## 参考文献

[https://docs.scipy.org/doc/numpy-1.13.0/reference/generated/numpy.expm1.html#numpy.expm1](https://docs.scipy.org/doc/numpy-1.13.0/reference/generated/numpy.expm1.html#numpy.expm1)