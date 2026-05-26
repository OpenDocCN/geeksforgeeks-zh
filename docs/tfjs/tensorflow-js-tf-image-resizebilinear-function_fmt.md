# TensorFlow.js TF.image.resizeBilinear() 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-image-resizebilinear-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-image-resizebilinear-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.image.resizeBilinear()` 函数用于将单个 3D 图像或一堆 3D 图像双线性缩放到不同的配置。

## 语法

```
tf.image.resizeBilinear(images, size, alignCorners?, halfPixelCenters?)
```

## 参数

*   `images`: 所述的等级 4 或等级 3 的图像，其具有配置 [批次、高度、宽度、通道]。此外，在等级 3 的情况下，则假定一个的批次。它可以是 `tf.tensor3D`，`tf.tensor4D`、TypedArray 或数组。
*   `size`: 不同的规定配置 [新高度，新宽度]，以便重新缩放图像。每个频道都被一个接一个地重新缩放。它是类型 `[number, number]`。
*   `alignCorners`: 是默认为 `false` 的可选参数。如果是 `true`，输入的大小会调整 `(new_height–1)/(height–1)`，这绝对会将所述图像的四个角以及重新缩放的图像进行排队。然而，如果它是 `false`，那么它会被 `new_height/height` 重新缩放。它以同样的方式处理宽度维度。它是类型 `boolean`。
*   `halfPixelCenters`: 是默认为 `false` 的可选参数。它是类型 `boolean`。

## 返回值

返回 `tf.tensor3D`，或 `tf.tensor4D`。

## 示例 1

在本例中，我们将在 `tf.image.resizeBilinear()` 函数中使用 4D 张量和大小参数。

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling image.resizeBilinear() method and
// Printing output
tf.image.resizeBilinear(tf.tensor4d([[[[4, 7], [21, 9]], [[8, 9], [1, 33]]]]), [3, 4]).print();
```

**输出:**

```
Tensor
    [[[[4        , 7        ],
       [12.5     , 8        ],
       [21       , 9        ],
       [21       , 9        ]],
      [[6.666667 , 8.333333 ],
       [7.1666665, 16.666666],
       [7.666666 , 25       ],
       [7.666666 , 25       ]],
      [[8        , 9        ],
       [4.5      , 21       ],
       [1        , 33       ],
       [1        , 33       ]]]]
```

## 示例 2

在本例中，我们将使用一个浮点数、`alignCorners` 以及 `halfPixelCenters` 的数组。

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining an array of floats
const arr = [[[ [1.1, 1.7, 1.5, 1.1], [1.7, 1.9, 8.1, 6.3] ], [ [3.3, 3.4, 3.7, 4.0], [5.1, 5.2, 5.3, 5.9] ]]];

// Calling image.resizeBilinear() method and
// Printing output
tf.image.resizeBilinear(arr, [1, 2], true, false).print();
```

**输出:**

```
Tensor
    [[[[1.1, 1.7, 1.5      , 1.1      ],
       [1.7, 1.9, 8.1000004, 6.3000002]]]]
```

**参考:** [https://js.tensorflow.org/api/latest/#image.resizeBilinear](https://js.tensorflow.org/api/latest/#image.resizeBilinear)