# TensorFlow.js `tf.image.resizeNearestNeighbor()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-image-resizenearestneighbor-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-image-resizenearestneighbor-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.image.resizeNearestNeighbor()` 函数用于将一批 3D 图像重新缩放到不同的尺寸。

## 语法

```javascript
tf.image.resizeNearestNeighbor(images,
    size, alignCorners?, halfPixelCenters?)
```

## 参数

*   `images`: 所述的等级 4 或等级 3 的图像，其具有配置 `[批次, 高度, 宽度, 通道数]`。此外，在等级 3 的情况下，则假定一个批次。它可以是 `tf.Tensor3D`、`tf.Tensor4D`、`TypedArray` 或数组。
*   `size`: 不同的规定配置 `[新高度, 新宽度]`，以便重新缩放图像。每个通道都被一个接一个地重新缩放。它是类型 `[number, number]`。
*   `alignCorners`: 是默认为 `false` 的可选参数。如果是 `true`，输入的大小会调整 `(newHeight–1)/(height–1)`，这绝对会将所述图像的四个角以及重新缩放的图像进行对齐。然而，如果它是 `false`，那么它会被 `newHeight/height` 重新缩放。它以同样的方式处理宽度维度。它属于布尔类型。
*   `halfPixelCenters`: 是默认为 `false` 的可选参数。它属于布尔类型。

## 返回值

返回 `tf.Tensor3D` 或 `tf.Tensor4D`。

## 示例 1

在本例中，我们将使用 4D 张量和 size 参数。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling image.resizeNearestNeighbor() method
// and printing output
tf.image.resizeNearestNeighbor(tf.tensor4d([[[[4, 7], [21, 9]], [[8, 9], [1, 33]]]]), [3, 4]).print();
```

**输出:**

```
Tensor
    [[[[4 , 7 ],
       [4 , 7 ],
       [21, 9 ],
       [21, 9 ]],
      [[4 , 7 ],
       [4 , 7 ],
       [21, 9 ],
       [21, 9 ]],
      [[8 , 9 ],
       [8 , 9 ],
       [1 , 33],
       [1 , 33]]]]
```

## 示例 2

在本例中，我们将使用一个浮点数组、`alignCorners` 以及 `halfPixelCenters`。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining an array of floats
const arr = [[[[1.1, 1.7, 1.5, 1.1],
  [1.7, 1.9, 8.1, 6.3]],
 [[3.3, 3.4, 3.7, 4.0],
  [5.1, 5.2, 5.3, 5.9]]]];

// Calling image.resizeNearestNeighbor() method
// and printing output
tf.image.resizeNearestNeighbor(arr, [1, 2], true, false).print();
```

**输出:**

```
Tensor
    [[[[1.1, 1.7, 1.5      , 1.1      ],
       [1.7, 1.9, 8.1000004, 6.3000002]]]]
```

参考: T2