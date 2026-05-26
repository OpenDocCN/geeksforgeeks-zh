# TensorFlow.js TF.metrics.binaryAccuracy() 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-metrics-binaryaccuracy-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-metrics-binaryaccuracy-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。

`TF.metrics.binaryAccuracy()` 函数用于计算预测与二进制标签匹配的频率。该函数以两个张量为参数，张量的值在 0 到 1 之间。

## 语法

```
tf.metrics.binaryAccuracy(True, Prediction)
```

## 参数

*   `True`：是真的二元张量，张量可以包含 0 到 1 之间的值。
*   `Prediction`：它是预测的张量，张量可以包含 0 到 1 之间的值。

## 返回值

返回张量。

## 示例 1

在本例中，我们给出了两个一维张量，其中包含 0 到 1 之间的值作为参数，`metrics.binaryAccuracy` 函数将计算匹配的预测并返回一个张量。

```javascript
// Importing the tensorflow library
import * as tf from "@tensorflow/tfjs"

// Defining the value of the tensor
const True = tf.tensor1d([1, 0, 1, 1, 0, 1, 0, 0]);
const Prediction = tf.tensor1d([0.2, 0.4, 0.6, 0.3, 0.7, 0.3, 0.4, 0.7]);

// Calculating predictions match
const accuracy = tf.metrics.binaryAccuracy(True, Prediction);

// Printing the tensor
accuracy.print();
```

**输出：**

```
Tensor
    0.375
```

## 示例 2

在本例中，我们给出了两个包含值 0 和 1 作为参数的 2D 张量，`metrics.binaryAccuracy` 函数将计算匹配的预测并返回一个张量。

```javascript
// Importing the tensorflow library
import * as tf from "@tensorflow/tfjs"

// Defining the value of the tensor
const True = tf.tensor2d([[1, 0, 1, 1], [1, 0, 1, 0]], [2, 4]);
const Prediction = tf.tensor2d([[1, 0, 1, 0], [0, 1, 0, 1]], [2, 4]);

// Calculating predictions match
const accuracy = tf.metrics.binaryAccuracy(True, Prediction);

// Printing the tensor
accuracy.print();
```

**输出：**

```
Tensor
    [0.75, 0]
```

**参考：** [https://js.tensorflow.org/api/latest/#metrics.binaryAccuracy](https://js.tensorflow.org/api/latest/#metrics.binaryAccuracy)