# Tensorflow.js tf.fetch()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-fetch-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-fetch-function/)

Tensorflow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.fetch()` 函数用于返回 `fetch` 的平台专用操作。此外，如果 `fetch` 被指定为与全局对象（即 `window`、`process` 等）相联系，那么 `tf.util.fetch` 返回该函数，否则返回平台专用的解释。

**语法:**

```
tf.fetch(path, requestInits?)
```

**参数:**

*   `path`: 是所述的字符串类型的路径。
*   `requestInits`: 所述的 `requestInits`。它是可选的，并且是 `RequestInit` 类型。

**返回值:** 返回 `Response` 的承诺。

## 例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling fetch() method with respect to global
const res = tf.env().global.fetch(
  'https://js.tensorflow.org/api/latest/#tf.Sequential.evaluateDataset');

// Printing output
console.log(res);
```

**输出:**

```
[object Response]
```

## 例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling fetch() method
const res = await tf.util.fetch(
  'https://js.tensorflow.org/api/latest/#fetch');

// Printing output
console.log(JSON.stringify(res));
```

**输出:**

```
{}
```

**参考:** [https://js.tensorflow.org/api/latest/#fetch](https://js.tensorflow.org/api/latest/#fetch)