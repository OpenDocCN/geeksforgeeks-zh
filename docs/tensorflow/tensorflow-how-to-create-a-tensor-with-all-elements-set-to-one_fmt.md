# TensorFlow – 如何创建所有元素都设置为一的张量

> 原文：`https://www.geeksforgeeks.org/tensorflow-how-to-create-a-tensor-with-all-elements-set-to-one/`

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

> **使用的方法:**
> *   `tf.ones`：此方法接受形状和类型，并返回给定形状和类型的张量，所有元素都设置为 1。
> *   `tf.fill`：此方法接受形状、值和类型，并返回给定形状和类型的张量，所有值都设置为指定的值。

**示例 1:** 本示例使用 `ones()` 方法创建所有元素都设置为 1 的张量。

## Python 3

```py
# importing the library
import tensorflow as tf

# Generating a Tensor of shape (2, 3)
res = tf.ones(shape = (2, 3))

# Printing the resulting Tensors
print("Res: ", res )
```

**输出:**

```py
Res:  tf.Tensor(
[[1. 1. 1.]
 [1. 1. 1.]], shape=(2, 3), dtype=float32)
```

**示例 2:** 本示例使用 `fill()` 方法，值= 1，创建一个所有元素都设置为 1 的张量。

## Python 3

```py
# importing the library
import tensorflow as tf

# Generating a Tensor of shape (2, 3)
res = tf.fill(dims = (2, 3), value = 1)

# Printing the resulting Tensors
print("Res: ", res )
```

**输出:**

```py
Res:  tf.Tensor(
[[1 1 1]
 [1 1 1]], shape=(2, 3), dtype=int32)
```