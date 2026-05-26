# TensorFlow.js TF.regularizers.l1() 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-regularizers-l1-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-regularizers-l1-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`正则化 l1()` 函数用于 L1 正则化。此外，为了惩罚巨大的权重，它在损失函数后面加上了一个惩罚项：`loss += sum(l1 * abs(x))`。

## 语法

```
tf.regularizers.l1(config?)
```

## 参数

*   `config`：是可选对象。它包含属性 `l1`。
*   `l1`：是所述的 L1 正则化率，其默认值为 `0.01`。它是数字类型的。

## 返回值

返回一个 `正则化器`。

## 示例 1

在本例中，我们将看到 L1 正则化器独立应用于核权重矩阵。

```
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs");

// Define sequential model
const model = tf.sequential();

// Adding layer to it and calling 
// regularizers.l1() method
model.add(tf.layers.dense({
    units: 37, batchInputShape:[null, 40],
    kernelRegularizer:tf.regularizers.l1()
}));

// Calling summary() method and 
// Printing output
model.summary();
```

**输出：**

```
_________________________________________________________________
Layer (type)                 Output shape              Param #   
=================================================================
dense_Dense52 (Dense)        [null,37]                 1517      
=================================================================
Total params: 1517
Trainable params: 1517
Non-trainable params: 0
_________________________________________________________________
```

## 示例 2

在本例中，我们将看到 L1 正则化器独立应用于偏置向量。

```
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs");

// Define sequential model
const model = tf.sequential();

// Adding layer to it and calling 
// regularizers.l1() method
model.add(tf.layers.dense({
    units: 2, batchInputShape:[null, 13],
    biasRegularizer:tf.regularizers.l1()
}));

// Calling summary() method and 
// Printing output
model.summary();
```

**输出：**

```
_________________________________________________________________
Layer (type)                 Output shape              Param #   
=================================================================
dense_Dense54 (Dense)        [null,2]                  28        
=================================================================
Total params: 28
Trainable params: 28
Non-trainable params: 0
_________________________________________________________________
```

**参考：** [https://js.tensorflow.org/api/latest/#regularizers.l1](https://js.tensorflow.org/api/latest/#regularizers.l1)