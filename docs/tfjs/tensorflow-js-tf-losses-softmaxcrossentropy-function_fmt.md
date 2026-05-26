# tf.losses.softmaxCrossEntropy() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-losses-softmaxcrossentropy-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-losses-softmaxcrossentropy-function/)

`TensorFlow.js` 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。

该函数计算两个张量之间的软最大交叉熵损失，并返回一个新的张量。

**语法:**

```javascript
tf.losses.softmaxCrossEntropy(onehotLabels, 
    logits, weights, labelSmoothing, reduction)
```

**参数:** 该函数接受五个参数（其中最后三个是可选的），如下所示：

*   `onehotLabels`: 它是一个热编码标签，其维度与预测相同。
*   `logits`: 是预测输出。
*   `weights`: 这些是等级为 0 或 1 的张量，必须是宽可铸才能变形。
*   `labelSmoothing`: 如果该参数的值大于 0，则平滑标签。
*   `reduction`: 适用于损失的还原类型。它必须是缩减类型。

**注意:** 参数如 `weights`、`labelSmoothing` 和 `reduction` 可选。

**返回值:** 它返回两个张量之间具有软最大交叉熵损失的张量。

## JavaScript 示例

```javascript
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Creating onehotLabels tensor
const a = tf.tensor2d([[1, 4, 5], [5, 5, 7]]);

// Creating logits tensor
const b = tf.tensor2d([[3, 2, 5], [3, 2, 7]])

// Computing soft max cross entropy distance
softmax_cross_entropy = tf.losses.softmaxCrossEntropy(a, b)
softmax_cross_entropy.print();
```

**输出:**

```
Tensor
   30.55956268310547
```

**示例 2:** 在本例中，我们传递了一个可选参数，即标签平滑。如果大于 0，则平滑标签。

## JavaScript 示例

```javascript
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// const tf = require("@tensorflow/tfjs")

// Creating labels tensor
const a = tf.tensor2d([[1,2,3,4,5], [7,8,9,10,11]])

// Creating predictions tensor
const b = tf.tensor2d([[6,735,8,59,10], [45,34,322,2,3]])

const c = tf.tensor2d([[4,34,34,2,4],[65,34,3,2,3]])

// Computing cross entropy with an option parameter number
softmax_cross_entropy = tf.losses.softmaxCrossEntropy(a, b, 5)
softmax_cross_entropy.print();
```

**输出:**

```
Tensor
    50477.5
```

**参考:** T2