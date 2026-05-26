# TensorFlow.js TF.data.Dataset.skip() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-skip-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-skip-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

## 描述

函数用于创建一个数据集，该数据集跳过该数据集中的初始元素。

## 语法

```
skip(count)
```

## 参数

*   `count`: 为形成新数据集而应跳过的该数据集的元素数。

## 返回值

返回 `tf.data.Dataset`。

## 示例

### 示例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

const a = tf.data.array(
    [5, 10, 15, 20, 25, 30]).skip(2);

await a.forEachAsync(e => console.log(e));
```

**输出:**

```
15
20
25
30
```

### 示例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

const gfg = tf.data.array(
    ['geeksforgeeks', 'gfg', 'geeks', 
    'for', 'geeks']).skip(2);

await gfg.forEachAsync(
    geeks => console.log(geeks));
```

**输出:**

```
geeks
for
geeks
```

## 参考

[https://js.tensorflow.org/api/latest/#tf.data.Dataset.skip](https://js.tensorflow.org/api/latest/#tf.data.Dataset.skip)