# TensorFlow.js TF.atan2()函数

> 哎哎哎: # t0] https://www.geeksforgeeks.org/tensorflow-js-tf-atan2-function/

Tensorflow.js 是谷歌正在开发的一个开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`atan2()`函数用于找到所述张量输入的反正切，并按元素方式进行。此外，它还有助于广播。

**语法:**

```javascript
tf.atan2(a, b)
```

**参数:**

*   `a`: 是第一个可以是 `tf.Tensor` 类型，或 `TypedArray`，或数组的张量输入。
*   `b`: 是第二张量输入，可以是 `tf.Tensor` 类型，或 `TypedArray`，或数组，并且它必须具有与 `a` 相同的数据类型。

**返回值:** 返回 `tf.Tensor` 对象。

### 示例 1

在本例中，我们定义了一个整数类型的输入张量，然后打印它的 `atan2` 值。为了创建输入张量，我们使用 `tensor1d()` 方法，为了打印输出，我们使用 `print()` 方法。

#### Javascript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining first tensor input elements
const y = tf.tensor1d([9, 10, 11, 12]);

// Defining second tensor input elements
const z = tf.tensor1d([13, 14, 15, 17]);

// Calling atan2() method and
// Printing output
(y).atan2(z).print();
```

#### 输出

```
Tensor
    [0.6055371, 0.6202452, 0.6327478, 0.6146573]
```

### 示例 2

在本例中，浮点类型值被视为张量输入，两个参数都直接传递给 `atan2` 函数。

#### Javascript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining float values for first tensor
var val1 = [.5, 4.9, .275];

// Defining float values for second tensor
var val2 = [1.5, 5.9, .775];

// Calling tensor1d method
const y = tf.tensor1d(val1);
const z = tf.tensor1d(val2);

// Calling atan2() method
var res = tf.atan2(y,z);

// Printing output
res.print();
```

#### 输出

```
Tensor
    [0.3217588, 0.6930802, 0.340989]
```

**参考:** [https://js.tensorflow.org/api/latest/#atan2](https://js.tensorflow.org/api/latest/#atan2)