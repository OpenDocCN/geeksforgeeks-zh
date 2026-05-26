# TensorFlow.js `tf.fill()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-fill-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-fill-function/)

`TensorFlow.js` 是一个开源库，用于在 JavaScript 中创建机器学习模型，允许用户直接在浏览器中运行模型。

`tf.fill()` 是在类 `tf.Tensor` 中定义的函数。它用于创建一个充满标量值的张量。

**语法:**

```
tf.fill( shape, value, dtype )
```

**参数:**

*   `shape`: 这是一个整数数组，定义了输出张量的形状。
*   `value`: 这是一个标量值，输出张量将被填充。
*   `dtype`: 定义输出张量中元素的数据类型。可以是 `'float32' | 'int32' | 'bool' | 'complex64' | 'string'`。包含可选，默认值为 `'float32'`。

**返回值:** 返回用标量值填充的指定形状的张量。

**示例 1: 用标量数字填充**

*   创建形状为 `[4,2]` 的张量，填充标量值 `2`。
*   设置输出张量中元素的默认数据类型为浮点型。

## JavaScript

```
// Dynamic loading the "@tensorflow/tfjs" module
const tf = require('@tensorflow/tfjs');
require('@tensorflow/tfjs-node');

// Creating a tensor of of shape [4,2] filled with 
// scalar value 2
var matrix = tf.fill(shape = [4,2],value = 2)

// Printing the tensor
matrix.print()
```

**输出:**

```
Tensor
    [[2, 2],
     [2, 2],
     [2, 2],
     [2, 2]]
```

**示例 2: 明确定义元素的数据类型**

*   创建形状为 `[3,4]` 的张量，填充字符串 `'gfg'`。

## JavaScript

```
// Dynamic loading the "@tensorflow/tfjs" module
const tf = require('@tensorflow/tfjs');
require('@tensorflow/tfjs-node');

// Creating a tensor  of shape [3,4] filled
// with string value 'Gfg'
var matrix = tf.fill(shape = [3, 4], 
        value = 'Gfg', dtype = 'string')

// Printing the tensor
matrix.print()
```

**输出:**

```
Tensor
    [['Gfg', 'Gfg', 'Gfg', 'Gfg'],
     ['Gfg', 'Gfg', 'Gfg', 'Gfg'],
     ['Gfg', 'Gfg', 'Gfg', 'Gfg']]
```

**参考:** [https://js.tensorflow.org/api/latest/#fill](https://js.tensorflow.org/api/latest/#fill)