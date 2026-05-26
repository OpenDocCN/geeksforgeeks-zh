# TensorFlow.js `tf.layers.minimum()` 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-layers-minimum-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-minimum-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。

`tf.layers.minimum()` 函数用于创建一个层，该层用于计算输入数组的元素式最小值。它将具有相同形状的张量列表作为输入。

## 语法

```javascript
tf.layers.minimum(args)
```

## 参数

它接受一个对象作为输入：`args` (Object)。提供 `args` 对象作为输入是可选的。以下是您可以在 `args` 对象中提供的字段。

*   `inputShape` ((empty or numeric) []): 在此层之前创建并插入一个输入层。
*   `batchInputShape` ((null or number) []): 与上述参数目的相同，但如果同时定义了 `inputShape` 和 `batchInputShape`，则优先使用 `batchInputShape`。
*   `batchSize` (number): 如果未指定上述两个参数，则使用 `batchInputShape` 来构造 `batchInputShape`。
*   `dtype`: 该层的数据类型。例如 `float32`, `int32` 等。
*   `name` (string): 用于命名该层。
*   `weights` (`tf.Tensor[]`):
*   `trainable` (Boolean): 用于指定权重是否可以通过拟合进行更新。默认值为 `true`。

## 返回值

返回元素方向的最小值。

## 例 1

```javascript
const tf = require("@tensorflow/tfjs")

// providing input
const x = tf.input({shape: [4, 4, 4]});
const y = tf.input({shape: [4, 4, 4]});

// creating required layer
const minimumLayer = tf.layers.minimum();
const minimum = minimumLayer.apply([x, y]);
console.log(minimum.shape);
```

**输出:**

```
[ null, 4, 4, 4 ]
```

## 例 2

在本例中，我们将提供 `args` 对象作为输入，其字段为 `name` 和 `trainable`。

```javascript
const tf = require("@tensorflow/tfjs")

// providing input
const x = tf.input({shape: [5, 5, 5]});
const y = tf.input({shape: [5, 5, 5]});
const z = tf.input({shape: [5, 5, 5]});

// creating required layer
const minimumLayer = tf.layers.minimum({name:"layer1", trainable:false});
const minimum = minimumLayer.apply([x, y, z]);
console.log(minimumLayer.name)
console.log(minimumLayer.trainable)
console.log(minimumLayer.shape);
```

**输出:**

```
layer1
false
[ null, 5, 5, 5 ]
```

**参考:** [https://js.tensorflow.org/api/latest/#minimum](https://js.tensorflow.org/api/latest/#minimum)