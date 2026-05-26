# TensorFlow.js `tf.layers.embedding()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layers-embedding-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-embedding-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.layers.embedding()` 函数用于将正整数映射为固定大小的密集向量。

## 语法

```
tf.layers.embedding(args)
```

## 参数

该函数接受 `args` 作为参数，该参数可以具有以下属性：

*   `inputDim`: 用于指定词汇量大小。
*   `outputDim`: 用于指定密集嵌入的维度。
*   `embeddingsInitializer`: 用于指定嵌入矩阵的初始化器。
*   `embeddingsRegularizer`: 用于指定哪个正则化函数应用于嵌入矩阵。
*   `activityRegularizer`: 用于指定哪个正则化函数应用于激活。
*   `embeddingsConstraint`: 用于指定哪个约束函数应用于嵌入矩阵。
*   `maskZero`: 用于检查输入值 0 是否为特殊的填充值。
*   `inputLength`: 用于指定输入序列的长度。
*   `inputShape`: 用于创建一个输入图层插入到该图层之前。
*   `batchInputShape`: 用于创建一个输入图层插入到该图层之前。
*   `batchSize`: 如果指定了 `inputShape`，但没有指定 `batchInputShape`，则用于构造 `batchInputShape`。
*   `dtype`: 用于表示该层的数据类型。
*   `name`: 用于表示该层的名称。
*   `trainable`: 用于指示该层的权重是否可通过拟合更新。
*   `weights`: 用于表示图层的初始权重值。
*   `inputType`: 只是为了遗留支持，不用于新代码。

## 返回值

返回嵌入层。

## 示例 1

```javascript
// Import library
import * as tf from "@tensorflow/tfjs"

// Create embedding layer
const embeddingLayer = tf.layers.embedding({
   inputDim: 10,
   outputDim: 3,
   inputLength: 2
});

const input = tf.ones([2, 2]);

// Apply embedding to input 
const output = embeddingLayer.apply(input);

// Print the output
console.log(output)
```

**输出:**

```
Tensor
    [[[0.0179072, 0.0069226, 0.0202718],
      [0.0179072, 0.0069226, 0.0202718]],

     [[0.0179072, 0.0069226, 0.0202718],
      [0.0179072, 0.0069226, 0.0202718]]]
```

## 示例 2

```javascript
// Import the library
import * as tf from "@tensorflow/tfjs"

// Create embedding layer
const embeddingLayer = tf.layers.embedding({
   inputDim: 100,
   outputDim: 4,
   inputLength: 3
});

const input = tf.ones([3, 3]);

// Apply embedding to input
const output = embeddingLayer.apply(input);

// Print the output
console.log(output)
```

**输出:**

```
Tensor
    [[[0.0443502, -0.0342815, 0.0228792, 0.0198386],
      [0.0443502, -0.0342815, 0.0228792, 0.0198386],
      [0.0443502, -0.0342815, 0.0228792, 0.0198386]],

     [[0.0443502, -0.0342815, 0.0228792, 0.0198386],
      [0.0443502, -0.0342815, 0.0228792, 0.0198386],
      [0.0443502, -0.0342815, 0.0228792, 0.0198386]],

     [[0.0443502, -0.0342815, 0.0228792, 0.0198386],
      [0.0443502, -0.0342815, 0.0228792, 0.0198386],
      [0.0443502, -0.0342815, 0.0228792, 0.0198386]]]
```

**参考:** [https://js.tensorflow.org/api/latest/#layers.embedding](https://js.tensorflow.org/api/latest/#layers.embedding)