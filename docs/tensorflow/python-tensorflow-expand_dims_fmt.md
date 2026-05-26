## `tf.expand_dims()`

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-expand_dims/](https://www.geeksforgeeks.org/python-tensorflow-expand_dims/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`expand_dims()` 用于在输入张量中插入一个附加维度。

> **语法:** `tensorflow.expand_dims(input, axis, name)`
>
> **参数:**
>
> *   `input`: 是输入 Tensor。
> *   `axis`: 定义插入维度的索引。如果输入有 `D` 个尺寸，那么 `axis` 的值必须在 `[-(D+1), D]` 范围内。
> *   `name` (可选): 定义操作的名称。
>
> **返回:** 返回一个展开维度的张量。

### 示例 1

```python
# Importing the library
import tensorflow as tf

# Initializing the input
x = tf.constant([[2, 3, 6], [4, 8, 15]])

# Printing the input
print('x:', x)

# Calculating result
res = tf.expand_dims(x, 1)

# Printing the result
print('res: ', res)
```

**输出:**

```python
x: tf.Tensor(
[[ 2  3  6]
 [ 4  8 15]], shape=(2, 3), dtype=int32)
res:  tf.Tensor(
[[[ 2  3  6]]

[[ 4  8 15]]], shape=(2, 1, 3), dtype=int32)

# shape has changed from (2, 3) to (2, 1, 3)
```

### 示例 2

```python
# Importing the library
import tensorflow as tf

# Initializing the input
x = tf.constant([[2, 3, 6], [4, 8, 15]])

# Printing the input
print('x:', x)

# Calculating result
res = tf.expand_dims(x, 0)

# Printing the result
print('res: ', res)
```

**输出:**

```python
x: tf.Tensor(
[[ 2  3  6]
 [ 4  8 15]], shape=(2, 3), dtype=int32)
res:  tf.Tensor(
[[[ 2  3  6]
  [ 4  8 15]]], shape=(1, 2, 3), dtype=int32)

# shape has changed from (2, 3) to (1, 2, 3)
```