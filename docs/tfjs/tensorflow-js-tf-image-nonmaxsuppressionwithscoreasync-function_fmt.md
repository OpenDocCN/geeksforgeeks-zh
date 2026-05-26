# TensorFlow.js `tf.image.nonMaxSuppressionWithScoreAsync()` 函数

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.image.nonMaxSuppressionWithScoreAsync()` 函数用于基于 IoU 异步执行边界框的非最大值抑制，即在并集上求交集。此外，该操作还支持软 NMS 模式，在该模式中，边界框会降低与其相交的其他边界框的置信度分数，因此除了高分框之外，还支持保留图像的各个区域。为了启用前面提到的软 NMS 模式，我们需要将 `softNmsSigma` 参数设置为大于零。

## 语法

```
tf.image.nonMaxSuppressionWithScoreAsync(boxes, scores, maxOutputSize, iouThreshold?, scoreThreshold?, softNmsSigma?)
```

## 参数

该方法接受以下参数：

*   `boxes`：一个二维张量，其形状为 `[numBoxes, 4]`。每个边界框由 `[y1, x1, y2, x2]` 表示，其中 `(y1, x1)` 和 `(y2, x2)` 是边界框的边缘。它可以是 `tf.Tensor2D`、`TypedArray` 或数组。
*   `scores`：一个一维张量，其形状为 `[numBoxes]`，包含每个边界框的置信度分数。它是 `tf.Tensor1D`、`TypedArray` 或数组。
*   `maxOutputSize`：一个数字，表示要被挑选的边界框的最大数量。
*   `iouThreshold`：一个介于 `[0, 1]` 之间的浮点数，用于决定边界框是否与另一个框的 IoU 相交过多。默认值为 `0.5`，即 50% 的重叠。此参数可选。
*   `scoreThreshold`：一个浮点数，作为根据置信度分数决定何时移除边界框的阈值。默认值是 `-Infinity`，即允许所有分数。此参数可选。
*   `softNmsSigma`：一个可选的数字参数，表示用于软 NMS 的西格玛参数。如果西格玛为零，则回退到标准非最大抑制。

## 返回值

返回一个 `Promise<{[name: string]: tf.Tensor}>`。

## 示例 1

使用二维张量、分数和最大输出大小参数。

```javascript
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs")

// Calling image.nonMaxSuppressionWithScoreAsync() method
const output = tf.image.nonMaxSuppressionWithScoreAsync(
    tf.tensor2d([1, 2, 3, 4, 2, 4, 6, 7], [2, 4]), [1, 1], 4);

// Printing output
console.log(output.then((result) => console.log(result)));
```

**输出：**

```
{
  selectedIndices: Tensor {
    kept: false,
    isDisposedInternal: false,
    shape: [ 2 ],
    dtype: 'int32',
    size: 2,
    strides: [],
    dataId: { id: 2 },
    id: 2,
    rankType: '1'
  },
  selectedScores: Tensor {
    kept: false,
    isDisposedInternal: false,
    shape: [ 2 ],
    dtype: 'float32',
    size: 2,
    strides: [],
    dataId: { id: 3 },
    id: 3,
    rankType: '1'
  }
}
```

## 示例 2

使用浮点数组、`iouThreshold`、`scoreThreshold` 以及 `softNmsSigma`。

```javascript
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs")

// Defining an array of floats
const arr = [[11.1, 2.3, 7.3, 6.4], [3, 6]]

// Calling image.nonMaxSuppressionWithScoreAsync() method
const output = tf.image.nonMaxSuppressionWithScoreAsync(
    arr, [2.1, 0], 100, 0.5, 1, 0.5);

// Printing output
console.log(output.then((result) => console.log(result)));
```

**输出：**

```
{
  selectedIndices: Tensor {
    kept: false,
    isDisposedInternal: false,
    shape: [ 1 ],
    dtype: 'int32',
    size: 1,
    strides: [],
    dataId: { id: 2 },
    id: 2,
    rankType: '1'
  },
  selectedScores: Tensor {
    kept: false,
    isDisposedInternal: false,
    shape: [ 1 ],
    dtype: 'float32',
    size: 1,
    strides: [],
    dataId: { id: 3 },
    id: 3,
    rankType: '1'
  }
}
```

## 参考

[https://js.tensorflow.org/api/latest/#image.nonMaxSuppressionWithScoreAsync](https://js.tensorflow.org/api/latest/#image.nonMaxSuppressionWithScoreAsync)