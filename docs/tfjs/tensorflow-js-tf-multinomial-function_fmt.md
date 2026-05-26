# TensorFlow.js tf.multinomial() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-multinomial-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-multinomial-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`tf.multinomial()` 函数用于生成一个 `tf.Tensor`，其中的值是从多项式分布中抽取的。

## 语法

```
tf.multinomial(logits, numSamples, seed?, normalized?)
```

## 参数

*   `logits`: 它是一个未归一化的对数概率的 1D 数组，或者是一个形状为 `[batchSize, numOutcomes]` 的 2D 数组。它可以是 `tf.Tensor1D`、`tf.Tensor2D`、`TypedArray` 或普通数组。
*   `numSamples`: 是为每个行（batch）抽取的样本数量。它是数字类型。
*   `seed`: 是用于随机数生成的种子值，是可选的数字类型参数。
*   `normalized`: 它检查给定的 `logits` 是否已经是真正的概率（即总和为 1）。默认值为 `false`，是可选的布尔类型参数。

## 返回值

返回 `tf.Tensor1D` 或 `tf.Tensor2D`。

## 示例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining logits
const logits = tf.tensor([35, 158]);

// Calling tf.multinomial() method and
// Printing output
tf.multinomial(logits, 4).print();
```

**输出:**

```
Tensor
    [1, 1, 1, 1]
```

## 示例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling tf.multinomial() method and
// Printing output
tf.multinomial(tf.tensor(
  [5.7, 8.7, NaN, 'a', null, 0]), 6).print();
```

**输出:**

```
Tensor
    [5, 5, 5, 5, 5, 5]
```

**参考:** [https://js.tensorflow.org/api/latest/#multinomial](https://js.tensorflow.org/api/latest/#multinomial)