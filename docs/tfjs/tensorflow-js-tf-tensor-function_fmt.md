# TensorFlow.js tf.tensor()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。

`tf.tensor()`函数用于借助`value`、`shape`、`dataType`创建新的张量。

**语法:**

```
tf.tensor( value, shape, dataType)
```

**参数:**

*   `value`: 张量的值，可以是简单的或嵌套的`array`或`number`类型的数。如果数组元素是`string`，那么它们将编码为`UTF-8`，并保持为`Uint8Array[]`。
*   `shape`【可选】: 为可选参数。它呈现张量的形状。如果没有提供，张量将从`value`推断的形状。
*   `dataType`【可选】: 也是可选参数。它可以是`"float32"`或`"int32"`或`"bool"`或`"complex64"`或`"string"`。

**返回值:** 返回相同数据类型的张量。

## 示例 1

在这个示例中，我们正在创建一个张量并打印它。为了创建张量，我们使用`tf.tensor()`方法和打印张量我们使用的是`print()`方法。

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating the tensor
var val = tf.tensor([1, 2, 3, 4, 5, 6, 7]);

// Printing the tensor
val.print()
```

**输出:**

```
Tensor
    [1, 2, 3, 4, 5, 6, 7]
```

## 示例 2

在这个示例中，我们正在创建张量，其中我们没有提到张量的形状参数，让我们在这里看到形状参数。

### JavaScript

```
// Importing the tensorflow library
import * as tf from "@tensorflow/tfjs"

// Defining the value of the tensor
var value = [1, 2, 3, 4, 5, 6]

// Specify the shape of the tensor
var shape = [2, 3]

// Creating the tensor
var val = tf.tensor(value, shape)

// Printing the tensor
val.print()
```

**输出:**

```
Tensor
    [[1, 2, 3],
     [4, 5, 6]]
```

上面的例子是创建 2 × 3 维的张量。

## 示例 3

在此示例中，我们正在创建一个具有`value`、`shape`和`dataType`的张量。我们正在创建字符串类型值的张量。

### JavaScript

```
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Creating a value variable which
// stores the value
var value = ['1', '2', '3', '4', '5', '6']

// Creating a shape variable
// which stores the shape
var shape = [2, 3]

// Creating a d_Type variable
// which stores the data-type
var d_Type = 'string'

// Creating the tensor
var val = tf.tensor(value, shape, d_Type)

// Printing the tensor
val.print()
```

**输出:**

```
Tensor
    [['1', '2', '3'],
     ['4', '5', '6']]
```

打印字符串类型值的张量。