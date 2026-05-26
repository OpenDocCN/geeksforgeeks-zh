# Python TensorFlow: GradientTape()

> 原文链接: [https://www.geeksforgeeks.org/python-tensorflow-gradienttape/](https://www.geeksforgeeks.org/python-tensorflow-gradienttape/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`GradientTape()` 用于记录自动微分的操作。

> **语法:** `tensorflow.GradientTape(persistent, watch_accessed_variables)`
>
> **参数:**
>
> *   `persistent` (可选): 可以是 `True` 或 `False`，默认值为 `False`。它定义是否创建持久梯度带。
> *   `watch_accessed_variables`: 它是一个布尔值，定义了磁带是否会自动观察磁带活动时访问的任何（可训练的）变量。

**例 1:**

## Python 3

```py
# Importing the library
import tensorflow as tf

x = tf.constant(4.0)

# Using GradientTape
with tf.GradientTape() as gfg:
  gfg.watch(x)
  y = x * x * x

# Computing gradient
res  = gfg.gradient(y, x)

# Printing result
print("res: ",res)
```

**输出:**

```py
res:  tf.Tensor(48.0, shape=(), dtype=float32)
```

**例 2:**

## Python 3

```py
# Importing the library
import tensorflow as tf

x = tf.constant(4.0)

# Using GradientTape
with tf.GradientTape() as gfg:
  gfg.watch(x)

# Using nested GradientTape for calculating higher order derivative
  with tf.GradientTape() as gg:
    gg.watch(x)
    y = x * x * x
  # Computing first order gradient
  first_order = gg.gradient(y, x)

# Computing Second order gradient
second_order  = gfg.gradient(first_order, x)

# Printing result
print("first_order: ",first_order)
print("second_order: ",second_order)
```

**输出:**

```py
first_order:  tf.Tensor(48.0, shape=(), dtype=float32)
second_order:  tf.Tensor(24.0, shape=(), dtype=float32)
```