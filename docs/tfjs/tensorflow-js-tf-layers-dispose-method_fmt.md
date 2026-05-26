# TensorFlow.js TF.Layers dispose() 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-layers-dispose-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-dispose-method/)

TensorFlow.js 是一个由谷歌开发的开源库，用于在浏览器或 Node.js 环境中运行机器学习模型以及深度学习神经网络。

## 功能说明

`dispose()` 方法用于处置（释放）所述层的权重。此外，它会将所述层对象的引用计数减 1。

**注意：**

*   此处，第一层是引用计数。当其 `apply()` 方法首次被调用时，TF.js 会进行对称传感器调用。
*   在 `apply()` 方法上，其引用数会增加 1。当某层的引用数变为零时，它的所有权重都将被处置，并且在基础内存（即 `WebGL`）中分配的纹理也将被清除。
*   当被处置层的引用计数大于零时，该层的权重将不会被处置。
*   最后，当一个层被处置后，它将不能再被调用，例如 `apply()`、`getWeights()` 或 `setWeights()`。

## 语法

```
dispose()
```

## 参数

此方法没有参数。

## 返回值

返回一个处置结果对象。

## 示例 1

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating a model
const model = tf.sequential();

// Adding a layer
model.add(tf.layers.dense({units: 1, inputShape: [3]}));

// Calling dispose method
const val = model.layers[0].dispose();

// Printing output
console.log(val);
```

### 输出

```
{
  "refCountAfterDispose": 0,
  "numDisposedVariables": 2
}
```

## 示例 2

### JavaScript

```javascript
// Importing the tensorflow.js library
//import * as tf from "@tensorflow/tfjs"

// Creating a model
const model = tf.sequential();

// Adding layers
model.add(tf.layers.dense({units: 1, inputShape: [5, 1]}));
model.add(tf.layers.dense({units: 4}));
model.add(tf.layers.dense({units: 2, inputShape: [6], batchSize: 5}));

// Calling dispose() method
const val1 = model.layers[0].dispose();
const val2 = model.layers[1].dispose();
const val3 = model.layers[2].dispose();

// Printing output
console.log(val1);
console.log(val2);
console.log(val3);
```

### 输出

```
{
  "refCountAfterDispose": 0,
  "numDisposedVariables": 2
}
{
  "refCountAfterDispose": 0,
  "numDisposedVariables": 2
}
{
  "refCountAfterDispose": 0,
  "numDisposedVariables": 2
}
```

## 参考

[https://js.tensorflow.org/api/latest/#TF.Layers.Layer.dispose](https://js.tensorflow.org/api/latest/#TF.Layers.Layer.dispose)