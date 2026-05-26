# TensorFlow.js `tf.cast()` 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-cast-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-cast-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。

`tf.cast()` 函数用于将指定的张量转换为新的数据类型。

## 语法

```
tf.cast(x, dtype)
```

## 参数

该函数接受两个参数，如下所示：

*   `x`: 正在转换的输入张量。
*   `dtype`: 输入张量将被转换的数据类型。

## 返回值

返回新数据类型的转换张量。

## 例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing a tensor of some values
const x = tf.tensor1d([2.3, 1.7, 5, 0, 1, 0.5]);

// Calling the .cast() function over the
// above tensor to cast in "int32" data type
tf.cast(x, 'int32').print();
```

**输出：**

```
 Tensor
   [2, 1, 5, 0, 1, 0]
```

## 例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Using a tensor of some values
// as the parameter for .cast() function to
// cast into bool data type
tf.cast(tf.tensor1d([0, 1, -3]), 'bool').print();
```

**输出：**

```
Tensor
   [false, true, true]
```

**参考：** [https://js.tensorflow.org/api/latest/#cast](https://js.tensorflow.org/api/latest/#cast)