# numpy.real() 函数

> 原文: [https://www.geeksforgeeks.org/numpy-real-function-python/](https://www.geeksforgeeks.org/numpy-real-function-python/)

`numpy.real()` 函数返回复数参数的实部。

## 语法

`numpy.real(arr)`

## 参数

- **arr** : 类似数组。输入数组。

## 返回值

**返回值** : ndarray 或标量。复数参数的实部。如果 `val` 是实数，则使用 `val` 的类型作为输出。如果 `val` 有复数元素，则返回的类型是 float。

## 代码示例

### 代码 #1

```py
# Python program explaining
# numpy.real() function

# importing numpy as geek 
import numpy as geek

arr = geek.array([1 + 3j, 5 + 7j, 9 + 11j])

gfg = arr.real

print (gfg)
```

**输出:**

```py
[1. 5. 9.]
```

### 代码 #2

```py
# Python program explaining
# numpy.real() function

# importing numpy as geek 
import numpy as geek

arr = geek.array([2 + 3j, 5 + 6j, 8 + 9j])

gfg = arr.real

print (gfg)
```

**输出:**

```py
[2. 5. 8.]
```