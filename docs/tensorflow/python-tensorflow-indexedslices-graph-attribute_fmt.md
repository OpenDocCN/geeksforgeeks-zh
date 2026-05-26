# Python - TensorFlow IndexedSlices.graph 属性

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-indexedslices-graph-attribute/](https://www.geeksforgeeks.org/python-tensorflow-indexedslices-graph-attribute/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`graph` 属性用于查找包含值、索引和形状张量的图形。

## 语法和返回值

> **语法:** `TensorFlow.IndexedSlices.graph`
>
> **返回:** 它返回一个图形实例。

## 示例 1

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([[1, 2, 3], [4, 5, 6]], dtype = tf.float32)

# Printing the input
print('data: ', data)

# Calculating result
res = tf.IndexedSlices(data, [0])

# Finding Graph
@tf.function
def gfg():
  tf.compat.v1.disable_eager_execution()

graph = res.graph

# Printing the result
  print('graph: ', graph)

gfg()
```

**输出:**

```py
data:  Tensor("Const_1:0", shape=(2, 3), dtype=float32)
graph:  <tensorflow.python.framework.ops.Graph object at 0x7f2eeda9e630>

<tf.Operation 'PartitionedCall_1' type=PartitionedCall>
```

## 示例 2

```py
# Importing the library
import tensorflow as tf

# Initializing the input
data = tf.constant([1, 2, 3])

# Printing the input
print('data: ', data)

# Calculating result
res = tf.IndexedSlices(data, [0])

# Finding Graph
graph = res.graph

# Printing the result
print('graph: ', graph)
```

**输出:**

```py
data:  Tensor("Const_6:0", shape=(3, ), dtype=int32)
graph:  <tensorflow.python.framework.ops.Graph object at 0x7f2eeda9e630>
```