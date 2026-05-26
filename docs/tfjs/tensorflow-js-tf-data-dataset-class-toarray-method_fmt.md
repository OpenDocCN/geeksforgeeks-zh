# TensorFlow.js TF.data.Dataset 类 toArray() 方法

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-class-toarray-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-class-toarray-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`toArray()` 方法用于在一个数组中累加所述数据集的每个元素。

## 语法

```
toArray()
```

## 参数

此方法不保存任何参数。

## 返回值

返回 `Promise(T[])`。

## 注

*   此方法仅适用于有限的数据集，即适合内存的数据集。
*   用于测试目的，如果可能应避免使用。

## 例 1

### Javascript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining dataset formed of an array
// of numbers
const res = tf.data.array([11, 12, 31, 43, 15, 64]);

// Calling toArray() method and
// Printing output
console.log(await res.toArray());
```

**输出:**

```
11, 12, 31, 43, 15, 64
```

## 例 2

### Javascript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling toArray() method and
// Printing output
console.log(await tf.data.array([5.7, -16, .31, 0, null, NaN]).toArray());
```

**输出:**

```
5.7, -16, 0.31, 0, , NaN
```

## 参考

[https://js.tensorflow.org/api/latest/#tf.data.Dataset.toArray](https://js.tensorflow.org/api/latest/#tf.data.Dataset.toArray)