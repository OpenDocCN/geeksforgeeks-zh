# TensorFlow.js tf.train.sgd() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-train-sgd-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-train-sgd-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`.train.sgd()` 函数用于构建一个利用随机梯度下降的 `tf.SGDOptimizer`。

## 语法

```
tf.train.sgd(learningRate)
```

## 参数

*   `learningRate`：用于支持 SGD 算法的规定学习速率。它是数字类型的。

## 返回值

返回 `tf.SGDOptimizer`。

## 例 1

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Declaring learningRate
const learning_rate = 0.02;

// Calling train.sgd() method
const res = tf.train.sgd(learning_rate);

// Printing output
console.log(res);
```

**输出：**

```
{
  "learningRate": 0.02,
  "c": {
    "kept": true,
    "isDisposedInternal": false,
    "shape": [],
    "dtype": "float32",
    "size": 1,
    "strides": [],
    "dataId": {
      "id": 1298
    },
    "id": 1192,
    "rankType": "0",
    "scopeId": 1251
  }
}
```

## 例 2

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling train.sgd() and sin() method
console.log(JSON.stringify(tf.train.sgd(tf.sin(45))));
```

**输出：**

```
{"learningRate":{"kept":false,"isDisposedInternal":false,"shape":[],
"dtype":"float32","size":1,"strides":[],"dataId":{"id":1316},"id":1207,
"rankType":"0","scopeId":1269},"c":{"kept":true,"isDisposedInternal":false,
"shape":[],"dtype":"float32","size":1,"strides":[],"dataId":{"id":1318},
"id":1208,"rankType":"0","scopeId":1269}}
```

**参考：** [https://js.tensorflow.org/api/latest/#train.sgd](https://js.tensorflow.org/api/latest/#train.sgd)