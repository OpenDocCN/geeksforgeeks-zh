# TensorFlow `math.add_n()` 方法

> 原文：[https://www.geeksforgeeks.org/python-tensorflow-math-add_n-method/](https://www.geeksforgeeks.org/python-tensorflow-math-add_n-method/)

TensorFlow 的 `math.add_n()` 方法用于逐元素地添加所有传入的张量。该方法属于数学模块。

## 语法

```python
tf.math.add_n(inputs, name=None)
```

## 参数

*   `inputs`：指定一个 `tf.Tensor` 或 `tf.IndexedSlices` 对象的列表，每个对象的形状和类型必须相同。`tf.IndexedSlices` 对象在方法应用前会自动转换为密集张量。
*   `name`：可选参数，用于指定操作的名称。

## 返回值

返回一个与传入的输入元素具有相同形状和类型的张量。

## 注意

该方法执行与 `tf.math.aggregate_n` 相同的操作，但 `math.add_n` 会等待所有输入准备就绪后才开始求和。因此，当输入可能未同时准备好时，这种缓冲机制会导致更多的内存消耗。

## 示例

### 示例 1

```python
# Importing the Tensorflow library 
import tensorflow as tf

# A constant a and b
a = tf.constant([[1, 3], [2, 8]])
b = tf.constant([[2, 1], [6, 7]])

# Applying the math.add_n() function 
# storing the result in 'c' 
c = tf.math.add_n([a, b])

# Initiating a Tensorflow session 
with tf.Session() as sess:
    print("Input 1", a)
    print(sess.run(a))
    print("Input 2", b)
    print(sess.run(b))
    print("Output: ", c)
```

**输出：**

```python
Input 1 Tensor("Const_99:0", shape=(2, 2), dtype=int32)
[[1 3]
 [2 8]]
Input 2 Tensor("Const_100:0", shape=(2, 2), dtype=int32)
[[2 1]
 [6 7]]
Output:  Tensor("AddN:0", shape=(2, 2), dtype=int32)
[[ 3  4]
 [ 8 15]]
```

### 示例 2

```python
# Importing the Tensorflow library 
import tensorflow as tf

# A constant a and b
a = tf.constant([[1, 1], [2, 6]])
b = tf.constant([[5, 1], [8, 7]])

# Applying the math.add_n() function 
# storing the result in 'c' 
c = tf.math.add_n([a, b], name = "Add_N")

# Initiating a Tensorflow session 
with tf.Session() as sess:
    print("Input 1", a)
    print(sess.run(a))
    print("Input 2", b)
    print(sess.run(b))
    print("Output: ", c)
    print(sess.run(c))
```

**输出：**

```python
Input 1 Tensor("Const_101:0", shape=(2, 2), dtype=int32)
[[1 1]
 [2 6]]
Input 2 Tensor("Const_102:0", shape=(2, 2), dtype=int32)
[[5 1]
 [8 7]]
Output:  Tensor("Add_N:0", shape=(2, 2), dtype=int32)
[[ 6  2]
 [10 13]]
```