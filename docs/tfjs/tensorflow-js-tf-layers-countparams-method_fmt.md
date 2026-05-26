# TensorFlow.js TF.layers.countParams() 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-layers-countparams-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-countparams-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`countParams()` 函数用于查找规定权重中 `float32`、`int32` 等数字的绝对计数。

**语法：**

```
countParams()
```

**参数：** 此方法不接受任何参数。

**返回值：** 返回一个数字。

## 示例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating a model
const model = tf.sequential();

// Adding a layer
model.add(tf.layers.dense({units: 2, inputShape: [11]}));

// Calling setWeights() method
model.layers[0].setWeights(
    [tf.truncatedNormal([11, 2]), tf.zeros([2])]);

// Calling countParams() method and also
// Printing output
console.log(model.layers[0].countParams());
```

**输出：** 这里，使用 `truncatedNormal()` 方法创建 `tf.Tensor`，其值从截断正态分布中采样；使用 `zeros()` 方法创建 `tf.Tensor`，其所有元素设置为 0；`setWeights()` 方法用于设置权重。

```
24
```

## 示例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating a model
const model = tf.sequential();

// Adding layers
model.add(tf.layers.dense({units: 1, 
    inputShape: [5], batchSize: 1, dtype: 'int32'}));
model.add(tf.layers.dense({units: 2, inputShape: [6], batchSize: 5}));
model.add(tf.layers.dense({units: 3, inputShape: [7], batchSize: 8}));
model.add(tf.layers.dense({units: 4, inputShape: [8], batchSize: 12}));

// Calling setWeights() method
model.layers[0].setWeights([tf.ones([5, 1]), tf.zeros([1])]);
model.layers[1].setWeights([tf.ones([1, 2]), tf.zeros([2])]);

// Calling countParams() method and also
// Printing outputs
console.log(model.layers[0].countParams());
console.log(model.layers[1].countParams());
console.log(model.layers[2].countParams());
```

**输出：** 这里，使用 `ones()` 方法创建一个 `tf.Tensor`，其所有元素设置为 1。

```
6
8
24
```

**参考：** [https://js.tensorflow.org/api/latest/#tf.layers.Layer.countParams](https://js.tensorflow.org/api/latest/#tf.layers.Layer.countParams)