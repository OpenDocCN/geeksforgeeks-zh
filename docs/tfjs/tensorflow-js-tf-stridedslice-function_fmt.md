# TensorFlow.js TF.stridedSlice()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-stridedslice-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-stridedslice-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`stridedSlice()`函数用于拉出所述输入张量的条纹部分。

**注意:** 该功能用于从所述输入张量中拉出所述长度*步幅*的一部分。从*给定的位置开始*，在所有测量值大于*结束*之前，切片通过将步幅附加到所述索引来进行。此外，步幅也可以是负的，这导致反向切片。

## 语法

```
tf.stridedSlice(x, begin, end, strides?, beginMask?, endMask?, 
ellipsisMask?, newAxisMask?, shrinkAxisMask?)
```

## 参数

*   `x`: 要进行切片的张量。可以是 `tf.Tensor` 类型或数组。
*   `begin`: 切片的起始坐标。是 `number[]` 类型。
*   `end`: 切片的结束坐标。是 `number[]` 类型。
*   `stride`: 切片的步长。可选，类型为 `number[]`。
*   `beginMask`: 可选参数，类型为 `number`。在这种情况下，`beginMask` 的第 i 位被固定，则 `begin[i]` 被忽略，相反，会利用该维度可达到的最大范围。
*   `endMask`: 可选参数，类型为 `number`。在这种情况下，`endMask` 的第 i 位被固定，则 `end[i]` 被忽略，相反，会利用该维度可达到的最大范围。
*   `ellipsisMask`: 可选参数，类型为 `number`。
*   `newAxisMask`: 可选参数，类型为 `number`。
*   `shrinkAxisMask`: 描述的位掩码，其中位 *i* 表示第 i 个维度必须被收缩。*begin* 和 *end* 应指示长度为 1 的片段的大小。可选，类型为 `number`。

## 返回值

返回 `tf.Tensor`。

## 示例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining tensor input
const tn = tf.tensor3d([5, 5, 5 ,7, 7, 7, 13, 
    13, 13, 14, 14, 14, 1, 1, 1, 2, 2, 2],
    [3, 3, 2]);

// Calling stridedSlice() method and 
// Printing output
tn.stridedSlice([5, 0, 5], [7, 5, 7], [2, 2, 2]).print();
```

**输出:**

```
Tensor
    [[[1],
      [2]]]
```

## 示例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining tensor input
const tn = tf.tensor3d([5, 5, 5 ,7, 7, 7, 13, 
    13, 13, 14, 14, 14, 1, 1, 1, 2, 2, 2],
    [3, 3, 2]);

// Defining all the parameters
const x = [-5, 5, 7];
const begin = [-7, 13, 14];
const end = [-7, 13, 13];
const strides = [1];
const beginMask = 2;
const endMask = 0;
const ellipsisMask = 2;
const shrinkAxisMask = 15;

// Calling stridedSlice() method and 
// Printing output
tn.stridedSlice(x, begin, end, strides, beginMask,
     endMask, ellipsisMask, shrinkAxisMask).print();
```

**输出:**

```
Tensor

```

**参考:** [https://js.tensorflow.org/api/latest/#stridedSlice](https://js.tensorflow.org/api/latest/#stridedSlice)