# TensorFlow.js TF.losses.logLoss() 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-losses-logloss-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-losses-logloss-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node 环境中运行机器学习模型和深度学习神经网络。

`tf.losses.logLoss()` 函数计算两个给定张量之间的对数损失。

## 语法

```
tf.losses.logLoss(labels, predictions, weights?, epsilon?, reduction?)
```

## 参数

*   `labels`：指定真值输出张量。基于这个张量预测绝对差。
*   `predictions`：指定预测输出张量，维度与 `labels` 相同。
*   `weights`：它指定等级张量等于 `labels` 的等级张量，因此它可以是可展宽的或 0。这是一个可选参数。
*   `epsilon`：一个小的常数值，避免取零的对数。这是一个可选参数。
*   `reduction`：规定了减少损失的类型。它是可选的。

## 返回值

返回一个由 `logLoss()` 函数计算的 `tf.Tensor`。

## 示例 1

在本例中，我们将使用两个 2D 张量作为 `labels` 和 `predictions`。然后我们会找到这两个张量的对数损失。

### JavaScript

```
// Importing the tensorflow.js library 
const tf = require("@tensorflow/tfjs");

// Defining label tensor 
const x_label = tf.tensor2d([ 
    [0., 1., 0.],  
    [1., 0., 1.] 
]);

// Defining prediction tensor 
const x_pred = tf.tensor2d([ 
    [1., 1., 1.],  
    [0., 0., 0.] 
]);

// Calculating log loss
const log_loss = tf.losses.logLoss(x_label,x_pred)

// Printing the output 
log_loss.print()
```

**输出：**

```
Tensor
    10.745397567749023
```

## 示例 2

在本例中，我们将记录两个给定张量的损失，并使用一个小的常数值 `epsilon` 来避免记录零。

### JavaScript

```
// Importing the tensorflow.js library 
const tf = require("@tensorflow/tfjs");

// Defining label tensor 
const x_label = tf.tensor2d([ 
    [1, 0, 0],  
    [1, 1, 0] 
]);

// Defining prediction tensor 
const x_pred = tf.tensor2d([ 
    [1, 1, 1],  
    [0, 0, 0] 
]);

const epsilon = 0.1;

// Calculating log loss 
const log_loss = tf.losses.logLoss(x_label,x_pred,epsilon)

// Printing the output 
log_loss.print()
```

**输出：**

```
Tensor
    1.0745397806167603
```

**参考：** `https://js.tensorflow.org/api/latest/#losses.logLoss`