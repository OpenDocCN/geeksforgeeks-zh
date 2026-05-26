# TensorFlow `raw_ops.Log1p()`

> 原文链接: [https://www.geeksforgeeks.org/python-tensorflow-raw_ops-log1p/](https://www.geeksforgeeks.org/python-tensorflow-raw_ops-log1p/)

[TensorFlow](https://www.geeksforgeeks.org/introduction-to-tensorflow/) 是谷歌为开发机器学习模型和深度学习神经网络而设计的开源 Python 库。`TensorFlow raw_ops` 提供对所有 TensorFlow 操作的低级访问。`Log1p()` 用于为输入 `x` 求 `(1+x)` 的逐元素对数。

> **语法:** `tf.raw_ops.Log1p(x, name)`
>
> **参数:**
>
> *   `x`: 是输入张量。这个张量允许的数据类型是 `bfloat16`，`half`，`float32`，`float64`，`complex64`，`complex128`。
> *   `name` (可选): 定义操作的名称。
>
> **返回:** 返回与 `x` 相同数据类型的张量。

**注意:** 只接受关键字参数。

## 示例 1

```py
# Importing the library
import tensorflow as tf

# Initializing the input tensor
a = tf.constant([1, 2, 3, 4, 5], dtype = tf.float64)

# Printing the input tensor
print('Input: ', a)

# Calculating logarithm(1 + x)
res = tf.raw_ops.Log1p(x = a)

# Printing the result
print('Result: ', res)
```

**输出:**

```py
Input:  tf.Tensor([1. 2. 3. 4. 5.], shape=(5, ), dtype=float64)
Result:  tf.Tensor([0.69314718 1.09861229 1.38629436 1.60943791 1.79175947], shape=(5, ), dtype=float64)
```

## 示例 2: 可视化

```py
# importing the library
import tensorflow as tf
import matplotlib.pyplot as plt

# Initializing the input tensor
a = tf.constant([1, 2, 3, 4, 5], dtype = tf.float64)

# Calculating logarithm(1 + x)
res = tf.raw_ops.Log1p(x = a)

# Plotting the graph
plt.plot(a, res, color ='green')
plt.title('tensorflow.raw_ops.Log1p')
plt.xlabel('Input')
plt.ylabel('Result')
plt.show()
```

**输出:**

![](img/3722a0311d225abc3544afd8ef04ebe4.png)