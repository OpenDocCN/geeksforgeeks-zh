# TensorFlow.js `tf.image.nonMaxSuppressionAsync()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-image-nonmaxsuppressionasync-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-image-nonmaxsuppressionasync-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.image.nonMaxSuppressionAsync()` 函数用于在 IoU（交并比）的基础上执行边界框的非最大值抑制。此外，它是 `tf.image.nonMaxSuppression()` 方法的*异步*版本。

**语法:**

```javascript
tf.image.nonMaxSuppressionAsync(boxes,
    scores, maxOutputSize, iouThreshold?, scoreThreshold?)
```

**参数:**

*   `boxes`: 一个二维张量，其形状为 `[numBoxes, 4]`。每个边界框由 `[y1, x1, y2, x2]` 表示，其中 `(y1, x1)` 和 `(y2, x2)` 是边界框的边缘。它可以是 `tf.Tensor2D`、`TypedArray` 或数组。
*   `scores`: 一个一维张量，包含边界框的分数，形状为 `[numBoxes]`。它是 `tf.Tensor1D`、`TypedArray` 或数组。
*   `maxOutputSize`: 整数，表示要保留的边界框的最大数量。
*   `iouThreshold`: 浮点数，用于决定边界框是否与已选框重叠过多（IoU）的阈值。取值范围应在 `[0, 1]` 之间。默认值为 `0.5`，表示允许 50% 的重叠。此参数可选。
*   `scoreThreshold`: 浮点数，根据分数决定何时移除边界框的阈值。默认值为 `-Infinity`，表示接受所有分数。此参数可选。

**返回值:** 返回一个 `Promise`，其解析值为 `tf.Tensor1D`。

**示例 1:** 在本例中，我们将使用一个二维张量、分数和 `maxOutputSize` 参数。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling image.nonMaxSuppressionAsync() method
const output = await tf.image.nonMaxSuppressionAsync(
    tf.tensor2d([[1, 2, 3, 4], [2, 4, 6, 7]]),
    [1, 1], 4);

// Printing output
output.print();
```

**输出:**

```
Tensor
    [0, 1]
```

**示例 2:** 在本例中，我们将使用一个浮点数组、`iouThreshold` 以及 `scoreThreshold`。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining an array of floats
const arr = [[11.1, 2.3, 7.3, 6.4], [3, 6, 8, 9]]

// Calling image.nonMaxSuppressionAsync() method
const res = await tf.image.nonMaxSuppressionAsync(
    arr, [2.1, 0], 100, 0.5, 1);

// Printing output
res.print();
```

**输出:**

```
Tensor
    [0]
```

**参考:** [https://js.tensorflow.org/api/latest/#image.nonMaxSuppressionAsync](https://js.tensorflow.org/api/latest/#image.nonMaxSuppressionAsync)