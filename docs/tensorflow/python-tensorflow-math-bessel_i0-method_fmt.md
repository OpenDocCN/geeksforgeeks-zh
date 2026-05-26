# Python | tensorflow.math.bessel_i0() 方法

> 原文：[https://www.geeksforgeeks.org/python-tensorflow-math-bessel_i0-method/](https://www.geeksforgeeks.org/python-tensorflow-math-bessel_i0-method/)

[TensorFlow](https://www.geeksforgeeks.org/introduction-to-tensorflow/) 是谷歌为开发机器学习模型和深度学习神经网络而设计的开源 Python 库。

`bessel_i0()` 是 TensorFlow 数学模块中的方法。该方法用于计算张量的元素贝塞尔 i0。

## 语法
```py
tensorflow.math.bessel_i0(
    input, name
)
```

## 参数
1.  `input`：它是一个张量或稀疏张量，用于计算其元素级的贝塞尔 i0。允许的数据类型有 half、float32、float64。
2.  `name`：这是一个可选参数，用于定义操作的名称。

## 返回值
如果输入是张量，则返回一个张量；如果是稀疏张量，则返回一个稀疏张量，其数据类型与输入相同。

## 例 1：
```py
# importing the library
import tensorflow as tf

# initializing constant tensor
a = tf.constant([-1.5, 3 ], dtype=tf.float64)

# calculating bessel i0
b = tf.math.bessel_i0(a)

# printing the input
print('Input: ',a)

# printing the output
print('Output: ',b)
```

**输出：**
```py
Input:  tf.Tensor([-1.5  3. ], shape=(2,), dtype=float64)
Output:  tf.Tensor([1.64672319 4.88079259], shape=(2,), dtype=float64)
```

## 例 2：
本示例使用 dtype 为 int32 的张量，这会引发错误。只允许使用 dtype half、float32、float64 的张量。

```py
# importing the library
import tensorflow as tf

# initializing constant tensor with dtype int32
a = tf.constant([1 , 3 ], dtype=tf.int32)

# printing the input
print('Input: ',a)

# calculating bessel i0
b = tf.math.bessel_i0(a)
```

**输出：**
```py
Input:  tf.Tensor([1 3], shape=(2,), dtype=int32)

NotFoundError                             Traceback (most recent call last)

<ipython-input-43-4c70ca866e4c> in <module>()
----> 1 b = tf.math.bessel_i0(a)
```