# TensorFlow.js TF.dilation2d() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-dilation2d-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-dilation2d-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`dilation2d()` 函数用于评估所述输入张量的灰度膨胀。

## 语法

```
tf.dilation2d(x, filter, strides, pad, dilations?, dataFormat?)
```

## 参数

*   `x`: 所述的输入张量，其或者是等级 3 或者是等级 4，并且具有形状: [`batch, height, width, in_channels`]。此外，在等级为 3 的情况下，则假定批量大小为 1。它可以是 `tf.Tensor3D`、`tf.Tensor4D`、`TypedArray` 或数组。
*   `filter`: 所述的秩 3 的滤波器张量和形状: [`filterHeight, filterWidth, depth`]。它可以是 `tf.Tensor3D`、`TypedArray` 或数组。
*   `strides`: 给定形状输入张量的每个尺寸的滑动窗口的规定步幅: [`strideHeight, strideWidth`]。在这种情况下，规定的步幅是一个单一的数字，那么 `strideHeight` = `strideWidth`。它可以是类型 `[number, number]` 或 `number`。
*   `pad`: 所述的填充算法类型。它可以是 `'same'` 类型或 `'valid'` 类型。
    1.  这里，对于 `'same'` 和步长 1，输出将具有与输入相同的大小，而与滤波器大小无关。
    2.  对于 `'valid'`，在滤波器尺寸大于 1*1*1 的情况下，输出应小于输入。
*   `dilations`: 规定的扩张速率: [`dilationHeight, dilationWidth`] 输入值在高度和宽度维度上进行采样，以利于萎缩形态扩张。默认值为 `[1, 1]`。此外，如果膨胀是一个单一的数字，那么 `dilationHeight` == `dilationWidth`。如果它大于 1，那么步幅的所有值都应该是 1。它是可选的，类型为 `[number, number]` 或 `number`。
*   `dataFormat`: 指定所述输入和输出数据的数据格式。默认值为 `'NHWC'`。而且，这里的数据是按照 [`batch, height, width, channels`] 的顺序存储的。它是可选的，类型为 `'NHWC'`。

## 返回值

返回 `tf.Tensor3D` 或 `tf.Tensor4D`。

## 例 1

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining input tensor
const x = tf.tensor3d([1, 2, 3, 4], [2, 2, 1]);

// Defining filter tensor
const y = tf.tensor3d([1, 1, 0, 4], [1, 1, 4]);

// Calling dilation2d() method
const result = tf.dilation2d(x, y, 2, 'valid');

// Printing output
result.print();
```

**输出:**

```
Tensor
     [ [[2],]]
```

## 例 2

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling dilation2d() method with
// all its parameters
tf.tensor3d([1.1, 2.2, 3.3, 4.4], [2, 2, 1]).dilation2d(
 tf.tensor3d([1.3, 1.2, null, -4], [1, 1, 4]),
             2, 'valid', [3, 2], 'NHWC').print();
```

**输出:**

```
Tensor
     [ [[2.4000001],]]
```

**参考:** [https://js.tensorflow.org/api/latest/#dilation2d](https://js.tensorflow.org/api/latest/#dilation2d)