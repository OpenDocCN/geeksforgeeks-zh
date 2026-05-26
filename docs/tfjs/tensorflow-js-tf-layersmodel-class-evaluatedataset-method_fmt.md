# TensorFlow.js tf.LayersModel 类 evaluateDataset() 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-evaluatedataset-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-evaluatedataset-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`evaluateDataset()` 函数用于通过指定的数据集对象来评估指定的模型。

**注意：** 此方法与 `evaluate()` 不同，因为它是异步的。

## 语法

```
evaluateDataset(dataset, args?)
```

## 参数

*   `dataset`：数据集对象。为了生成数据集迭代器对象，你需要调用其 `iterator()` 方法，然后调用其 `next()` 方法来生成一个用于计算的数据批次。此外，`next()` 调用的返回值必须包含一个布尔型的 `done` 字段和一个 `value` 字段。`value` 字段可以是一个由两个 `tf.Tensor` 组成的数组，或一个由两个嵌套的 `tf.Tensor` 组成的数组。第一种情况适用于只有一个输入和一个输出的模型，即序贯模型。后者适用于具有多个输入和/或多个输出的模型。数组中的两个元素，第一个是输入特征，第二个是输出目标。其类型为 `tf.data.Dataset`。
*   `args`：描述在 **支持基于数据集的评估** 中提到的配置对象。它是可选的，属于对象类型。包含以下参数：
    1.  `batch`：在终止评估之前，从给定的数据集对象中拖出的指定批次数。其类型为数值型。
    2.  `verbose`：声明详细模式。类型为 `model detail`。

## 返回值

返回一个 `tf.Scalar` 或 `tf.Scalar[]` 的承诺（Promise）。

## 例 1

### JavaScript

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

// Defining model
const mymodel = tf.sequential({
   layers: [tf.layers.dense({units: 1, inputShape: [8]})]
});

// Compiling model
mymodel.compile({optimizer: 'sgd', loss: 'meanSquaredError'});

// Calling evaluateDataset() method
const res = await mymodel.evaluateDataset(Dataset_xy, 
tf.ones([7, 10]), tf.ones([7, 1]), {
   batchSize: 5,
});

// Printing output
res.print();
```

### 输出

```
Tensor
    0.9196577668190002
```

## 例 2

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining dataset of xy using zip method
const Dataset_xy = tf.data.zip({
    xs: tf.data.array([[1, 0, 1, 2, 1]]), 
    ys: tf.data.array([1, 2, 1, 3])})
    .batch(8);

// Defining model
const mymodel = tf.sequential({
   layers: [tf.layers.dense(
      {units: 1, inputShape: [5], activation: 'sigmoid'})
   ]
});

// Compiling model
mymodel.compile({optimizer: 'sgd', loss: 'meanSquaredError'});

// Calling evaluateDataset() method
const res = await mymodel.evaluateDataset(
    Dataset_xy, tf.truncatedNormal([7, 10]), 
        tf.randomNormal([7, 1]), 
        {batchSize: 2, steps: 1}
    );

// Printing output
console.log(JSON.stringify(res));
```

### 输出

```
{"kept":false,"isDisposedInternal":false,"shape":[],"dtype":"float32",
"size":1,"strides":[],"dataId":{"id":6923},"id":4594,
"rankType":"0","scopeId":4223}
```

## 参考

[https://js.tensorflow.org/api/latest/#tf.LayersModel.evaluateDataset](https://js.tensorflow.org/api/latest/#tf.LayersModel.evaluateDataset)