# Python–TensorFlow `bitwise.bitwise_or()` 方法

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-bitwise-bitwise_or-method/](https://www.geeksforgeeks.org/python-tensorflow-bitwise-bitwise_or-method/)

TensorFlow `bitwise.bitwise_or()` 方法执行按位“或”运算，并返回在 `a` 或 `b` 或两者中设置（1）的那些位。操作是在 `a` 和 `b` 的二进制表示上完成的。这个方法属于 `bitwise` 模块。

## 语法
`tf.bitwise.bitwise_or(a, b, name=None)`

## 参数
*   `a`: 这一定是张量。它应该来自以下类型之一：`int8`、`int16`、`int32`、`int64`、`uint8`、`uint16`、`uint32`、`uint64`。
*   `b`: 这也应该是张量，类型和 `a` 一样。
*   `name`: 这是可选参数，是操作的名称。

## 返回值
它返回一个与 `a` 和 `b` 类型相同的张量。

让我们通过几个例子来理解这个概念：

### 示例 1
```py
# Importing the Tensorflow library 
import tensorflow as tf

# A constant a and b 
a = tf.constant(43, dtype = tf.int32) 
b = tf.constant(5, dtype = tf.int32)

# Applying the bitwise_or function 
# storing the result in 'c' 
c = tf.bitwise.bitwise_or(a, b)

# Initiating a Tensorflow session 
with tf.Session() as sess:
    print("Input 1", a)
    print(sess.run(a))
    print("Input 2", b)
    print(sess.run(b))
    print("Output: ", c)
    print(sess.run(c))
```

**输出:**
```py
Input 1 Tensor("Const_22:0", shape=(), dtype=int32)

Input 2 Tensor("Const_23:0", shape=(), dtype=int32)

Output:  Tensor("BitwiseOr_1:0", shape=(), dtype=int32)
```

### 示例 2
```py
# Importing the Tensorflow library 
import tensorflow as tf

# A constant vector of size 2 
a = tf.constant([1, 6], dtype = tf.int32) 
b = tf.constant([2, 5], dtype = tf.int32)

# Applying the bitwise_or function 
# storing the result in 'c' 
c = tf.bitwise.bitwise_or(a, b)

# Initiating a Tensorflow session 
with tf.Session() as sess:
    print("Input 1", a)
    print(sess.run(a))
    print("Input 2", b)
    print(sess.run(b))
    print("Output: ", c)
    print(sess.run(c))
```

**输出:**
```py
Input 1 Tensor("Const_20:0", shape=(2, ), dtype=int32)
[1 6]
Input 2 Tensor("Const_21:0", shape=(2, ), dtype=int32)
[2 5]
Output:  Tensor("BitwiseOr:0", shape=(2, ), dtype=int32)
[3 7]
```