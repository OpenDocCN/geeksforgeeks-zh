# Python – tensorflow.math.count_nonzero()

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-math-count_nonzero/](https://www.geeksforgeeks.org/python-tensorflow-math-count_nonzero/)

[TensorFlow](https://www.geeksforgeeks.org/introduction-to-tensorflow/) 是谷歌为开发机器学习模型和深度学习神经网络而设计的开源 Python 库。

`count_nonzero()` 用于计算张量中非零元素的数量。

> **语法:** `TF.math.count_nonzero(input, axis, keepdims, dtype, name)`
>
> **参数:**
>
> *   `input`: 是一个需要缩减的张量。
> *   `axis` (可选): 定义需要缩减输入的轴。允许的范围是 `[-rank(input), rank(input))`。如果未给出任何值，则默认值为 `None`，即输入将沿所有轴缩减。
> *   `keepdims` (可选): 如果为 `True`，将保留长度为 1 的缩减维度。
> *   `dtype` (可选): 定义输出数据类型。默认为 `int32`。
> *   `name` (可选): 定义操作的名称。
>
> **返回:**
>
> 它返回包含非零值数量的张量。

## 例 1

```py
# importing the library
import tensorflow as tf

# initializing the input
a = tf.constant([1,0,2,5,0], dtype = tf.int32)  # 3 non-zero

# Printing the input
print("Input: ",a)

# Counting non-zero
res  = tf.math.count_nonzero(a)

# Printing the result
print("No of non-zero elements: ",res)
```

**输出:**

```py
Input:  tf.Tensor([1 0 2 5 0], shape=(5,), dtype=int32)
No of non-zero elements:  tf.Tensor(3, shape=(), dtype=int64)
```

## 例 2

当输入张量为类型字符串时，`""` 被认为是空字符串。`" "` 为非零。

```py
# importing the library
import tensorflow as tf

# initializing the input
a = tf.constant([""," ","a","b"])  # 3 non-zero

# Printing the input
print("Input: ",a)

# Counting non-zero
res  = tf.math.count_nonzero(a)

# Printing the result
print("No of non-zero elements: ",res)
```

**输出:**

```py
Input:  tf.Tensor([b'' b' ' b'a' b'b'], shape=(4,), dtype=string)
No of non-zero elements:  tf.Tensor(3, shape=(), dtype=int64)
```