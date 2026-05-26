# tensorflow.js TF.layers.activation()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layers-activation-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-activation-function/)

**简介:** Tensorflow.js 是 Google 开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。`tensorflow.js TF.layers.activation()`函数用于将函数应用于我们输入层的所有元素。我们还可以将函数应用于具有密集层的输入数据。

**语法:**
```
tf.layers.activation(args);    
```

**参数:** 以下是该函数接受的参数:
*   **Parameter:** 是一个对象类型的参数，包含以下字段：
    *   **activation:** 是应用于所有输入元素的函数名称。
    *   **inputShape:** 是模型输入层的形状。用于创建输入层。
    *   **batchInputShape:** 用于创建输入层。它定义了输入层中样本的批次形状。
    *   **batchSize:** 用于创建输入层。它是输入层结构中`batchInputShape`的补充。
    *   **dtype:** 定义层的数据类型。用于模型的第一层。
    *   **name:** 声明一个字符串，即输入层的名称。
    *   **trainable:** 声明一个层是否可以通过函数进行训练。它是一个布尔数据类型。
    *   **weights:** 是一个张量，也是层的初始数据。
    *   **inputType:** 是层中输入数据的数据类型。

**返回:** 激活层。

下面是这个函数的一些例子:

**示例 1:** 在本例中，我们将制作激活层并检查返回值。

## Javascript
```
import * as tf from "@tensorflow/tfjs"

// Creating config for the activation layer
const config = {
    activation: 'sigmoid',
    inputShape: 5,
    dtype: 'int32',
    name: 'activationLayer'
};

// Defining the activation layer
const activationLayer = tf.layers.activation(config);

// printing return of activation layer
console.log(activationLayer);
```

**输出:**
```
{
  "_callHook": null,
  "_addedWeightNames": [],
  "_stateful": false,
  "id": 38,
  "activityRegularizer": null,
  "inputSpec": null,
  "supportsMasking": true,
  "_trainableWeights": [],
  "_nonTrainableWeights": [],
  "_losses": [],
  "_updates": [],
  "_built": false,
  "inboundNodes": [],
  "outboundNodes": [],
  "name": "ActivationLayer",
  "trainable_": true,
  "initialWeights": null,
  "_refCount": null,
  "fastWeightInitDuringBuild": false,
  "activation": {}
}
```

**示例 2:** 在本例中，我们将使用一些配置创建我们的激活层，并使用激活层训练我们的输入数据。

## Javascript
```
import * as tf from "@tensorflow/tfjs"

// Configuration file for the activation layer
const geek_config = {
    activation: 'sigmoid',
    inputShape: 5,
    dtype: 'int32',
    name: 'activationLayer'
};

const geek_activation = tf.layers.activation(geek_config);
const geek_inputLayer = tf.layers.dense({units: 1});

// Our Input layer for the model
const geek_input = tf.input({shape: [7]});

// Making structure for the model
const geek_output = geek_inputLayer.apply(geek_input);
const geek_result = geek_activation.apply(geek_output);

// Making Model from structure 
const config2 = {inputs: geek_input, outputs: geek_result}
const model = tf.model(config2);

// Collect both outputs and print separately.
const config3 = tf.randomUniform([4, 7])
const geek_activationResult = model.predict(config3);
geek_activationResult.print();
```

**输出:**
```
Tensor
    [[0.4178988],
     [0.2027801],
     [0.2813435],
     [0.2546847]]
```

**参考:** [https://js.tensorflow.org/api/latest/#layers.activation](https://js.tensorflow.org/api/latest/#layers.activation)