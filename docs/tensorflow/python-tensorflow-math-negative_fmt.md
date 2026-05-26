# TensorFlow tf.math.negative() 函数详解

> 原文：[https://www.geeksforgeeks.org/python-tensorflow-math-negative/](https://www.geeksforgeeks.org/python-tensorflow-math-negative/)

[TensorFlow](https://www.geeksforgeeks.org/introduction-to-tensorflow/) 是谷歌为开发机器学习模型和深度学习神经网络而设计的开源 Python 库。`tf.math.negative()` 函数用于计算输入张量 `x` 中每个元素的负值。

## 语法

`tf.math.negative(x, name)`

## 参数

*   `x`：输入张量。该张量支持的数据类型包括 `bfloat16`、`half`、`float32`、`float64`、`int32`、`int64`、`complex64`、`complex128`。
*   `name`（可选）：定义操作的名称。

## 返回值

返回一个与 `x` 数据类型相同的张量，其值为 `x` 中各元素的负值。

## 示例 1：基本用法

```py
# Importing the library
import tensorflow as tf

# Initializing the input tensor
a = tf.constant([1, 2, -3, -4], dtype = tf.float64)

# Printing the input tensor
print('Input: ', a)

# Calculating result
res = tf.math.negative(x = a)

# Printing the result
print('Result: ', res)
```

**输出：**

```py
Input:  tf.Tensor([ 1.  2. -3. -4.], shape=(4, ), dtype=float64)
Result:  tf.Tensor([-1. -2.  3.  4.], shape=(4, ), dtype=float64)
```

## 示例 2：使用复数张量

本例使用复数张量。

```py
# importing the library
import tensorflow as tf

# Initializing the input tensor
a = tf.constant([1 + 3j, 2-5j, -3 + 7j, -4-8j], dtype = tf.complex128)

# Printing the input tensor
print('Input: ', a)

# Calculating result
res = tf.math.negative(x = a)

# Printing the result
print('Result: ', res)
```

**输出：**

```py
Input:  tf.Tensor([ 1.+3.j  2.-5.j -3.+7.j -4.-8.j], shape=(4, ), dtype=complex128)
Result:  tf.Tensor([-1.-3.j -2.+5.j  3.-7.j  4.+8.j], shape=(4, ), dtype=complex128)
```