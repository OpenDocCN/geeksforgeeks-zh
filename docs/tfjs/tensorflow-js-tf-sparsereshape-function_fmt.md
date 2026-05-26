# TensorFlow.js TF.sparseReshape() 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-sparsereshape-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-sparsereshape-function/)

TensorFlow.js 是一个由谷歌开发的开源库，用于在浏览器或 Node.js 环境中运行机器学习模型以及深度学习神经网络。`sparseReshape()` 函数在稀疏张量上拥有与 `reshape()` 函数相同的语法。其中输入索引会根据所需的新形状重新计算。

**注意：**

*   在这种情况下，如果新形状的一个元素是不同的值，即 `-1`，则该维度的大小会被计算得出，以使稠密元素的总数保持不变。
*   新形状中最多只能有一个分量为 `-1`。
*   新形状所指示的稀疏分量数量应与输入形状最初指示的稀疏分量数量相同。
*   `sparseReshape` 不能影响稀疏张量中值的顺序。
*   如果输入张量的秩为 `r_in` 并且有 `n` 个非零值，而新形状的长度为 `r_out`，那么输入索引的形状为 `[n， r_in]`，输入形状的长度为 `r_in`。

**语法：**

```javascript
tf.sparseReshape(inputIndices, inputShape, newShape)
```

**参数：** 该方法接受以下参数：

*   `inputIndices`：一个二维的 `N x R_in` 矩阵，表示稀疏张量中非零值的索引。它可以是 `tf.Tensor2D`、`TypedArray` 或数组。
*   `inputShape`：一个一维的 `R_in` 张量，表示输入稀疏张量的稀疏形状。它可以是 `tf.Tensor1D`、`TypedArray` 或数组。
*   `newShape`：一个一维的 `R_out` 张量，表示所需的新稀疏形状。它可以是 `tf.Tensor1D`、`TypedArray` 或数组。

**返回值：** 返回一个 `tf.Tensor` 对象。

**示例 1：** 在下面的示例中，我们调用了 `sparseReshape()` 函数及其所有参数，并打印了不包含其索引和形状的输出响应。

```javascript
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs")

// Calling sparse.sparseReshape() function
// with all its parameter
const res = tf.sparse.sparseReshape(
    [[1, 0, 1], [2, 0, 1], [1, 1, 2], [0, -1, 0], [-3, 1, 2]],
    [1, 2, 9], [-1, 9]);

// Printing output
console.log(res);
```

**输出：**

```javascript
{
  "outputIndices": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [
      5,
      2
    ],
    "dtype": "float32",
    "size": 10,
    "strides": [
      2
    ],
    "dataId": {
      "id": 82
    },
    "id": 82,
    "rankType": "2",
    "scopeId": 36
  },
  "outputShape": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [
      2
    ],
    "dtype": "float32",
    "size": 2,
    "strides": [],
    "dataId": {
      "id": 83
    },
    "id": 83,
    "rankType": "1",
    "scopeId": 36
  }
}
```

**示例 2：** 在下面的示例中，我们调用了 `sparseReshape()` 函数及其所有参数，并打印了包含其索引和形状的输出响应。

```javascript
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs")

// Calling sparse.sparseReshape() function
// with all its parameter
const res = tf.sparse.sparseReshape(
    [[1.1, 0, 1.2], [2.1, 0.2, 1.3], [1.4, 2.3, 2.5], [null, -1, 0], [-3, 1, 2]],
    [1.0, 3, 3], [-1, 9]);

// Printing output indices
res['outputIndices'].print();

// Printing output shape
res['outputShape'].print();
```

**输出：**

```javascript
Tensor
    [[1 , 2 ],
     [2 , 2 ],
     [2 , 3 ],
     [0 , -3],
     [-2, -4]]
Tensor
    [1, 9]
```

**参考：** [https://js.tensorflow.org/api/latest/#sparseReshape](https://js.tensorflow.org/api/latest/#sparseReshape)