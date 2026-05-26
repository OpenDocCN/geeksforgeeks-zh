# TensorFlow.js tf.LayersModel类的evaluate()方法

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-evaluate-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-evaluate-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`evaluate()`函数用于在测试方法中找到有利于原型的损失度量和度量值。

**注意:**

*   这里的损失值和度量是在编译时确定的，也就是说，需要在调用 `evaluate()` 方法之前完成。
*   这里的枚举是按批次进行的。

## 语法

```
evaluate(x, y, args?)
```

## 参数

*   `x`: 是规定的测试材料的 `tf.Tensor`，或者如果原型有不同输入，则是 `tf.Tensor` 数组。它可以是 `tf.Tensor` 类型或 `tf.Tensor[]`。
*   `y`: 是规定的对象的 `tf.Tensor`，或者如果原型有不同输入，则是 `tf.Tensor` 数组。它可以是 `tf.Tensor` 类型或 `tf.Tensor[]`。
*   `args`: 是一个可选的 `ModelEvaluateArgs` 对象。
    *   `batchSize`: 是指定的批次大小；如果未定义，默认值为 32。数值类型。
    *   `verbose`: 是报告详细程度的模式。`ModelVerbose` 类型。
    *   `sampleWeight`: 是上述的权重张量，用于为各种情况对损失和度量的影响加权。`tf.Tensor` 类型。
    *   `steps`: 是评估轮次终止前的总步数，即实例组。如果未指定则被忽略，默认值为未指定。数值类型。

## 返回值

返回 `tf.Scalar` 或 `tf.Scalar[]`。

## 示例 1

使用优化器作为 `'sgd'`，使用损失作为 `'meanAbsoluteError'`。

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining model
const modl = tf.sequential({
   layers: [tf.layers.dense({units: 2, inputShape: [30]})]
});

// Compiling model
modl.compile({optimizer: 'sgd', loss: 'meanAbsoluteError'});

// Calling evaluate() and randomNormal
// method
const output = modl.evaluate(
     tf.randomNormal([8, 30]), 
     tf.randomNormal([8, 2]), 
     {batchSize: 3}
);

// Printing output
output.print();
```

**输出:** 这里，使用 `randomNormal()` 方法作为张量输入。

```
Tensor
    1.1059763431549072
```

## 示例 2

使用优化器作为 `'adam'`，使用损失作为 `'meanSquaredError'`，使用 `'accuracy'` 作为度量。

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining model
const modl = tf.sequential({
   layers: [tf.layers.dense({units: 1, inputShape: [20]})]
});

// Compiling model
modl.compile({optimizer: 'adam', loss: 'meanSquaredError'}, 
             (metrics = ["accuracy"]));

// Calling evaluate() and truncatedNormal
// method
const output = modl.evaluate(
     tf.truncatedNormal([8, 20]), tf.truncatedNormal([8, 1]), 
      {batchSize: 3}, {steps: 2});

// Printing output
output.print();
```

**输出:** 这里，使用 `truncatedNormal()` 方法作为张量输入，还包括 `steps` 参数。

```
Tensor
    1.2484867572784424
```

**参考:** [https://js.tensorflow.org/api/latest/#tf.LayersModel.evaluate](https://js.tensorflow.org/api/latest/#tf.LayersModel.evaluate)