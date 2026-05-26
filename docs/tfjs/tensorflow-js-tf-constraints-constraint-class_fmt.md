## tf.constraints.Constraint 类

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-constraints-constraint-class/](https://www.geeksforgeeks.org/tensorflow-js-tf-constraints-constraint-class/)

Tensorflow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。`tf.constraints.Constraint` 类用于扩展 `Serializabe` 类。此外，它是支持对权重值实施约束的函数的基类。

这个 `tf.constraints.Constraint` 类包含四个内置函数，如下所示:

*   `tf.constraints.maxNorm()` 函数
*   `tf.constraints.minMaxNorm()` 函数
*   `tf.constraints.nonNeg()` 函数
*   `tf.constraints.unitNorm()` 函数

**示例 1:** 在本例中，`tf.constraints.Constraint` 类的 `minMaxNorm()` 函数用于基于给定的配置对象创建 `minMaxNorm` 约束。它继承自约束类。约束是层的属性，如权重、核、偏差。`minMaxNorm` 是一个重量约束。

### JavaScript

```javascript
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Calling maxNorm() function
var a = tf.constraints.maxNorm(2, 0)

// Printing output
console.log(a)
```