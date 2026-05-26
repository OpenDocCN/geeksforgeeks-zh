# TensorFlow.js TF.metrics.meanSquaredError() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-metrics-meansquarederror-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-metrics-meansquarederror-function/)

**TensorFlow.js** 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。

`tf.metrics.meanSquaredError()` 函数是一个损失或度量函数，用于计算 `y_true` 和 `y_pred` 之间的均方误差。`y_true` 是真实张量，`y_pred` 是预测张量。

## 语法

```
tf.metrics.meanSquaredError(tensor1, tensor2);
```

## 参数

该函数接受两个参数，如下所示：

*   `tensor1`: 是真实张量 (`y_true`)。
*   `tensor2`: 是预测张量 (`y_pred`)。

## 返回值

返回真实张量和预测张量之间的均方误差张量。

## 示例 1

```javascript
// Importing the TensorFlow.js library
// import * as tf from "@tensorflow/tfjs"

// Creating the tensor
let truth = tf.tensor1d([6, 4]);
let prediction = tf.tensor1d([-3, -4]);

// Calculating mean squared Error
// between truth and prediction tensor
const mse = tf.metrics.meanSquaredError(truth, prediction);

// Printing mean square error
mse.print();
```

**输出:**

```
Tensor
    72.5
```

## 示例 2

```javascript
// Importing the TensorFlow.js library
// import * as tf from "@tensorflow/tfjs"

// Calculating mean squared Error between
// truth and prediction tensor
let mse = tf.metrics.meanSquaredError(
    tf.tensor1d([0, 1, 2, 3]),
    tf.tensor1d([-8,-9, -10, -11])
);

// Printing mean square error
mse.print();
```

**输出:**

```
Tensor
    121
```

**参考:** [https://js.tensorflow.org/api/latest/#metrics.meanSquaredError](https://js.tensorflow.org/api/latest/#metrics.meanSquaredError)