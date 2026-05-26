# TensorFlow.js tf.pool() 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-pool-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-pool-function/)

## 简介
TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node.js 环境下运行机器学习模型以及深度学习神经网络。

`tf.pool()` 函数用于执行一个 N-D 池化功能。

## 语法
```
tf.pool(input, windowShape, poolingType, pad, dilations?, strides?)
```

## 参数
*   `input`：所述输入张量为等级 3 或等级 4，并且具有形状：`[batch, height, width, inChannels]`。此外，在等级为 3 的情况下，则假定批量大小为 1。它可以是 `tf.Tensor3D`、`tf.Tensor4D`、`TypedArray` 或数组。
*   `windowShape`：规定的过滤器尺寸：`[filterHeight, filterWidth]`。它可以是类型 `[number, number]` 或 `number`。在这种情况下，如果 `filterSize` 是一个单数，那么 `filterHeight == filterWidth`。
*   `poolingType`：池化的指定类型，可以是 `'max'` 或 `'avg'`。
*   `pad`：所述的填充算法类型。它可以是 `'valid'`、`'same'`、`'number'` 或 `'conv'` 类型。
    1.  这里，对于 `'same'` 和步长 1，输出将具有与输入相同的大小，而与滤波器大小无关。
    2.  对于 `'valid'`，在滤波器尺寸大于 `1*1*1` 的情况下，输出应小于输入。
*   `dilations`：规定的扩张速率：`[dilationHeight, dilationWidth]`，在扩张池的高度和宽度维度上对输入值进行采样。默认值为 `[1, 1]`。此外，如果膨胀是一个单一的数字，那么 `dilationHeight == dilationWidth`。如果它大于 1，那么步幅的所有值都应该是 1。它是可选的，类型为 `[number, number]` 或 `number`。
*   `strides`：池化的规定步幅：`[strideHeight, strideWidth]`。在这种情况下，如果跨步是一个单数，那么 `strideHeight == strideWidth`。它是可选的，类型为 `[number, number]` 或 `number`。

## 返回值
返回 `tf.Tensor3D` 或 `tf.Tensor4D`。

## 例 1
### JavaScript
```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining input tensor
const x = tf.tensor3d([1, 2, 3, 4], [2, 2, 1]);

// Calling pool() method
const result = tf.pool(x, 3, 'avg', 'same', [1, 2], 1);

// Printing output
result.print();
```

**输出：**
```
Tensor
    [[[0.4444444],
      [0.6666667]],

[[0.4444444],
      [0.6666667]]]
```

## 例 2
### JavaScript
```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling pool() method
tf.tensor3d([1.2, 2.1, 3.0, -4], [2, 2, 1]).pool(3,
                    'conv_util.ExplicitPadding', 1, 1).print();
```

**输出：**
```
Tensor
    [[[3],
      [3]],

[[3],
      [3]]]
```

## 参考
[https://js.tensorflow.org/api/latest/#pool](https://js.tensorflow.org/api/latest/#pool)