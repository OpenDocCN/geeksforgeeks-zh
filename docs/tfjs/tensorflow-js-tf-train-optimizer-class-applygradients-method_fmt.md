# TensorFlow.js TF.train.Optimizer 类的 applyGradients() 方法

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-train-optimizer-class-applygradients-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-train-optimizer-class-applygradients-method/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node 环境中运行机器学习模型和深度学习神经网络。

`tf.train.Optimizer.applyGradients()` 用于通过使用计算的梯度来更新变量。

**语法:**

```
Optimizer.applyGradients( variableGradients );
```

**参数:**

*   `variableGradients({[name:String]:tf.Tensor} | NamedTensorMap)`: 变量名到其梯度值的映射。

**返回:** `void`

**示例 1:** 在本例中，我们将借助默认优化器的 `applyGradients()` 方法更新变量值。

## 示例 1：使用默认优化器

```javascript
// Importing tensorflow
import * as tf from "@tensorflow/tfjs"

const xs = tf.tensor1d([0, 1, 2]);
const ys = tf.tensor1d([1.58, 2.24, 3.41]);

const x = tf.scalar(Math.random()).variable();
const y = tf.scalar(Math.random()).variable();

// Define a function f(x) = x^2 + y.
const f = x => (x.square()).add(y);

const learningRate = 0.05;

// Create adagrad optimizer
const optimizer = tf.train.rmsprop(learningRate);

// Updating variable
const varGradients = f(xs).dataSync();
for (let i = 0; i < 5; i++){
  optimizer.applyGradients(varGradients);
}

// Make predictions.
console.log(`x: ${x.dataSync()}, y: ${y.dataSync()}`);
const preds = f(xs).dataSync();
preds.forEach((pred, i) => {
  console.log(`x: ${i}, pred: ${pred}`);
});
```

**输出:**

```
x: -0.526353657245636, y: 0.15607579052448273
x: 0, pred: 0.15607579052448273
x: 1, pred: 1.1560758352279663
x: 2, pred: 4.156075954437256
```

**示例 2:** 在本例中，我们将借助自定义优化器的 `applyGradients()` 方法更新变量。

## 示例 2：使用自定义优化器

```javascript
// Importing tensorflow
import * as tf from "@tensorflow/tfjs"

const xs = tf.tensor1d([0, 1, 2, 3]);
const ys = tf.tensor1d([1.3, 3.7, 12.4, 26.6]);

// Choosing random coefficients
const a = tf.scalar(Math.random()).variable();
const b = tf.scalar(Math.random()).variable();
const c = tf.scalar(Math.random()).variable();

// Defining function f = (a*x^2 + b*x + c)
const f = x => a.mul(x.mul(3)).add(b.square(x)).add(c);

// Setting configurations for our optimizer
const learningRate = 0.01;
const initialAccumulatorValue = 10;

// Create the Optimizer
const optimizer = tf.train.adagrad(learningRate, initialAccumulatorValue);

// Updating variable
const varGradients = f(xs).dataSync();
for (let i = 0; i < 8; i++){
  optimizer.applyGradients(varGradients)
}

// Make predictions.
console.log(`a: ${a.dataSync()}, b: ${b.dataSync()}, c: ${c.dataSync()}`);
const preds = f(xs).dataSync();
preds.forEach((pred, i) => {
  console.log(`x: ${i}, pred: ${pred}`);
});
```

**输出:**

```
a: 0.032658617943525314, b: 0.9213025569915771, c: 0.7167015671730042
x: 0, pred: 1.565500020980835
x: 1, pred: 1.663475751876831
x: 2, pred: 1.7614517211914062
x: 3, pred: 1.8594274520874023
```

**参考资料:** [https://js.tensorflow.org/api/3.8.0/#tf.train.Optimizer.applyGradients](https://js.tensorflow.org/api/3.8.0/#tf.train.Optimizer.applyGradients)