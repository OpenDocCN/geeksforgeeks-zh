# TensorFlow.js tf.data.Dataset.filter() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-filter-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-filter-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

`tf.data.Dataset.filter()` 函数用于根据谓词过滤数据集。

## 语法

```
filter(predicate)
```

## 参数

*   `predicate`: 将数据集元素映射为布尔值或承诺值的函数。

## 返回值

返回 `tf.data.Dataset`。

## 例 1

### JavaScript

```
const gfg = tf.data.array([8, 12, 25, 6, 34, 2, 67, 43])
   .filter(x => x >= 10);
await gfg.forEachAsync(geeks => console.log(geeks));
```

## 输出

```

```

## 例 2

### JavaScript

```
const gfg = tf.data.array([10, 21, 36, 24, 54, 65, 72, 90, 95, 12])
   .filter(x => x%6 === 0);
await gfg.forEachAsync(geeks => console.log(geeks));
```

## 输出

```

```

## 参考

[https://js.tensorflow.org/api/latest/#tf.data.Dataset.filter](https://js.tensorflow.org/api/latest/#tf.data.Dataset.filter)