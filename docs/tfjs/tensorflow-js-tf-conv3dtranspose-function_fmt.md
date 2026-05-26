# TensorFlow.js TF.conv3dTranspose() 函数

> 哎哎哎: # t0]https://www.geeksforgeeks.org/tensorflow-js-TF-conv3dTranspose-function/

## 简介

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型以及深度学习神经网络。

`tf.conv3dTranspose()` 函数用于确定体积的转置 3D 卷积。这也称为反卷积。

## 语法

```
tf.conv3dTranspose(x, filter, outputShape, strides, pad)
```

## 参数

*   `x`: 所述输入图像，其或者是等级 5 或者是等级 4，并且具有形状: [`batch, inDepth, inHeight, inWidth, inChannels`]。此外，在等级为 4 的情况下，则假定批量大小为 1。它可以是 `tf.Tensor4D`、`tf.Tensor5D`、`TypedArray` 或数组。
*   `filter`: 所述的秩为 4 的滤波器张量和形状: [`filterDepth, filterHeight, filterWidth, outChannels, inChannels`]。其中，`inChannels` 必须与输入张量中的 `inChannels` 匹配。它可以是 `tf.Tensor5D`、`TypedArray` 或数组。
*   `outputShape`: 所述的输出形状为等级 5 或等级 4，形状为 [`batch, outDepth, outHeight, outWidth, outChannels`]。在这种情况下，等级为 3，则假定批次为 1。它可以是 `[number, number, number, number, number]` 或 `[number, number, number, number]` 类型。
*   `strides`: 形状的原始卷积的规定步幅: [`strideDepth, strideHeight, strideWidth`]。它可以是类型 `[number, number, number]` 或数字。
*   `pad`: 在运算的非转置形式中有用的填充算法的指定类型。它可以是 `'valid'` 类型，也可以是 `'same'` 类型。

## 返回值

返回 `tf.Tensor4D` 或 `tf.Tensor5D`。

## 例 1

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining input tensor
const x = tf.tensor5d([1, 2, 2, 3], [2, 2, 1, 1, 1]);

// Defining filter tensor
const y = tf.tensor5d([3, 3, 3, 2], [1, 2, 2, 1, 1]);

// Calling conv3dTranspose() method
const result = tf.conv3dTranspose(x, y, [1, 1, 2, 1, 1], 2, 'same');

// Printing output
result.print();
```

### 输出

```
Tensor
    [[[ [[3],],

[[3],]]]]
```

## 例 2

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling conv3dTranspose() method
tf.conv3dTranspose(tf.tensor5d(
    [1.1, 2.1, 2.2, 3.6], [2, 2, 1, 1, 1]),
    tf.tensor5d([3.6, 3.1, 3.2, 2.0], [1, 2, 2, 1, 1]),
    [1, 1, 2, 1, 1], 7, 'valid').print();
```

### 输出

```
Tensor
    [[[ [[0],],

[[0],]]]]
```

## 参考

https://js.tensorflow.org/api/latest/#conv3dTranspose