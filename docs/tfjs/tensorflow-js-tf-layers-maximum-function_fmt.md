# `tf.layers.maximum()` 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-layers-maximum-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-maximum-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

当提供多个数组作为输入时，`tf.layers.maximum()` 函数用于计算每个元素的最大值。

## 语法

```
tf.layers.maximum().apply([input1, input2, ...... , inputn])
```

## 参数

*   `inputShape`：这是一个可选参数，用于创建输入图层，它采用数字和 `null` 等值。
*   `batchInputShape`：是一个可选参数，用于在主图层之前创建输入图层，取数值如 `number` 和 `null`。
*   `batchSize`：它是用于制作 `batchInputShape` 的可选参数，只接受数字。
*   `dtype`：可选参数，代表数据类型。默认情况下，它有 `"float32"`，还支持其他值如 `"int32"`、`"bool"` 等。
*   `name`：为可选参数，用于定义图层名称，接受字符串。
*   `trainable`：是一个可选参数，决定提供的输入图层是否更新。它接受布尔值。
*   `weights`：拥有图层的起始权重。它也是一个可选参数。
*   `inputType`：是用于输入数据类型的可选参数。像 `dtype` 一样，它也支持它的所有值。

## 返回值

返回最大值。

## 例1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

const input1 = tf.input({shape: [3, 3]});
const input2 = tf.input({shape: [3, 3]});
const maximumLayer = tf.layers.maximum();
const maximum = maximumLayer.apply([input1, input2]);
console.log(JSON.stringify(maximum.shape));
```

**输出：**

```
[null,3,3]
```

## 例2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

const input1 = tf.input({shape: [4, 4]});
const input2 = tf.input({shape: [4, 4]});
const input3 = tf.input({shape: [4, 4]});
const input4 = tf.input({shape: [4, 4]});
const input5 = tf.input({shape: [4, 4]});
const input6 = tf.input({shape: [4, 4]});
const maximumLayer = tf.layers.maximum();
const maximum = maximumLayer.apply([input1,
    input2, input3, input4, input5, input6]);

console.log(JSON.stringify(maximum.shape));
```

**输出：**

```
[null,4,4]
```

**参考：** [https://js.tensorflow.org/api/latest/#layers.maximum](https://js.tensorflow.org/api/latest/#layers.maximum)