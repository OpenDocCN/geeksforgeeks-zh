# TensorFlow.js `tf.layers.elu()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layers-elu-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-elu-function/)

**TensorFlow.js** 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

`tf.layers.elu()` 函数缩写为指数线性单位。其定义为:
`f(a) = α * (exp(a) - 1)` for `a < 0`, `f(a) = a` for `a >= 0`。

## 语法

```
tf.layers.elu(arguments)
```

## 参数

*   **inputShape**: 是一个可选参数，用于创建输入层，其值可以是数字或 `null`。
*   **batchInputShape**: 是一个可选参数，用于在主层之前创建输入层，其值可以是数字或 `null`。
*   **batchSize**: 是一个可选参数，用于构建 `batchInputShape`，它只接受数字。
*   **dtype**: 是一个可选参数，表示数据类型。默认为 `"float32"`，也支持 `"int32"` 和 `"bool"` 等值。
*   **name**: 是一个可选参数，用于定义层的名称，接受字符串。
*   **trainable**: 是一个可选参数，决定提供的输入层是否更新。它接受布尔值。
*   **weights**: 它具有层的初始权重。也是一个可选参数。
*   **inputType**: 是一个可选参数，用于输入数据类型。与 `dtype` 类似，它支持所有相同的值。

## 返回值

返回 ELU 层。

## 例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the tensor
const geek = tf.tensor1d([11, 12, 23, 74]);

// Reshaping tensor
const geek1 = tf.reshape(geek, [2, 2]);

// Creating ELU of poolSize 2*2
const elu = tf.layers.elu({poolSize: [2, 2]});

//Applying ELU on geek1 tensor
const result = elu.apply(geek1);

//Printing the result tensor
result.print();
```

**输出:**

```
Tensor
    [[11, 12],
     [23, 74]]
```

## 例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Reshaping tensor
const geek1 = tf.reshape(tf.tensor1d([55, 63, 17, 28]), [2, 2]);

// Applying elu on geek1 tensor
tf.layers.elu(
  {
    poolSize: [2, 2]
  }
).apply(
  geek1).print();
```

**输出:**

```
Tensor
    [[55, 63],
     [17, 28]]
```

## 参考资料

[https://js.tensorflow.org/api/3.6.0/#layers.elu](https://js.tensorflow.org/api/3.6.0/#layers.elu)