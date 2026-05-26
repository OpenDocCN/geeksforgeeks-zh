# TensorFlow.js `tf.layers.dropout()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layers-dropout-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-dropout-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node 环境中运行机器学习模型和深度学习神经网络。

`tf.layers.dropout()` 函数是 `TensorFlow.js` 库的内置函数。该函数用于防止模型中的过拟合，方法是在训练期间每次更新时，随机将输入单位的分数设置为 0。

## 语法

```
tf.layers.dropout( {rate} )
```

## 参数

*   **参数:** 给定对象作为参数。
*   **rate:** 指定要下降的输入单位的分数。它的值介于 0 和 1 之间。
*   **noiseShape:** 整数列表，表示将与输入相乘的缺失形状。这是一个可选参数。
*   **seed:** 指定随机种子。这是一个可选参数。
*   **inputShape:** 如果定义了该参数，它将创建另一个输入层插入到该层之前。
*   **batchInputShape:** 如果定义了这个参数，它会创建另一个输入图层，插入到这个图层之前。
*   **batchSize:** 用于构造 `batchInputShape`，如果尚未指定。
*   **dtype:** 指定该图层的数据类型。此参数的默认值为 `"float32"`。
*   **name:** 指定该图层的名称。
*   **trainable:** 指定是否通过拟合更新该层的权重。
*   **weights:** 指定图层的初始权重值。
*   **inputType:** 用于表示输入类型，其值可以是 `"float32"` 或 `"int32"` 或 `"bool"` 或 `"complex64"` 或 `"string"`。

## 返回值

返回压差层。

## 示例 1

我们将创建一个新模型，并在其中添加脱落层。

### JavaScript

```javascript
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs");

// Define the model
const model = tf.sequential({
    layers: [tf.layers.dense({ 
        units: 1, inputShape: [10] 
    })],
});

// Add dropout to model
model.add(tf.layers.dropout({ rate: 0.25 }));

// Compile the model
model.compile(
    { optimizer: "sgd", loss: "meanAbsoluteError" },
    (metrics = ["accuracy"])
);

// Evaluate the model
const result = model.evaluate(
    tf.ones([8, 10]), tf.ones([8, 1]), {
    batchSize: 4,
});

// Print the resulting tensor
result.print();
```

**输出:**

```
Tensor
    1.608272910118103
```

## 示例 2

### JavaScript

```javascript
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs");

// Define the model
const model = tf.sequential({
    layers: [tf.layers.dense({ 
        units: 1, inputShape: [10] 
    })],
});

// Add dropout to model
model.add(tf.layers.dropout({ rate: 0.5 }));

// Compile the model
model.compile({ optimizer: "adam", 
    loss: "meanSquaredError" });

// Evaluate the model
const result = model.evaluate(
    tf.ones([8, 10]), tf.ones([8, 1]), {
    batchSize: 2,
});

// Print the result
result.print();
```

**输出:**

```
Tensor
    0.9941154718399048
```

**参考:** [https://js.tensorflow.org/api/latest/#layers.dropout](https://js.tensorflow.org/api/latest/#layers.dropout)