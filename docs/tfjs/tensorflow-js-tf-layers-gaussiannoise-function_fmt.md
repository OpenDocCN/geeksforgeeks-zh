# TensorFlow.js TF.layers.gaussianNoise() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layers-gaussiannoise-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-gaussiannoise-function/)

**TensorFlow.js** 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

`tf.layers.gaussianNoise()` 函数用于应用加性零中心高斯噪声。因为它是正则化层，所以只在训练时有效。

```
tf.layers.gaussianNoise(arguments)
```

## 参数

*   `inputShape`: 是一个可选参数，用于创建输入层，接受数字和 `null` 等值。
*   `batchInputShape`: 是一个可选参数，用于在主层之前创建输入层，其值等于数字和 `null`。
*   `batchSize`: 是用于构造 `batchInputShape` 的可选参数，只接受数字。
*   `dtype`: 是一个可选参数，表示数据类型。默认为 `"float32"`，也支持 `"int32"` 和 `"bool"` 等其他值。
*   `name`: 是一个可选参数，用于定义层名称，接受字符串。
*   `trainable`: 是一个可选参数，决定是否更新提供的输入层。它接受布尔值。
*   `weights`: 它具有层的初始权重。这也是一个可选参数。
*   `inputType`: 是用于输入数据类型的可选参数。与 `dtype` 类似，它支持其所有值。

## 返回值

返回高斯型。

## 例 1

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the tensor
const geek= tf.tensor1d([28561, 53678, 21343, 81422]);

// Reshaping tensor
const geek1 = tf.reshape(geek,[2,2]);

// Creating gaussianNoise of poolSize 2*2
const gaussianNoise = 
      tf.layers.gaussianNoise({poolSize:[2,2]});

// Applying gaussianNoise on geek1 tensor
const result = gaussianNoise.apply(geek1);

// Printing the result tensor
result.print();
```

**输出:**

```
Tensor
    [[28561, 53678],
     [21343, 81422]]
```

## 例 2

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Reshaping tensor
const geek1 = tf.reshape(
  tf.tensor1d([215, 637, 172, 368]),
  [2,2]);

// Applying gaussianNoise on geek1 tensor
tf.layers.gaussianNoise(
  {
    poolSize:[2,2]
  }
).apply(
  geek1).print();
```

**输出:**

```
Tensor
    [[215, 637],
     [172, 368]]
```

**参考资料:** [https://js.tensorflow.org/api/3.6.0/#layers.gaussianNoise](https://js.tensorflow.org/api/3.6.0/#layers.gaussianNoise)