# TensorFlow.js TF.initializer.constant()方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-constant-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-constant-method/)

TensorFlow.js 中的初始值设定项用于初始化内核、权重和基础的初始值。`tf.initializers.constant()` 是从 `Initializer` 基类继承的初始值设定项函数。该函数用于生成初始化为某个常数的值。在这篇文章中，我们将了解 TensorFlow.js 中的 `tf.initializers.constant()` 函数。

## 语法

```
tf.initializers.constant(args)
```

## 参数

`args` 对象包含以下属性。

*   `value`：变量中每个元素的值。

## 返回值

返回 `tf.initializers.Initializer`。

## 示例 1

在本例中，我们将看到 `tf.initializers.constant()` 函数的独立使用。

### JavaScript

```
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs")

// Use  tf.initializers.constant() function
var initializer = tf.initializers.constant({ value: 7, })

// Print the value of constant
console.log(initializer);
```

**输出：**

```
Constant { value: 7 }
```

## 示例 2

在本例中，我们将在模型创建中使用 `constant()` 函数来初始化内核。

### JavaScript

```
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs")

// Using tf.initializers.constant() function
var initializer = tf.initializers.constant({ value: 7, })

// Create model
const model = tf.sequential();

// Add layer and initialize the kernel
model.add(tf.layers.dense({
    units: 3,
    activation: 'softmax',
    kernelInitializer: initializer,
    inputShape: [2]
}));

// Print the summary
model.summary();
```

**输出：**

```
Layer (type)                 Output shape              Param #   
=================================================================
dense_Dense1 (Dense)         [null,3]                  9
=================================================================
Total params: 9
Trainable params: 9
Non-trainable params: 0
_________________________________________________________________
```

**参考：** [https://js.tensorflow.org/api/latest/#initializers.constant](https://js.tensorflow.org/api/latest/#initializers.constant)