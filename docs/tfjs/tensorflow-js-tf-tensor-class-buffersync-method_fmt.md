# TensorFlow.js tf.Tensor 类的 bufferSync() 方法

> 原文：[`https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-buffersync-method/`](https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-buffersync-method/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node.js 环境中运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

`tf.Tensor` 类的 `bufferSync()` 方法用于返回一个保存底层数据的 `tf.TensorBuffer`。

## 语法

```
bufferSync()
```

## 参数

*   它不需要参数。

## 返回值

返回 `tf.TensorBuffer`。

## 示例 1

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

console.log(tf.tensor([1, 3, 5, 4, 2]).bufferSync())
```

**输出：**

```
{
  "dtype": "float32",
  "shape": [],
  "size": 5,
  "values": {
    "0": 1,
    "1": 3,
    "2": 5,
    "3": 4,
    "4": 2
  },
  "strides": []
}
```

## 示例 2

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

const a = tf.tensor2d([[0, 1], [2, 3]])
console.log(a.bufferSync())
```

**输出：**

```
{
  "dtype": "float32",
  "shape": [
    2,
    2
  ],
  "size": 4,
  "values": {
    "0": 0,
    "1": 1,
    "2": 2,
    "3": 3
  },
  "strides": [
    2
  ]
}
```

**参考：** [`https://js.tensorflow.org/api/latest/#tf.Tensor.bufferSync`](https://js.tensorflow.org/api/latest/#tf.Tensor.bufferSync)