# TensorFlow.js TF.initializer.leCunUniform()函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-lecununiform-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-lecununiform-function/)

`TensorFlow.js` 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

`TF.initializer.leCunUniform()` 函数从间隔 `[-cap, cap]` 中的均匀分布中获取样本，`cap = sqrt(3 / fanIn)`。请注意，`fanIn` 是张量权重中的输入数量。

**语法：**

```
tf.initializers.leCunUniform(arguments)
```

**参数：**

*   `arguments`：它是一个包含种子（一个数）的对象，种子是随机数生成器种子/数。

**返回值：** 返回一个初始化器对象。

## 例 1

### JavaScript

```
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Initialising the .initializers.leCunUniform() function
console.log(tf.initializers.leCunUniform(4));

// Printing individual values from the gain
console.log("\nIndividual Values\n");
console.log(tf.initializers.leCunUniform(4).scale);
console.log(tf.initializers.leCunUniform(4).mode);
console.log(tf.initializers.leCunUniform(4).distribution);
```

**输出：**

```
{
  "scale": 1,
  "mode": "fanIn",
  "distribution": "uniform"
}

Individual Values

1
fanIn
uniform
```

## 例 2

### JavaScript

```
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Defining the input value
let inputValue = tf.input({ shape: [4] });

// Initializing tf.initializers.leCunUniform() function
let funcValue = tf.initializers.leCunUniform(6)

// Creating dense layer 1
let dense_layer_1 = tf.layers.dense({
    units: 3,
    activation: 'relu',
    kernelInitialize: funcValue
});

// Creating dense layer 2
let dense_layer_2 = tf.layers.dense({
    units: 6,
    activation: 'softmax'
});

// Output Value
let outputValue = dense_layer_2.apply(
    dense_layer_1.apply(inputValue)
);

// Creation the model
let model = tf.model({
    inputs: inputValue,
    outputs: outputValue
});

// Predicting the output
let finalOutput = model.predict(tf.ones([2, 4]));
finalOutput.print();
```

**输出：**

```
Tensor
    [[0.1853671, 0.1406064, 0.1505066, 0.1183221, 0.2430924, 0.1621054],
     [0.1853671, 0.1406064, 0.1505066, 0.1183221, 0.2430924, 0.1621054]]
```

**参考：** [https://js.tensorflow.org/api/latest/#initializers.leCunUniform](https://js.tensorflow.org/api/latest/#initializers.leCunUniform)