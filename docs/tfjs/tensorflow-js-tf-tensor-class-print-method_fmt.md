# TensorFlow.js `tf.Tensor` 类 `print()` 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-print-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-print-method/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node 环境中运行机器学习模型和深度学习神经网络。

`tf.print()` 函数用于打印关于 `tf.Tensor` 的信息，包括它的数据。

## 语法

```
tf.print(value, verbose)
```

## 参数

*   `value`：张量的值，可以是简单的或嵌套的数组或数字类型。如果数组元素是字符串，那么它们将编码为 UTF-8，并保持为 `Uint8Array[]`。
*   `verbose`：是一个布尔值，用来告诉是否打印 Tensor 的详细信息，包括数据类型和大小，`verbose` 的默认值为 `false`。

以下示例演示了 `tf.print()` 函数：

### 示例 1

在本例中，我们使用 `tf.tensor2d` 创建张量，并使用 `tf.print` 函数打印，使用 `verbose` 值作为 `true`。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating the tensor
const verbose = true;
var val = tf.tensor2d(["geeks","for","geeks","website"], [2, 2]);

// Printing the tensor
val.print(verbose);
```

**输出：**

```
Tensor
  dtype: string
  rank: 2
  shape: [2,2]
  values:
    [['geeks', 'for'    ],
     ['geeks', 'website']]
```

### 示例 2

在本例中，我们使用 `tf.tensor` 创建一个张量，并使用 `tf.print` 函数打印，使用 `verbose` 值作为 `false`。

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating the tensor
const verbose = false;
var val = tf.tensor(["geeks","for","geeks"]);

// Printing the tensor
val.print(verbose);
```

**输出：**

```
Tensor
    ['geeks', 'for', 'geeks']
```

**参考：** [`tf.Tensor.print`](https://js.tensorflow.org/api/latest/#tf.Tensor.print)