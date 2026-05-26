# TensorFlow.js `tf.LayersModel` 类 `trainOnBatch()` 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-trainonbatch-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-trainonbatch-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`trainOnBatch()` 函数用于对特定批次的数据运行单独的梯度更新。

**注：** 该方法与 `fit()` 以及 `fitDataset()` 的不同之处在于：
*   此方法绝对适用于单个批次的数据。
*   此方法仅返回损失和度量值，而不是逐批返回。
*   此方法不支持诸如详细程度和回调之类的细粒度选项。

**语法：**
```
trainOnBatch(x, y)
```

**参数：**
*   `x`：输入数据。可以是 `tf.Tensor`、`tf.Tensor[]` 或 `{[inputName: string]: tf.Tensor}`。可以是以下任何一种：
    1.  `tf.Tensor`，或者如果模型有多个输入，则是 `tf.Tensor` 数组。
    2.  如果模型有命名输入，则是将输入名称映射到相应 `tf.Tensor` 的对象。
*   `y`：目标数据。可以是 `tf.Tensor`、`tf.Tensor[]` 或 `{[inputName: string]: tf.Tensor}`。它必须与 `x` 保持相同的相对结构。

**返回值：** 返回一个 `number` 或 `number[]` 的承诺。

**例 1：**

## JavaScript
```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Training Model
const mymodel = tf.sequential(
     {layers: [tf.layers.dense({units: 2, inputShape: [2]})]});

// Compiling our model
const config = {optimizer:'sgd',
           loss:'meanSquaredError'};
mymodel.compile(config);

// Test tensor and target tensor
const xs = tf.ones([3,2]);
const ys = tf.ones([3,2]);

// Calling trainOnBatch() method
const result = await mymodel.trainOnBatch(xs, ys);

// Printing output
console.log(result);
```

**输出：**
```
2.0696773529052734
```

**例 2：**

## JavaScript
```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

async function run() {

// Training Model
  const mymodel = tf.sequential(
     {layers: [tf.layers.dense({units: 2, inputShape: [2], 
                                activation: 'sigmoid'})]});

// Compiling our model
  const config = {optimizer:'sgd',
           loss:'meanSquaredError'};
  mymodel.compile(config);

// Test tensor and target tensor
  const xs = tf.truncatedNormal([3,2]);
  const ys = tf.randomNormal([3,2]);

// Calling trainOnBatch() method
  const result = await mymodel.trainOnBatch(xs, ys);

// Printing output
  console.log(JSON.stringify(+result));
}

// Function call
await run();
```

**输出：**
```
0.5935208797454834
```

**参考：** [https://js.tensorflow.org/api/latest/#tf.LayersModel.trainOnBatch](https://js.tensorflow.org/api/latest/#tf.LayersModel.trainOnBatch)