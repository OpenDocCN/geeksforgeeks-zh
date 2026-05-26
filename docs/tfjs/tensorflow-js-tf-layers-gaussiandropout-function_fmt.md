# TensorFlow.js `tf.layers.gaussianDropout()` 函数

> 原文: [`https://www.geeksforgeeks.org/tensorflow-js-tf-layers-gaussiandropout-function/`](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-gaussiandropout-function/)

`TensorFlow.js` 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

`tf.layers.gaussianDropout()` 函数用于应用乘法 1 中心高斯噪声。因为它是一个正则化层，所以它只在训练时有效。

```
tf.layers.gaussianDropout(arguments)
```

## 参数

*   `inputShape`: 是一个可选参数，用于创建输入层，接受数字和 `null` 等值。
*   `batchInputShape`: 是一个可选参数，用于在主层之前创建输入层，它等于数字和 `null`。
*   `batchSize`: 是用于构造 `batchInputShape` 的可选参数，它只接受数字。
*   `dtype`: 是一个可选参数，表示数据类型。默认为 `"float32"`，同时也支持 `"int32"` 和 `"bool"` 等值。
*   `name`: 是一个可选参数，用于定义层名称并接受字符串。
*   `trainable`: 是一个可选参数，决定是否更新提供的输入层。它接受布尔值。
*   `weights`: 它具有层的起始权重。它也是一个可选参数。
*   `inputType`: 是用于输入数据类型的可选参数。与 `dtype` 类似，它支持其所有值。

## 返回值

返回高斯 Dropout 层。

## 示例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the tensor
const geek= tf.tensor1d([128561, 1536782, 221343, 781422]);

// Reshaping tensor
const geek1 = tf.reshape(geek,[2,2]);

// Creating gaussianDropout of poolSize 2*2
const gaussianDropout = 
      tf.layers.gaussianDropout({poolSize:[2,2]});

// Applying gaussianDropout on geek1 tensor
const result = gaussianDropout.apply(geek1);

// Printing the result tensor
result.print();
```

**输出:**

```
Tensor
    [[128561, 1536782],
     [221343, 781422 ]]
```

## 示例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Reshaping tensor
const geek1 = tf.reshape(
  tf.tensor1d([2125, 1637, 1272, 3268]),
  [2,2]);

// Applying gaussianDropout on geek1 tensor
tf.layers.gaussianDropout(
  {
    poolSize:[2,2]
  }
).apply(
  geek1).print();
```

**输出:**

```
Tensor
    [[2125, 1637],
     [1272, 3268]]
```

## 参考

[`https://js.tensorflow.org/api/3.6.0/#layers.gaussianDropout`](https://js.tensorflow.org/api/3.6.0/#layers.gaussianDropout)