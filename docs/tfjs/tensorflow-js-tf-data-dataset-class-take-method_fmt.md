# TensorFlow.js tf.data.Dataset 类的 take() 方法

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-class-take-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-class-take-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`take()` 方法用于形成一个数据集，其中包含所述数据集中最前面的 `count` 项。

## 语法

```
take(count)
```

## 参数

*   `count`: 是所述数据集中存在的元素数量，用于创建不同的数据集。此外，如果未定义 `count`，或者 `count` 为负，或者 `count` 高于所述数据集的维度，则新创建的数据集将保存给定数据集的每个项目。

## 返回值

返回 `tf.data.Dataset`。

## 例 1

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining dataset formed of an array of
// numbers and calling take() method
const res = tf.data.array([11, 12, 31, 43, 15, 64]).take(4);

// Calling forEachAsync() method and
// Printing output
await res.forEachAsync(op => console.log(op));
```

**输出:**

```
11
12
31
43
```

## 例 2

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling forEachAsync(), take() method
// and printing output
await tf.data.array([31.1, 81.2, 5.1, 0, NaN, 'a']).
take(10.7).forEachAsync(op => console.log(op));
```

**输出:**

```
31.1
81.2
5.1
0
NaN
a
```

**参考:** `https://js.tensorflow.org/api/latest/#tf.data.Dataset.take`