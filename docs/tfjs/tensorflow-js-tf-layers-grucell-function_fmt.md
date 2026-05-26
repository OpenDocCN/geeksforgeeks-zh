# TensorFlow.js `tf.layers.gruCell()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layers-grucell-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-grucell-function/)

TensorFlow.js 是谷歌正在开发的一个开源库，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`tf.layers.gruCell()` 函数用于为 GRU 创建一个单元格类。

## 语法

```javascript
tf.layers.gruCell(args)
```

## 参数

*   `recurrentActivation`: 它是张量输入，是用于递归步骤的激活函数，默认为 hard sigmoid。如果传递 `null`，则不会应用任何激活。
*   `implementation`: 是张量输入，有两种实现方式:
    1.  模式 0 将把它的操作构造成大量的小点积和加法。
    2.  模式 1 会将它们批量化为更少、更大的操作。这些模式在不同的硬件和不同的应用中会有不同的性能特征。
*   `resetAfter`: 这是一个张量输入，可以是 GRU 惯例，是在矩阵乘法之后还是之前应用 reset gate，其中 `false` = “之前” 和 `true` = “之后”。
*   `units`: 它是张量输入，具有正整数 units，是输出空间的维度。
*   `activation`: 它是一个张量输入，是一个激活函数，默认为 `tanh`。如果传递 `null`，将应用线性激活。
*   `useBias`: 这是一个张量输入，其中偏置向量用于图层。
*   `kernelInitializer`: 它是一个张量输入，是内核权重矩阵的初始化器，用于输入的线性变换。
*   `recurrentInitializer`: 它是一个张量输入，是递归核权重矩阵的初始化器，用于递归状态的线性变换。
*   `biasInitializer`: 它是一个张量输入，是偏置向量的初始化器。
*   `kernelRegularizer`: 它是一个张量输入，正则化函数应用于核权重矩阵。
*   `recurrentRegularizer`: 它是一个张量输入，正则化函数应用于递归核权重矩阵。
*   `biasRegularizer`: 它是一个张量输入，正则化函数应用于偏置向量。
*   `kernelConstraint`: 这是一个张量输入，其中约束函数应用于核权重矩阵。
*   `recurrentConstraint`: 这是一个张量输入，其中约束函数应用于递归核权重矩阵。
*   `biasConstraint`: 这是一个张量输入，其中约束函数应用于偏置向量。
*   `dropout`: 这是一个张量输入，其中输入和浮点数的线性变换要下降的单位分数在 0 和 1 之间。
*   `recurrentDropout`: 这是一个张量输入，其中递归状态和 0 到 1 之间的浮点数的线性变换要下降的单位分数。
*   `inputShape`: 这是一个张量输入，将用于创建一个输入图层，如果定义的话，插入到该图层之前。它仅适用于输入图层。
*   `batchInputShape`: 这是一个张量输入，将用于创建一个输入图层，如果定义的话，插入到该图层之前。它仅适用于输入图层。
*   `batchSize`: 如果指定了 `inputShape` 而未指定 `batchInputShape`，则是张量输入，其中 `batchSize` 用于构造 `batchInputShape`。
*   `dtype`: 这是一个张量输入，是这个图层的数据类型，默认为 `'float32'`。
*   `name`: 是张量输入，是这个图层的名称。
*   `trainable`: 无论该层的权重是否可通过拟合更新，它都是默认为 `true` 的张量输入。
*   `weights`: 可以是图层初始权重值的张量输入。
*   `inputType`: 是张量输入，有遗留支持，不用于新代码。

## 返回值

返回 `GRUCell`。

## 示例 1

在此示例中，`GRUCell` 不同于 RNN 子类 `GRU`，因为它的 `apply` 方法只获取单个时间步长的输入数据，并在该时间步长返回单元格的输出，而 `GRU` 则获取多个时间步长的输入数据。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining input elements
const cell = tf.layers.gruCell({units: 3});
const input = tf.input({shape: [11]});
const output = cell.apply(input);

console.log(JSON.stringify(output.shape));
```

**输出:**

```
[null,11]
```

## 示例 2

在此示例中，可以使用 `GRUCell` 的实例来构建 RNN 图层。此工作流最典型的用途是将多个像元组合成一个堆叠的 RNN 像元（即内部堆叠的像元），并使用它创建一个 RNN 像元。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining input elements
const cells = [
   tf.layers.gruCell({units: 8}),
   tf.layers.gruCell({units: 16}),
];
const rnn = tf.layers.rnn({
    cell: cells, 
    returnSequences: true
});

// Create an input with 20 time steps and 
// a length-30 vector at each step.
const input = tf.input({shape: [20, 30]});
const output = rnn.apply(input);

console.log(JSON.stringify(output.shape));
```

**输出:**

```
[null,20,16]
```

**参考:** [https://js.tensorflow.org/api/latest/#layers.gruCell](https://js.tensorflow.org/api/latest/#layers.gruCell)