# TensorFlow.js tf.oneHot() 函数

> 参考：[TensorFlow.js TF.oneHot() 函数](https://www.geeksforgeeks.org/tensorflow-js-tf-onehot-function/)

**TensorFlow.js** 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。

`tf.oneHot()` 函数用于创建一个 one-hot `tf.Tensor`。由索引表示的位置取值为 1（默认值），也称为 `onValue`，而所有其他位置取值为 0（默认值），也称为 `offValue`。

**语法：**

```
tf.oneHot(indices, depth, onValue, offValue)
```

**参数：** 该函数接受四个参数，如下所示：

*   `indices`：可以是 `tf.Tensor`（数据类型为 `int32`）或数组。
*   `depth`：数据类型是数字。它用于表示 one-hot 维度的深度。
*   `onValue`：数据类型是数字。它用于在索引与位置匹配时填充输出。这是一个可选的参数。
*   `offValue`：数据类型是数字。当索引与位置不匹配时，它用于填充输出。这也是一个可选的参数。

**返回：** 它返回一个 `tf.Tensor`。

**例 1：**

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Use of oneHot function.
var val = tf.oneHot(tf.tensor1d([0,1,2], 'int32'), 3);

// Printing the tensor
val.print()
```

**输出：**

```
Tensor
    [[1, 0, 0],
    [0, 1, 0],
    [0, 0, 1]]
```

**例 2：**

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating and initializing a new variable
var val = tf.oneHot(tf.tensor1d([0,1,2], 'int32'), 3, 9, -1);

// Printing the tensor
val.print()
```

**输出：**

```
Tensor
    [[9 , -1, -1],
    [-1, 9 , -1],
    [-1, -1, 9 ]]
```

**参考：** [TensorFlow.js API - oneHot](https://js.tensorflow.org/api/latest/#oneHot)