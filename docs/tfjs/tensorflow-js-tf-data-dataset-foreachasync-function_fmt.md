# TensorFlow.js `tf.data.Dataset.forEachAsync()`函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-foreachasync-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-foreachasync-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

将函数应用于数据集的每个元素后，将使用`forEachAsync`函数。

## 语法

```
forEachAsync(f)
```

## 参数

*   `f`：应用于每个数据集元素的函数。

## 返回值

返回`Promise<void>`。

## 示例 1

```
const a = tf.data.array([1, 2, 3]);
await a.forEachAsync(e => console.log(e));
```

**输出：**

```

```

## 示例 2

```
const a = tf.data.array([1, 2, 3]);
await a.forEachAsync(e => console.log(e*2));
```

**输出：**

```

```

**参考：**[https://js.tensorflow.org/api/latest/#tf.data.Dataset.forEachAsync](https://js.tensorflow.org/api/latest/#tf.data.Dataset.forEachAsync)