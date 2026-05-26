# TensorFlow `GradientTape.gradients()` 方法详解

> 原文链接: [https://www.geeksforgeeks.org/python-tensorflow-gradienttape-gradients/](https://www.geeksforgeeks.org/python-tensorflow-gradienttape-gradients/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`gradients()` 方法用于使用在该磁带上下文中记录的操作来计算梯度。

## 语法

`gradients(target, sources, output_gradients, unconnected_gradients)`

## 参数

*   `target`: 是待区分张量或张量列表。
*   `sources`: 是张量或张量列表。目标值与来源不同。
*   `output_gradients`: 是一个梯度列表，默认值为 `None`。
*   `unconnected_gradients`: 其值可以是 `None`，也可以是零，默认值为 `None`。

## 返回值

返回张量的列表或嵌套结构。

## 示例 1

```python
# Importing the library
import tensorflow as tf

x = tf.constant(4.0)

# Using GradientTape
with tf.GradientTape() as gfg:
  gfg.watch(x)
  y = x * x * x

# Computing gradient
res = gfg.gradient(y, x)

# Printing result
print("res: ", res)
```

**输出:**

```python
res:  tf.Tensor(48.0, shape=(), dtype=float32)
```

## 示例 2

```python
# Importing the library
import tensorflow as tf

x = tf.constant(4.0)

# Using GradientTape
with tf.GradientTape() as gfg:
  gfg.watch(x)

  # Using nested GradientTape for
  # calculating higher order derivative
  with tf.GradientTape() as gg:
    gg.watch(x)
    y = x * x * x

  # Computing first order gradient
  first_order = gg.gradient(y, x)

# Computing Second order gradient
second_order = gfg.gradient(first_order, x)

# Printing result
print("first_order: ", first_order)
print("second_order: ", second_order)
```

**输出:**

```python
first_order:  tf.Tensor(48.0, shape=(), dtype=float32)
second_order:  tf.Tensor(24.0, shape=(), dtype=float32)
```