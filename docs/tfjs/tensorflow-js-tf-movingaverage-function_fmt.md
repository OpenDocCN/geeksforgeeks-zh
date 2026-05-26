# TensorFlow.js TF.movingAverage() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-movingaverage-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-movingaverage-function/)

**简介:** TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型以及深度学习神经网络。

`tf.movingAverage()` 函数用于确定一个变量的移动平均值。

**注:**

*   不使用 `zeroDebias` 时，移动平均操作定义为：`v += delta`。其中 `delta = (1–attenuation) * (x–v)`。
*   存在 `zeroDebias` 时（默认值），测量 `delta` 项以消除（假定的）`v` 零初始化的影响，其中 `delta/=(1- attenuation step size)`。
*   此函数是完全无状态的，不保存步数路径。此外，步数需要由调用者保存并作为 `step` 传入。

**语法:**

```
tf.movingAverage(v, x, decay, step?, zeroDebias?)
```

**参数:**

*   `v`: 当前的移动平均值。可以是 `tf.Tensor` 类型或数组。
*   `x`: 描述的新输入值，应具有与 `v` 相同的形状和数据类型。
*   `decay`: 指定的衰减因子。值通常为 0.95 和 0.99。可以是 `number` 类型或 `tf.Scalar`。
*   `step`: 描述的步数。可选，类型为 `number` 或 `tf.scalar`。
*   `zeroDebias`: 检查是否执行 `zeroDebias`。默认值为 `true`。可选，类型为 `Boolean`。

**返回值:** 返回 `tf.Tensor`

**例 1:**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining current moving average value
const v = tf.tensor1d([1, 3, 5, 1]);

// Defining new input value
const x = tf.tensor1d([1, 7, 2, 1]);

// Defining decay factor
const decay_factor = 0.75;

// Calling movingAverage() method
const res = tf.movingAverage(v, x, decay_factor, 2, true);

// Printing output
res.print();
```

**输出:**

```
Tensor
    [1, 5.2857141, 3.2857144, 1]
```

**例二:**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling movingAverage() method
tf.movingAverage(tf.tensor1d([1.1, 3.1, 5.5, 1.3]),
               tf.tensor1d([1.2, 7.4, 2.6, 1.1]), 0.99, 5, false).print();
```

**输出:**

```
Tensor
    [1.1010001, 3.1429999, 5.4710002, 1.298]
```

**参考:** [https://js.tensorflow.org/api/latest/#movingAverage](https://js.tensorflow.org/api/latest/#movingAverage)