# TensorFlow `tf.raw_ops.Exp()` 详解

> 原文链接: [https://www.geeksforgeeks.org/python-tensorflow-raw_ops-exp/](https://www.geeksforgeeks.org/python-tensorflow-raw_ops-exp/)

[TensorFlow](https://www.geeksforgeeks.org/introduction-to-tensorflow/) 是谷歌为开发机器学习模型和深度学习神经网络而设计的开源 Python 库。`TensorFlow` 的 `raw_ops` 模块提供对所有 TensorFlow 操作的低级访问。`Exp()` 函数用于计算输入张量 `x` 中每个元素的指数。

```py
对于复数
e^(x+iy) = e^x * e^iy = e^x * (cos y + i sin y)
```

## 语法

`tf.raw_ops.Exp(x, name)`

## 参数

*   `x`: 输入张量。该张量允许的数据类型是 `bfloat16`，`half`，`float32`，`float64`，`complex64`，`complex128`。
*   `名称` (可选): 定义操作的名称。

## 返回

返回与 `x` 相同数据类型的张量。

## 注意

只接受关键字参数。

## 示例 1

### Python 3

```py
# Importing the library
import tensorflow as tf

# Initializing the input tensor
a = tf.constant([1, 2, 3, 4, 5], dtype = tf.float64)

# Printing the input tensor
print('Input: ', a)

# Calculating exponential
res = tf.raw_ops.Exp(x = a)

# Printing the result
print('Result: ', res)
```

**输出:**

```py
Input:  tf.Tensor([1. 2. 3. 4. 5.], shape=(5, ), dtype=float64)
Result:  tf.Tensor([  2.71828183   7.3890561   20.08553692  54.59815003 148.4131591 ], shape=(5, ), dtype=float64)
```

## 示例 2: 可视化

### Python 3

```py
# importing the library
import tensorflow as tf
import matplotlib.pyplot as plt

# Initializing the input tensor
a = tf.constant([1, 2, 3, 4, 5], dtype = tf.float64)

# Calculating exponential
res = tf.raw_ops.Exp(x = a)

# Plotting the graph
plt.plot(a, res, color ='green')
plt.title('tensorflow.raw_ops.Exp')
plt.xlabel('Input')
plt.ylabel('Result')
plt.show()
```

**输出:**

![](img/aa414a3f439d0a4d8b08f40c42fe3794.png)