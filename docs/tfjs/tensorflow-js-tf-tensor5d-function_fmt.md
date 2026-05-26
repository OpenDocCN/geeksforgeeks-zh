# TensorFlow.js `tf.tensor5d()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-tensor5d-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-tensor5d-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node 环境中运行机器学习模型和深度学习神经网络。

`.tensor5d()` 函数用于创建一个新的 5 维张量，其参数为 `value`、`shape` 和 `dataType`。

### 语法

```
tf.tensor5d(value, shape?, dataType?)
```

### 参数

*   `value`: 张量的值，可以是嵌套的数字数组、平面数组或类型数组。
*   `shape`: 张量的形状。如果不提供，张量将从该值推断其形状。这是一个可选参数。
*   `dataType`: 可以是 `"float32"` 或 `"int32"` 或 `"bool"` 或 `"complex64"` 或 `"string"` 值。这是一个可选参数。

### 返回值

返回相同数据类型的张量。返回的张量将永远是 5 维的。

### 注意

5d 张量功能也可以使用 `tf.tensor()` 函数实现，但是使用 `tf.tensor5d()` 使得代码易于理解和阅读。

### 示例 1

这里，我们正在创建一个 5d 张量并打印它。为了创建 5d 张量，我们使用 `tf.tensor5d()` 函数，我们使用 `.print()` 函数打印张量。这里，我们将把 5d 数组（即嵌套数组）传递给 `value` 参数。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs";

// Create the tensor
let example1 = tf.tensor5d([[[[[1, 3], [2, 8]], [[3, 9], [4, 2]]]]]);

// Print the tensor
example1.print()
```

**输出:**

```
Tensor
    [[[[[1, 3],
        [2, 8]],

       [[3, 9],
        [4, 2]]]]]
```

### 示例 2

在上面的例子中，我们正在创建张量，在这里我们传递平面数组并指定张量的 `shape` 参数。这里我们将看到 `shape` 参数的用法。

```javascript
// Import the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Define the value of the tensor
var value = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12];

// Specify the shape of the tensor
var shape = [1, 2, 6, 1, 1];

// Create the tensor
let example2 = tf.tensor5d(value, shape);

// Print the tensor
example2.print();
```

**输出:**

```
Tensor
    [[[ [[1 ],],
        [[2 ],],
        [[3 ],],
        [[4 ],],
        [[5 ],],
        [[6 ],]],

      [ [[7 ],],
        [[8 ],],
        [[9 ],],
        [[10],],
        [[11],],
        [[12],]]]]
```

### 示例 3

在本例中，我们将通过指定 `value`、`shape` 和 `dataType` 来创建张量。我们将创建张量，其中所有值都是字符串数据类型。

```javascript
// Import the tensorflow.js library
import * as tf from "@tensorflow/tfjs";

// Define the value of the tensor
var value = ["C", "C++", "Java", "Python", "PHP", "JS", "SQL", "React"];

// Specify the shape of the tensor
var shape = [1, 2, 4, 1, 1];

// Create the tensor
var example3 = tf.tensor5d(value, shape);

// Print the tensor
example3.print();
```

**输出:**

```
Tensor
    [[[ [['C'     ],],
        [['C++'   ],],
        [['Java'  ],],
        [['Python'],]],

      [ [['PHP'   ],],
        [['JS'    ],],
        [['SQL'   ],],
        [['React' ],]]]]
```

**参考:** [https://js.tensorflow.org/api/latest/#tensor5d](https://js.tensorflow.org/api/latest/#tensor5d)