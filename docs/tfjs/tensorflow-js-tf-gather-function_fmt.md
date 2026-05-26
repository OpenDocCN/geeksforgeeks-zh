# TensorFlow.js tf.gather() 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-gather-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-gather-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`tf.gather()` 函数用于根据指定的索引从输入张量的指定轴上收集切片。

**语法：**

```
tf.gather(x, indices, axis?, batchDims?)
```

**参数：**

*   `x`：是输入张量，要从中收集切片，可以是 `tf.Tensor`、类型化数组或普通数组。
*   `indices`：是要拉取的数值的索引，可以是 `tf.Tensor`、类型化数组或普通数组。
*   `axis`：是进行收集操作的轴。默认值为 `0`，是数字类型。此参数是可选的。
*   `batchDims`：是批次维度的数量，应小于或等于 `indices` 的秩。默认值为 `0`。此外，返回的输出张量的形状必须是 `x.shape[:axis] + indices.shape[batchDims:] + x.shape[axis+1:]`。它是数字类型，是可选的。

**返回值：** 返回一个 `tf.Tensor` 对象。

**例 1：**

## JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining tensor input and indices
const y = tf.tensor1d([1, 6, 7, 8]);
const ind = tf.tensor1d([1, 6, 2], 'int32');

// Calling tf.gather() method and
// Printing output
y.gather(ind).print();
```

**输出：**

```
Tensor
    [6, NaN, 7]
```

**例 2：**

## JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining tensor input, indices, axis,
// and batchdims
const y = tf.tensor2d([7, 8, 12, 13], [4, 1]);
const ind = tf.tensor1d([2, 3, 0], 'int32');
const axis = 1;
const batchdims = -1;

// Calling tf.gather() method
var res = tf.gather(y, ind, axis, batchdims);

// Printing output
res.print();
```

**输出：**

```
Tensor
    [[12 , 13 , 7 ],
     [13 , NaN, 8 ],
     [NaN, NaN, 12],
     [NaN, NaN, 13]]
```

**参考：** [https://js.tensorflow.org/api/latest/#gather](https://js.tensorflow.org/api/latest/#gather)