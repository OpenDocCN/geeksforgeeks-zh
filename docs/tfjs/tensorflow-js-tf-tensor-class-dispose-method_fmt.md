# TensorFlow.js `tf.Tensor` 类 `dispose()` 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-dispose-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-dispose-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`dispose()` 方法用于释放所述 `tf.Tensor` 所占用的内存。

## 语法

```
dispose()
```

## 参数

此方法不接受任何参数。

## 返回值

返回 `void`。

## 示例 1

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating a tensor
const t = tf.tensor([6, 7]);

// Calling dispose() method
t.dispose();

// Printing output
console.log("Tensor Disposed.")
```

### 输出

```
Tensor Disposed.
```

## 示例 2

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating a 2d tensor
const tn = tf.tensor2d([6, 7], [1, 2]);

// Calling dispose() method
const y = tn.dispose();

// Printing output
console.log(tn)
```

### 输出

```
An error occured on line: 11
Tensor is disposed.
```

这里，打印张量输出时发生错误，因为张量已经被释放掉了。

## 参考

[https://js.tensorflow.org/api/latest/#tf.Tensor.dispose](https://js.tensorflow.org/api/latest/#tf.Tensor.dispose)