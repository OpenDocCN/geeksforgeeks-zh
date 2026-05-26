# TensorFlow.js TF.ones() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-ones-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-ones-function/)

TensorFlow.js 是一个开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。`TF.ones()` 函数用于创建一个新的张量，其中所有元素都设置为 1。

**语法:**

```javascript
tf.ones(shape, dtype, name)
```

**参数:**

*   `shape`: 它接受张量的形状。可以是一个多维数组或 `int32`。
*   `dtype`: 接受我们要插入的 1 的数据类型。默认设置为 `float32`，但也可以是 `int32`。这是一个可选参数。
*   `name`: 接受我们正在执行的操作的名称。默认为 `None`。这是一个可选参数。

**返回值:** 返回数据类型相同的张量。

## 示例 1

在本例中，我们将创建一个 2D 张量，其所有值都设置为整数数据类型的 1。

```javascript
// Import tensorflow
import tensorflow as tf

// Get a Tensor
val = tf.ones([10, 10], tf.int32)

// Print the Tensor
print(val)
```

**输出:**

```javascript
tf.Tensor(
[[1 1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1 1]], shape=(10, 10), dtype=int32)
```

## 示例 2

在本例中，我们将创建一个 1D 张量，其所有值都设置为浮点数据类型的 1。

```javascript
// Import tensorflow
import tensorflow as tf

// Get a Tensor
val = tf.ones(5, tf.float32)

// Print a Tensor
print(val)
```

**输出:**

```javascript
tf.Tensor([1. 1. 1. 1. 1.], shape=(5,), dtype=float32)
```

**参考:** [https://js.tensorflow.org/api/latest/#ones](https://js.tensorflow.org/api/latest/#ones)