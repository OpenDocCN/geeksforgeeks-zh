# Python–tensorflow.math.unsorted_segment_max()

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-math-unsorted_segment_max/](https://www.geeksforgeeks.org/python-tensorflow-math-unsorted_segment_max/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`unsorted_segment_max()` 用于在张量的线段中寻找最大元素。

## 语法

`tensorflow.math.unsorted_segment_max(data, segment_ids, num_segments, name)`

## 参数

*   `data`: 是张量。允许的数据类型有 `float32`、`float64`、`int32`、`uint8`、`int16`、`int8`、`int64`、`bfloat16`、`uint16`、`half`、`uint32`、`uint64`。
*   `segment_ids`: 是一维张量，取值排序。它的大小应该等于第一维 `data` 的大小。允许的数据类型是 `int32` 和 `int64`。
*   `num_segments`: 是张量。允许的数据类型是 `int32` 和 `int64`。
*   `name` (可选): 定义操作的名称。

## 返回

它将数据类型的张量返回为 x。

## 示例 1

```py
# importing the library
import tensorflow as tf

# Initializing the input tensor
data = tf.constant([1, 2, 3])
segment_ids = tf.constant([2, 2, 2])

# Printing the input tensor
print('data: ', data)
print('segment_ids: ', segment_ids)

# Calculating result
res = tf.math.unsorted_segment_max(data, segment_ids, tf.constant(3))

# Printing the result
print('Result: ', res)
```

**输出:**

```py
data:  tf.Tensor([1 2 3], shape=(3, ), dtype=int32)
segment_ids:  tf.Tensor([2 2 2], shape=(3, ), dtype=int32)
Result:  tf.Tensor([-2147483648 -2147483648           3], shape=(3, ), dtype=int32)
```

## 示例 2

```py
# importing the library
import tensorflow as tf

# Initializing the input tensor
data = tf.constant([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
segment_ids = tf.constant([0, 0, 2])

# Printing the input tensor
print('data: ', data)
print('segment_ids: ', segment_ids)

# Calculating result
res = tf.math.unsorted_segment_max(data, segment_ids, tf.constant(3))

# Printing the result
print('Result: ', res)
```

**输出:**

```py
data:  tf.Tensor(
[[1 2 3]
 [4 5 6]
 [7 8 9]], shape=(3, 3), dtype=int32)
segment_ids:  tf.Tensor([0 0 2], shape=(3, ), dtype=int32)
Result:  tf.Tensor(
[[          4           5           6]
 [-2147483648 -2147483648 -2147483648]
 [          7           8           9]], shape=(3, 3), dtype=int32)
```