# Tensorflow.js tf.any()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-any-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-any-function/)

Tensorflow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，以便 ML 可以直接在浏览器或 Node.js 中使用。

`tf.any()` 函数主要用于为 `tf.Tensor` 计算给定维度上元素的逻辑或。

**语法**:

```
tf.any(x, axis, keepDims)
```

**参数**:

*   `x` : 输入的张量。
*   `axis`: 要缩小的尺寸。
*   `keepDims`: 如果为真，保留尺寸为 1 的缩小元素。

**返回值**: 返回 `tf.Tensor`。

## 例 1

```javascript
// Importing @tensorflow/tfjs
const tf = require("@tensorflow/tfjs")

// Initialization of tensor1d
const gfg = tf.tensor1d([-1, -2, -3, -4], 'bool')

// Printing the boolean value
gfg.any().print();
```

**输出:**

```
Tensor
    true
```

## 例 2

```javascript
// Importing @tensorflow/tfjs
const tf = require("@tensorflow/tfjs")

// Initialization of the axis
const axis = 1;

// Initialization 2d tensor of shape [2,2]
const gfg = tf.tensor2d([1, 1, 0, 0], [2, 2], 'bool')

gfg.any(axis).print()
```

**输出:**

```
Tensor
    [True, False]
```

**参考:** [https://js.tensorflow.org/api/latest/#any](https://js.tensorflow.org/api/latest/#any)