# TensorFlow.js `tf.batchNorm()` 函数

> 原文链接：[https://www.geeksforgeeks.org/tensorflow-js-tf-batchnorm-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-batchnorm-function/)

TensorFlow.js 是一个由谷歌开发的开源库，用于在浏览器或 Node.js 环境中运行机器学习模型以及深度学习神经网络。

`batchNorm()` 函数在批处理规范化中很有用。

此外，`mean`、`variance`、`scale` 以及 `offset` 可以是以下两种形状之一：

*   与输入张量形状相同。
*   通常，深度是输入张量的最后一个维度大小，因此该值可以是形状为 `[depth]` 的 1D `tf.Tensor`。

**语法：**

```
tf.batchNorm(x, mean, variance, offset?, scale?, varianceEpsilon?)
```

**参数：**

*   `x`: 输入张量。可以是 `tf.Tensor`、类型或数组。
*   `mean`: 描述的平均值张量。可以是 `tf.Tensor`、1D 张量或数组。
*   `variance`: 描述的方差张量。可以是 `tf.Tensor`、1D 张量或数组。
*   `offset`: 描述的偏移张量。可选，可以是 `tf.Tensor`、1D 张量或数组。
*   `scale`: 描述的缩放张量。可选，可以是 `tf.Tensor`、1D 张量或数组。
*   `varianceEpsilon`: 描述的小浮点数，用于避免除以零。可选，为数值类型。

**返回值：** 返回一个 `tf.Tensor`。

**例 1：**

```javascript
// 导入 tensorflow.js 库
import * as tf from "@tensorflow/tfjs"

// 定义输入张量
const a = tf.tensor1d([1, 5, 3]);

// 定义均值
const b = tf.tensor1d([1, 1, 2]);

// 定义方差
const c = tf.tensor1d([1, 0, 1]);

// 调用 batchNorm() 函数
tf.batchNorm(a, b, c).print();
```

**输出：**

```
Tensor
    [0, 126.4911041, 0.9995003]
```

**例 2：**

```javascript
// 导入 tensorflow.js 库
import * as tf from "@tensorflow/tfjs"

// 定义输入张量
const a = tf.tensor1d([1, 5, 3]);

// 定义均值
const b = tf.tensor1d([1, 1, 2]);

// 定义方差
const c = tf.tensor1d([1, 0, 1]);

// 定义偏移
const d = tf.tensor1d([1, 6, 2]);

// 定义缩放
const e = tf.tensor1d([1, 0, 1]);

// 调用 batchNorm() 函数
a.batchNorm(b, c, d, e, 9).print();
```

**输出：**

```
Tensor
    [1, 6, 2.3162277]
```

**参考：** [https://js.tensorflow.org/api/latest/#batchNorm](https://js.tensorflow.org/api/latest/#batchNorm)