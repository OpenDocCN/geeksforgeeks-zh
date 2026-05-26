# TensorFlow.js `tf.util.now()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-util-now-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-util-now-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.util.now()` 函数用于查找当前时间，以毫秒为单位，分辨率高，相对于过去不一致的时间。此外，它通过各种平台运行，即 node.js、浏览器。

## 语法

```
tf.util.now()
```

## 参数

它不接受任何参数。

## 返回值

返回数字。

## 示例 1

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling tf.util.now() method and
// printing output
console.log(tf.util.now());
```

**输出:**

```
1106999.345
```

## 示例 2

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling tf.sin() and tf.util.now()
// methods
var res = (tf.sin(tf.util.now()));

// printing output
console.log(res);
```

**输出:**

```
Tensor
    0.6055543422698975
```

**参考:** [https://js.tensorflow.org/api_node/2.0.1/#util.now](https://js.tensorflow.org/api_node/2.0.1/#util.now)