# TensorFlow.js TF.separableConv2d() 函数

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`.separableConv2d()` 函数用于确定 2D 复杂度以及可分离的滤波器。它执行深度方向的复杂度，该复杂度在通过点方向的复杂度追求的通道上明显工作，这有助于混合通道。而且，它规定了[1，2]和 3 维内的可分性，绝对不是 1 维和 2 维内的结构可分性。

## 语法

```
tf.separableConv2d(x, depthwiseFilter, pointwiseFilter, 
        strides, pad, dilation?, dataFormat?)
```

## 参数

*   `x`: 所述的输入张量，其或者是等级 3 或者是等级 4，并且具有形状:【批次、高度、宽度、英寸通道】。此外，在等级为 3 的情况下，则假定批量大小为 1。它可以是 `tf.tensor3D`，`tf.tensor4D`、TypedArray 或数组。
*   `depthwiseFilter`: 所述的深度方向滤波器张量等级 4 和形状:【滤波器高度，滤波器宽度，通道，通道倍增器】。然而，它是在最初阶段使用的。它可以是 `tf.tensor4D`、TypedArray 或数组。
*   `pointwiseFilter`: 所述的点态滤波器张量等级 4 和形状:[1，1，inChannels * channelMultiplier，outChannels]。然而，它被用于操作的第二阶段。它可以是 `tf.tensor4D`、TypedArray 或数组。
*   `strides`: 所述的形态复杂化的步幅:【条纹，条纹】。在这种情况下，所述步幅是一个单数，那么 `strideHeight` = `strideWidth`。它可以是类型 `[number, number]` 或 `number`。
*   `pad`: 所述的填充算法类型。它可以是 `'valid'` 类型或 `'same'` 类型。
    *   对于 `'same'` 和步幅 1，输出将具有与输入相同的大小，而与滤波器大小无关。
    *   对于 `'valid'` 输出应小于输入，以防滤波器尺寸大于 1*1×1。
*   `dilation`: 所述的膨胀。它是可选的，类型为 `[number, number]` 或 `number`。
*   `dataFormat`: 来自 `'NHWC'` 或 `'NCHW'` 的指定选择字符串。它指定所述输入和输出数据的数据形状。默认值为 `'NHWC'`。此外，这里的数据按照以下顺序保存:【批次、高度、宽度、通道】。它是可选的，类型为 `'NHWC'`。

## 返回值

返回 `tf.tensor3D` 或 `tf.tensor4D`。

## 示例 1

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining input tensor
const x = tf.tensor4d([1, 2, 3, 4], [1, 1, 2, 2]);

// Defining depthwise filter tensor
const y = tf.tensor4d([1, 1, 0, 4], [1, 1, 2, 2]);

// Defining pointwise filter tensor
const z = tf.tensor4d([1, 1, 0, 4], [1, 1,     4, 1]);

// Calling separableConv2d() method
const result = tf.separableConv2d(x, y, z, 2, 'valid');

// Printing output
result.print();
```

### 输出

```
Tensor
     [ [ [[34],]]]
```

## 示例 2

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling separableConv2d() method
tf.separableConv2d(
    tf.tensor4d([1.1, 2.2, 3.3, 4.4], [1, 1, 2, 2]), 
    tf.tensor4d([1.2, 1.1, 0.3, 4.5], [1, 1, 2, 2]),
    tf.tensor4d([1.4, 1.6, 0.5, 4.8], [1, 1,     4, 1]),
    1, 'same', 1, 'NHWC').print();
```

### 输出

```
Tensor
    [[[[51.6340065 ],
       [107.0520096]]]]
```

## 参考资料

[https://js.tensorflow.org/api/latest/#separableConv2d](https://js.tensorflow.org/api/latest/#separableConv2d)