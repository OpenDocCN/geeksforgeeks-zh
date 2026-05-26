# Python–tensorflow.executing_eagerly()

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-executing_eagerly/](https://www.geeksforgeeks.org/python-tensorflow-executing_eagerly/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`executing_eagerly()` 用于检查当前线程中是否启用或禁用了紧急执行。默认情况下，启用了紧急执行，因此在大多数情况下，它将返回 `True`。在以下情况下，这将返回 `False`:

*   如果是在 `tensorflow.function`、`tf.init_scope` 或 `tf.config.experimental_run_functions_eagerly(True)` 之前没有调用。
*   在 `tensorflow.dataset` 的转换函数中执行。
*   调用 `tensorflow.compat.v1.disable_eager_execution()`。

## 语法

`tensorflow.executing_eagerly()`

## 参数

这个不接受任何参数。

## 返回

如果启用了紧急执行，则返回真，否则返回假。

## 例 1

```py
# Importing the library
import tensorflow as tf

# Checking eager execution
res = tf.executing_eagerly()

# Printing the result
print('res: ', res)
```

**输出:**

```py
res:  True
```

## 示例 2

本示例检查有和没有 `init_scope` 的 `tensorflow.function` 的紧急执行。

```py
# Importing the library
import tensorflow as tf

@tf.function
def gfg():
  with tf.init_scope():
    # Checking eager execution inside init_scope
    res = tf.executing_eagerly()
    print("res 1:", res)

  # Checking eager execution outside init_scope
  res = tf.executing_eagerly()
  print("res 2:", res)
gfg()
```

**输出:**

```py
res 1: True
res 2: False
```