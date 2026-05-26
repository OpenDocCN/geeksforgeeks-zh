# TensorFlow.js `tf.zerosLike()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-zeroslike-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-zeroslike-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。`tf.zerosLike()` 用于创建一个 `tf.tensor`，通过传递参数 `value`，将所有元素设置为 `0`，使其具有与给定张量相同的形状。

## 语法

```
tf.zerosLike(value)
```

## 参数

它接受如上所述的单个参数，如下所述：

*   `value`: 它是张量的值，可以是一个简单或嵌套的数组或数字类型。这里我们传递所需形状的张量。

## 返回值

返回所需形状的张量。

## 注

以上功能**不改变**原张量。

## 示例 1

在本例中，我们使用 `tf.zerosLike()` 方法。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating the tensor
var val = tf.tensor([1, 2, 3, 4, 5, 6, 7]);

//using tf.zerosLike() and printing the tensor
tf.zerosLike(val).print()

// Printing the tensor
tf.print("Original tensor:\n"+val)
```

```
Tensor
    [0, 0, 0, 0, 0, 0, 0]
Original tensor:
Tensor
    [1, 2, 3, 4, 5, 6, 7]
```

## 示例 2

在本例中，我们使用 `tf.tensor1d()` 方法创建张量，并应用 `tf.zerosLike` 方法。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating the tensor
var val = tf.tensor1d([1, 2, 3]);

//using tf.zerosLike() and printing the tensor
tf.zerosLike(val).print()

// Printing the tensor
tf.print("Original tensor:\n"+val)
```

```
Tensor
    [0, 0, 0]
Original tensor:
Tensor
    [1, 2, 3]
```

## 示例 3

在本例中，我们使用 `tf.tensor2d()` 方法创建张量并应用 `tf.zerosLike` 方法。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating the tensor
var val = tf.tensor2d([[1, 2], [3, 4]]);

//using tf.zerosLike() and printing the tensor
tf.zerosLike(val).print()

// Printing the tensor
tf.print("Original tensor:\n"+val)
```

```
Tensor
    [[0, 0],
     [0, 0]]
Original tensor:
Tensor
    [[1, 2],
     [3, 4]]
```

## 示例 4

在本例中，我们将使用 `tf.tensor3d()` 方法创建张量，并应用 `tf.zerosLike()` 方法。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating the tensor
var val = tf.tensor3d([[[1], [2]], [[3], [4]]]);

//using tf.zerosLike() and printing the tensor
tf.zerosLike(val).print()

// Printing the tensor
tf.print("Original tensor:\n"+val)
```

```
Tensor
    [[[0],
      [0]],

     [[0],
      [0]]]
Original tensor:
Tensor
    [[[1],
      [2]],

     [[3],
      [4]]]
```

## 示例 5

在本例中，我们使用 `tf.tensor4d()` 方法创建张量，并应用 `tf.zerosLike()` 方法。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating the tensor
var val = tf.tensor4d([[[[1], [2]], [[3], [4]]]])

//using tf.zerosLike() and printing the tensor
tf.zerosLike(val).print()

// Printing the tensor
tf.print("Original tensor:\n"+val)
```

```
Tensor
    [[[[0],
       [0]],

      [[0],
       [0]]]]
Original tensor:
Tensor
    [[[[1],
       [2]],

      [[3],
       [4]]]]
```

## 参考

[https://js.tensorflow.org/api/latest/#zerosLike](https://js.tensorflow.org/api/latest/#zerosLike)