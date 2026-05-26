# TensorFlow.js `tf.GraphModel` 类 `execute()` 方法

> 原文：`https://www.geeksforgeeks.org/tensorflow-js-tf-graphmodel-class-execute-method/`

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`execute()` 方法用于为所述输入张量实现有利于给定模型的蕴涵。

**语法：**

```javascript
execute(inputs, outputs?)
```

**参数：**

*   `inputs`：它是有利于模型的输入的陈述张量或张量阵列或张量图，通过输入节点指定来处理。它属于类型 (`tf.Tensor | tf.Tensor[] | {[name: string]: tf.Tensor}`)。
*   `outputs`：是来自所述 TensorFlow 模型的所述输出节点名称。如果未说明输出，则必须应用所述模型的默认输出。此外，我们可以通过将指定模型的节点附加到输出数组来分析它们之间的关系。它属于 `string` 或 `string[]` 类型。

**返回值：** 返回 `tf.Tensor` 或 `tf.Tensor[]`。

**示例 1：** 在本例中，我们从一个 URL 加载 MobileNetV2。

## 示例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining tensor input elements
const model_Url =
'https://storage.googleapis.com/tfjs-models/savedmodel/mobilenet_v2_1.0_224/model.json';

// Calling the loadGraphModel() method
const mymodel = await tf.loadGraphModel(model_Url);

// Defining inputs
const inputs = tf.zeros([1, 224, 224, 3]);

// Calling execute() method and
// Printing output
mymodel.execute(inputs).print();
```

**输出：**

```javascript
Tensor
     [[-0.1800361, -0.4059965, 0.8190175,
     ...,
     -0.8953396, -1.0841646, 1.2912753],]
```

**示例 2：** 在本例中，我们从 TF Hub URL 加载 MobileNetV2。

## 示例 2

```javascript
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

// Calling execute() method and
// Printing output
mymodel.execute(inputs, outputs).print();
```

**输出：**

```javascript
Tensor
     [[-1.1690605, 0.0195426, 1.1962479,
     ...,
     -0.4825858, -0.0055641, 1.1937635],]
```

**参考：** `https://js.tensorflow.org/api/latest/#tf.GraphModel.execute`