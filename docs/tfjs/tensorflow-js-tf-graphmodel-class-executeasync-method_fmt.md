# TensorFlow.js tf.GraphModel 类的 executeAsync() 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-graphmodel-class-executeasync-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-graphmodel-class-executeasync-method/)

Tensorflow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`executeAsync()` 函数用于以异步方式为所述输入张量实现有利于给定模型的隐含。此外，如果您的模型包含流操作，您可以使用这种方法。

## 语法

```
executeAsync(inputs, outputs?)
```

## 参数

*   `inputs`：它是有利于模型的输入的陈述张量或张量阵列或张量图，通过输入节点指定来处理。它属于类型 `tf.Tensor | tf.Tensor[] | {[name: string]: tf.Tensor}`。
*   `outputs`：是来自所述张量流模型的所述输出节点名称。如果未说明输出，则必须应用所述模型的默认输出。此外，我们可以通过将指定模型的中间节点附加到输出数组来分析它们。它属于 `string` 或 `string[]` 类型。

## 返回值

返回 `tf.Tensor` 或 `tf.Tensor[]` 的承诺。

## 示例 1

在本例中，我们从一个 URL 加载 MobileNetV2。

### Javascript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining tensor input elements
const model_Url =
'https://storage.googleapis.com/tfjs-models/savedmodel/mobilenet_v2_1.0_224/model.json';

// Calling the loadGraphModel() method
const mymodel = await tf.loadGraphModel(model_Url);

// Defining inputs
const inputs = tf.zeros([1, 224, 224, 3]);

// Calling executeAsync() method
const res = await mymodel.executeAsync(inputs);

// Printing output
console.log(res);
```

### 输出

```
Tensor
     [[-0.1800361, -0.4059965, 0.8190175, 
     ..., 
     -0.8953396, -1.0841646, 1.2912753],]
```

## 示例 2

在本例中，我们从 TF Hub URL 加载 MobileNetV2。

### Javascript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining tensor input elements
const model_Url =
'https://tfhub.dev/google/imagenet/mobilenet_v2_140_224/classification/2';

// Calling the loadGraphModel() method
const mymodel = await tf.loadGraphModel(
        model_Url, {fromTFHub: true});

// Defining inputs
const inputs = tf.zeros([1, 224, 224, 3]);

// Defining outputs
const outputs = "module_apply_default/MobilenetV2/Logits/output";

// Calling executeAsync() method
const res = await mymodel.executeAsync(inputs, outputs);

// Printing output
console.log(res);
```

### 输出

```
Tensor
     [[-1.1690605, 0.0195426, 1.1962479, 
     ..., 
     -0.4825858, -0.0055641, 1.1937635],]
```

## 参考

[https://js.tensorflow.org/api/latest/#tf.GraphModel.executeAsync](https://js.tensorflow.org/api/latest/#tf.GraphModel.executeAsync)