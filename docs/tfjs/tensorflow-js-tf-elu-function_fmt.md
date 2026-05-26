# TensorFlow.js TF.elu() 函数

> 哎哎哎:# t0]https://www . geeksforgeeks . org/tensorlow-js-TF-elu-function/

TensorFlow.js 是谷歌正在开发的一个开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`.elu()` 函数用于找到所述张量输入的指数线性，并按元素进行。

## 语法

```
tf.elu(x)
```

其中，x > 0？东^ x-1:0。

## 参数

*   `x`: 是待计算的指数线性值的张量输入，类型可以是 `tf.Tensor`、`TypedArray` 或 `Array`。

## 返回值

返回 `tf.Tensor` 对象。

## 示例 1

在这个示例中，我们定义了一个整数类型的输入张量，然后打印它的指数线性值。为了创建输入张量，我们使用 `tensor1d()` 方法，为了打印输出，我们使用 `.print()` 方法。

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining tensor input elements
const y = tf.tensor1d([10, 1, 8, 0]);

// Calling elu() method and
// printing output
y.elu().print();
```

## 输出

```
Tensor
    [10, 1, 8, 0]
```

## 示例 2

在本例中，浮点类型值被视为张量输入，参数直接传递给 `elu` 函数。

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining float values
var val = [-0.5, 1.5, .56];

// Calling tensor1d method
const y = tf.tensor1d(val);

// Calling elu() method
var res = tf.elu(y)

// Printing output
res.print();
```

## 输出

```
Tensor
    [-0.3934693, 1.5, 0.56]
```

## 参考

https://js.tensorflow.org/api/latest/#elu