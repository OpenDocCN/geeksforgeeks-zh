# TensorFlow IndexedSlices.dense_shape 属性

> 原文：[https://www.geeksforgeeks.org/python-tensorflow-indexedslices-dense_shape-attribute/](https://www.geeksforgeeks.org/python-tensorflow-indexedslices-dense_shape-attribute/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`dense_shape` 返回一个包含相应稠密张量形状的一维张量。

> **语法：** `tf.IndexedSlices.dense_shape`
>
> **返回：** 返回一维张量。

## 示例 1

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([1, 2, 3])

# Printing the input
print('data: ', data)

# Calculating result
res = tf.IndexedSlices(data, [0], 2)

# Finding dense shape
dense = res.dense_shape

# Printing the result
print('dense shape: ', dense)
```

**输出：**

```py
data:  tf.Tensor([1 2 3], shape=(3, ), dtype=int32)
dense shape:  2
```

## 示例 2

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([1, 2, 3])

# Printing the input
print('data: ', data)

# Calculating result
res = tf.IndexedSlices(data, [0])

# Finding dense shape
dense = res.dense_shape

# Printing the result
print('dense shape: ', dense)
```

**输出：**

```py
data:  tf.Tensor([1 2 3], shape=(3, ), dtype=int32)
dense shape:  None
```