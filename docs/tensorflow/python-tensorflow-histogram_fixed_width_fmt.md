# Python - tensorflow.histogram_fixed_width()

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-histogram_fixed_width/](https://www.geeksforgeeks.org/python-tensorflow-histogram_fixed_width/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`histogram_fixed_width()` 用于查找直方图值。

## 语法

`tensorflow.histogram_fixed_width(values, value_range, nbins, dtype, name)`

## 参数

*   `values`: 它是一个数值张量。
*   `value_range`: 是形状为 `[2]` 的张量，其数据类型与 `values` 相同。
*   `nbins` (可选): 定义直方图中的箱数。默认值为 100。
*   `dtype` (可选): 定义返回直方图的数据类型。默认值为 `int32`。
*   `name` (可选): 定义操作的名称。

## 返回

返回直方图值的张量。

## 例 1

```py
# Importing the library
import tensorflow as tf

# Initializing the input
nbins = 6
value_range = [0.0, 6.0]
new_values = [3.0, 0.0, 1.5, 2.0, 5.0, 15]

# Finding histogram values
hist = tf.histogram_fixed_width(new_values, value_range, nbins)

# Printing the result
print("res: ", hist.numpy())
```

**输出:**

```py
res:  [1 1 1 1 0 2]
```

## 例 2

```py
# Importing the library
import tensorflow as tf

# Initializing the input
nbins = 6
value_range = [0.0, 4.0]
new_values = [3.0, 0.0, 1.5, 2.0, 5.0, 1.0]

# Finding histogram values
hist = tf.histogram_fixed_width(new_values, value_range, nbins)

# Printing the result
print("res: ", hist.numpy())
```

**输出:**

```py
res:  [1 1 1 1 1 1]
```