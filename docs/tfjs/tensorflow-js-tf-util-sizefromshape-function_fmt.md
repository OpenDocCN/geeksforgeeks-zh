# TensorFlow.js `tf.util.sizeFromShape()` 函数

> 原文链接：[https://www.geeksforgeeks.org/tensorflow-js-tf-util-sizefromshape-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-util-sizefromshape-function/)

TensorFlow.js 是谷歌正在开发的一个开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.util.sizeFromShape()` 函数用于从所述形状中找到元素的数量，即所述张量输入的大小。

## 语法

```
tf.util.sizeFromShape(shape)
```

## 参数

*   `shape`: 是要返回大小的指定形状。它是 `number[]` 类型。

## 返回值

返回一个数字。

## 示例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining shape
const sh = [5, 8, 1];

// Calling tf.util.sizeFromShape() method
const num = tf.util.sizeFromShape(sh);

// printing output
console.log(num);
```

**输出:**

```
40
```

## 示例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling tf.util.sizeFromShape() method and
// printing output
console.log(tf.util.sizeFromShape([1.4, 5.6, 9.0]));
```

**输出:**

```
70.55999999999999
```

## 参考资料

[https://js.tensorflow.org/api/1.0.0/#sizeFromShape](https://js.tensorflow.org/api/1.0.0/#sizeFromShape)