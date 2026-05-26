# TensorFlow.js TF.layers.reshape() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layers-reshape-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-reshape-function/)

TensorFlow.js 是谷歌正在开发的一个开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.layers.reshape()` 函数用于将输入重塑为特定形状。

## 语法

```
tf.layers.reshape(args)
```

## 参数

该函数将 `args` 对象作为参数，该参数可以具有以下属性：

*   `targetShape`: 不包括批次轴的数字。
*   `inputShape`: 是一个数字，用于创建一个输入图层，插入到该图层之前。
*   `batchInputShape`: 是一个数字，用来创建一个输入图层插入到该图层之前。
*   `batchSize`: 是用于构造 `batchInputShape` 的数字。
*   `dtype`: 该层的数据类型。
*   `name`: 是该层的字符串。
*   `trainable`: 这是一个布尔值，其中该层的权重是否可通过拟合更新。
*   `weights`: 图层的初始权重值。
*   `inputType`: 用于遗留支持。不要用于新代码。

## 返回值

返回整形后的层。

以下示例演示了使用 `tf.layers.reshape()` 函数对图层进行整形。

## 例 1

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining the tensor input elements
const input = tf.input({shape: [2, 6]});

// Calling the layers.reshape() function
const reshapeLayer = tf.layers.reshape({targetShape: [3, 9]});

// Inspect the inferred output shape of the
// Reshape layer, which equals `[null, 3, 9]`.
// (The 1st dimension is the undermined batch size.)
console.log(JSON.stringify(
    reshapeLayer.apply(input).shape));
```

**输出:**

```
[null, 3, 9]
```

## 示例 2

在本例中，我们讨论的是图层的重塑。

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining the tensor input elements
const input = tf.input({shape: [4, 8]});

// Calling the layers.reshape() function
const reshapeLayer =
    tf.layers.reshape({targetShape: [4, 8]});

// Inspect the inferred output shape of
// the Reshape layer, which equals `[null, 4, 8]`.
// (The 1st dimension is the undermined batch size.)
console.log(JSON.stringify(
    reshapeLayer.apply(input).shape));
```

**输出:**

```
[null, 4, 8]
```

**参考:** [https://js.tensorflow.org/api/latest/#layers.reshape](https://js.tensorflow.org/api/latest/#layers.reshape)