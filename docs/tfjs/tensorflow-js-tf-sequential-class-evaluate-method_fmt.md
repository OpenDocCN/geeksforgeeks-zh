# TensorFlow.js tf.Sequential类.evaluate()方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-sequential-class-evaluate-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-sequential-class-evaluate-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`.evaluate()`函数用于在测试方法中找到有利于原型的损失度量和度量值。

**注意：**

*   这里，损失值和度量是在编译时确定的，也就是说，需要在调用 `.evaluate()` 方法之前完成。
*   这里的枚举是分组进行的。

**语法：**

```
evaluate(x, y, args?)
```

**参数：**

*   `x`：是规定的测试材料的 `tf.Tensor`，或者在原型具有不同输入时是 `tf.Tensor` 的数组。它可以是 `tf.Tensor` 或 `tf.Tensor[]` 类型。
*   `y`：是规定的对象的 `tf.Tensor`，或者在原型具有不同输出时是 `tf.Tensor` 的数组。它可以是 `tf.Tensor` 或 `tf.Tensor[]` 类型。
*   `args`：是 `ModelEvaluateArgs` 的可选字段。它是一个对象。
    *   `batch size`：是指定的批处理大小；如果未定义，则默认值为 32。它是数值类型。
    *   `detail`：是报告详细程度的模式。类型为 `model detail`。
    *   `sample weight`：是上面提到的权重张量，用于对各种情况对损失和度量的影响进行加权。它是 `tf.tensor` 类型。
    *   `steps`：是在声明评估轮次终止之前的总步数，即实例组。它被忽略，默认值为未指定。它是数值类型。

**返回值：** 返回 `tf.Scalar` 或 `tf.Scalar[]`。

**示例 1：** 使用优化器作为 `'sgd'`，使用损失作为 `'meanAbsoluteError'`。

## JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining model
const modl = tf.sequential({
   layers: [tf.layers.dense({units: 3, inputShape: [40]})]
});

// Compiling model
modl.compile({optimizer: 'sgd', loss: 'meanAbsoluteError'});

// Calling evaluate() and randomNormal
// method
const output = modl.evaluate(
    tf.randomNormal([5, 40]), 
    tf.randomNormal([5, 3]), 
    {Sizeofbatch: 3}
);

// Printing output
output.print();
```

**输出：**

```
Tensor
    1.554270625114441
```

这里使用 `randomNormal()` 方法作为张量输入。

**示例 2：** 使用优化器作为 `'adam'`，使用损失作为 `'meanSquaredError'` 和 `'accuracy'` 作为度量。

## JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining model
const modl = tf.sequential({
   layers: [tf.layers.dense({units: 2, inputShape: [30]})]
});

// Compiling model
modl.compile({optimizer: 'adam', loss: 'meanSquaredError'}, 
             (metrics = ["accuracy"]));

// Calling evaluate() and truncatedNormal
// method
const output = modl.evaluate(
     tf.truncatedNormal([6, 30]), tf.truncatedNormal([6, 2]), 
      {Sizeofbatch: 2}, {steps: 2});

// Printing output
output.print();
```

**输出：**

```
Tensor
    2.7340292930603027
```

这里，`truncatedNormal()` 方法用作张量输入，并且还包括步长参数。

**参考：** [https://js.tensorflow.org/api/latest/#tf.Sequential.evaluate](https://js.tensorflow.org/api/latest/#tf.Sequential.evaluate)