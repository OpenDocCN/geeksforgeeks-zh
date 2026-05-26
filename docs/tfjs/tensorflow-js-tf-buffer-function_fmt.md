# Tensorflow.js tf.buffer()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-buffer-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-buffer-function/)

**Tensorflow.js** 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。

`tf.buffer()` 函数用于为指定的数据类型和形状创建一个空的 Tensor Buffer。使用 `buffer.set()` 函数在创建的缓冲区中设置这些值。

## 语法

```
tf.buffer(shape, dtype, values)
```

## 参数

该函数接受三个参数，如下所示：

*   `shape`: 定义输出张量形状的整数数组。
*   `dtype`: 创建的缓冲区的数据类型。它的默认值是 `"float32"`。此参数是可选的。
*   `values`: 创建的缓冲区的值。它的默认值是零。此参数是可选的。

## 返回值

该函数不返回值，因为它只创建缓冲区。

## 例 1

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating a buffer of [2, 2] shape
const buffer = tf.buffer([2, 2]);

// Getting the created buffer in the
// form of Tensor of zeros values
// as no values are set in the buffer
buffer.toTensor().print();
```

**输出:**

```
Tensor
   [[0, 0],
    [0, 0]]
```

## 例 2

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating a buffer of [3, 3] shape
const buffer = tf.buffer([3, 3]);

// Setting values in the created buffer
// at particular indices
buffer.set(10, 2, 0);
buffer.set(15, 0, 1);
buffer.set(20, 1, 2);

// Getting the buffer in the form of Tensor
// along with the set values
buffer.toTensor().print();
```

**输出:**

```
Tensor
   [[0 , 15, 0 ],
    [0 , 0 , 20],
    [10, 0 , 0 ]]
```

**参考:** [https://js.tensorflow.org/api/latest/#buffer](https://js.tensorflow.org/api/latest/#buffer)