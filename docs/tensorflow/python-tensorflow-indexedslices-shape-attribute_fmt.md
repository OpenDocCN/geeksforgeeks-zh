# Python TensorFlow IndexedSlices Shape 属性

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-indexedslices-shape-attribute/](https://www.geeksforgeeks.org/python-tensorflow-indexedslices-shape-attribute/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`shape` 属性用于获取 TensorFlow `IndexedSlices` 的形状。它表示该稀疏张量所对应的稠密张量的形状。

> **语法:** `tf.IndexedSlices.shape`
>
> **返回:** 返回一个 `TensorShape` 对象，表示稠密张量的形状。

## 示例 1

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([[1, 2, 3], [4, 5, 6]])

# Printing the input
print('data: ', data)

# Calculating result
res = tf.IndexedSlices(data, [0], tf.constant([1, 2]))

# Finding Shape
shape = res.shape

# Printing the result
print('Shape: ', shape)
```

**输出:**

```py
data:  tf.Tensor(
[[1 2 3]
 [4 5 6]], shape=(2, 3), dtype=int32)
Shape:  (1, 2)
```

## 示例 2

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([[1, 2, 3], [4, 5, 6]])

# Printing the input
print('data: ', data)

# Calculating result
res = tf.IndexedSlices(data, [0], tf.constant([1]))

# Finding Shape
shape = res.shape

# Printing the result
print('Shape: ', shape)
```

**输出:**

```py
data:  tf.Tensor(
[[1 2 3]
 [4 5 6]], shape=(2, 3), dtype=int32)
Shape:  (1, )
```