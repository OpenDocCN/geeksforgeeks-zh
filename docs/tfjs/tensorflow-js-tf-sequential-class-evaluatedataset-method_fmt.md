# TensorFlow.js tf.Sequential类的evaluateDataset()方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-sequential-class-evaluatedataset-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-sequential-class-evaluatedataset-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`.evaluateDataset()` 方法用于通过指定的数据集对象评估指定的序列模型。

**注意：** 此方法与 `evaluate()` 不同，因为它是异步的。

**语法：**

```javascript
evaluateDataset(dataset, args?)
```

**参数：**

*   `dataset`：数据集对象。为了生成数据集迭代器对象，我们需要调用其 `iterator()` 方法，然后调用返回的迭代器的 `next()` 方法来生成用于评估的数据批次。此外，`next()` 调用的返回值必须包含一个布尔类型的 `done` 字段和一个 `value` 字段。`value` 字段可以是一个由两个 `tf.Tensor` 组成的数组，或者一个由两个嵌套的 `tf.Tensor` 数组构成的数组。前者适用于模型只有一个输入和一个输出的情况（例如 `Sequential` 模型）。后者适用于模型有多个输入和/或多个输出的情况。数组中的两个元素，第一个是输入特征，第二个是输出目标。类型为 `tf.data.Dataset`。
*   `args`：支持基于数据集的评估的配置对象。它是可选的，类型为对象。包含以下参数：
    1.  `batch`：在终止评估之前，从给定数据集对象中提取的指定批次的数量。类型为数值。
    2.  `verbose`：状态详细模式。类型为 `model` 详细级别。

**返回值：** 返回一个 `tf.Scalar` 或 `tf.Scalar[]` 的 Promise。

**例 1：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining an array x
const Array_x = [
   [1, 1, 1, 1, 1, 1, 1, 1],
   [1, 1, 1, 1, 1, 1, 1, 1],
   [1, 1, 1, 1, 1, 1, 1, 1],
   [1, 1, 1, 1, 1, 1, 1, 1],
];

// Defining an array y
const Array_y = [1, 1, 1, 1];

// Defining dataset of x
const Dataset_x = tf.data.array(Array_x);

// Defining dataset of y
const Dataset_y = tf.data.array(Array_y);

// Defining dataset of xy using zip method
const Dataset_xy = tf.data.zip({xs: Dataset_x, ys: Dataset_y})
     .batch(5)
     .shuffle(3);

// Training Model 
const gfg = tf.sequential();

// Adding layer to model   
const layer = tf.layers.dense({units:1, 
               inputShape : [8]});
   gfg.add(layer);

// Compiling our model 
const config = {optimizer:'sgd', 
              loss:'meanSquaredError'};
  gfg.compile(config);

// Calling evaluateDataset() method
const res = await gfg.evaluateDataset(Dataset_xy, 
tf.ones([7, 10]), tf.ones([7, 1]), {
   batchSize: 5,
});

// Printing output
res.print();
```

**输出：**

```text
Tensor
    2.9478049278259277
```

**例 2：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining dataset of xy using zip method
const Dataset_xy = tf.data.zip({
    xs: tf.data.array([[1, 0, 1, 2, 1]]), 
    ys: tf.data.array([1, 2, 1, 3])}).batch(8);

// Training Model 
const gfg = tf.sequential();

// Adding layer to model   
const layer = tf.layers.dense({units:1, 
    inputShape : [5], activation: 'sigmoid'});

gfg.add(layer);

// Compiling our model 
const config = {optimizer:'sgd', 
              loss:'meanSquaredError'};

gfg.compile(config);

// Calling evaluateDataset() method
const res = await gfg.evaluateDataset(
    Dataset_xy, tf.truncatedNormal([7, 10]), 
    tf.randomNormal([7, 1]), 
    {batchSize: 2, steps: 1});

// Printing output
console.log(JSON.stringify(res));
```

**输出：**

```json
{"kept":false,"isDisposedInternal":false,"shape":[],
"dtype":"float32","size":1,"strides":[],"dataId":{"id":7097},
"id":4731,"rankType":"0","scopeId":4352}
```

**参考：** [https://js.tensorflow.org/api/latest/#tf.Sequential.evaluateDataset](https://js.tensorflow.org/api/latest/#tf.Sequential.evaluateDataset)