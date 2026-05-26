# TensorFlow.js `tf.image.nonMaxSuppressionPadded()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-image-nonmaxsuppressionpadded-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-image-nonmaxsuppressionpadded-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`tf.image.nonMaxSuppressionPadded()` 函数用于基于 IoU（交集超过并集）异步执行限制框的非最大抑制，并提供填充结果的机会。

## 语法

```
tf.image.nonMaxSuppressionPadded(boxes, scores, maxOutputSize,
    iouThreshold?, scoreThreshold?, padToMaxOutputSize?)
```

## 参数

*   `boxes`: 二维张量，其形状为 `[numBoxes, 4]`。每个框由 `[y1, x1, y2, x2]` 表示，其中 `(y1, x1)` 和 `(y2, x2)` 是限制框的边缘。可以是 `tf.Tensor2D`、`TypedArray` 或数组。
*   `scores`: 一维张量，包含框的分数，形状为 `[numBoxes]`。可以是 `tf.Tensor1D`、`TypedArray` 或数组。
*   `maxOutputSize`: 要被挑选的框的最大数量。数字类型。
*   `iouThreshold`: 浮点数，表示决定框是否与 IoU 相交过多的阈值。应在 `[0, 1]` 之间。默认值为 `0.5`，即 50% 的方块相交。可选，数字类型。
*   `scoreThreshold`: 根据分数决定何时移除框的阈值。默认值是 `-Infinity`，即允许每一个分数。可选，数字类型。
*   `padToMaxOutputSize`: 布尔类型的可选参数。默认值为 `false`。如果为 `true`，则结果的维度 `selectedIndices` 会被填充到 `maxOutputSize`。

## 返回值

返回 `{[name: string]: tf.Tensor}`。

## 示例 1

在本例中，我们将使用 2D 张量、分数和 `maxOutputSize` 参数。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling image.nonMaxSuppressionPadded() method
const output = tf.image.nonMaxSuppressionPadded(
    tf.tensor2d([1, 2, 3, 4, 2, 4, 6, 7],
    [2, 4]), [1, 1], 4
);

// Printing output
console.log(output);
```

**输出:**

```
{
  "selectedIndices": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [],
    "dtype": "int32",
    "size": 2,
    "strides": [],
    "dataId": {
      "id": 22
    },
    "id": 22,
    "rankType": "1",
    "scopeId": 12
  },
  "validOutputs": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [],
    "dtype": "int32",
    "size": 1,
    "strides": [],
    "dataId": {
      "id": 23
    },
    "id": 23,
    "rankType": "0",
    "scopeId": 12
  }
}
```

## 示例 2

在本例中，我们将使用浮点数组、`iouThreshold`、`scoreThreshold` 以及 `padToMaxOutputSize`。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining an array of floats
const arr = [[11.1, 2.3, 7.3, 6.4], [3, 6]]

// Calling image.nonMaxSuppressionPadded() method
const res = tf.image.nonMaxSuppressionPadded(
    arr, [2.1, 0], 100, 0.5, 1, true);

// Printing output
console.log(res);
```

**输出:**

```
{
  "selectedIndices": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [],
    "dtype": "int32",
    "size": 2,
    "strides": [],
    "dataId": {
      "id": 42
    },
    "id": 42,
    "rankType": "1",
    "scopeId": 22
  },
  "validOutputs": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [],
    "dtype": "int32",
    "size": 1,
    "strides": [],
    "dataId": {
      "id": 43
    },
    "id": 43,
    "rankType": "0",
    "scopeId": 22
  }
}
```

## 参考

[https://js.tensorflow.org/api/latest/#image.nonMaxSuppressionPadded](https://js.tensorflow.org/api/latest/#image.nonMaxSuppressionPadded)