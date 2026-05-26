# TensorFlow.js tf.Variable类

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-variable-class/](https://www.geeksforgeeks.org/tensorflow-js-tf-variable-class/)

TensorFlow 是谷歌设计的开源 Python 库，用于在浏览器或节点环境中开发机器学习模型和深度学习神经网络。

`tf.Variable`类用于制作一个新的可变`tf.Tensor`，并提供了一个复制`tf.Tensor`的赋值。包含相同形状和数据类型的新变量的`tf.Tensor`。

`tf.Variable`类扩展`tf.Tensor`类。

**语法：**

```
tensorflow.Variable(initialTensor)
```

**参数：**

*   `initialTensor`：它是分配给变量类对象的初始张量。

**返回值：** 不返回任何内容（即无效）。

**示例 1：** 本示例仅使用初始值创建`tf.Variable`对象。没有传递可选参数。

## JavaScript

```
// Defining tf.Tensor object for initial value
initialValue = tf.tensor([[1, 2, 3]])

// Defining tf.Variable object
const x = new tf.Variable(initialValue);

// Checking variables dtype
console.log("dtype:", x.dtype)

// Checking variable shape
console.log("shape:", x.shape)

// Printing the tf.Variable object
x.print()
```

**输出：**

```
dtype: float32
shape: 1,3
Tensor
     [[1, 2, 3],]
```

**示例 2：** 本示例使用可选参数和初始值来创建变量对象。

## JavaScript

```
// Defining tf.Tensor object for initial value
initialValue = tf.tensor([[1, 2, 3]])

// Defining tf.Variable object
const x = new tf.Variable(initialValue,
    false, 'example_varaible', 'int32');

// Checking if variable is trainable
console.log("Is trainable:", x.trainable)

// Checking variables dtype
console.log("dtype:", x.dtype)

// Checking variable shape
console.log("shape:", x.shape)

// Checking variable name
console.log("Name:", x.name)

// Printing the tf.Variable object
x.print()
```

**输出：**

```
Is trainable: false
dtype: int32
shape: 1,3
Name: example_varaible
Tensor
     [[1, 2, 3],]
```

**示例 3：** 本示例创建一个`tf.Variable`使用初始值的变量对象然后再次将初始值添加到变量中。

## JavaScript

```
// Defining tf.Tensor object for initial value
initialValue = tf.tensor([[1, 2, 3]])

// Defining tf.Variable object
const x = new tf.Variable(initialValue);

// Printing the tf.Variable object
x.print()

// Adding initial value Tensor to Variable
result = x.add(initialValue)

// Printing result
result.print()
```

**输出：**

```
Tensor
     [[1, 2, 3],]
Tensor
     [[2, 4, 6],]
```