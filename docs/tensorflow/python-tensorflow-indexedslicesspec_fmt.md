# Python - TensorFlow IndexedSlicesSpec()

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-indexedslicesspec/](https://www.geeksforgeeks.org/python-tensorflow-indexedslicesspec/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

## IndexedSlicesSpec 类

`IndexedSlicesSpec` 类继承自 `TypeSpec`，并为索引切片（IndexedSlices）提供类型规范。

## 语法

```python
tf.IndexedSlicesSpec(shape, dtype, index_dtype, dense_shape_dtype, index_shape)
```

## 参数

*   `shape`（可选）：定义索引切片的密集形状。默认值为 `None`，允许任何密集形状。
*   `dtype`（可选）：定义 `IndexedSlices` 值的数据类型。默认值为 `tf.float32`。
*   `index_dtype`（可选）：定义 `IndexedSlices` 中索引的数据类型。它可以是 `tf.int32` 或 `tf.int64`，默认值为 `tf.int64`。
*   `dense_shape_dtype`（可选）：定义 `IndexedSlices` 中密集形状的数据类型。它可以是 `tf.int32`、`tf.int64` 或 `None`，默认值为 `None`。
*   `index_shape`（可选）：它定义了 indexes 组件的形状，表示 `IndexedSlices` 中有多少切片。

## 示例

### 示例 1

本示例使用所有默认值。

```python
# Importing the library
import tensorflow as tf

# Calculating result
res = tf.IndexedSlicesSpec()

# Printing the result
print('IndexedSlicesSpec: ', res)
```

**输出：**

```python
IndexedSlicesSpec:  IndexedSlicesSpec(TensorShape(None), tf.float32, tf.int64, None, TensorShape([None]))
```

### 示例 2

```python
# Importing the library
import tensorflow as tf

# Calculating result
res = tf.IndexedSlicesSpec((2, 3))

# Printing the result
print('IndexedSlicesSpec: ', res)
```

**输出：**

```python
IndexedSlicesSpec:  IndexedSlicesSpec(TensorShape([2, 3]), tf.float32, tf.int64, None, TensorShape([None]))
```