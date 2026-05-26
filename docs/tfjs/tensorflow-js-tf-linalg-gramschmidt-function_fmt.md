# TensorFlow.js tf.linalg.gramSchmidt()函数

> 来源：https://www.geeksforgeeks.org/tensorflow-js-tf-linalg-gramschmidt-function/

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。

`tf.linalg.gramSchmidt()` 函数用于使用 Gram-Schmidt 过程正交化向量。

**语法:**

```
tf.linalg.gramSchmidt(xs)
```

**参数:**

*   `xs` (一个 `tf.Tensor1D` 数组或 `tf.Tensor2D`): 这些是要正交化的向量。

**返回值:** 返回一个 `tf.Tensor1D` 数组或 `tf.Tensor2D`。

**例 1:**

### JavaScript

```
const tf = require("@tensorflow/tfjs")

// Creating a 2-D tensor
const input = tf.tensor2d([
    [3, 7], 
    [4, 6]
]);

// Getting the orthogonalized vector
let result = tf.linalg.gramSchmidt(input);

result.print();
```

**输出:**

```
Tensor
    [[0.3939193, 0.919145  ],
     [0.919145 , -0.3939194]]
```

**例二:**

### JavaScript

```
const tf = require("@tensorflow/tfjs")

// Creating a 2-D tensor
const input = tf.tensor2d([
    [5, 7, 2], 
    [7, 6, 9],
    [1, 2, 3]
]);

// Getting the orthogonalized vector
let result = tf.linalg.gramSchmidt(input);

result.print();
```

**输出:**

```
Tensor
    [[0.5661386, 0.792594  , 0.2264554],
     [0.1283516, -0.3561312, 0.925579 ],
     [-0.814256, 0.4949402 , 0.3033505]]
```

**参考:** https://js.tensorflow.org/api/latest/#linalg.gramSchmidt