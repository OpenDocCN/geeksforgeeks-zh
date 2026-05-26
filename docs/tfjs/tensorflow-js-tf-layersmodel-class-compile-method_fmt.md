# TensorFlow.js tf.LayersModel.compile()方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-compile-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-compile-method/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node 环境中运行机器学习模型和深度学习神经网络。

`.compile()` 方法用于配置模型，为其训练和评估过程做准备。通过调用 `.compile()` 函数，我们为模型配置优化器、损失函数和度量标准。该函数接受一个参数对象。

**注意：** 如果在未编译的模型上调用 `.fit()` 或 `.evaluate()` 函数，程序将抛出错误。

## 语法

```javascript
model.compile({optimizer, loss, metrics})
```

## 参数

*   **optimizer**：必选参数。接受 `tf.train.Optimizer` 对象或优化器的字符串名称。以下是优化器的字符串名称：`"sgd"`、`"adam"`、`"adamax"`、`"adadelta"`、`"adagrad"`、`"rmsprop"`。
*   **loss**：必选参数。接受表示损失类型的字符串值或字符串数组。如果模型有多个输出，可以通过传递损失函数数组来为每个输出使用不同的损失。模型将最小化的总损失值是所有单个损失的总和。以下是损失函数的字符串名称：`"meanSquaredError"`、`"meanAbsoluteError"`、`"categoricalCrossentropy"` 等。
*   **metrics**：可选参数。接受模型在训练和测试阶段评估的度量指标列表。通常，我们使用 `metrics = ['accuracy']`。为了为多输出模型的不同输出指定不同的度量指标，也可以传递一个字典。

## 返回值

由于此方法是为训练准备模型，因此不返回任何内容（即返回类型为 `void`）。

## 示例 1

在本例中，我们将创建一个简单的模型，并传递 `optimizer` 和 `loss` 参数的值。这里我们使用 `"adam"` 作为优化器，`"meanSquaredError"` 作为损失函数。

```javascript
// 导入 tensorflow.js 库
const tf = require("@tensorflow/tfjs");

// 定义模型
const model = tf.sequential({
    layers: [tf.layers.dense({ units: 1, inputShape: [10] })],
});

// 编译模型
// 使用 "adam" 优化器和 "meanSquaredError" 损失函数
model.compile({ optimizer: "adam", loss: "meanSquaredError" });

// 评估上面编译的模型
// 计算以批次大小为 4 进行
const result = model.evaluate(tf.ones([8, 10]), tf.ones([8, 1]), {
    batchSize: 4,
});

// 打印结果
result.print();
```

**输出：**

```
Tensor
    2.6806342601776123
```

## 示例 2

在本例中，我们将创建一个简单的模型，并传递 `optimizer`、`loss` 和 `metrics` 参数的值。这里我们使用 `"sgd"` 作为优化器，`"meanAbsoluteError"` 作为损失函数，`"accuracy"` 作为度量指标。

```javascript
// 导入 tensorflow.js 库
const tf = require("@tensorflow/tfjs");

// 定义模型
const model = tf.sequential({
    layers: [tf.layers.dense({ units: 1, inputShape: [10] })],
});

// 编译模型
// 使用 "sgd" 优化器、"meanAbsoluteError" 损失函数和 "accuracy" 度量指标
model.compile(
    { optimizer: "sgd", loss: "meanAbsoluteError" },
    (metrics = ["accuracy"])
);

// 评估上面编译的模型
// 计算以批次大小为 4 进行
const result = model.evaluate(tf.ones([8, 10]), tf.ones([8, 1]), {
    batchSize: 4,
});

// 打印结果
result.print();
```

**输出：**

```
Tensor
    1.4847172498703003
```

## 示例 3

在本例中，我们将创建一个简单的模型，并传递 `optimizer`、`loss` 和 `metrics` 参数的值。这里我们使用 `"sgd"` 作为优化器，`"meanAbsoluteError"` 作为损失函数，`"precision"` 作为度量指标。

```javascript
// 导入 tensorflow.js 库
const tf = require("@tensorflow/tfjs");

// 定义模型
const model = tf.sequential({
    layers: [tf.layers.dense({ units: 1, inputShape: [10] })],
});

// 编译模型
// 使用 "sgd" 优化器、"meanAbsoluteError" 损失函数和 "precision" 度量指标
model.compile(
    { optimizer: "sgd", loss: "meanAbsoluteError" },
    (metrics = ["precision"])
);

// 评估上面编译的模型
// 计算以批次大小为 4 进行
const result = model.evaluate(tf.ones([8, 10]), tf.ones([8, 1]), {
    batchSize: 4,
});

// 打印结果
result.print();
```

**输出：**

```
Tensor
   1.507279634475708
```

**参考：** [https://js.tensorflow.org/api/latest/#tf.LayersModel.compile](https://js.tensorflow.org/api/latest/#tf.LayersModel.compile)