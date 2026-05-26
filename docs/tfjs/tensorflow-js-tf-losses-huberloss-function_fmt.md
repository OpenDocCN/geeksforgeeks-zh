# TensorFlow.js TF.losses.huberLoss() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-losses-huberloss-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-losses-huberloss-function/)

**TensorFlow.js** 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

函数的作用是：计算两个给定张量之间的 Huber 损失。

## 语法

```
tf.losses.huberLoss(
    labels, predictions,
    weights, delta, reduction
);
```

## 参数

*   `labels`：是地面真值输出张量。它在维度上类似于 `predictions`。
*   `predictions`：预测的是输出。
*   `weights`：这些张量的秩不是 0 就是 1，它们必须是可展宽的，才能失去形状。
*   `delta`：就是 `huberLoss` 从二次型转化为线性型的点。
*   `reduction`：适用于亏损的还原类型。它必须是缩减类型。

**注：** `weights`、`delta` 和 `reduction` 为可选参数。

## 返回值

返回 `tf.Tensor`。

## 例 1

### JavaScript

```
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Initializing tensor1 as geek1
let geek1 = tf.tensor2d([[1, 2, 5], [6, 7, 10]]);

// Initializing tensor2 as geek2
let geek2 = tf.tensor2d([[5, 7, 11], [2, 4, 8]])

// Computing huber loss between geek1 and geek2
// using .huberLoss() function
geek = tf.losses.huberLoss(geek1, geek2)
geek.print();
```

**输出：**

```
Tensor
    3.5
```

## 例 2

### JavaScript

```
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Computing huber loss between two 3D
// tensors and printing the result
tf.losses.huberLoss(
    tf.tensor4d([[[[9], [8]], [[7], [5]]]]),
    tf.tensor4d([[[[1], [2]], [[3], [4]]]])
).print();
```

**输出：**

```
Tensor
    4.25
```

**参考：** [https://js.tensorflow.org/api/latest/#losses.huberLoss](https://js.tensorflow.org/api/latest/#losses.huberLoss)