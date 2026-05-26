# TensorFlow: tf.math.nextafter()

## 概述

[TensorFlow](https://www.geeksforgeeks.org/introduction-to-tensorflow/) 是谷歌为开发机器学习模型和深度学习神经网络而设计的开源 Python 库。`tf.math.nextafter()` 用于在 `x2` 方向上寻找 `x1` 的下一个可表示值。

## 语法

```py
tf.math.nextafter(x1, x2, name)
```

## 参数

*   `x1`: 是输入张量。这个张量允许的数据类型是 `float64`，`float32`。
*   `x2`: 是与 `x1` 相同数据类型的输入张量。
*   `name` (可选): 定义操作的名称。

## 返回值

它返回一个数据类型与 `x1` 相同的张量。

## 示例1

```py
# Importing the library
import tensorflow as tf

# Initializing the input tensor
x1 = tf.constant([1, 2, -3, -4], dtype = tf.float64)
x2 = tf.constant([5, -7, 3, -8], dtype = tf.float64)

# Printing the input tensor
print('x1: ', x1)
print('x2: ', x2)

# Calculating result
res = tf.math.nextafter(x1, x2)

# Printing the result
print('Result: ', res)
```

**输出:**

```py
x1:  tf.Tensor([ 1.  2. -3. -4.], shape=(4, ), dtype=float64)
x2:  tf.Tensor([ 5. -7.  3. -8.], shape=(4, ), dtype=float64)
Result:  tf.Tensor([ 1.  2. -3. -4.], shape=(4, ), dtype=float64)
```

## 示例2

本示例对 `x1` 和 `x2` 使用不同的数据类型。它将引发无效参数错误。

```py
# importing the library
import tensorflow as tf

# Initializing the input tensor
x1 = tf.constant([1, 2, -3, -4], dtype = tf.float64)
x2 = tf.constant([5, -7, 3, -8], dtype = tf.float32)

# Printing the input tensor
print('x1: ', x1)
print('x2: ', x2)

# Calculating result
res = tf.math.nextafter(x1, x2)

# Printing the result
print('Result: ', res)
```

**输出:**

```py
x1:  tf.Tensor([ 1.  2. -3. -4.], shape=(4, ), dtype=float64)
x2:  tf.Tensor([ 5. -7.  3. -8.], shape=(4, ), dtype=float32)

InvalidArgumentError                      Traceback (most recent call last)

<ipython-input-1-9f3a0a5a9a64> in <module>
      9 # Calculating result
---> 10 res = tf.math.nextafter(x1, x2)
     12 # Printing the result

2 frames

/usr/local/lib/python3.6/dist-packages/six.py in raise_from(value, from_value)

InvalidArgumentError: cannot compute NextAfter as input #1(zero-based) was expected to be a double tensor but is a float tensor [Op:NextAfter]
```