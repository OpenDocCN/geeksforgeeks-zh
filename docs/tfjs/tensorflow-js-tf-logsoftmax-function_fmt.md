# TensorFlow.js tf.logSoftmax() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-logsoftmax-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-logsoftmax-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

`tf.logSoftmax()` 函数用于计算 logSoftmax。

**语法**:

```
tf.logSoftmax(logits, axis?)
```

**参数**:

*   `logits`: 逻辑数组
*   `axis`: 维度，Softmax 将在该维度上计算

**返回值**: 返回 `tf.Tensor`

### 示例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

const a = tf.tensor1d([3, 2, 6]);

a.logSoftmax().print();
```

**输出**:

```
Tensor
    [-3.0658839, -4.0658841, -0.0658839]
```

### 示例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

const a = tf.tensor2d([2, 4, 6, 1, 3, 7], [2, 3]);

a.logSoftmax().print();
```

**输出**:

```
Tensor
    [[-4.1429315, -2.1429317, -0.1429316],
     [-6.0205812, -4.0205812, -0.0205811]]
```

**参考**: [https://js.tensorflow.org/api/latest/#logSoftmax](https://js.tensorflow.org/api/latest/#logSoftmax)