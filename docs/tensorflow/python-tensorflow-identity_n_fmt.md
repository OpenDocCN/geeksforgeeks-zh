# Python - `tensorflow.identity_n()`

> 原文链接: https://www.geeksforgeeks.org/python-tensorflow-identity_n/

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`identity_n()` 用于获取与输入 Tensor 具有相同形状和内容的 Tensor 列表。

> **语法:** `tensorflow.identity_n(input, name)`
>
> **参数:**
>
> *   `input`: 是张量。
> *   `name` (可选): 定义操作的名称。
>
> **返回:** 返回一个与输入形状和内容相同的张量列表。

**例 1:**

## Python 3

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([[1, 2, 3], [3, 4, 5], [5, 6, 7]])

# Printing the input
print('data: ', data)

# Calculating result
res = tf.identity_n(data)

# Printing the result
print('res: ', res)
```

**输出:**

```py
data:  tf.Tensor(
[[1 2 3]
 [3 4 5]
 [5 6 7]], shape=(3, 3), dtype=int32)
res:  [<tf.Tensor: shape=(3, ), dtype=int32, numpy=array([1, 2, 3], dtype=int32)>,
     <tf.Tensor: shape=(3, ), dtype=int32, numpy=array([3, 4, 5], dtype=int32)>, 
     <tf.Tensor: shape=(3, ), dtype=int32, numpy=array([5, 6, 7], dtype=int32)>]
```

**例 2:**

## Python 3

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([1, 2, 3])

# Printing the input
print('data: ', data)

# Calculating result
res = tf.identity_n(data)

# Printing the result
print('res: ', res)
```

**输出:**

```py
data:  tf.Tensor([1 2 3], shape=(3, ), dtype=int32)
res:  [<tf.Tensor: shape=(), dtype=int32, numpy=1>,
     <tf.Tensor: shape=(), dtype=int32, numpy=2>, 
     <tf.Tensor: shape=(), dtype=int32, numpy=3>]
```