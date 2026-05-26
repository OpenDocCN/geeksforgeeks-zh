# TensorFlow.js tf.Sequential 类 trainOnBatch() 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-sequential-class-trainonbatch-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-sequential-class-trainonbatch-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`trainOnBatch()` 函数用于对特定批次的数据运行单独的梯度更新。

**注意：**

该方法从 `fit()` 以及 `fitDataset()` 以下列方式变化：

*   这种方法绝对适用于一批数据。
*   该方法只返回损失和度量值，而不是逐批返回损失和度量值。
*   这种方法不支持像冗长和回调这样的细粒度选项。

**语法：**

```
trainOnBatch(x, y)
```

**参数：**

*   **x:** 输入数据。它可以是 `tf.Tensor`、`tf.Tensor[]` 或 `{[inputName: string]: tf.Tensor}` 类型。它可以是以下任何一种：
    1.  指定的 `tf.Tensor`，或者如果模型有多个输入，则是 `tf.Tensor` 的数组。
    2.  将输入名称绘制到匹配 `tf.Tensor` 的对象，以防模型具有命名输入。
*   **y:** 目标数据。它可以是 `tf.Tensor`、`tf.Tensor[]` 或 `{[inputName: string]: tf.Tensor}` 类型。它必须相对于 `x` 是常量。

**返回值：** 返回一个 `number` 或 `number[]` 的承诺。

**示例 1：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Training Model 
const gfg = tf.sequential();

// Adding layer to model  
const layer = tf.layers.dense({units:3, 
               inputShape : [5]});
   gfg.add(layer);

// Compiling our model 
const config = {optimizer:'sgd', 
               loss:'meanSquaredError'};
  gfg.compile(config);

// Test tensor and target tensor
const xs = tf.ones([3, 5]);
const ys = tf.ones([3, 3]);

// Calling trainOnBatch() method
const result = await gfg.trainOnBatch(xs, ys);

// Printing output
console.log(result);
```

**输出：**

```
0.3589147925376892
```

**示例 2：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

async function run() {

// Training Model 
  const gfg = tf.sequential();

// Adding layer to model  
  const layer = tf.layers.dense({units:2, 
               inputShape : [2]});
  gfg.add(layer);

// Compiling our model 
  const config = {optimizer:'sgd', 
               loss:'meanSquaredError'};
  gfg.compile(config);

// Test tensor and target tensor
  const xs = tf.truncatedNormal([3, 2]);
  const ys = tf.randomNormal([3, 2]);

// Calling trainOnBatch() method
  const result = await gfg.trainOnBatch(xs, ys);

// Printing output
  console.log(JSON.stringify(+result));
}

// Function call
await run();
```

**输出：**

```
1.6889342069625854
```

**参考：** [https://js.tensorflow.org/api/latest/#tf.Sequential.trainOnBatch](https://js.tensorflow.org/api/latest/#tf.Sequential.trainOnBatch)