# Python - TensorFlow `IndexedSlices.dtype`属性

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-indexedslices-dtype-attribute/](https://www.geeksforgeeks.org/python-tensorflow-indexedslices-dtype-attribute/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`dtype` 用于查找 `Tensor` 中值的类型。

> **语法:** `tensorflow.IndexedSlices.dtype`
>
> **返回:** 返回张量中元素的数据类型。

## Python 3示例1

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([[1, 2, 3], [4, 5, 6]])

# Printing the input
print('data: ', data)

# Calculating result
res = tf.IndexedSlices(data, [0])

# Finding dtype
dtype = res.dtype

# Printing the result
print('dtype: ', dtype)
```

**输出:**

```py
data:  tf.Tensor(
[[1 2 3]
 [4 5 6]], shape=(2, 3), dtype=int32)
dtype:  <dtype: 'int32'>
```

## Python 3示例2

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([[1, 2, 3], [4, 5, 6]], dtype = tf.float32)

# Printing the input
print('data: ', data)

# Calculating result
res = tf.IndexedSlices(data, [0])

# Finding dtype
dtype = res.dtype

# Printing the result
print('dtype: ', dtype)
```

**输出:**

```py
data:  tf.Tensor(
[[1. 2. 3.]
 [4. 5. 6.]], shape=(2, 3), dtype=float32)
dtype:  <dtype: 'float32'>
```