# TensorFlow.js TF.depthwiseConv2d()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-depthwiseconv2d-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-depthwiseconv2d-function/)

**简介:** TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型以及深度学习神经网络。

`tf.depthwiseConv2d()`函数用于计算深度方向 2D 卷积。

此外，对于给定的 4D 输入张量以及由深度为 1 的*通道*卷积滤波器组成的形状为 `[filterHeight, filterWidth, inChannels, channelMultiplier]` 的滤波器张量，该方法对所有输入通道运行不同的滤波器（从 1 个通道扩展到每个通道的 `channelMultiplier` 个通道），然后联合连接结果。但是，输出有 `inChannels * channelMultiplier` 个通道。

**语法:**

```javascript
tf.depthwiseConv2d(x, filter, strides, pad, dataFormat?, 
dilations?, dimRoundingMode?)
```

**参数:**

*   `x`: 输入张量，为 3 阶或 4 阶，形状为：`[batch, height, width, inChannels]`。此外，在 3 阶的情况下，假定批次大小为 1。可以是 `tf.Tensor3D`、`tf.Tensor4D`、`TypedArray` 或 `Array`。
*   `filter`: 滤波器张量，形状为 `[filterHeight, filterWidth, inChannels, channelMultiplier]` 的 4 阶张量。可以是 `tf.Tensor4D`、`TypedArray` 或 `Array`。
*   `strides`: 卷积的步长：`[strideHeight, strideWidth]`。如果步长是一个数字，则 `strideHeight = strideWidth`。可以是 `[number, number]` 或 `number` 类型。
*   `pad`: 填充算法的类型。可以是 `'valid'`、`'same'`、数字类型或显式填充类型。
    1.  对于 `'same'` 和 `'valid'`，输出将具有与输入相同的大小，与滤波器大小无关。
    2.  对于需要有效输出小于输入的情况，滤波器大小应大于 `1x1`。
*   `dataFormat`: 来自 `'NHWC'` 或 `'NCHW'` 的可选字符串。它指定输入和输出数据的数据格式。默认值为 `'NHWC'`。数据按批次、高度、宽度和通道的顺序存储。可选，类型为 `'NHWC'` 或 `'NCHW'`，但目前仅支持 `'NHWC'`。
*   `dilations`: 指定的膨胀率：`[dilationHeight, dilationWidth]`。在高度和宽度维度上对输入值进行采样，这有利于稀疏卷积。默认值为 `[1, 1]`。此外，如果膨胀率是一个数字，则 `dilationHeight = dilationWidth`。如果它大于 1，则所有 `strides` 值应为 1。可选，类型为 `[number, number]` 或 `number`。
*   `dimRoundingMode`: 由 `'ceil'`、`'round'` 或 `'floor'` 组成的字符串。如果未声明，则默认为截断。可选，可以是 `'floor'`、`'round'` 或 `'ceil'` 类型。

**返回值:** 返回 `tf.Tensor3D` 或 `tf.Tensor4D`。

**例 1:**

## JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining input tensor
const x = tf.tensor4d([2, 2, 3, 4], [2, 1, 1, 2]);

// Defining filter tensor
const y = tf.tensor4d([2, 1, 4, 4], [1, 1, 2, 2]);

// Calling depthwiseConv2d() method
const result = tf.depthwiseConv2d(x, y, 2, 'same');

// Printing output
result.print();
```

**输出:**

```javascript
Tensor
    [ [ [[4, 2, 8 , 8 ],]],

[ [[6, 3, 16, 16],]]]
```

**例 2:**

## JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling depthwiseConv2d() method
tf.tensor4d([2.1, 2.2, 3.4, 4.1], [2, 1, 1, 2]).depthwiseConv2d(
 tf.tensor4d([2.1, 1.2, 4.2, 1.3], [1, 1, 2, 2]), 1, 1,
'NHWC', [1, 1], 'round').print();
```

**输出:**

```javascript
Tensor
    [[[[0        , 0        , 0         , 0        ],
       [0        , 0        , 0         , 0        ],
       [0        , 0        , 0         , 0        ]],

[[0        , 0        , 0         , 0        ],
       [4.4099994, 2.52     , 9.2399998 , 2.8599999],
       [0        , 0        , 0         , 0        ]],

[[0        , 0        , 0         , 0        ],
       [0        , 0        , 0         , 0        ],
       [0        , 0        , 0         , 0        ]]],

[[[0        , 0        , 0         , 0        ],
       [0        , 0        , 0         , 0        ],
       [0        , 0        , 0         , 0        ]],

[[0        , 0        , 0         , 0        ],
       [7.1399999, 4.0800004, 17.2199993, 5.3299994],
       [0        , 0        , 0         , 0        ]],

[[0        , 0        , 0         , 0        ],
       [0        , 0        , 0         , 0        ],
       [0        , 0        , 0         , 0        ]]]]
```

**参考:** [https://js.tensorflow.org/api/latest/#depthwiseConv2d](https://js.tensorflow.org/api/latest/#depthwiseConv2d)