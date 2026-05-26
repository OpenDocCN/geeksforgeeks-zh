# TensorFlow.js `tf.eye()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-eye-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-eye-function/)

`TensorFlow.js` 是一个用 JavaScript 创建机器学习模型的开源库，允许用户直接在浏览器中运行模型。

`tf.eye()` 是在类 `tf.Tensor` 中定义的函数。它用于创建指定行和列的单位矩阵。

形状 `[m, n]` 的单位矩阵由所有对角元素的值 `1` 和剩余位置的值 `0` 组成。

## 语法

```
tf.eye(numRows, numColumns, batchShape, dtype)
```

## 参数

*   `numRows`: 返回单位矩阵的行数。
*   `numColumns`: 返回单位矩阵的列数。这是一个可选参数。如果未指定，返回的单位矩阵形状为 `[numRows, numRows]`。
*   `batchShape`: 这是一个数组，用于定义要附加到返回的单位矩阵形状开头的形状，通过复制单位矩阵实现。这是一个可选参数。假设 `batchShape = [a, b]`，返回的单位矩阵形状为 `[a, b, numRows, numColumns]`。
*   `dtype`: 指定为返回单位矩阵中元素的数据类型。这对于 `numColumns` 和 `batchShape` 是可选的。

## 返回值

返回一个 `tf.Tensor` 单位矩阵。

## 示例 1：创建方形形状

通过在 `tf.eye()` 方法中定义 `numRows = 3`，创建形状为 `[3,3]` 的单位矩阵。

### JavaScript

```
// 动态加载 "@tensorflow/tfjs" 模块
const tf = require('@tensorflow/tfjs');
require('@tensorflow/tfjs-node');

// 创建形状为 [3,3] 的单位矩阵
var matrix = tf.eye(numRows = 3)

// 打印单位矩阵
matrix.print()
```

### 输出

```
Tensor
    [[1, 0, 0],
     [0, 1, 0],
     [0, 0, 1]]
```

## 示例 2：创建矩形形状的单位矩阵

通过在 `tf.eye()` 方法中定义 `numRows = 3` 和 `numColumns = 4`，创建形状为 `[3,4]` 的单位矩阵。

### JavaScript

```
// 动态加载 "@tensorflow/tfjs" 模块
const tf = require('@tensorflow/tfjs');
require('@tensorflow/tfjs-node');

// 创建形状为 [3,4] 的单位矩阵
var matrix = tf.eye(numRows = 3, numColumns = 4)

// 打印单位矩阵
matrix.print()
```

### 输出

```
Tensor
    [[1, 0, 0, 0],
     [0, 1, 0, 0],
     [0, 0, 1, 0]]
```

## 示例 3：通过指定 `batchShape` 创建单位矩阵

通过在 `tf.eye()` 方法中定义 `numRows = 2` 和 `numColumns = 3`，创建形状为 `[2,3]` 的单位矩阵。
指定 `batchShape = [3]`。
将上述单位矩阵复制三次，返回的单位矩阵形状为 `[3,2,3]`。

### JavaScript

```
// 动态加载 "@tensorflow/tfjs" 模块
const tf = require('@tensorflow/tfjs');
require('@tensorflow/tfjs-node');

// 创建形状为 [2,3] 的单位矩阵，并沿新轴复制 3 次
var matrix = tf.eye(2, 3, [3])

// 打印单位矩阵
matrix.print()
```

### 输出

```
Tensor
    [[[1, 0, 0],
      [0, 1, 0]],

     [[1, 0, 0],
      [0, 1, 0]],

     [[1, 0, 0],
      [0, 1, 0]]]
```

## 参考

[https://js.tensorflow.org/api/latest/#eye](https://js.tensorflow.org/api/latest/#eye)